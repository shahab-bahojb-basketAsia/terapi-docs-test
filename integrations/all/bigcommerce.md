---
title: BigCommerce
sidebarTitle: BigCommerce
---

API configuration: `bigcommerce`

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

-   [How to register an Application](https://developers.tremendous.com/docs/oauth-20#step-1-register-a-developer-app)
-   [OAuth-related docs](https://developer.bigcommerce.com/docs/integrations/apps/guide/auth)
-   [List of OAuth scopes](https://developer.bigcommerce.com/docs/start/authentication/api-accounts#oauth-scopes)
-   [API rate limiting](https://developer.bigcommerce.com/docs/start/best-practices/api-rate-limits)

Do you need help? Please check this link.

## API gotchas

- BigCommerce offers various apps with different levels of visibility. For more details, see [BigCommerce types of Apps](https://developer.bigcommerce.com/docs/integrations/apps/guide/types)
- After creating a new connection on Terapi, you will need to modify your HTTP request headers to use the `X-Auth-Token` header to pass the API account's `access_token` instead of the Authorization header as described [here](https://developer.bigcommerce.com/docs/start/authentication/api-accounts#how-to-migrate). Please look at the following example:

```js
const connection = await terapi.getConnection();

if (!connection.credentials || typeof connection.credentials !== 'object') );
}

let access_token: string;
if ('access_token' in connection.credentials)  else );
}

const config = 
};

const response = await terapi.get(config);
```

