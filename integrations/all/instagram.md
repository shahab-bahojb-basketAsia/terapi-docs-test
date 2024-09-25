---
title: Instagram
sidebarTitle: Instagram
---

API configuration: [`instagram`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the [community](https://terapi.dev/slack).

## Getting started

-   Apps for the Instagram API can be [registered here](https://developers.facebook.com/apps)
-   [Instagram Basic Display API docs](https://developers.facebook.com/docs/instagram-basic-display-api)
-   [Instagram Basic Display API OAuth scopes](https://developers.facebook.com/docs/instagram-basic-display-api/overview/permissions) -> These scopes did not work for me. What worked was `user_profile` and `user_media`.
-   [Instagram Graph API docs](https://developers.facebook.com/docs/instagram-api) (see below for how to add OAuth)

Need help getting started? Get help in the [community](https://terapi.dev/slack).

## API gotchas

-   For the Basic Display API, the scope `user_profile` is mandatory. The only other available scope seems to be `user_media`.
-   For access to the [Instagram Graph API](https://developers.facebook.com/docs/instagram-api), follow these steps:
    1. The Instagram Graph API uses [Facebook OAuth](/integrations/all/facebook) to authenticate the accounts. Add a provider config for it to Terapi with the scopes [specified here](https://developers.facebook.com/docs/instagram-api/getting-started#2--implement-facebook-login).
    2. Once the login flow completes, you can [query the Facebook API for the Instagram account details](https://developers.facebook.com/docs/instagram-api/getting-started#4--get-the-user-s-pages) (follow steps 4-6).

Add Getting Started links and Gotchas by [editing this page]()

