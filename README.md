# An API of Ice and Fire

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
