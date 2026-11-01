# Telia Company

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

Telia Company is the Nordic and Baltic telecommunications group headquartered in Solna, Sweden, operating mobile and fixed networks in Sweden, Finland, Norway, Denmark, Lithuania, Latvia and Estonia, plus a global carrier and IoT business. As a mobile network operator it sits on the connectivity side of the telecom value chain rather than the developer-facing side, and its API posture reflects that split. Telia runs a real first-party developer hub at developer.teliacompany.io that fronts exactly two programmes — LSO Sonata (MEF/Mplify and TM Forum derived wholesale ordering APIs) and CAMARA (GSMA Open Gateway network APIs) — but both catalogs sit on Apigee portals that require an existing commercial agreement with Telia, a whitelisted corporate email domain and manual support approval before any specification or credential is issued. Only one OpenAPI definition is downloadable anonymously across the whole estate. Its CAMARA portal names Quality on Demand and Device Location but publishes nothing callable without login, and Telia reaches network-API developers mainly through Nokia's Network as Code aggregator platform rather than directly. The genuinely open surface is a public Bulk Messaging implementation guide covering an SMPP endpoint and an SMS REST API, and a gRPC audio-forwarding contract for its Telia ACE contact-centre product.

**Areas:** Telecommunications · Sweden · Nordic · Baltics · Mobile Network Operator · Network APIs · CAMARA · Open Gateway · Messaging · SMS · SMPP · IoT

## Telia Company on APIs.io

