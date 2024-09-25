---
title: CodeClimate
sidebarTitle: CodeClimate
---

API configuration: `CodeClimate`

## Features

| Features | Status |
| - | - |
| [Auth (Basic)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

If you're looking for more features, let us know and we'll add them within 48 hours!

## Getting started

-   [How to generate a CodeClimate token](https://codeclimate.com/profile/tokens)
-   [Learn about CodeClimate Authentication](https://developer.codeclimate.com/#authentication)
-   [Check out the CodeClimate API documentation](https://developer.codeclimate.com/#overview)

If you have any questions, our community is ready to assist you.

## API gotchas

- To authenticate with CodeClimate, use `API_KEY` mode, including `Authorization: Token token=token` in the request headers.
- When setting up a new connection in terapi, make sure to specify the appropriate domain. For cloud-based setups, use `api.codeclimate.com`, and for on-premise setups, replace it with your host's domain.
- CodeClimate applies a rate limit of 5,000 requests per token per hour.

Add Getting Started links and Gotchas by editing this page.

