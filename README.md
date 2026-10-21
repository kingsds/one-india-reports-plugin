# 1 India Reports

![1 India icon](./assets/icon.png)

Read approved 1 India retail sales, stock and target summaries through Claude,
using your own platform account. This small package contains a remote MCP
connection, a reporting skill and the brand icon. It contains no platform
server code, business records or shared credentials. MIT covers the reporting
skill, connector/plugin manifests and supporting documentation. The hosted
platform, business data, assets/icon.png and 1 India branding/trademarks are
excluded from that license grant. No trademark rights are granted.

## Account requirements

You need an existing 1 India admin or superadmin account that the connector
owner has explicitly approved. Phone verification, a platform role or plugin
installation alone does not grant AI access. Approved people must sign in,
verify MFA, select allowed stores and reports, and approve each client's
separate OAuth connection. Customer and staff accounts are not enabled in this
release. The server checks current permissions on every request.

## Connect in Claude

1. Open [AI access settings](https://1-india-loyalty-six.vercel.app/ai-connect)
   on the platform. Sign in, complete MFA and choose your reports and stores.
2. Install this plugin through Claude's supported plugin flow. Open its
   **Connectors** tab and connect **1 India Reports**. If adding the connector
   directly, use `https://1-india-loyalty-six.vercel.app/mcp`.
3. Choose OAuth and **Register automatically** when asked. Review the listed
   reports and locations before approving consent on the platform's own page.

Never paste a password, MFA code, token or service key into chat. On Claude
Team or Enterprise, an Owner also adds the remote connector for the
organization; each person connects with their own account.

The server supports hosted Claude callbacks and native Claude Code loopback
callbacks at `http://localhost:PORT/callback` and `http://127.0.0.1:PORT/callback`.
The full registered address stays bound to the connection, including its port.
Public directory review and publisher verification remain pending; this
repository does not establish an approved listing or authenticated client test.

## Reports and limits

The tools are `access_context`, `sales_summary`, `stock_summary` and
`targets_summary`. Reports are read-only and contain fixed aggregate fields.
Customer identities and contacts, costs, margins, vendor terms, raw exports,
financial changes, stock adjustments and account administration are excluded.
Only active retail locations appear; warehouse and head office are excluded.
Stock reports identify their source snapshot and freshness.

Admin limits are 20 calls per minute and 500 per day. Superadmin limits are
30 per minute and 1,000 per day. Both allow two concurrent calls, at most
100 rows and a 31-day inclusive report range. Daily reset uses Asia/Kolkata.
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

The client asks for dates or locations when needed. An access denial or missing
report is a boundary; the plugin must not substitute raw database access or
another person's account.

## Support and documentation

For setup or access help, contact the publisher at
[saurabh.singh@1018mb.com](mailto:saurabh.singh@1018mb.com). Include the problem
and client name, and leave passwords, MFA codes, tokens and business data out of
support messages. Review your permissions at
[AI access settings](https://1-india-loyalty-six.vercel.app/ai-connect).

Provider references: [Claude plugin installation](https://claude.com/docs/plugins/build),
[remote connector setup](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp),
and [directory review](https://claude.com/docs/directory/publish).

License: [MIT](./LICENSE), copyright 2026 kingsds, for the skill, manifests and
supporting documentation only. The icon, branding, trademarks, hosted platform
and business data are excluded. Publishing these instructions does not make
the private platform repository or its data public.
