# Reykjawwwik — Web Agency SaaS

[![Quality Gate](https://github.com/kamiljan11/reykjawwwik-platform/actions/workflows/quality.yml/badge.svg)](https://github.com/kamiljan11/reykjawwwik-platform/actions/workflows/quality.yml)

**Live:** [reykjawwwik.is](https://reykjawwwik.is) · **Status:** production

A full SaaS platform powering a web/design agency end to end.

## What it does
- **Multi-market pricing engine** across 10 countries with geo-detection
- Lead-to-contract pipeline + admin **CRM**
- **PDF contract generation** with per-country VAT logic
- Push notifications

## Stack
React · TypeScript · Supabase · Vercel

## What this repository is

This is a **public reference repo, not the application** — there is no `package.json`, no
`src/`, nothing to `npm install` or run. The application source is private (see
[Source](#source) below). What lives here is the documentation trail: what the platform does,
why it's split this way, and how to tell if it's still alive. See
[`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md) and
[`docs/adr/0001-public-repo-is-a-reference-not-the-source.md`](docs/adr/0001-public-repo-is-a-reference-not-the-source.md).

## Checking it's alive

```bash
curl -I https://reykjawwwik.is          # 200 = up
curl -I https://cars.reykjawwwik.is     # client build
curl -I https://tours.reykjawwwik.is    # client build
curl -I https://beauty.reykjawwwik.is   # client build
```

CI (`.github/workflows/quality.yml`) runs a secrets scan and Semgrep on this repo's own
content; the npm-based steps (lint/typecheck/test/build) no-op here (`if: hashFiles('package.json') != ''`)
because there's no application code in this repo to run them on.

## Source
Application source: [`spirit-way-bloom`](https://github.com/kamiljan11/spirit-way-bloom) — proprietary and private (verified: returns 404 unauthenticated). Live at [reykjawwwik.is](https://reykjawwwik.is). Selected client builds: [cars.reykjawwwik.is](https://cars.reykjawwwik.is) · [tours.reykjawwwik.is](https://tours.reykjawwwik.is) · [beauty.reykjawwwik.is](https://beauty.reykjawwwik.is)

## Licence

See [`LICENSE`](LICENSE) — proprietary, published for reference only.
