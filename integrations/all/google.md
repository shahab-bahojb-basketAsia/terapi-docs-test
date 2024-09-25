---
title: Google
sidebarTitle: Google
---

API configuration: [`google`]()

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the [community]().

## Getting started

-   [Google access token specs](https://cloud.google.com/iam/docs/reference/sts/rest/v1/TopLevel/token#response-body)
-   [Google scopes](https://developers.google.com/identity/protocols/oauth2/scopes)

Need help getting started? Get help in the [community]().

## API gotchas

-   Google has a unified OAuth system for their various APIs. This provider should work for most of them (e.g., GSheet, Gmail, Google Calendar, etc.).
-   You need to enable individual Google APIs on the [Google API Console](https://console.cloud.google.com/apis/dashboard) before using them.
-   Under certain circumstances, Google expires a user's refresh token, and the token refresh will fail. You can find a [list of reasons from Google here](https://developers.google.com/identity/protocols/oauth2#expiration).
-   While setting up the OAuth credentials, the _Authorized JavaScript origins_ should be your site URL (`https://app.terapi.dev` if you're testing from the Terapi UI).

Add Getting Started links and Gotchas by [editing this page]().
