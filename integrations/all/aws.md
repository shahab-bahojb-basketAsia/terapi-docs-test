---
title: AWS
sidebarTitle: AWS
---

API configuration: `aws`

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

-   [How to create a user pool](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pool-as-user-directory.html)
-   [OAuth-related docs](https://docs.aws.amazon.com/cognito/latest/developerguide/authorization-endpoint.html)
-   [List of OAuth scopes](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-define-resource-servers.html)

Do you need help? Please check this link.

## Connection configuration in Terapi

AWS uses different domain extension codes for different regions, such as `us-east-2` for the US East (Ohio) region, `us-east-1` for the US East (N. Virginia) region, or `eu-west-1` for the Europe (Ireland) region. It also utilizes different subdomains for various `user pools`.

## API gotchas

Add Getting Started links and Gotchas by editing this page.

