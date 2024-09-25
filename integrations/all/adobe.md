---
title: Adobe
sidebarTitle: Adobe
---

API configuration: `adobe`

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

-   [How to register an Application](https://developer.adobe.com/developer-console/docs/guides/getting-started)
-   [OAuth-related docs](https://developer.adobe.com/developer-console/docs/guides/authentication/OAuth)
-   [Adding an Adobe service](https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/)
-   [List of OAuth scopes](https://developer.adobe.com/developer-console/docs/guides/authentication/OAuth/Scopes/)

Do you need help? Please check this link.

## API gotchas

-   If the service you are trying to integrate allows `offline_access`, then you will be able to get a refresh token by adding this in the scopes.
-   Depending on the selected API, some platforms may not be compatible with that API. Choose the platform that aligns best with your application's needs if multiple platforms are available.
-   When setting up an API, ensure you select a web app as the application type. (Not all apps support OAuth 2.0.)
-   To refresh the token, simply use `terapi.getConnection()` to generate a new set of tokens.

Add Getting Started links and Gotchas by editing this page.

