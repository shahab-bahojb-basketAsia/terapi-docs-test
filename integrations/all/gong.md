---
title: Gong  
sidebarTitle: Gong  
---

API configuration: [`gong`](https://terapi.dev/providers.yaml), [`gong-oauth`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (OAuth + Basic)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the [community](#).

## Getting started

Gong offers both Basic auth (API key) and OAuth as authentication. terapi implements both. To register an OAuth app, you need to request a developer account. At first, the OAuth app will be private (only for test) and you need an additional approval to make it public.

-   [How to find API credentials (for end-users)](https://help.gong.io/hc/en-us/articles/360042449451-Receive-access-to-the-API)
-   [Request a developer account to create an OAuth app](https://app.gong.io/welcome/developer/sign-up)
-   [API Docs](https://app.gong.io/settings/api/documentation#overview)
-   [Oauth-related docs](https://help.gong.io/hc/en-us/articles/13944551222157-Create-an-app-for-Gong)

Need help getting started? Get help in the [community](#).

## API gotchas

- End users can generate API keys [on the Gong API page](https://app.gong.io/company/api). They must have the "technical administrator" user role to do this.
- Gong uses BASIC auth for their API, but doesn't call them username and password: `Access Key` is the username in terapi and `Access Key Secret` is the password in terapi.
- [Gong rate-limits](https://app.gong.io/settings/api/documentation#overview) are per second and a total of 10k requests a day.
- Gong-oauth uses `api_base_url_for_customer`, which varies for each customer, as its `base_url` for proxy requests. This parameter is returned in the response of `generate-customer-token`.

Add Getting Started links and Gotchas by [editing this page](#).

