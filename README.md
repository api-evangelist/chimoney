# Chimoney (chimoney)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Chimoney is a developer-first global payouts and disbursement platform with deep coverage across Africa and 130+ countries. Its REST API sends money to bank accounts, mobile money wallets, airtime, gift cards, Chimoney wallets, and Interledger wallet addresses, and manages multicurrency wallets, sub-accounts, redemption, inbound payment collection, and reference lookups (supported banks, assets, exchange rates).

## Access Model

Chimoney is **self-serve**. You sign up at the [developer dashboard](https://dash.chimoney.io/developers), receive an **API key** immediately, and authenticate every request with that key in the **`X-API-KEY`** HTTP header. There are two environments:

- **Sandbox** — `https://api-v2-sandbox.chimoney.io` — test against the full API surface with test funds, no live money movement.
- **Production** — `https://api.chimoney.io` — live payouts, enabled after account verification (KYB / compliance). Chimoney is MSB-licensed and PSP-licensed (Canada).

The current public API is **v0.2**, so full base URLs look like `https://api.chimoney.io/v0.2/...`. Asynchronous notifications are delivered via **outbound webhooks** you configure in the dashboard (Developers → App WebHooks → Endpoints); Chimoney POSTs JSON event payloads such as `payout.bank.completed` to your server. There is **no WebSocket API**.

Pricing is **transaction-based** (per-payout fees plus FX spread that vary by rail and destination country); Chimoney does not publish a numeric API price table, so the `plans/` and `finops/` documents here model it honestly with `reconciled: false`.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/chimoney/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/chimoney/refs/heads/main/apis.yml)

## Tags

- Payouts
- Disbursements
- Payments
- Africa
- Global Payouts
- Wallets
- Multicurrency
- Gift Cards
- Mobile Money
- Fintech

## Timestamps

- **Created:** 2026-07-12
- **Modified:** 2026-07-12

## APIs

### Chimoney Payouts API

Send money to beneficiaries across 130+ countries - bank accounts, mobile money wallets, airtime, gift cards, Chimoney wallets, Interac, and Interledger wallet addresses - plus initiate, process, and check the status of payout transactions.

- **Human URL:** [https://chimoney.readme.io/reference/payouts](https://chimoney.readme.io/reference/payouts)
- **Base URL:** `https://api.chimoney.io/v0.2`

#### Tags

- Payouts
- Disbursements
- Mobile Money
- Gift Cards

#### Properties

- [Documentation](https://chimoney.readme.io/reference/payouts)
- [API Reference](https://api.chimoney.io/v0.2/api-docs/)
- [OpenAPI](openapi/chimoney-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/chimoney.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/chimoney.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Chimoney Wallets API

List associated Chimoney wallets, look up a single wallet's details, and transfer value between Chimoney wallets.

- **Human URL:** [https://chimoney.readme.io/reference/wallets](https://chimoney.readme.io/reference/wallets)
- **Base URL:** `https://api.chimoney.io/v0.2`

#### Tags

- Wallets
- Transfers

#### Properties

- [Documentation](https://chimoney.readme.io/reference/wallets)
- [OpenAPI](openapi/chimoney-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/chimoney.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/chimoney.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Chimoney Multicurrency Wallets API

Create, update, retrieve, and list multicurrency wallets, request transfer quotes, and move funds between multicurrency wallets, emails, or phone numbers.

- **Human URL:** [https://chimoney.readme.io/reference/multicurrency-wallets](https://chimoney.readme.io/reference/multicurrency-wallets)
- **Base URL:** `https://api.chimoney.io/v0.2`

#### Tags

- Multicurrency
- Wallets

#### Properties

- [Documentation](https://chimoney.readme.io/reference/multicurrency-wallets)
- [OpenAPI](openapi/chimoney-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/chimoney.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/chimoney.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Chimoney Sub-Accounts API

Create, update, delete, and list sub-accounts (wallet accounts) under your organization, and manage sub-account communities and their members.

- **Human URL:** [https://chimoney.readme.io/reference/sub-accounts](https://chimoney.readme.io/reference/sub-accounts)
- **Base URL:** `https://api.chimoney.io/v0.2`

#### Tags

- Sub-Accounts
- Accounts

#### Properties

- [Documentation](https://chimoney.readme.io/reference/sub-accounts)
- [OpenAPI](openapi/chimoney-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/chimoney.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/chimoney.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Chimoney Redeem API

Redeem issued value - any asset, Chimoney, airtime, gift cards, or mobile money - against a Chimoney transaction reference.

- **Human URL:** [https://chimoney.readme.io/reference/redeem](https://chimoney.readme.io/reference/redeem)
- **Base URL:** `https://api.chimoney.io/v0.2`

#### Tags

- Redeem
- Payouts

#### Properties

- [Documentation](https://chimoney.readme.io/reference/redeem)
- [OpenAPI](openapi/chimoney-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/chimoney.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/chimoney.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Chimoney Info API

Reference lookups powering payouts - supported banks and bank codes, bank branches, assets, airtime countries, mobile money codes, exchange rates, USD/local currency conversion, and bank account verification.

- **Human URL:** [https://chimoney.readme.io/reference/info](https://chimoney.readme.io/reference/info)
- **Base URL:** `https://api.chimoney.io/v0.2`

#### Tags

- Reference Data
- Banks
- Exchange Rates

#### Properties

- [Documentation](https://chimoney.readme.io/reference/info)
- [OpenAPI](openapi/chimoney-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/chimoney.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/chimoney.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Chimoney Accounts API

Retrieve all or single transactions, look up transactions by issue ID, fetch public profiles, transfer between accounts, delete unpaid transactions, and issue Interledger wallet addresses for users.

- **Human URL:** [https://chimoney.readme.io/reference/accounts](https://chimoney.readme.io/reference/accounts)
- **Base URL:** `https://api.chimoney.io/v0.2`

#### Tags

- Accounts
- Transactions

#### Properties

- [Documentation](https://chimoney.readme.io/reference/accounts)
- [OpenAPI](openapi/chimoney-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/chimoney.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/chimoney.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Chimoney Payments API

Initiate inbound payment (collection) requests, verify a payment's status, and simulate status changes in the sandbox environment.

- **Human URL:** [https://chimoney.readme.io/reference/payments](https://chimoney.readme.io/reference/payments)
- **Base URL:** `https://api.chimoney.io/v0.2`

#### Tags

- Payments
- Collection

#### Properties

- [Documentation](https://chimoney.readme.io/reference/payments)
- [OpenAPI](openapi/chimoney-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/chimoney.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/chimoney.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Domain Security](security/chimoney-domain-security.yml)
- [Authentication](authentication/chimoney-authentication.yml)
- [GitHub Organization](https://github.com/Chimoney)
- [LinkedIn](https://www.linkedin.com/company/chimoney)
- [Website](https://chimoney.io)
- [Documentation](https://chimoney.readme.io)
- [Plans](plans/chimoney-plans-pricing.yml)
- [Rate Limits](rate-limits/chimoney-rate-limits.yml)
- [Fin Ops](finops/chimoney-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
