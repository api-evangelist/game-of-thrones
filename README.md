# An API of Ice and Fire

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

An API of Ice and Fire is a free, open REST API providing comprehensive Game of Thrones and A Song of Ice and Fire (ASOIAF) data including books, characters, and houses from George R.R. Martin's universe.

- **Website:** https://anapioficeandfire.com/
- **Documentation:** https://github.com/joakimskoog/AnApiOfIceAndFire/wiki
- **GitHub:** https://github.com/joakimskoog/AnApiOfIceAndFire
- **Base URL:** https://www.anapioficeandfire.com/api

## Overview

The API provides structured, quantified data covering:

- **Books** — All published books in the A Song of Ice and Fire series with ISBNs, authors, page counts, publishers, release dates, and character lists
- **Characters** — Named characters with aliases, titles, cultural backgrounds, relationships (father, mother, spouse), allegiances, book appearances, POV chapters, TV season appearances, and actors
- **Houses** — Noble houses with regions, coats of arms, words (mottos), current lords, heirs, overlords, founders, ancestral weapons, cadet branches, and sworn members

## Authentication

No authentication is required. The API is completely open and free to use.

## Rate Limits

- 20,000 requests per day per IP address
- Exceeding the limit returns a 403 Forbidden response for the remainder of the 24-hour period
- Caching is recommended to reduce unnecessary requests

## Pagination

All list endpoints support pagination via query parameters:

- `?page` — Page number (1-based, default: 1)
- `?pageSize` — Results per page (default: 10, maximum: 50)

Navigation links are provided in the `Link` response header (`next`, `prev`, `first`, `last`).

## Endpoints

| Resource | URL |
|----------|-----|
| Root | `GET /api` |
| Books | `GET /api/books` |
| Book by ID | `GET /api/books/{id}` |
| Characters | `GET /api/characters` |
| Character by ID | `GET /api/characters/{id}` |
| Houses | `GET /api/houses` |
| House by ID | `GET /api/houses/{id}` |

## APIs.json

This repository contains an APIs.json 0.19 profile for this API maintained by [API Evangelist](https://apievangelist.com).

- [apis.yml](apis.yml) — Main API index
- [plans/game-of-thrones-plans-pricing.yml](plans/game-of-thrones-plans-pricing.yml) — Plans and pricing
- [rate-limits/game-of-thrones-rate-limits.yml](rate-limits/game-of-thrones-rate-limits.yml) — Rate limit details
- [finops/game-of-thrones-finops.yml](finops/game-of-thrones-finops.yml) — Financial operations guidance
