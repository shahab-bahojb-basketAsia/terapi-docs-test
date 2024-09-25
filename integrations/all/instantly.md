---
title: Instantly
sidebarTitle: Instantly
---

API configuration: [`instantly`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (API Key)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the [community](https://terapi.dev/slack).

## Getting started

-   [Generate an API key](https://app.instantly.ai/app/settings/integrations)
-   [API docs](https://app.theneo.io/instantly-ai/instantlyapidocs/introduction)

Need help getting started? Get help in the [community](https://terapi.dev/slack).

## API gotchas

- You need to be on the Hypergrowth plan (or above) to be able to access the API key.
- Instantly uses the `API_KEY` authentication mode to access different endpoints. The `api_key` is used differently depending on the endpoint. For GET, PATCH, and DELETE requests, it is appended to the query parameters, while for some POST requests, it is included in the request body. To clarify this, please check the corresponding Instantly docs pages.
- After creating a connection, you can use the `api_key` as follows:
    ```js
    const connection = await terapi.getConnection();

    let api_key: string;
    if ('apiKey' in connection.credentials)  else );
    }

    const postData = ;

    const resp = await terapi.post();
    ```
- You can have a look at the following simple [action template](/integrations/integration-templates/instantly) based on the [Instantly Set campaign name action](https://app.theneo.io/instantly-ai/instantlyapidocs/campaign-1/set-campaign-name).
- Instantly enforces a general rate limit of 10 requests per second. For more details, check [Instantly rate limits](https://app.theneo.io/instantly-ai/instantlyapidocs/introduction/rate-limits).

Add Getting Started links and Gotchas by [editing this page]()

