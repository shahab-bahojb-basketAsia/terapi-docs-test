---

title: Egnyte
sidebarTitle: Egnyte

---

API configuration: `egnyte`

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

Missing features can be added within 48 hours. Feel free to reach out in the community.

## Getting started

-   [Register an Application](https://developers.egnyte.com/member/register)
-   [OAuth-related documentation](https://developers.egnyte.com/docs/read/Public_API_Authentication#Authorization-Code-Flow)
-   [List of OAuth scopes](https://developers.egnyte.com/docs/read/Public_API_Authentication#OAuth-Scopes)
-   [Egnyte REST API documentation](https://developers.egnyte.com/docs/read/Home)

If you need assistance while setting up, feel free to visit the community for support.

## API gotchas

- Terapi currently supports the integration of public applications using the [authorization code flow](https://developers.egnyte.com/docs/read/Public_API_Authentication#auth_code) to retrieve an access token.
- Egnyte requires a unique user-specific subdomain for OAuth authentication. You’ll need to include this subdomain as part of your application's setup.
- Applications will only function on the subdomain associated with your application key, and full production approval is necessary for broader use beyond this initial subdomain.

Add any additional links or API notes by editing this page.

