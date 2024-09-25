---
title: Contentstack
sidebarTitle: Contentstack
---

API configuration: `contentstack`

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

If you need additional features, just ask, and we'll implement them within 48 hours!

## Getting started

-   [Register an Application](https://www.contentstack.com/docs/developers/developer-hub/contentstack-oauth/#configuring-contentstack-oauth)
-   [OAuth documentation](https://www.contentstack.com/docs/developers/developer-hub/contentstack-oauth)
-   [OAuth scopes overview](https://www.contentstack.com/docs/developers/developer-hub/oauth-scopes/)

Join our community if you need guidance on getting started.

## Connection configuration in terapi

Contentstack requires a region-specific subdomain based on where your user’s data is hosted. You'll also need your app’s UID, provided after registration.

Pass this information to terapi in the `terapi.auth()` call:

```js
terapi.auth('contentstack', '',
            
            });
```

Add Connection configuration in Terapi by editing this page.
    
