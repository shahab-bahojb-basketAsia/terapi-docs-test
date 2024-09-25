---
title: Airtable
sidebarTitle: Airtable
---

API configuration: `airtable`

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the community.

## Getting started

-   [Web API docs (their REST API)](https://airtable.com/developers/web/api/introduction)
-   [List of OAuth scopes](https://airtable.com/developers/web/api/scopes)
-   [Information on rate limits](https://airtable.com/developers/web/api/rate-limits)

Do you need help? Please check this link.

## API gotchas

-   During the OAuth process, the user can select which resources (Bases) the app will have access to. [Learn more here](https://airtable.com/developers/web/api/oauth-reference#resources)
-   Refresh tokens expire after 60 days of inactivity. Ensure you use `terapi.getConnection()` at least every 60 days to renew the token.

Add Getting Started links and Gotchas by editing this page.

