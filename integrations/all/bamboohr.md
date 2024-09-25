---
title: BambooHR
sidebarTitle: BambooHR
---

API configuration: `bamboohr`, `bamboohr-basic`

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

-   [Web API docs (their REST API)](https://documentation.bamboohr.com/docs/getting-started)
-   [How to register/integrate an Application](https://documentation.bamboohr.com/docs#what-will-you-need-to-get-started)
-   [OAuth-related docs](https://documentation.bamboohr.com/page/single-sign-on-sso-with-openid-connect)
-   [Web API docs (their REST API)](https://documentation.bamboohr.com/reference/get-employee)

Do you need help? Please check this link.

## Connection configuration in Terapi

BambooHR requires a user-specific subdomain to authenticate.

You should request this from the user and pass it to Terapi in the `terapi.auth()` call:

```js
// oAuth
terapi.auth('bamboohr', '', });
// API key
terapi.auth('bamboohr-basic', '', ,
        params: 
    })
```

Add Connection configuration in Terapi by editing this page.
    
