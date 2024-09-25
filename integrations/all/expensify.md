---
title: Expensify
sidebarTitle: Expensify
---

API configuration: `expensify`

## Features

| Features | Status |
| - | - |
| [Auth (Basic)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

If you need additional features, we can add them within 48 hours—reach out to the community for assistance.

## Getting started

-   [Generate API credentials](https://www.expensify.com/tools/integrations)
-   [API documentation](https://integrations.expensify.com/Integration-Server/doc)
-   [Authentication details](https://integrations.expensify.com/Integration-Server/doc/#authentication)

Need help? Join the community to get assistance with setup.

## API gotchas

- Expensify uses `Basic` authentication. Set your `partnerUserID` as the Username and `partnerUserSecret` as the Password.
- After establishing a connection, use the Basic credentials like this:
```js
const connection = await terapi.getConnection();
let credentials = ;
if ('username' in connection.credentials && 'password' in connection.credentials) ;
} else );
}
const postData = 'requestJobDescription=' + encodeURIComponent(JSON.stringify(
}));

const resp = await terapi.post(,
    data: postData,
});
```

Add Connection configuration in Terapi by editing this page.
    
