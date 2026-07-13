# Chimoney (chimoney)

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
