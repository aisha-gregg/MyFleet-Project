# Content audit and retirement log

A record of what was reviewed, what changed, and what was retired after Release 4.2.
Goal: every customer-facing page is current within one release cycle, in every language.

**Audit period:** 3–14 November 2026 · **Trigger:** Release 4.2 and MT-100 launch · **Auditor:** technical writer
**Scope:** 64 items (knowledge base, guides, API docs, print, video) across EN, ES, FR

## Summary

| Result | Items | Share |
|--------|------:|------:|
| Current, no change | 38 | 59% |
| Updated | 17 | 27% |
| Merged into another page | 4 | 6% |
| Retired | 5 | 8% |

## How each item was checked

1. **Accuracy:** matches the product in Release 4.2 (UI labels, steps, screenshots, LED behaviour, endpoints).
2. **Use:** page views and search terms over the last 6 months, plus support tickets that link to it.
3. **Consistency:** follows the style guide and glossary; same content in every language.
4. **Ownership:** has a named owner and a review date.

## Log

| ID | Item | Channel | Lang | Finding | Action | Owner | Status |
|----|------|---------|------|---------|--------|-------|--------|
| A-01 | KB-0101 Install the MT-200 | KB | EN/ES/FR | Firmware 3.8 shortens GPS fix time; step 4 timing outdated | Updated: "up to 3 minutes" | Tech writer | ✓ Done |
| A-02 | KB-0142 MT-100 vehicle not visible | KB | EN/ES | New article for MT-100 launch | Published, linked from box insert QR | Tech writer | ✓ Done |
| A-03 | KB-0088 FT-series LED codes | KB | EN/ES/FR | Product end of life; 12 views in 6 months | Retired, redirect to KB-0142 | Tech writer | ✓ Done |
| A-04 | Driver App guide: pre-trip check | Guide | EN/ES/FR | 4.2 allows 5 photos per defect (was 1) | Updated step 3 and screenshot | Tech writer | ✓ Done |
| A-05 | API reference: `GET /trips` | API docs | EN | Max range changed from 7 to 31 days | Updated parameter table and error text | Tech writer + API team | ✓ Done |
| A-06 | API reference: `driver_name` field | API docs | EN | Deprecated in 2.4 | Marked deprecated, removal date added | Tech writer | ✓ Done |
| A-07 | "Getting started with webhooks" and "Webhook security" | KB | EN | Overlap; developers landed on the wrong one | Merged into the integration guide | Tech writer | ✓ Done |
| A-08 | MT-200 box insert rev. C | Print | EN/ES | Still says "black box" in ES | Updated to *localizador* for next print run (rev. D) | Tech writer + print vendor | ◐ In print |
| A-09 | MT-200 installation video | Video | EN (ES/FR subs) | Shows old Installer app screens | Re-record shots 8–10; subtitles re-translated | Tech writer + video team | ◐ Scheduled Q1 |
| A-10 | Release notes 3.x (2024) | Release notes | EN/ES/FR | Older than 2 years; no traffic | Archived (kept, not indexed) | Tech writer | ✓ Done |
| A-11 | Product Availability Matrix | Web | EN | Missing MT-100 and defect alerts | Updated for Q4 2026 | Tech writer | ✓ Done |
| A-12 | FR knowledge base: OEM Connect setup | KB | FR | Out of sync with EN (2 steps missing) | Sent for translation update (LOC-240) | Localization | ◐ In translation |

## Retirement rules

A page is retired when **any** of these is true:

- the product or feature has reached end of life
- it has had fewer than 20 views in 6 months **and** no support ticket links to it
- its content is fully covered by another page (merge instead, and redirect)

Retired pages are redirected, never just deleted, so links from old emails, PDFs, and printed QR codes still work.
Translations are retired at the same time as the English page.

## Follow-ups for the next cycle

- Re-print MT-200 insert rev. D with corrected Spanish (A-08).
- Re-record MT-200 video shots before Release 4.3 (A-09).
- Add a "Last reviewed" date to every KB template so freshness is visible to customers.
