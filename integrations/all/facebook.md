---
title: Facebook
sidebarTitle: Facebook
---

API configuration: `facebook`

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

Missing features can be added within 48 hours—reach out to the community if needed.

## Getting started

-   [How to register an Application](https://developers.facebook.com/docs/development/create-an-app/)
-   [OAuth-related documentation](https://developers.facebook.com/docs/facebook-login/guides/advanced/manual-flow#confirm)
-   [List of available OAuth scopes](https://developers.facebook.com/docs/permissions/reference)
-   [Facebook API Documentation](https://developers.facebook.com/docs/)

To integrate Facebook OAuth with **Terapi**, follow these steps to register your app and set up the necessary OAuth callback URL:
1. First, create a new app in the Meta Developer Portal.
2. From the dashboard, click "**Set Up**" under the "Facebook Login" product to enable it.
3. Go to the "**Settings**" section under "Facebook Login."
4. In the "**Valid OAuth Redirect URIs**" field, paste your **Terapi** callback URL (default: `https://api.terapi.dev/oauth/callback`).
5. Save the changes, and your app is ready for use with Terapi.

If you need further assistance, join the community for help with your setup.

## API gotchas

No specific gotchas yet. Please contribute if you encounter any!

Add more Getting Started links and Gotchas by editing this page.

