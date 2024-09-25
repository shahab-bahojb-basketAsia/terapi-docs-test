---
title: E-conomic
sidebarTitle: E-conomic
---

API configuration: `e-conomic`

## Features

| Features | Status |
| - | - |
| [Auth (Basic)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the community.

## Getting started

-   [How to generate API credentials](https://www.e-conomic.com/developer/connect)
-   [API docs](https://www.e-conomic.com/developer/documentation)
-   [Auth-related docs](https://apis.e-conomic.com/#Accounts..section/Authentication)

Need help getting started? Get help in the community.

## API gotchas
- E-conomic in this setup uses `Basic` auth mode for different API endpoints. Provide `YOUR_PRIVATE_TOKEN` as the Username and `YOUR_AGREEMENT_GRANT_TOKEN` as the Password.
- After establishing a connection, use the Basic credentials as follows:
```js
const connection = await terapi.getConnection();
let headers:  = ;
if ('username' in connection.credentials && 'password' in connection.credentials) ;
} else );
}

const resp = await terapi.get();
```

Add Getting Started links and Gotchas by editing this page.
    
