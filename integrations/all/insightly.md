---
title: Insightly
sidebarTitle: Insightly
---

API configuration: [`insightly`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (Basic)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the [community](https://terapi.dev/slack).

## Getting started

-   [Insightly basic auth related docs](https://api.na1.insightly.com/v3.1/#!/Overview/Introduction)
-   [Insightly API docs](https://api.na1.insightly.com/v3.1)
-   [API Versions](https://api.na1.insightly.com/v3.1/#!/Overview/Introduction)
-   [API rate limits](https://api.na1.insightly.com/v3.1/#!/Overview/Technical_Details)

Need help getting started? Get help in the [community](https://terapi.dev/slack).

## API gotchas

- Insightly uses `Basic` auth mode to access different endpoints. Provide your `api key` as your username and leave the password field empty.
- Your instances `pod` can be determined by accessing `User Settings` and finding the API URL right under your API Key in the API Section. This connection config will be set when creating a new connection on Terapi, i.e., if this is your API URL: `https://api.na1.insightly.com/v3.1/`, add `na1` as your pod connection config.
- Insightly still supports older API versions, but they have fewer endpoints. To use a specific version of the API, append it to your `base_url` as follows: `/v3.1/Contacts` or `/v3.0/Contacts`.
- Depending on the pricing plan, there are various rate limits. Once your limit is reached, you will no longer be able to make requests against that endpoint until the next day.
- You can have a look at the following resource to see how best you can handle rate limits.

Add Getting Started links and Gotchas by [editing this page]()
