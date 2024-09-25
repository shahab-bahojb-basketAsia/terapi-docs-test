---
title: Fitbit
sidebarTitle: Fitbit
---

API configuration: [`fitbit`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (OAuth](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the [community](https://terapi.dev/slack).

## Getting started

-   [Web/REST API docs](https://dev.fitbit.com/build/reference/web-api/)
-   [The full list of OAuth scopes](https://dev.fitbit.com/build/reference/web-api/developer-guide/application-design/#Scopes)
-   [Web API docs (their REST API)](https://dev.fitbit.com/build/reference/)

Need help getting started? Get help in the [community](https://terapi.dev/slack).

## API gotchas

-   There does not seem to be any approval process, and you can immediately use your app.
-   During the authorization flow, users need to manually select which scopes they grant to your application (from the ones you requested). They can complete the flow without granting all the requested scopes. The raw token response (which you can get from the Terapi backend SDK) contains the `scope` key that lists the granted scopes.

Add Getting Started links and Gotchas by [editing this page](https://github.com/terapi/terapi/tree/master/docs-v2/integrations/all/fitbit.mdx)

