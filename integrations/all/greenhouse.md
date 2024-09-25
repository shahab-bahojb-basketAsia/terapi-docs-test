---
title: Greenhouse
sidebarTitle: Greenhouse
---

API configuration: [`greenhouse`](), [`greenhouse-basic`]()

## Features

| Features | Status |
| - | - |
| [Auth (OAuth + Basic)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the [community]().

## Getting started
Greenhouse offers both `Basic` and `OAuth` as authentication and Terapi implements both.

-   [How to register an Application](https://developers.greenhouse.io/candidate-ingestion.html#authentication)
-   [OAuth-related docs](https://developers.greenhouse.io/candidate-ingestion.html#introduction)
-   [List of OAuth scopes](https://developers.greenhouse.io/candidate-ingestion.html#oauth-scopes)
-   [API](https://developers.greenhouse.io)
-   [Harvest API authentication](https://developers.greenhouse.io/harvest.html#authentication)

Need help getting started? Get help in the [community]().

## API gotchas

- For `Basic` auth, pass the Greenhouse API token as the username, and leave the password blank.
- If you need to use the proxy, it is important to provide the resource that you will be calling in the config (as Greenhouse has many forms for API resources). Please see [here](https://developers.greenhouse.io/) for different types of resources. Once confirmed, you have to add `resource` as a config.

Add Getting Started links and Gotchas by [editing this page]().

