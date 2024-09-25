---
title: Harvest
sidebarTitle: Harvest
---

API configuration: [`harvest`]()

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the [community]().

## Getting started

-   [OAuth-related docs](https://help.getharvest.com/api-v2/authentication-api/authentication/authentication/#oauth2-application)
-   [Register an Application](https://id.getharvest.com/sessions/new?go_back=%2Fdevelopers)
-   [Scopes](https://help.getharvest.com/api-v2/authentication-api/authentication/authentication/#scopes-and-account-access)
-   [Harvest REST API docs](https://help.getharvest.com/api-v2)

Need help getting started? Get help in the [community]().

## API gotchas

- When creating a connection, you need to add the `appDetails` configuration parameter in the format `MyApp (yourname@example.com)`, which will be appended to the request as a header: `User-Agent: MyApp (yourname@example.com)`. This information will be used to get in touch if you’re doing something wrong (so the provider can warn you before you’re blocked) or something awesome (so the provider can congratulate you). Requests without a valid `User-Agent` header are rejected.
- Harvest enforces different rate limits for different endpoints. For more details check [harvest rate limits](https://help.getharvest.com/api-v2/introduction/overview/general/#rate-limiting)

Add Getting Started links and Gotchas by [editing this page]().

