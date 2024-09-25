---
title: Help Scout
sidebarTitle: Help Scout
---

API configuration: [`helpscout-docs`](https://terapi.dev/providers.yaml), [`helpscout-mailbox`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (OAuth + API Key)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

Missing functionalities can be implemented within 48 hours; contact the [community](https://terapi.dev/slack).

## Getting started

Each user has a Help Scout Docs API key, which is used to authenticate the Docs API. For the Mailbox API, OAuth2 authentication is required.

-   [Help Scout Docs API](https://developer.helpscout.com/docs-api/)
-   [Help Scout Mailbox create an OAuth2 application](https://developer.helpscout.com/mailbox-api/overview/authentication/#oauth2-application)
-   [Help Scout Mailbox OAuth-related docs](https://developer.helpscout.com/mailbox-api/overview/authentication/)

Need assistance getting started? Visit the [community](https://terapi.dev/slack).

## API gotchas

- For Help Scout Docs Basic Auth, you will need to pass your `API key` as the username and a dummy password like `X` as the password. Each API key is associated with a Help Scout user.
- For Help Scout Mailbox, access tokens expire every 172800 seconds (2 days). Use `terapi.getConnection()` to generate a new set of tokens.
- Both `helpscout-docs` and `helpscout-mailbox` enforce different rate limits based on your current plan. For more details, check the rate limiting guidelines for [HelpScout Docs](https://developer.helpscout.com/docs-api/#rate-limiting) and [HelpScout Mailbox](https://developer.helpscout.com/mailbox-api/overview/rate-limiting/).

Add Getting Started links and Gotchas by [editing this page]()

