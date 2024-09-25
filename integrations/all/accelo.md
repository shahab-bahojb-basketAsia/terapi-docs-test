---
title: Accelo
sidebarTitle: Accelo
---

API configuration: `terapi`

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

-   [How to register an Application](https://api.accelo.com/docs/#registering-your-application)
-   [OAuth-related docs](https://api.accelo.com/docs/#authentication)
-   [List of OAuth scopes](https://api.accelo.com/docs/#scope)

Do you need help? Please check this link.

## Connection configuration in Terapi

Accelo [requires a user specific subdomain](https://api.accelo.com/docs/#oauth2-0-uri) to run OAuth.

You should request this from the user and pass it to Terapi in the `terapi.auth()` call:

```js
terapi.auth('accelo', '', });

