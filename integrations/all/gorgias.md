---
title: Gorgias
sidebarTitle: Gorgias
---

API configuration: [`gorgias`]()

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

-   [How to register an Application](https://developers.gorgias.com/docs/1-register-on-developer-portal)
-   [OAuth-related docs](https://developers.gorgias.com/docs/oauth2-authentication-for-creating-apps-with-gorgias)
-   [List of OAuth scopes](https://developers.gorgias.com/docs/oauth2-scopes)
-   [Web API docs (their REST API)](https://developers.gorgias.com/reference/introduction)

Need help getting started? Get help in the [community]().

## Connection configuration in Terapi

Gorgias requires a user-specific subdomain to run OAuth.

You should request this from the user and pass it to Terapi in the `terapi.auth()` call:

```js
terapi.auth('gorgias', '', });
```

Add Connection configuration in Terapi by [editing this page](/integrate/guides/connect-an-api).
    
