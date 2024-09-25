---
title: Confluence
sidebarTitle: Confluence
---

API configuration: `confluence`

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

Need a specific feature? We can build it in less than 48 hours, just reach out to the community!

## Getting started

-   [How to register an App](https://developer.atlassian.com/cloud/confluence/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-)
-   [OAuth documentation](https://developer.atlassian.com/cloud/confluence/oauth-2-3lo-apps)
-   [Full list of OAuth scopes](https://developer.atlassian.com/cloud/jira/platform/scopes-for-oauth-2-3LO-and-forge-apps/#classic-scopes)

Need help? Connect with our community to get the support you need.

## API gotchas

- To enable token refreshing, make sure to include the `offline_access` scope when setting up the integration in Terapi.
- OAuth 2.0 (3LO) apps are private by default. If you plan to make your app public, follow the steps outlined [here](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps/#distributing-your-oauth-2-0--3lo--apps).
- Refresh tokens will expire after a year if unused, and after 90 days if the resource owner is inactive. Call `terapi.getConnection()` within this period to avoid expiration. For more details, check out the [token renewal guide](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps/#how-do-i-get-a-new-access-token--if-my-access-token-expires-or-is-revoked-).

Add Getting Started links and Gotchas by editing this page.

