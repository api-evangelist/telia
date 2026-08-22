# Telia Company (telia)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Telia Company is the Nordic and Baltic telecommunications group headquartered in Solna, Sweden, operating mobile and fixed networks in Sweden, Finland, Norway, Denmark, Lithuania, Latvia and Estonia, plus a global carrier and IoT business. As a mobile network operator it sits on the connectivity side of the telecom value chain rather than the developer-facing side, and its API posture reflects that split. Telia runs a real first-party developer hub at developer.teliacompany.io that fronts exactly two programmes — LSO Sonata (MEF/Mplify and TM Forum derived wholesale ordering APIs) and CAMARA (GSMA Open Gateway network APIs) — but both catalogs sit on Apigee portals that require an existing commercial agreement with Telia, a whitelisted corporate email domain and manual support approval before any specification or credential is issued. Only one OpenAPI definition is downloadable anonymously across the whole estate.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/telia/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/telia/refs/heads/main/apis.yml)

## Tags

- Telecommunications
- Sweden
- Nordics
- Baltics
- Mobile Network Operator
- Network APIs
- CAMARA
- Open Gateway
- Messaging
- SMS
- SMPP
- IoT
- 5G
- Broadband
- Identity Verification
- BSS
- OSS
- TM Forum
- MEF
- Standards

## Timestamps

- **Created:** 2026-07-25
- **Modified:** 2026-07-25

## Developer surface

| Surface | URL | Status | Verdict |
| --- | --- | --- | --- |
| Telia Developer Portal | https://developer.teliacompany.io/ | 200 | Real, but an index that links out to two gated catalogs |
| CAMARA portal | https://camara.teliacompany.com/ | 200 | Apigee portal, **zero** API documents to an anonymous caller |
| LSO Sonata portal | https://lso.teliacompany.com/ | 200 | Apigee portal, **one** spec downloadable anonymously |
| Telia Finland portal | https://developer.telia.fi/ | 200 | Apigee portal, **zero** API documents to an anonymous caller |
| Bulk Messaging guide | https://cdn.messaging.teliacompany.com/documents/developer/index.html | 200 | Fully public implementation guide (SMPP + SMS REST) |

`www.teliacompany.com/developer`, `/api` and `/opengateway` all return HTTP 200 but are **soft 404s** — the corporate site returns 200 for arbitrary paths. Telia publishes no developer or Open Gateway page on its corporate domain.

## CAMARA posture

Telia operates a branded CAMARA portal that describes itself in terms of GSMA Open Gateway, so this is more than a press release — there is a real portal with a real product catalog behind it. But nothing is callable or downloadable without an existing Telia commercial agreement and a whitelisted corporate domain. The portal's anonymous API catalog returns an empty list.

CAMARA APIs with real evidence on Telia's surface:

- **Quality on Demand (QoD)**
- **Device Location**

Also listed on the same portal, but *not* a CAMARA-defined API: **NGMLC Location** (a GSMA/3GPP-lineage location exposure service).

No Number Verification, SIM Swap, Device Status, Carrier Billing, KYC Match, Scam Signal, Device Swap or Population Density API was found anywhere. Telia is not an Aduna venture partner; its public route to network-API developers runs through Nokia's Network as Code platform (Telia Finland's Sirius programme).

## APIs

### Telia LSO Sonata Geographic Site Management API

MEF 122 / MEF 79 geographic site management API designed using TM Forum TMF674 as its template. The only Telia OpenAPI that could be downloaded anonymously.

- **Human URL:** [https://lso.teliacompany.com/apis](https://lso.teliacompany.com/apis)
- **Base URL:** `https://api-garden.teliacompany.com/v1/api/mef/geographicSiteManagement`
- [OpenAPI](openapi/telia-lso-sonata-site-management.yml)

### Telia LSO Sonata (remaining programme)

Named and described on the public portal home page, specifications behind sign-in:

- Geographic Address Management API (TMF673)
- Product Offering Qualification API (TMF679)
- Quote Management API (TMF648)
- Order Management API (TMF622)
- Notification API (buyer-registered listener for quote/order events)

### Telia CAMARA APIs

- Quality on Demand API
- Device Location API
- NGMLC Location API

- **Human URL:** [https://camara.teliacompany.com/apis](https://camara.teliacompany.com/apis)

### Telia Finland APIs

- Public Catalogue Service API
- Mobile Subscription API
- Mobile Subscription Order Service API

- **Human URL:** [https://developer.telia.fi/apis](https://developer.telia.fi/apis)

### Telia Bulk Messaging

- **SMS REST API** — `https://api.messaging.teliacompany.com/sms/rest/v2`, HTTP Basic auth, `POST ~/messages`
- **SMS Callback API** — customer-implemented webhooks for mobile-originated SMS and delivery reports
- **SMPP API** — `smpp.messaging.teliacompany.com:3550`, TLS 1.2+, SNI required, static IP ACL

- **Human URL:** [https://cdn.messaging.teliacompany.com/documents/developer/index.html](https://cdn.messaging.teliacompany.com/documents/developer/index.html)

### Telia ACE Audio Stream Forwarding API

Bidirectional streaming gRPC over HTTP/2 with mutual TLS, forwarding contact-centre call audio to a customer-implemented receiver. Telia publishes the proto3 definition openly.

- **Human URL:** [https://github.com/telia-oss/ace-audio-stream-forwarding-api](https://github.com/telia-oss/ace-audio-stream-forwarding-api)
- [gRPC proto](proto/telia-ace-audio-stream-forwarding-v1.proto)

### Telia Tunnistus Identification Broker

OpenID Connect / OAuth 2.0 identification broker for Finnish strong electronic identification. Discovery document served anonymously; **no CIBA backchannel endpoint** is advertised.

- **Human URL:** [https://github.com/telia-oss/tunnistus](https://github.com/telia-oss/tunnistus)
- **Issuer:** `https://tunnistus.telia.fi/uas`

## Auth models

| Scheme | Where |
| --- | --- |
| HTTP Basic | Bulk Messaging SMS REST API |
| Bearer token | LSO Sonata APIs (`prodBearerAuth`, `testBearerAuth`) |
| Mutual TLS | Telia ACE Audio Stream Forwarding gRPC |
| OAuth 2.0 / OIDC | Telia Tunnistus (no CIBA) |
| IP allow-listing | SMPP API |

## Links

- [Telia Company](https://www.teliacompany.com/)
- [Telia Developer Portal](https://developer.teliacompany.io/)
- [telia-oss on GitHub](https://github.com/telia-oss)
