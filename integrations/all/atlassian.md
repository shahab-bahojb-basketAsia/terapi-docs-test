---
title: Atlassian
sidebarTitle: Atlassian
---

API configuration: `atlassian`

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

Missing features can be implemented within 48 hours; contact the community.

## Getting started

-   [Registering an App](https://developer.atlassian.com/cloud/confluence/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-)
-   [OAuth-related docs](https://developer.atlassian.com/cloud/confluence/oauth-2-3lo-apps)
-   [List of OAuth scopes](https://developer.atlassian.com/cloud/jira/platform/scopes-for-oauth-2-3LO-and-forge-apps/#classic-scopes)
-   [Confluence Cloud Rest API](https://developer.atlassian.com/cloud/confluence/rest/v1/intro/#using)

Looking for assistance? Join the community.

## API gotchas

- **To allow the possibility of refreshing the token**, you must add `offline_access` to your scopes when creating the integration on the Terapi UI.
- When you create an OAuth 2.0 (3LO) app, it's private by default. Before using the integration, you must make your app public. If you want to make your app public, find the how-to [here](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps/#distributing-your-oauth-2-0--3lo--apps)
- Refresh tokens will expire after 365 days of non-use and will expire by 90 days if the resource owner is inactive for 90 days. Make sure you call `terapi.getConnection()` at least every 365 days to trigger a refresh. See reference [here](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps/#how-do-i-get-a-new-access-token--if-my-access-token-expires-or-is-revoked-).

Add Getting Started links and Gotchas by editing this page.

