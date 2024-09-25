---
title: Freshdesk  
sidebarTitle: Freshdesk  
---

API configuration: [`freshdesk`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (API Key)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can add the missing features within 48 hours; feel free to reach out in the [community](#).

## Getting started

-   [Where can I find my API key?](https://support.freshdesk.com/en/support/solutions/articles/215517-how-to-find-your-api-key)
-   [Freshservice API Docs](https://developers.freshdesk.com/api/#introduction)

Need assistance getting started? Visit the [community](#).

## API gotchas

- Freshdesk requires a user-specific subdomain for API requests.
- You should request this from the user and pass it to Terapi in the `terapi.auth()` call:
  ```js
  terapi.auth('freshdesk', '', ,
      credentials: });
```
    
