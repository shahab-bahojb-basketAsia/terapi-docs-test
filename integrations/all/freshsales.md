---
title: Freshsales  
sidebarTitle: Freshsales  
---

API configuration: [`freshsales`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (API Key)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the [community](#).

## Getting started

-   [Generate an API key in your Freshsales account](https://support.freshsales.io/en/support/solutions/articles/220099-how-to-find-my-api-key)
-   [Freshsales API docs](https://developer.freshsales.io/api)
-   [Freshsales Authentication](https://developer.freshsales.io/api/#authentication)

Need help getting started? Get help in the [community](#).

## API gotchas

- Freshsales uses API_KEY auth mode with `Authorization: Token token= API_KEY` as a request header.
- When creating a connection, you need to add the subdomain as a connection configuration parameter, for example: `terapi.auth('freshsales', 'test-connection-id', })`.
- Freshsales enforces rate limit on the account level. For more details check [freshsales rate limit](https://support.freshsales.io/en/support/solutions/articles/223406-does-freshsales-have-api-request-limits-for-an-account-)

Add Getting Started links and Gotchas by [editing this page](#).

