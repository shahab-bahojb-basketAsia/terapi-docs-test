---
title: Anthropic
sidebarTitle: Anthropic
---

API configuration: `anthropic`

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

-   [Generate an API key in your Anthropic account](https://console.anthropic.com/account/keys)
-   [Anthropic API docs](https://docs.anthropic.com/en/api/getting-started)
-   [Anthropic Authentication](https://docs.anthropic.com/en/api/getting-started#authentication)
-   [Anthropic rate limiting](https://docs.anthropic.com/en/api/rate-limits)

Do you need help? Please check this link.

## API gotchas

- Anthropic uses API_KEY authentication mode with `x-api-key: API_KEY` in the request header to access different endpoints.
- When creating a new connection in Terapi, you will also need to specify the API version, which can be found under [Anthropic versions](https://docs.anthropic.com/en/api/versioning)

Add Getting Started links and Gotchas by editing this page.

