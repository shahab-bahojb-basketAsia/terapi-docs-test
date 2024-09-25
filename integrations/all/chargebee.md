---
title: Chargebee
sidebarTitle: Chargebee
---

API configuration: `chargebee`

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

Chargebee provides REST APIs and webhooks to interact with their data. Currently, only the REST APIs are supported.
[API docs](https://apidocs.chargebee.com/docs/api/)

## Connection configuration in Terapi

Chargebee requires a user-specific subdomain for the API base URL.

You should request this from the user and pass it to Terapi in the `terapi.auth()` call:

```js
terapi.auth('chargebee', '', });
```

Add Connection configuration in Terapi by [editing this page](/integrate/guides/connect-an-api).

