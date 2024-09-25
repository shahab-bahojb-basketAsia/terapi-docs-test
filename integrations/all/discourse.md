---
title: Discourse
sidebarTitle: Discourse
---

API configuration: `discourse`

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

-   [Discourse API docs](https://docs.discourse.org)

Need help getting started? Get help in the community.

## API gotchas

- Discourse uses API_KEY authentication mode with `Api-Key: apiKey` and `Api-Username: API Username` in the request header to access different endpoints. Both keys can be obtained from the admin panel.
- Since the platform automatically sets the `Accept: application/json` header, there is no need to include the `.json` suffix in API endpoint URLs. For example, instead of sending a request to `/categories.json`, you can send it to `/categories`, and the JSON response will still be returned.

Add Getting Started links and Gotchas by editing this page.

