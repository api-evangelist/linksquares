# LinkSquares

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

LinkSquares is an AI-powered contract lifecycle management (CLM) platform that helps legal teams draft, review, execute, and analyze agreements. Its public REST API is split across two products - Analyze, which surfaces processed agreements plus the metadata, Smart Values, terms, types, tags, and parent/child hierarchy extracted from them, and lets you import DOCX/PDF documents for AI processing; and Finalize, which lets external systems retrieve templates, create draft/intake/request agreements, and retrieve and approve tasks so stakeholders can collaborate on contracts without leaving their own tools. A single API token is shared across Analyze and Finalize and is passed as an x-api-key header. API access is gated to LinkSquares customers, and keys are self-managed by Administrator users; user and group provisioning is offered through SCIM 2.0 on the Enterprise tier rather than a public REST endpoint.

**Areas:** Contract Management · Contract Lifecycle Management · Contracts · Artificial Intelligence · Legal · Agreements · Document Management · Contract Analytics

## LinkSquares on APIs.io

Everything profiled for LinkSquares is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/linksquares/](https://apis.io/providers/linksquares/)** — or go straight to one of the APIs or properties below.

### APIs (6)

- [LinkSquares User and Group Provisioning (SCIM)](https://apis.io/apis/linksquares/linksquares-scim-provisioning-api/) — User and group lifecycle management is offered through SCIM 2.0 provisioning on the Enterprise tier rather than a public REST endpoint. There is no…
- [LinkSquares Account API](https://apis.io/apis/linksquares/linksquares-account-api/) — Identity and status of the API user (confirmed).
- [LinkSquares Agreements API](https://apis.io/apis/linksquares/linksquares-agreements-api/) — Analyze agreements and document import/upload (confirmed).
- [LinkSquares Attachments API](https://apis.io/apis/linksquares/linksquares-attachments-api/) — Additional attachments on Analyze agreements (confirmed).
- [LinkSquares Finalize API](https://apis.io/apis/linksquares/linksquares-finalize-api/) — Finalize templates, tasks, and agreement creation (MODELED paths).
- [LinkSquares Metadata and Smart Values API](https://apis.io/apis/linksquares/linksquares-metadata-and-smart-values-api/) — Terms, Smart Values, hierarchy, and agreement types (confirmed).

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Linksquares Agentic Access](https://apis.io/agentic-access/linksquares/linksquares-agentic-access/)

#### Collections (6)

Postman and Open Collection request collections.

- [LinkSquares API](https://apis.io/collections/linksquares/open-linksquares/)
- [LinkSquares Account API](https://apis.io/collections/linksquares/open-linksquares-account-api/)
- [LinkSquares Account Agreements API](https://apis.io/collections/linksquares/open-linksquares-agreements-api/)
- [LinkSquares Account Attachments API](https://apis.io/collections/linksquares/open-linksquares-attachments-api/)
- [LinkSquares Account Finalize API](https://apis.io/collections/linksquares/open-linksquares-finalize-api/)
- [LinkSquares Account Metadata and Smart Values API](https://apis.io/collections/linksquares/open-linksquares-metadata-and-smart-values-api/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Linksquares Authentication](https://apis.io/security/linksquares/linksquares-authentication/)
- [Linksquares Domain Security](https://apis.io/security/linksquares/linksquares-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Linksquares Plans Pricing](https://apis.io/plans/linksquares/linksquares-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Linksquares Rate Limits](https://apis.io/rate-limits/linksquares/linksquares-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Linksquares Finops](https://apis.io/finops/linksquares/linksquares-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://linksquares.com)
- [Documentation](https://help.linksquares.com/hc/en-us/sections/26436087990551-LinkSquares-APIs-Overview)
- [Sign up](https://help.linksquares.com/hc/en-us/articles/10575849523735-Managing-API-Keys)
- [Blog](https://blog.linksquares.com)

## API Evangelist rating

**Kin Score 28.7** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 66.1 |
| Contract quality | 50.6 |
| Contract governance | 0.0 |
| Operational transparency | 5.3 |
| Developer ergonomics | 32.1 |
| Access clarity | 18.4 |

**Agent readiness 17.9** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 10.9** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/linksquares/](https://apis.io/providers/linksquares/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for LinkSquares: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/linksquares/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
