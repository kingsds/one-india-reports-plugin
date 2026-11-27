# Changelog

What changed in each 1 India Reports release. Downloads for the newest
release are always at
`https://github.com/kingsds/one-india-reports-plugin/releases/latest`.
After any release that adds reports, tick them on AI access settings, save
and reconnect your AI app.

## 0.7.0 — November 2026

- **Gemini.** Works in Gemini CLI (`gemini extensions install
  https://github.com/kingsds/one-india-reports-plugin`, then
  `/mcp auth one-india-platform`), Antigravity, and the Gemini app on personal
  Google accounts (Settings > Connected Apps > Add custom app). Gemini
  Enterprise work accounts are not supported yet. A new Gemini CLI extension
  ZIP joins the Claude, OpenAI and Antigravity downloads.
- **Store names.** Every report accepts store names or codes, for example
  "Banda", as well as store IDs.
- **Fewer questions back.** Clear requests run straight away. Only
  purchase-cohort sell-through (`merchandise_performance`) and salary still ask
  you to confirm what you mean. Stock health defaults to Shops with a
  by-store breakdown; dispatch defaults to by department.
- **Shorter guidance.** The reporting skill is a quarter of its old size: a
  question-to-report table, the stock words, answer rules and boundaries. The
  connector's own instructions and tool descriptions are trimmed to match.
  Approval, sign-in and security detail moved to the documentation.
- **Two little-used reports hidden.** Customer recommendations and supplier
  buyer profile (no use in the last 60 days) no longer appear unless the
  owner turns them back on.
- One source file now drives every package, and download links point at the
  latest release, so they never go stale.

## 0.6.2 — 19 November 2026

- New, separately selected **shop controls** report: each approved shop's
  Ginesys cash book (cash sales, banked, petty cash spent, cash in hand, days
  since banked), day-end form checks (diesel, generator, opening and closing
  times, staff against attendance) and day-ends reopened in Ginesys. Includes
  cash values; no customer records or phone numbers.

## 0.6.1 — 13 November 2026

- One stock vocabulary shared with the store team: Shops by default and the
  warehouse only when asked, held transit with its reason, Ginesys season
  words with Promo as its own season, delisted stock counted in its season and
  shown separately, and "how old is stock" answered from the age × season view.

## 0.6.0 — 8 November 2026

- New, separately selected **business performance** report: monthly sales
  against the same days last year with like-for-like growth, category sales,
  a store's top styles, Finance store P&L as booked (with margins) and the
  company loyalty summary. Inventory Intelligence is now covered by the skill.

## 0.5.0 — 7 November 2026

- Reports are marked read-only, so apps need not ask before every read.
- Errors come with a short recovery hint; a future end date is rejected
  straight away; store lists may be left out to mean all approved stores.

## 0.4.0 — 6 November 2026

- New, separately selected **monthly salary** (named salary approval only) and
  **Finance booked rent** reports. Missing months stay missing, never zero.

## 0.3.0 — 6 November 2026

- Stock health with cost values and age since last sale, warehouse dispatch
  progress, company purchase-cohort sell-through and catalogue photos.

## 0.2.0 — 5 November 2026

- First Claude and OpenAI packages: sales, targets, footfall, category stock,
  target trends, category sell-through, and saving confirmed unanswered
  questions for the owner.
