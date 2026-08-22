# LinkSquares (linksquares)

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
