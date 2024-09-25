---
title: Jira Data Center
sidebarTitle: Jira Data Center
---

API configuration: [`jira-data-center`](https://terapi.dev/providers.yaml)

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

-   [How to create an incoming Application Link](https://confluence.atlassian.com/adminjiraserver/configure-an-incoming-link-1115659067.html)
-   [OAuth related docs](https://confluence.atlassian.com/adminjiraserver/jira-oauth-2-0-provider-api-1115659070.html)
-   [List of OAuth scopes](https://confluence.atlassian.com/adminjiraserver/jira-oauth-2-0-provider-api-1115659070.html#JiraOAuth2.0providerAPI-scopes)
-   [Jira Data Center API docs](https://docs.atlassian.com/software/jira/docs/api/REST/9.14.0/)

Need help getting started? Get help in the [community](https://terapi.dev/slack).

## API gotchas
-  Jira Data Center enforces HTTPS for the base URL of production environments. You can use insecure URIs and base URLs for staging or development environments by enabling the relevant [system properties](https://confluence.atlassian.com/adminjiraserver/oauth-2-0-provider-system-properties-1115659073.html).

Add Getting Started links and Gotchas by [editing this page]()

