---
name: telia-lso-site-lookup
description: Look up service sites in Telia's LSO Sonata wholesale programme — list the geographic sites in a Telia country, then retrieve full detail (structured address, coordinates, sub-address tree) for one site by identifier.
api: openapi/telia-lso-sonata-site-management.yml
operations:
  - listGeographicSite
  - retrieveGeographicSite
generated: '2026-07-25'
method: generated
source: openapi/telia-lso-sonata-site-management.yml
---

# Look up a Telia LSO Sonata geographic site

Telia's LSO Sonata programme is buyer-to-seller wholesale ordering built on MEF 122 /
MEF 79 and TM Forum TMF674. Site lookup is the first step of every Sonata flow — you
resolve the site before you qualify a product, quote it, or order it.

## Before you start

This API is not self-serve. You need an existing Telia commercial agreement, an
approved developer account on `https://lso.teliacompany.com/`, and an approved
registered application. Without those, every call returns `401` or `403`.

## 1. Get a token

The API declares two `oauth2` `clientCredentials` schemes and **no scopes** — what you
are allowed to see is set by the commercial entitlement on your client id, not by
anything you request.

| Environment | Token endpoint |
|---|---|
| Production | `https://api-garden.teliacompany.com/v4/oauth/client_credential/accesstoken` |
| Test / sandbox | `https://api-garden-test.teliacompany.com/v4/oauth/client_credential/accesstoken` |

Send the token as `Authorization: Bearer <token>`.

Start against the test host
(`https://api-garden-test.teliacompany.com/v1/api/mef/geographicSiteManagement`).
Note the trap in `sandbox/telia-sandbox.yml`: the *sandbox* server lives on the
**production** host under a `/sandbox` path, so it uses the **production** token
endpoint, not the test one.

## 2. List the sites — `listGeographicSite`

`GET /{country}/geographicSite`

`country` is a required path parameter constrained to an enum of Telia LSO country
codes (`se`, …). Every lookup is scoped to one country; identifiers are not shared
across countries, so never carry an id from one country segment to another.

Filter with the query parameters the spec declares. The contract declares **no
pagination parameters** — you cannot bound or page a country-wide list from the
contract alone, so always filter rather than requesting everything.

Each item is a `GeographicSiteSummary`: `id`, `siteCompanyName`, `status`, and a flat
`geographicAddress`.

## 3. Retrieve one site — `retrieveGeographicSite`

`GET /{country}/geographicSite/{id}`

Returns a `GeographicSite`: `fieldedAddress` (structured, adds `stateOrProvince`),
`geographicLocation` (a `spatialRef` plus one or more `geographicPoint` lat/long
pairs), and `geographicSubAdress[]` (buildings, each with `subUnit[]`).

Two things will bite you, both real properties of Telia's published spec — see
`data-model/telia-data-model.yml`:

- The list projection returns `id` as a **string**; the detail projection returns `id`
  as an **integer**. Do not assume one type.
- Two field names carry spelling errors inherited from the MEF source document:
  `additionnalSiteInformation` and `geographicSubAdress`. They are the real wire
  names — send and read them exactly as written.

## Errors

Not RFC 9457. The envelope is the TM Forum object — `code` and `reason` required,
`message` optional — served as `application/json`. Full catalog in
`errors/telia-problem-types.yml`.

| Status | What it actually means here |
|---|---|
| 400 | A mandatory parameter is missing, or `country` is outside the enum |
| 401 | Token expired or missing — mint a new one from the right environment's endpoint |
| 403 | Token is valid but your agreement does not entitle you to that country or product |
| 404 | Unknown site id, or the id belongs to a different country segment |
| 500 / 503 | Retry with backoff; escalate to `mef-lso.team@teliacompanyspace.onmicrosoft.com` |

## Retry safety

Both operations are `GET` and therefore safe to retry. There is **no idempotency key
anywhere on Telia's estate** (`conventions/telia-conventions.yml`) — when you move on
to the write-bearing Sonata APIs (Quote, Order), you have no replay protection from
the contract and must build your own de-duplication.
