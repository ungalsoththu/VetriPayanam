# Vetri Payanam Hub — வெற்றி பயணம் ஆய்வுக்கூடம்
> **Live site:** https://ungalsoththu.github.io/VetriPayanam/ — renders the metrics table straight from `data/metrics.csv` on every visit, so it updates itself when the daily watch pushes.

**One umbrella for everything on Tamil Nadu's fare-free bus travel for women & transgender persons: government orders, day-to-day news, social-media analysis, and the numbers behind the scheme.**

Covers both phases of the scheme:

| Phase | Name | Government | Window | Scope |
| --- | --- | --- | --- | --- |
| Legacy | **Vidiyal Payanam** (விடியல் பயணம், "Dawn Journey") — Kalaignar Magalir Vidiyal Payanam | DMK (CM M.K. Stalin) | May 2021 → Sep 2026 | Free travel for women in ordinary city/town buses of the 7 STCs |
| Current | **Magalir Vetri Payanam** (வெற்றி பயணம், "Victory Journey") | TVK (CM C. Joseph Vijay) | Launched 2 Oct 2026 | Expanded: + Express/LSS/Deluxe in corp & municipal limits, Mofussil Ordinary inter-district, Ghat Ordinary >40 km, transgender persons explicitly included |

Part of the [UngalSoththu](../README.md) desk — இது உங்கள் சொத்து. Public money buys these buses; the public gets to audit the scheme.

## Folder Map

| Folder | Purpose |
| --- | --- |
| `notes/` | Research notes & deep-dives (`YYYY-MM-DD-topic.md`); baseline note is the anchor |
| `gos/` | Government-order ledger: Rule 110 announcements, scheme G.O.s, circulars, reimbursement orders — every row gets a G.O. number or a "to locate" flag |
| `news/` | Day-to-day news log — single rolling file `news/NEWSLOG.md`, newest month section at bottom |
| `social/` | Social-media analysis: X/Instagram/YouTube/WhatsApp sentiment, narratives, misinformation watch — single rolling file `social/SOCIALLOG.md` |
| `data/` | Metrics time-series (`metrics.csv`) + datasets (ETM counts, reimbursements, fleet coverage) |

## Conventions

- Every number gets a source: URL + date. No exceptions.
- Tag notes with the operating company when relevant: `[MTC]`, `[TNSTC]`, `[SETC]`, plus `[VETRI]` / `[VIDIYAL]` for the scheme phase.
- Name-spelling variants observed in the wild: Vetri/Vettri Payanam, வெற்றி பயணம்; Vidiyal விடியல் பயணம். Search all variants when researching.
- PII-free: never log individual riders' details from social posts.

## Monitoring

- **Daily Vetri Payanam Watch** (Zo agent, 19:30 IST): scans news + Transport Dept releases + X for scheme updates, appends to `news/NEWSLOG.md` and `social/SOCIALLOG.md` (new `## YYYY-MM` section when the month changes; front matter at top stays intact), updates `gos/GO-INDEX.md` when orders surface, commits & pushes, and posts a brief to Discord **#ungalsoththu** — silent when nothing changed.

## Site

Jekyll (GitHub Pages) renders the md sources into pages on every push:

| Page | Source | URL |
| --- | --- | --- |
| Landing | `index.html` | `/` |
| Scheme Baseline | `notes/2026-10-03-scheme-baseline.md` | `/baseline/` |
| Fleet Composition | `notes/2026-10-03-fleet-composition.md` | `/fleet/` |
| G.O. Ledger | `gos/GO-INDEX.md` | `/gos/` |
| News Log | `news/NEWSLOG.md` | `/news/` |
| Social Analysis | `social/SOCIALLOG.md` | `/social/` |
| Numbers & Data | `data.md` (live-fetches `data/metrics.csv`) | `/data/` |

Rules: pages carry Jekyll front matter (layout/permalink) at the top — never delete it; new pages get front matter + a nav link in `_layouts/default.html`; `README.md` and `data/` are excluded from the site build.
- The desk's morning X thread (9 AM IST) covers transit-wide news; this hub is the scheme-specific archive.

## Research Agenda (standing)

1. **The G.O. trail** — Rule 110 announcement (24 Aug 2026) is not a G.O. Locate the operational scheme G.O., eligibility conditions, and the reimbursement mechanism to the 7 STCs.
2. **Follow the money** — ₹6,000 cr/yr estimate (Assembly, 24 Aug 2026): actual 2026–27 budget line, monthly reimbursement rates per corporation, arrears history under Vidiyal Payanam.
3. **Coverage edge cases** — AC buses, SETC express, ghat routes <40 km, municipal-limit boundaries for Express/LSS/Deluxe free travel.
4. **Ridership & ETM data** — gender-coded ETM counts vs claimed beneficiaries (84.32 lakh/day projected); pre/post Oct 2 comparisons.
5. **Service quality** — crowding, conductor refusal anecdotes, bus frequency on women-heavy routes; grievance trends.
6. **Social narratives** — empowerment vs fiscal-burden framings, misinformation (fake "eligibility" rules), political credit contests.

## Repo

- GitHub: https://github.com/ungalsoththu/VetriPayanam (mirror of this folder; push on every update)
