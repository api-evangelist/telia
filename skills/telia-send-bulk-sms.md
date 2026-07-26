---
name: telia-send-bulk-sms
description: Send a mobile-terminated SMS through the Telia Company Bulk Messaging Platform over the SMS REST API v2, and receive mobile-originated messages and delivery reports on the SMS Callback API.
api: https://cdn.messaging.teliacompany.com/documents/developer/index.html
operations:
  - POST /messages (Submit SMS message)
  - POST /content (Submit SMS content)
  - Receive SMS (MO callback, customer-implemented)
  - Receive delivery report (DLR callback, customer-implemented)
generated: '2026-07-25'
method: generated
source: https://cdn.messaging.teliacompany.com/documents/developer/index.html
---

# Send an SMS through Telia Bulk Messaging

Telia's Bulk Messaging Implementation Guide (v1.5, 2026-05-18) is the only substantive
API documentation Telia publishes without a login. The OpenAPI definition for this API
exists but is hosted inside the Bulk Messaging portal behind a sign-in, so the steps
below are grounded in the guide's published endpoints and payload examples — there is
no `operationId` vocabulary to bind to.

## Before you start

Three prerequisites, all sales-led:

1. A signed Bulk Messaging agreement — **per Telia country** you want to send to.
2. A user account on the Bulk Messaging web portal (`https://messaging.teliacompany.com/`).
3. An active SMS service, with API credentials created by a user holding the
   **Technical** role under *Services → Technical Configuration*.

Choose the protocol there too. Telia recommends REST for new integrations and SMPP for
high volume or existing SMPP estates.

## 1. Authenticate

HTTP Basic. Base URL:

```
https://api.messaging.teliacompany.com/sms/rest/v2
```

Anonymous calls to that path return `401`, which confirms the challenge is live.

## 2. Submit a simple text message — `POST ~/messages`

```json
{
  "cref": "47aaf1fd-0910-4a69-bc64-affe49df9dfb",
  "to": "+4712345678",
  "from": "12345",
  "message": "Hello World"
}
```

Addressing rules (`conventions/telia-conventions.yml`):

- `to` — MSISDN in E.164 with `+` and country code, max 15 digits.
- `from` — an access number (4–6 digits, **no** `+` and **no** country code), or an
  alphanumeric sender ID of max 11 GSM7 characters. Adding a country code to an access
  number causes errors.
- Norwegian sub-numbers are exactly 9 digits appended to the access number.

Optional fields: `dataCoding: "UNICODE"` for emoji, `flash: true` for a flash SMS.
Long text is segmented automatically — up to **16 segments**, 153 GSM7 characters each.

## 3. Submit custom content — `POST ~/content`

Use this only when you need control over the data coding scheme, UDH headers or binary
content. `content` may be an object or an array of segments, each with a `header` and a
`message`; `dcs` sets the data coding scheme (`8` = Unicode, `0` = default SMSC
charset); `content.format: "HEX"` sends a hex-encoded body. Each custom segment is a
hard maximum of **140 bytes**.

## 4. Understand `cref`

`cref` is a client-supplied reference carried on every published example. Telia does
**not** document it as an idempotency or de-duplication key — treat it as correlation
only, and do not assume a retry with the same `cref` is safe. Telia documents no
idempotency contract on any surface.

## 5. Receive MO messages and delivery reports

To receive anything, you implement the **SMS Callback API** and register your callback
address and callback credentials in the portal. Telia calls two operations on you:

- **Receive SMS (MO)** — a subscriber messaged your access, long or sub-number.
- **Receive delivery report (DLR)** — the outcome of a message you submitted.

Telia states your implementation must match the OpenAPI specification it supplies
through the portal. No AsyncAPI exists for this surface
(`asyncapi/telia-webhooks.yml`).

## 6. Failure modes that are not errors

Two behaviours in `errors/telia-error-codes.yml` will silently cost you money or
traffic:

- **A success response is not proof of delivery.** Under Sender ID Protection, a
  message using a blacklisted look-alike sender ID returns **OK**, is blocked, and is
  still charged — on a separate invoice line.
- On SMPP, Telia's vendor-specific `command_status` values are `1040` (sender ID
  reserved / not authorised), `1041` (traffic quota exceeded — daily or monthly, all
  or foreign traffic) and `1042` (traffic blocked). `1042` is a service
  configuration, not a transient condition: stop retrying and contact support.

## 7. If you use SMPP instead

Endpoint `smpp.messaging.teliacompany.com:3550`, TLS 1.2 minimum with **SNI required**,
interface version `0x34`, and your static source IPs must be whitelisted in Telia's
ACL. Use TON/NPI `0x01`/`0x01` for international numbers, `0x03`/`0x00` for short
numbers, `0x05`/`0x00` for alphanumeric. Default window size is 10 PDUs; connection
count is capped per service. Always `unbind` gracefully — and handle an
**SMSC-initiated** unbind during patching by acknowledging, closing, and immediately
re-binding.
