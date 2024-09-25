---
title: Brex
sidebarTitle: Brex
---

API configurations: `brex`, `brex-staging`, `brex-api-key`

## Features

| Features | Status |
| - | - |
| [Auth (OAuth + Basic)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the community.

## Getting started
Brex offers both Basic auth `API key` and OAuth as authentication, and Terapi implements both. To register an OAuth app, you will need to register as a Brex developer partner. If you are a Brex client—i.e., you have your own Brex account—you can use Basic auth `API key`.

-   [Register as Partner](https://www.brex.com/partners)
-   [Brex API docs](https://developer.brex.com/)
-   [Brex Developers Slack Community (official)](https://join.slack.com/t/brexdev/shared_invite/zt-vgwh6rja-CjydrUA4uJSB90ZO~gnI8Q)
-   [List of OAuth scopes](https://developer.brex.com/docs/roles_permissions_scopes/#scopes)
-   [Web API docs (their REST API)](https://developer.brex.com/openapi/onboarding_api/)
-   [Generate an API key](https://dashboard.brex.com/settings/developer)
-   [Basic Auth-related docs](https://developer.brex.com/docs/authentication/#2-pass-the-user-token-in-your-api-call-headers)

Do you need help? Please check this link.

## API gotchas

-   Include the scope `offline_access` to get a refresh token (access tokens expire after 1h).
-   Refresh tokens expire after 90 days of non-use. Ensure you regularly make an API request as long as you need the connection.
-   Brex offers a staging system to test your apps; you will get access when you register as a partner. Staging details are [here](https://developer.brex.com/docs/partner_authentication/#api-servers)

Add Getting Started links and Gotchas by editing this page.
