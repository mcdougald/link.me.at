<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/hero-dark.png">
    <img src=".github/assets/hero.png" alt="link.me.at landing page" width="880">
  </picture>
</p>

<h1 align="center">link.me.at</h1>

<p align="center"><strong>Short links that know which click became a customer.</strong></p>

<p align="center">
  <img src="https://img.shields.io/badge/status-in%20development-171717?style=flat-square" alt="Status: in development">
  <img src="https://img.shields.io/badge/license-source--available-404040?style=flat-square" alt="License: source-available">
  <img src="https://img.shields.io/badge/self--host-supported-525252?style=flat-square" alt="Self-host: supported">
  <img src="https://img.shields.io/badge/part%20of-me.at-737373?style=flat-square" alt="Part of me.at">
</p>

<p align="center">
  <a href="#features">Features</a> ·
  <a href="#how-it-works">How it works</a> ·
  <a href="#built-with">Built with</a>
</p>

Most link shorteners count every hit as a visitor and hand each signup to whichever click came last. I built link.me.at for short links on a domain you own, each with a matching QR code and attribution that says which click actually became a signup. A conversion lands on the click it names, or is stored as unattributed with a reason, and nothing is guessed onto the most recent click. Link is in active development, and its landing page states what is built and what is still missing.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/overview-dark.svg">
    <img src=".github/assets/overview.svg" alt="link.me.at at a glance: attribution not guesses, bots counted apart, screened destinations, QR codes that last" width="880">
  </picture>
</p>

## Why link.me.at

| The usual link shortener | link.me.at |
| --- | --- |
| Credits a signup to the most recent click | Joins a conversion only to the click it names, or keeps it as unattributed with the reason |
| Counts bots and link previews as visitors | Classifies every click as human, declared bot, preview or unclassified |
| Checks a destination once, if at all | Screens before a link exists and re-screens live links on a schedule |
| A dead code tells you whether it ever existed | Unknown, expired and disabled codes all answer the same 404 |

## Features

- **Honest attribution**: a conversion is joined to a click only when it names that click inside the attribution window. Anything else is kept as unattributed, with the reason.
- **Bots are counted separately**: every click is classified as human, self-declared bot, link-preview fetch or unclassified, without fingerprinting.
- **Bad destinations are refused up front**: URL shape, phishing patterns, shortener chains, an optional threat-intelligence lookup and creation rate are checked before a link exists.
- **Links are re-checked later**: a scheduled sweep re-screens live links and disables one that has gone bad, with an audit record.
- **Printed QR codes keep working**: the short URL inside a QR code is fixed on first generation, and a code is never reused for a different destination.
- **One 404 for every dead code**: unknown, expired and disabled codes all answer the same response, so nobody can enumerate which codes exist.
- **Private redirects**: redirects are sent with no-referrer, no-store and noindex, and read only a precomputed copy of the link.
- **API keys, custom domains and password-locked links** for programmatic and branded use.

## How it works

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/flow-dark.svg">
    <img src=".github/assets/flow.svg" alt="How link.me.at works: create, screen, redirect, classify, attribute" width="880">
  </picture>
</p>

A link is screened before it exists: its shape, known phishing patterns, shortener chains and the creator's rate are all checked first. A redirect reads only a precomputed copy of the link and sends no referrer, and every click is classified before it is counted. When a signup reports back, it is joined to the click it names inside the attribution window, or kept as unattributed with the reason.

## Built with

<p>
  <img src="https://img.shields.io/badge/Next.js-16-000000?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js 16">
  <img src="https://img.shields.io/badge/React-19-171717?style=flat-square&logo=react&logoColor=white" alt="React 19">
  <img src="https://img.shields.io/badge/TypeScript-5-262626?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/Tailwind%20CSS-4-404040?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS 4">
  <img src="https://img.shields.io/badge/Drizzle-Postgres-525252?style=flat-square&logo=drizzle&logoColor=white" alt="Drizzle ORM and Postgres">
  <img src="https://img.shields.io/badge/oRPC-REST%20API-737373?style=flat-square" alt="oRPC and a REST API">
</p>

- Next.js 16 (App Router), React 19, TypeScript
- Tailwind CSS 4
- oRPC for the typed API, plus a REST API for API-key access
- Drizzle ORM + Postgres
- Better Auth (the shared me.at account)
- uqr for QR codes, isbot for bot classification

## Part of the me.at family

link.me.at is one of my [`*.me.at`](https://me.at) apps. They share one design system, account, and app shell. Development happens in a private monorepo; this repository is the project's public-facing home.

## License

Source-available. See [LICENSE](LICENSE).
