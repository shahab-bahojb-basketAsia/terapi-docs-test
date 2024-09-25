---
title: Jira
sidebarTitle: Jira
---

API configuration: [`jira`](https://terapi.dev/providers.yaml), [`jira-basic`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (OAuth + Basic)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the [community](https://terapi.dev/slack).

## Getting started

-   [Registering an App](https://developer.atlassian.com/cloud/confluence/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-)
-   [OAuth-related docs](https://developer.atlassian.com/cloud/confluence/oauth-2-3lo-apps)
-   [List of OAuth scopes](https://developer.atlassian.com/cloud/jira/platform/scopes-for-oauth-2-3LO-and-forge-apps/#classic-scopes)
-   [API v3 docs](https://developer.atlassian.com/cloud/jira/platform/rest/v3/intro/#about)
-   [OAuth app list (developer console)](https://developer.atlassian.com/console/myapps/)
-   [API rate limits](https://developer.atlassian.com/cloud/jira/platform/rate-limiting/)
-   [Basic Auth-related docs](https://developer.atlassian.com/cloud/jira/platform/basic-auth-for-rest-apis/)

Need help getting started? Get help in the [community](https://terapi.dev/slack).

## API gotchas

-   Refreshing tokens require the `offline_access` scope when creating the integration on the UI.
-   You will need to fetch your Cloud ID to be able to make API requests to the Jira API v3. You can do this with the proxy by calling:

```ts
const response = await terapi.get();
const cloudId = response.data[0].id;
```

Add Getting Started links and Gotchas by [editing this page](/integrate/guides/connect-an-api).
            
