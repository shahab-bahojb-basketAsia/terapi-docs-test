---
title: Affinity
sidebarTitle: Affinity
---

API configuration: `Affinity`

## Features

| Features | Status |
| - | - |
| [Auth (API Key)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the community.

## Getting started

-   [Generate an API secret key in your Affinity account](https://api-docs.affinity.co/#getting-started)
-   [API docs](https://api-docs.affinity.co/#introduction)
-   [Auth-related docs](https://api-docs.affinity.co/#authentication)

Do you need help? Please check this link.

## API gotchas
- Affinity provides an `API Key` but uses Basic auth for the API. Use the `API Key` as the password when setting up Terapi, and leave the username field empty.
- The Affinity API is available only to Premium and Enterprise tier customers, and to Professional tier customers who signed up before July 5, 2023.
- Affinity currently supports _one key per user_ in your team.
- There's a limit of _three webhook subscriptions per Affinity instance_.
- For rate limit information, see the [Affinity documentation](https://api-docs.affinity.co/#rate-limits).

Add Getting Started links and Gotchas by editing this page.

