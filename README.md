# LinkSquares (linksquares)

LinkSquares is an AI-powered contract lifecycle management (CLM) platform that helps legal teams draft, review, execute, and analyze agreements. Its public REST API spans two products - **Analyze** (processed agreements plus the metadata, Smart Values, terms, types, tags, and parent/child hierarchy extracted from them, and document import for AI processing) and **Finalize** (retrieve templates, create draft/intake/request agreements, and retrieve and approve tasks so external systems can collaborate with legal without leaving their own tools).

## Access model (read first)

API access is **customer / enterprise-gated**. There is no public self-service signup for the API.

- **Authentication:** API key sent as an `x-api-key` header on every request. The key is a unique alphanumeric string that identifies your company's data.
- **Key management:** Keys are self-managed by **Administrator** users inside the LinkSquares application. A single token is shared across Analyze and Finalize and works with either product.
- **Gated surfaces:** `https://api.linksquares.com` returns `403` without a valid key. The interactive API reference at `developer.linksquares.com` is login-walled.
- **Users & groups:** provisioned via **SCIM 2.0 on the Enterprise tier**, not a public REST user-management API. The SCIM endpoint and supported operations are provided during a vendor onboarding call.
- **Base URL:** `https://api.linksquares.com` (Analyze under `/api/analyze/v1` and `/api/analyze/v2`).

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/linksquares/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/linksquares/refs/heads/main/apis.yml)

## Real vs. modeled

- **Analyze endpoints are confirmed** against the public LinkSquares help-center articles (API Overview and Analyze API Sample Use Cases), including live cURL examples.
- **Finalize endpoints are MODELED** from LinkSquares' capability-level documentation (retrieve templates, retrieve/approve tasks, create agreements). The concrete paths live behind the customer-gated API reference and are flagged `MODELED` in the OpenAPI and collections.
- Request/response **schemas throughout are modeled** from documented behavior and examples, not copied from an official OpenAPI definition.
- **SCIM user/group provisioning** is an honest gated stub - no endpoints are modeled because no path is publicly confirmable.

## Tags

- Contract Management
- Contract Lifecycle Management
- CLM
- Contracts
- AI
- Legal
- Agreements
- Document Management
- Contract Analytics

## Timestamps

- **Created:** 2026-07-12
- **Modified:** 2026-07-12

## APIs

### LinkSquares Analyze Agreements API

List and retrieve processed Analyze agreements, import DOCX/PDF documents (a two-step create-metadata then PUT-to-presigned-S3-URL flow), check upload status, add and download attachments, and update agreement fields.

- **Base URL:** `https://api.linksquares.com/api/analyze`
- **Confirmed:** `GET /v1/me`, `GET /v1/agreements`, `GET /v1/agreements/{agreement_id}`, `POST /v1/agreements`, `PATCH /v2/agreements/{agreement_id}`, `POST /v1/agreements/{agreement_id}/attachments`, `GET /v2/agreements/{agreement_id}/attachments`, `GET /v2/agreements/{agreement_id}/attachments/{attachment_id}/download`, `GET /v1/uploads/{upload_id}`

### LinkSquares Analyze Metadata and Smart Values API

Retrieve the metadata LinkSquares Analyze extracts - Smart Values (100+ automatically extracted data points), Terms, Types, Tags, and parent/child hierarchy - in bulk or per agreement, with Type, Tag, and updated-since date filters plus `next_cursor` pagination.

- **Base URL:** `https://api.linksquares.com/api/analyze`
- **Confirmed:** `GET /v1/agreements/{agreement_id}/terms`, `PATCH /v2/agreements/{agreement_id}/terms/{term_id}`, `GET /v1/agreements/{agreement_id}/hierarchy`, `GET /v1/agreement_types`

### LinkSquares Finalize Workflow API (MODELED paths)

Let external systems collaborate with legal on contracts in Finalize - retrieve templates (Draft, Intake, Request forms) and their Agreement Detail Questions and tokens, create agreements, and retrieve and approve tasks.

- **Base URL:** `https://api.linksquares.com/api/finalize`
- **Modeled:** `GET /v1/templates`, `GET /v1/tasks`, `GET /v1/tasks/{task_id}`, `PATCH /v1/tasks/{task_id}`, `POST /v1/agreements`

### LinkSquares User and Group Provisioning (SCIM)

User and group lifecycle via SCIM 2.0 on the Enterprise tier. Honest gated stub - no public REST user-management API, base path, or published SCIM auth flow; endpoint details are provided during vendor onboarding. `GET /api/analyze/v1/me` returns the identity of the user the API key is assigned to.

## Files

- [`apis.yml`](apis.yml) - APIs.json 0.19 index
- [`openapi/linksquares-openapi.yml`](openapi/linksquares-openapi.yml) - OpenAPI 3.0.3 (Analyze confirmed, Finalize modeled)
- [`collections/linksquares.postman_collection.json`](collections/linksquares.postman_collection.json) - Postman Collection 2.1
- [`collections/linksquares.opencollection.json`](collections/linksquares.opencollection.json) - Open Collection 1.0
- [`authentication/linksquares-authentication.yml`](authentication/linksquares-authentication.yml) - x-api-key auth
- [`plans/linksquares-plans-pricing.yml`](plans/linksquares-plans-pricing.yml) - plans (contact sales, not reconciled)
- [`rate-limits/linksquares-rate-limits.yml`](rate-limits/linksquares-rate-limits.yml) - 15 rps / burst 30
- [`finops/linksquares-finops.yml`](finops/linksquares-finops.yml) - FinOps view
- [`security/linksquares-domain-security.yml`](security/linksquares-domain-security.yml) - live DNS/TLS/HTTP probes
- [`review.yml`](review.yml) - WebSocket review (answer: false)

## Common Properties

- [Website](https://linksquares.com)
- [Documentation](https://help.linksquares.com/hc/en-us/sections/26436087990551-LinkSquares-APIs-Overview)
- [Authentication](authentication/linksquares-authentication.yml)
- [Plans](plans/linksquares-plans-pricing.yml)
- [Rate Limits](rate-limits/linksquares-rate-limits.yml)
- [Fin Ops](finops/linksquares-finops.yml)
- [Domain Security](security/linksquares-domain-security.yml)
- [LinkedIn](https://www.linkedin.com/company/linksquares)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
