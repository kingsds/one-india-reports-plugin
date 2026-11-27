# 1 India Reports for Claude, ChatGPT and Gemini

![1 India icon](./assets/icon.png)

Ask your AI assistant about your approved 1 India Family Mart stores and get
answers from the platform's own reports: sales and targets, this month's
target pace, store closures, footfall, stock and how old it is, sell-through,
category and season sales, dispatch, the buying plan and Store Health reviews
and, with separate approval, stock cost values, store P&L, loyalty, shop cash,
booked rent and salary.

This repository holds only connector links, the reporting skill and the brand
icon: no platform code, business records or shared credentials.

## Before you connect

You need an existing 1 India admin or superadmin account that the connector
owner has approved. Open
[AI access settings](https://1-india-loyalty-six.vercel.app/ai-connect),
enter your registered email and type the eight-digit code there (or use your
authenticator app), tick your reports and stores and press **Save AI access**.
Installing anything from this repository grants no access by itself.

Connector address for every app: `https://1-india-loyalty-six.vercel.app/mcp`

## Download

- [Claude plugin](https://github.com/kingsds/one-india-reports-plugin/releases/latest/download/one-india-claude-plugin.zip)
- [OpenAI plugin](https://github.com/kingsds/one-india-reports-plugin/releases/latest/download/one-india-openai-plugin.zip)
- [Gemini CLI extension](https://github.com/kingsds/one-india-reports-plugin/releases/latest/download/one-india-gemini-extension.zip)
- [Antigravity plugin](https://github.com/kingsds/one-india-reports-plugin/releases/latest/download/one-india-antigravity-plugin.zip)

## Claude

Open **Customize > Plugins**, upload the Claude ZIP, open its **Connectors**
tab and connect **1 India Reports** (OAuth, **Register automatically**). Or add
a custom connector with the address above. Claude Code:

```sh
claude plugin marketplace add kingsds/one-india-reports-plugin
claude plugin install one-india-platform@one-india
```

## ChatGPT and Codex

ChatGPT: **Plugins > + > Add custom MCP server**, enter the address above,
choose OAuth with automatic registration and create the plugin. Codex:

```sh
codex plugin marketplace add kingsds/one-india-reports-plugin
codex plugin add one-india-platform@one-india
```

## Gemini

Gemini CLI:

```sh
gemini extensions install https://github.com/kingsds/one-india-reports-plugin
```

Then start `gemini` and run `/mcp auth one-india-platform`. Sign-in returns to
`http://localhost:<port>/oauth/callback`, so sign in on the same computer.

Gemini app (personal Google accounts): **Settings > Connected Apps > Add
custom app**, paste the address above and approve on the 1 India page.
Gemini Enterprise is not supported yet.

Antigravity: unzip the Antigravity plugin into
`~/.gemini/config/plugins/one-india-platform/`; sign-in returns to
`https://antigravity.google/oauth-callback`.

In every app, approve only your permitted reports and stores on the 1 India
page, then ask "Check my 1 India access" as the first test.

## Reports

<!-- tools:start -->
| Tool | What it answers |
| --- | --- |
| `access_context` | Your approved stores, reports, limits, expiry and the latest loaded bill and stock dates |
| `sales_summary` | Sales (₹), bills and units per store, up to 31 days |
| `sales_trends` | Daily sales and bills per store |
| `targets_summary` | Target, sales and achievement per store, up to 31 days |
| `target_trends` | Daily sales vs target, average bill, footfall and bills per 100 visits |
| `monthly_targets` | This month's full target, month-to-date target and sales, and the daily pace still needed |
| `store_closures` | Which stores were closed on a date and why, checked against footfall and bills |
| `footfall_summary` | Submitted team footfall and the dates covered |
| `stock_summary` | Stock units per store from the latest snapshot, with its date |
| `stock_by_category` | Book stock by category for one store |
| `category_sell_through` | Sell-through by category for one store over a period |
| `inventory_health` | Book stock units and cost value, in transit, held, and stock age since last sale (Shops, by store, by default) |
| `inventory_intelligence` | Inventory Intelligence: stock by age group and season, intake, vendor journeys, Buying SOP lots, slow stock, replenishment, COGS ageing (includes costs) |
| `dispatch_readiness` | Warehouse orders awaiting scan, scanned and invoiced, by department, with order values; not truck booking |
| `merchandise_performance` | Company purchase-cohort sell-through against the Buying SOP pace (asks you to confirm dates and categories first) |
| `catalogue_styles` | Catalogue style names, colours, sizes, MRP and approved photos |
| `category_sales_review` | Best-selling categories, named-category sales, vendor GRC sell-through and season-vs-season comparisons |
| `buying_plan_review` | The Regular/Summer 2027 display-stock plan checked against last season's sales and current stock |
| `store_analysis` | The Store Health Review for one or several stores, as text |
| `store_health_review` | Opens the interactive Store Health Review with a store picker, charts and email draft |
| `business_performance` | Monthly sales vs last year, category sales, top styles, Finance store P&L and loyalty summary (includes margins) |
| `store_controls` | Shop cash book, diesel and generator, shop hours and reopened day-ends (includes cash values) |
| `salaries_monthly` | Monthly payroll or Finance manpower cost; named salary approval required |
| `rent_monthly` | Monthly Finance booked rent (not proof of payment) |
| `save_unanswered_question` | Saves a short question you confirm for the owner; the only write |
<!-- tools:end -->

Ask with store names ("How did Banda do last week against target?"). Clear
questions run straight away; purchase-cohort sell-through asks you to confirm
receipt dates and categories first. Missing data is shown as missing, never
as zero.

## Access and security

- Read-only. Only `save_unanswered_question` writes, and only the exact
  summary you confirm; saved summaries expire 90 days after last submission.
- You see only the reports and stores you selected. Salary also needs the
  named salary-access approval, rechecked on every call.
- Never returned: customer records, vendor terms, bank, tax or contact
  details, raw data or bulk exports. No changes to money, stock or accounts.
- Your selection lasts 1, 7 or 30 days; email verification lasts 24 hours.
  A connection lasts at most one hour, then the app reconnects. Changing your
  selection means reconnecting.
- Limits: admin 20 calls a minute and 500 a day; superadmin 30 a minute and
  1,000 a day; 31 days per standard report. The day resets at midnight IST.
- Never paste a password, email or authenticator code, token or key into chat.

## Support

Setup or access help: [saurabh.singh@1018mb.com](mailto:saurabh.singh@1018mb.com).
Leave passwords, codes, tokens and business data out of support messages.
What changed in each release: [CHANGELOG](./CHANGELOG.md).

License: [MIT](./LICENSE), copyright 2026 kingsds, for the skill, manifests and
supporting documentation only. The icon, branding, trademarks, hosted platform
and business data are excluded; no trademark rights are granted.
