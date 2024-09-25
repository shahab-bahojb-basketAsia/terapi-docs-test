---
title: Fiserv
sidebarTitle: Fiserv
---

API configurations: [`fiserv`](https://terapi.dev/providers.yaml), [`fiserv-api-key`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (OAuth + API Key)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the [community](https://terapi.dev/slack).

## Getting started

-   [How to generate OAuth Client Credentials](https://developer.fiserv.com/product/BankingHub/docs/?path=docs/getting-started/before-you-start.md#creating-a-banking-hub-workspace)
-   [OAuth related docs](https://developer.fiserv.com/product/BankingHub/docs/?path=docs/getting-started/before-you-start.md#generating-access-token)
-   [Fiserv OAuth docs](https://developer.fiserv.com)
-   [How to generate a Fiserv APIKey](https://docs.fiserv.dev/public/docs/general-getting-started#steps-to-api-success)
-   [Fiserv APIKey docs](https://docs.fiserv.dev/public/reference)

Need help getting started? Get help in the [community](https://terapi.dev/slack).

## API gotchas

- Fiserv supports different authentication methods for different products.
- When creating a new Fiserv connection in terapi, please provide your `API key` as your client ID and `API secret` as your client secret.
- To obtain the Fiserv `hostUrl`, navigate to the API key section of your workspace. If your `hostUrl` from Fiserv is `https://card-sandbox.api.fiservapps.com`, add your `hostUrl` in terapi as `card-sandbox.api.fiservapps.com`. For more details check the [request URL](https://developer.fiserv.com/product/BankingHub/docs/?path=docs/get-started.md&branch=main#request-url).

Add Getting Started links and Gotchas by [editing this page](https://github.com/terapihq/terapi/tree/master/docs-v2/integrations/all/fiserv.mdx)

