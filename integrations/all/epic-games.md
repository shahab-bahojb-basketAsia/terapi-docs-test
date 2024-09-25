---
title: Epic Games
sidebarTitle: Epic Games
---

API configuration: `epic-games`

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

Need specific features? We can build missing functionality in less than 48 hours. Reach out to us in the community!

## Getting started

-   [Register your Application](https://dev.epicgames.com/portal) on the Epic Games Dev Portal.
-   Terapi supports the [Epic Games OAuth Web APIs](https://dev.epicgames.com/docs/web-api-ref/authentication), specifically the `authorization code` flow.

Struggling to get started? Our community is here to help!

## API gotchas

-   Epic Games does not provide a publicly available list of OAuth scopes, but you can access them while setting up your app in the developer portal.
-   The refresh tokens expire quickly, typically within a few hours. It’s essential to make API requests regularly to keep access active.
-   When you receive the access token, Epic Games includes additional details (like user data). You can use Terapi's `getRawTokenResponse` method to retrieve this information. For more advanced info, inspect the access token to access [extra data](https://dev.epicgames.com/docs/web-api-ref/authentication#account-information).

Add Getting Started links and Gotchas by [editing this page](https://github.com/terapihq/terapi/tree/master/docs-v2/integrations/all/epic-games.mdx)

