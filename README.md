# Telia Company (telia)

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
