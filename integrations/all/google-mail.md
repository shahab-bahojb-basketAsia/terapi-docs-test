---
title: Gmail
sidebarTitle: Gmail
---

API configuration: [`google-mail`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the [community](https://terapi.dev/slack).

## Getting started

-   [Gmail access token specs](https://cloud.google.com/iam/docs/reference/sts/rest/v1/TopLevel/token#response-body)
-   [Gmail OAuth scopes](https://developers.google.com/identity/protocols/oauth2/scopes#gmail)

Need help getting started? Get help in the [community](https://terapi.dev/slack).

## API gotchas

-   While setting up the OAuth app, use the `https://mail.google.com/` scope for extended capabilities.

Add Getting Started links and Gotchas by [editing this page](https://terapi.dev/docs-v2/integrations/all/google-mail.mdx)

