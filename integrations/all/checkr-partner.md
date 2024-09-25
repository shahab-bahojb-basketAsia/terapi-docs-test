---
title: Checkr Partner
sidebarTitle: Checkr Partner
---

API configurations: `checkr-partner`, `checkr-partner-staging`

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | ✅  |

We can implement missing features in &lt;48h, just ask for it in the community.

## Getting started

-   [How to register a partner Application](https://docs.checkr.com/partners/#section/Getting-Started/Create-a-Partner-Application-for-your-Checkr-account)
-   [OAuth related docs](https://docs.checkr.com/partners/#section/Getting-Started/Connect-your-customers-to-Checkr)
-   [Checkr API docs](https://docs.checkr.com/)
-   [Checkr rate limiting](https://docs.checkr.com/#section/Reference/Rate-limiting)

Need assistance getting started? Visit our community for help.

## API gotchas

-  Partners are provided with both staging and production accounts for testing and live environments. For more information, refer to [staging vs production accounts](https://docs.checkr.com/partners/#section/Getting-Started/Staging-vs-Production-accounts).
-  The `access_token` issued is long-lived and remains valid until revoked, so there is no need for frequent refreshes.
-  Checkr requires partners to undergo an integration review to ensure the connection is ready for production. See more details about the [production approval process](https://docs.checkr.com/partners/#section/Production-Approval-Process).
-  After establishing a connection, Checkr mandates that you send the `access_token` using Basic Authentication like this:

```js
        const connection = await terapi.getConnection();
        let access_token: string;
        if ('access_token' in connection.credentials)  else );
        }
        const config = 
        }

        const response = await terapi.get(config);
```

Add Connection configuration in Terapi by [editing this page](/integrate/guides/connect-an-api).
    
