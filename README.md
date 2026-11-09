# 1 India Reports for Claude, ChatGPT and Codex

![1 India icon](./assets/icon.png)

Read approved 1 India retail sales, category stock, target trends and category sell-through through Claude,
using your own platform account. This small package contains a remote MCP
connection, a reporting skill and the brand icon. It contains no platform
server code, business records or shared credentials. MIT covers the reporting
skill, connector/plugin manifests and supporting documentation. The hosted
platform, business data, assets/icon.png and 1 India branding/trademarks are
excluded from that license grant. No trademark rights are granted.


## Download version 0.6.0

- [Claude plugin ZIP](https://github.com/kingsds/one-india-reports-plugin/releases/download/v0.6.0/one-india-claude-plugin.zip)
- [OpenAI plugin ZIP](https://github.com/kingsds/one-india-reports-plugin/releases/download/v0.6.0/one-india-openai-plugin.zip)

For Claude, open **Customize > Plugins**, select the upload option and choose
the Claude ZIP, then connect with your own 1 India account.

For ChatGPT, open **Plugins > + > Add custom MCP server**, enter
`https://1-india-loyalty-six.vercel.app/mcp`, choose OAuth and automatic
registration, then create **1 India Reports** as a plugin. Install it and
select it with `@` in a new chat. Availability depends on account and workspace
policy. The OpenAI ZIP is a portable plugin package for supported import and
local distribution surfaces; it is not a universal directory listing.

### Codex and Claude Code marketplace source

This repository includes a single-plugin marketplace for each client.

Codex:

```sh
codex plugin marketplace add kingsds/one-india-reports-plugin
codex plugin add one-india-platform@one-india
```

Claude Code:

```sh
claude plugin marketplace add kingsds/one-india-reports-plugin
claude plugin install one-india-platform@one-india
```

Review the MCP sign-in request and approve only your permitted reports and
stores. Installing a skill or marketplace does not establish an authenticated
connection. Use `access_context` as the first test.

References: [OpenAI packaging](https://developers.openai.com/plugins/build/plugins),
[ChatGPT connection](https://developers.openai.com/plugins/deploy/connect-chatgpt),
[Claude plugin installation](https://support.claude.com/en/articles/13837440-use-plugins-in-claude).

## Account requirements

You need an existing 1 India admin or superadmin account that the connector
owner has explicitly approved. Phone verification, a platform role or plugin
installation alone does not grant AI access. Approved people must sign in,
verify their registered email, select allowed stores and reports, and approve each client's
separate OAuth connection. Customer and staff accounts are not enabled in this
release. The server checks current permissions on every request.

## Connect in Claude

1. Open [AI access settings](https://1-india-loyalty-six.vercel.app/ai-connect)
   on the platform. Enter your approved account’s registered email, request the
   code and enter its eight digits there. Choose your reports and stores, enable
   read-only AI access and press **Save AI access**. An authenticator app is
   optional for personal reporting; existing verified MFA sessions also work.
2. Open **Customize > Plugins**, choose the upload option and select
   `one-india-claude-plugin.zip`. Open its
   **Connectors** tab and connect **1 India Reports**. If adding the connector
   directly, use `https://1-india-loyalty-six.vercel.app/mcp`.
3. Choose OAuth and **Register automatically** when asked. Review the listed
   reports and locations before approving consent on the platform's own page.

Never paste a password, email/MFA code, token or service key into chat. Owner
account approvals still require MFA. On Claude
Team or Enterprise, an Owner also adds the remote connector for the
organization; each person connects with their own account.

The server supports hosted Claude callbacks and native Claude Code loopback
callbacks at `http://localhost:PORT/callback` and `http://127.0.0.1:PORT/callback`.
The full registered address stays bound to the connection, including its port.
Public directory review and publisher verification remain pending; this
repository does not establish an approved listing or authenticated client test.

## Reports and limits

The report tools are `access_context`, `sales_summary`, `sales_trends`,
`stock_summary`, `stock_by_category`, `targets_summary`, `target_trends`,
`footfall_summary` and `category_sell_through`. Available tools depend on your
selected permissions. Reports contain fixed aggregate fields.
The separate `save_unanswered_question` action stores a short redacted summary
for the owner only after you confirm the exact text. It does not copy chat
history or grant extra report access. Saved summaries expire 90 days after last
submission.
Customer identities and contacts, margins, vendor terms, raw exports,
financial changes, stock adjustments and account administration are excluded.
Standard reports use active retail locations. Separately approved company stock and purchase reports include active warehouse/head office stock and require every active retail store approved.
Stock reports identify their source snapshot and freshness.

Admin limits are 20 calls per minute and 500 per day. Superadmin limits are
30 per minute and 1,000 per day. Both allow two concurrent calls, at most
100 rows and a 31-day inclusive standard report range; purchase receipt cohorts allow up to 366 days. Daily reset uses Asia/Kolkata.
The server's returned access context is authoritative. Do not split requests
to bypass limits.

Personal AI selections expire after 24 hours. Connections last at most one
hour and never outlive the original platform access token or account approval.
Changing selections invalidates existing grants, so reconnect afterward.

## Example prompts

- "Check my 1 India AI access and list the reports and locations I can read."
- "Summarize yesterday's sales, bill count and units for my approved stores."
- "Show the latest available stock summary for my approved stores, with the snapshot date and any missing locations."
- "Compare this month's sales against targets for my approved stores, and explain missing or stale data."
- "For one approved store, compare last week's sales against target, average bill value and category sell-through. Flag missing data."
- "If a report cannot answer my business question, show a redacted summary and ask before saving it for the owner."

The client asks for dates or locations when needed. An access denial or missing
report is a boundary; the plugin must not substitute raw database access or
another person's account.

## Support and documentation

For setup or access help, contact the publisher at
[saurabh.singh@1018mb.com](mailto:saurabh.singh@1018mb.com). Include the problem
and client name, and leave passwords, email/MFA codes, tokens and business data out of
support messages. Review your permissions at
[AI access settings](https://1-india-loyalty-six.vercel.app/ai-connect).

Provider references: [Claude plugin installation](https://claude.com/docs/plugins/build),
[remote connector setup](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp),
and [directory review](https://claude.com/docs/directory/publish).

License: [MIT](./LICENSE), copyright 2026 kingsds, for the skill, manifests and
supporting documentation only. The icon, branding, trademarks, hosted platform
and business data are excluded. Publishing these instructions does not make
the private platform repository or its data public.


## New in 0.3.0

Additional opt-in tools: `inventory_health` (units, costs and last-sale ageing),
`dispatch_readiness` (scan/invoice progress and order-rate/MRP values),
`merchandise_performance` (owned-stock receipt FIFO, Buying SOP and daily pace),
and `catalogue_styles` (existing full names and photos). Existing grants keep
their scope. Select the new reports on AI Connect, save, then reconnect and
review consent. Inventory and purchase reports include confidential cost values.

Ask Claude to clarify ambiguous receipt dates, category variants, brand/vendor
matches, location scope and the benchmark before calculating. Single-store
ageing uses only the selected approved store. Company stock/purchases require
all active retail stores approved. SOR receipts are excluded from owned-stock
FIFO and identified explicitly. Stock age since last sale differs from receipt
age. Scanned stock does not establish a truck booking, loading or departure.

Installing or updating the plugin does not remove coding or developer tools.
The reporting connection keeps its own approved scope and expiry.


## New in 0.6.0: monthly sales, categories, store P&L and loyalty

A new opt-in report, `business_performance`, with five views:

- `monthly_sales`: up to 24 months per store with the same days last year and like-for-like growth, so quarter, financial-year and versus-last-year questions take one call.
- `category_sales`: rupee sales, units and share by category group for up to 12 months.
- `top_styles`: best-selling styles at one store over up to 31 days, with approved catalogue photos.
- `store_pnl`: the Finance store P&L as booked (net sales, gross profit, gross margin, COGS, rent, store EBITDA). Manpower stays behind the salary approval.
- `loyalty_summary`: the company loyalty P&L.

Sales views read POS bills rolled up per store and day every three hours. They normally track Finance gross revenue closely (for example 100.02% for October 2025), but differ for March to August 2026; the report lists those differences in `dataNotes`. POS sales include GST; Finance net sales do not.

## New in 0.5.0: faster, clearer, safer answers

- Reports are marked read-only, so Claude and ChatGPT no longer ask for approval on every call.
- Errors explain how to recover (for example, an end date after today is now reported as an argument problem, not an outage).
- Omit `storeIds` to cover every store approved for the connection. Results name each store.
- `access_context` shows the latest loaded bill and stock dates, so today's partial numbers are flagged.
- Stock ageing uses actual last-sale dates per store (refreshed nightly). Category rows carry readable names.
- Purchase-cohort sell-through now includes sales from stores that have since closed.
- Targets keep stores with some missing target days (achievement withheld, `target_days` shown).
- Wide result pages are shortened to fit, with `nextOffset`, instead of failing.
- Individual pay is returned one employee at a time, and salary over AI needs an authenticator-app sign-in.
- Owners can keep AI access for 1, 7 or 30 days.

## New in 0.4.0: monthly salary and rent

`salaries_monthly` reads monthly location totals or scoped individual payroll
for people on the platform's named salary-access list. A generic admin or
superadmin role does not grant salary access. The live salary-list grant,
selected MCP report, approved store scope and client consent are all required.
`rent_monthly` reads monthly Finance booked rent. Choose these reports on AI
Connect, save and reconnect; existing grants do not expand automatically.

Clarify payroll versus Finance Manpower Cost, gross earned/net take-home/fixed
monthly pay, calendar month range and location scope. Reimbursements stay
separate. Missing months remain null; a partial company result has an available
subtotal rather than a fabricated complete total. Booked rent does not prove
payment or contractual rent. Company scope is the current active retail cohort
plus HO and warehouse, and needs all active retail stores approved.
Individual salary results may include employee names/codes and pay, but no bank,
tax identifiers, contact fields or raw detail maps. No business edits or exports.
