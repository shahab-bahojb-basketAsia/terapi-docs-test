---
title: Blackbaud
sidebarTitle: Blackbaud
---

API configuration: `blackbaud`

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

-   [How to register an Application](https://developer.blackbaud.com/skyapi/docs/applications/createapp)
-   [OAuth-related docs](https://developer.blackbaud.com/skyapi/docs/authorization)
-   [List of OAuth scopes](https://developer.blackbaud.com/skyapi/docs/authorization/auth-code-flow/confidential-application/tutorial)

Do you need help? Please check this link.

## API gotchas

-   For security purposes, access tokens will expire after 60 minutes. When this happens, you can use `terapi.getConnection()` to generate a new set of tokens.

Add Getting Started links and Gotchas by editing this page.