Everything profiled for Telia Company is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/telia/](https://apis.io/providers/telia/)** — or go straight to one of the APIs or properties below.

### APIs (25)

- [Telia LSO Sonata Geographic Address Management API](https://apis.io/apis/telia/telia-lso-sonata-geographic-address-management-api/) — LSO Sonata Geographic Address API allows a buyer to retrieve a geographic address from the seller database by address id and to validate geographic address…
- [Telia LSO Sonata Product Offering Qualification API](https://apis.io/apis/telia/telia-lso-sonata-product-offering-qualification-api/) — Determines whether it is feasible for the seller to deliver a particular product to a particular geographic location, and manages create POQ, retrieve POQ…
- [Telia LSO Sonata Quote Management API](https://apis.io/apis/telia/telia-lso-sonata-quote-management-api/) — Manages quote request and completion between seller and buyer for Telia operator customers and selected B2O products. Designed using TM Forum TMF648 as its…
- [Telia LSO Sonata Order Management API](https://apis.io/apis/telia/telia-lso-sonata-order-management-api/) — Creates product orders covering new, change, disconnect and suspend scenarios, with the current version focused on new order creation. Designed using TM…
- [Telia LSO Sonata Notification API](https://apis.io/apis/telia/telia-lso-sonata-notification-api/) — Buyer-registered listener API for quote and order notifications — state change, create quote, attribute change and BAFO quotes — pushed from seller to…
- [Telia CAMARA Quality on Demand API](https://apis.io/apis/telia/telia-camara-quality-on-demand-api/) — CAMARA Quality on Demand (QoD) API listed on Telia's CAMARA portal, allowing an application to request a higher-quality network connection. Named and…
- [Telia CAMARA Device Location API](https://apis.io/apis/telia/telia-camara-device-location-api/) — CAMARA Device Location API listed on Telia's CAMARA portal, allowing a caller to request the area in which a user device is located. Named on the public…
- [Telia NGMLC Location API](https://apis.io/apis/telia/telia-ngmlc-location-api/) — Ngmlc_Location_ProvideLocation service operation, invoked by a service consumer towards the ENL to request the geodetic location of a single device or to…
- [Telia Finland Public Catalogue Service API](https://apis.io/apis/telia/telia-finland-public-catalogue-service-api/) — A request mapper proxying requests to Telia Finland's internal Catalogue Service API, deliberately limiting and restricting the functionality present in the…
- [Telia Finland Mobile Subscription API](https://apis.io/apis/telia/telia-finland-mobile-subscription-api/) — Manages business mobile subscriptions for Telia Finland customers — list subscription, get subscription, update subscription information, deactivate,…
- [Telia Finland Mobile Subscription Order Service API](https://apis.io/apis/telia/telia-finland-mobile-subscription-order-service-api/) — Exposes available packages and products and allows ordering them for both new and existing mobile subscriptions at Telia Finland. Named and described on the…
- [Telia Bulk Messaging SMS REST API](https://apis.io/apis/telia/telia-bulk-messaging-sms-rest-api/) — JSON REST API for submitting mobile-terminated SMS through the Telia Company Bulk Messaging Platform, with a Submit SMS message operation (POST ~/messages)…
- [Telia Bulk Messaging SMS Callback API](https://apis.io/apis/telia/telia-bulk-messaging-sms-callback-api/) — The webhook half of Telia's Bulk Messaging REST surface. Customers must implement a Receive SMS (mobile originated) operation and a Receive delivery report…
- [Telia Bulk Messaging SMPP API](https://apis.io/apis/telia/telia-bulk-messaging-smpp-api/) — SMPP v3.4-style binary protocol interface into the Telia Company Bulk Messaging Platform, reached over TLS 1.2 or better at smpp.messaging.teliacompany.com…
- [Telia ACE Audio Stream Forwarding API](https://apis.io/apis/telia/telia-ace-audio-stream-forwarding-api/) — Bidirectional streaming gRPC service over HTTP/2 that forwards copies of the audio streams in Telia ACE contact-centre voice calls to a customer-implemented…
- [Telia Tunnistus Identification Broker](https://apis.io/apis/telia/telia-tunnistus-identification-broker/) — Telia Tunnistus is Telia Finland's identification broker service — an OpenID Connect and OAuth 2.0 identity provider that brokers Finnish strong electronic…
- [Telia ACE Knowledge REST API](https://apis.io/apis/telia/telia-ace-knowledge-rest-api/) — The REST API behind Telia ACE Knowledge (formerly Humany), the self-service knowledge and contact-deflection product inside the Telia ACE contact-centre…
- [Telia ACE Knowledge Contact Method WebHook](https://apis.io/apis/telia/telia-ace-knowledge-contact-method-webhook/) — The outbound webhook surface of Telia ACE Knowledge. A contact method of type Web service forwards an end user's form submission and the current ACE…
- [Telia ACE Web API](https://apis.io/apis/telia/telia-ace-web-api/) — Client-side and server-side REST interface that lets an end user communicate with a Telia ACE contact centre from the customer's own website. Telia…
- [Telia ACE Agent API](https://apis.io/apis/telia/telia-ace-agent-api/) — Integration API between the Telia ACE contact-centre platform and a customer's CRM system, used to drive agent-side integration such as surfacing and…
- [Telia ACE Workitem API](https://apis.io/apis/telia/telia-ace-workitem-api/) — Work-item management API for the Telia ACE contact centre, covering prioritisation, queue management and forwarding of tasks across the platform. Named and…
- [Telia ACE Screen Pop API](https://apis.io/apis/telia/telia-ace-screen-pop-api/) — Screen-pop integration API for Telia ACE that automatically opens the matching customer profile in the agent's business system when an interaction arrives,…
- [Telia ACE Interaction View API](https://apis.io/apis/telia/telia-ace-interaction-view-api/) — Export API against Telia ACE Interaction View that allows content and data from recorded contact-centre interactions to be exported to external systems for…
- [Telia Company List Geographic Site API](https://apis.io/apis/telia/telia-listgeographicsite-api/) — Retrieves a list of geographic sites based on the provided site id or other fields.
- [Telia Company Retrieve Geographic Site API](https://apis.io/apis/telia/telia-retrievegeographicsite-api/) — Retrieves detailed information for a specific geographic site using its ID.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Telia Webhooks](https://apis.io/asyncapis/telia/telia-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [telia-lso-sonata](https://apis.io/servers/telia/telia-lso-sonata/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Telia Agentic Access](https://apis.io/agentic-access/telia/telia-agentic-access/)

#### Collections (1)

Postman and Open Collection request collections.

- [B2X-Global-SiteManagement-API-v1](https://apis.io/collections/telia/open-telia-lso-sonata-site-management/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Telia Lso Sonata Site Management Overlay](https://apis.io/overlays/telia/telia-lso-sonata-site-management-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Telia Authentication](https://apis.io/security/telia/telia-authentication/)
- [Telia Domain Security](https://apis.io/security/telia/telia-domain-security/)
- [Telia Vulnerability Disclosure](https://apis.io/security/telia/telia-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Telia Scopes](https://apis.io/scopes/telia/telia-scopes/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.teliacompany.com/)
- [Documentation](https://developer.teliacompany.io/)
- [Getting started](https://lso.teliacompany.com/get-started)
- [API reference](https://cdn.messaging.teliacompany.com/documents/developer/index.html)
- [Sign up](https://lso.teliacompany.com/register)
- [Blog](https://ace-showcase.com/blog/)
- [GitHub](https://github.com/telia-oss)
- [Status](https://www.telia.se/support/driftinformation-mobilt)

## API Evangelist rating

**Kin Score 46.8** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 57.1 |
| Contract quality | 57.0 |
| Contract governance | 18.2 |
| Operational transparency | 52.6 |
| Developer ergonomics | 67.3 |
| Access clarity | 0.0 |

**Agent readiness 43.0** — agent-native

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | na |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | na |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | — |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | na |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | na |

**Regulatory alignment 49.2** — Telecommunications

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/telia/](https://apis.io/providers/telia/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Telia Company: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/telia/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
