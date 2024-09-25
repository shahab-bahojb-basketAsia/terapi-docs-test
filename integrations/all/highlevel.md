---
title: HighLevel
sidebarTitle: HighLevel
---

API configuration: [`highlevel`](https://terapi.dev/providers.yaml), [`highlevel-white-label`](https://terapi.dev/providers.yaml)

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

-   [How to register an Application](https://highlevel.stoplight.io/docs/integrations/a04191c0fabf9-authorization#1-register-an-oauth-app)
-   [OAuth related docs](https://highlevel.stoplight.io/docs/integrations/a04191c0fabf9-authorization)
-   [List of OAuth scopes](https://highlevel.stoplight.io/docs/integrations/vcctp9t1w8hja-scopes)
-   [HighLevel REST API docs](https://highlevel.stoplight.io/docs/integrations/0443d7d1a4bd0-overview)

Need help getting started? Get help in the [community](https://terapi.dev/slack).

## API gotchas

-   HighLevel offers two different authorization flows for their users. The `standard` option allows for general OAuth2 authentication, while the `highlevel-white-label` option allows users to generate access tokens, enabling them to white-label the platform. This means users can rebrand the platform with their own branding elements and customize it to match their brand identity.
-   HighLevel enforces rate limits for its public V2 APIs. For more details check the HighLevel rate limits documentation.
-   When creating an app, there are two types of access: Location Level Access (also known as Sub-Account) and Agency Level Access (also known as Company). These access levels provide comprehensive control over location data at either the individual location or agency-wide level.
-   The App Type determines the accessibility and visibility of your application. A public app is available for anyone to use and access, while a private app is restricted to a specific group or individuals and is not publicly listed in the marketplace. For more details, check the profile information documentation.

Add Getting Started links and Gotchas by [editing this page]()

