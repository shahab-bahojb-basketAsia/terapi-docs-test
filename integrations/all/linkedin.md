---
title: LinkedIn
sidebarTitle: LinkedIn
---

API configuration: [`linkedin`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

If you notice any missing features, let us know and we can typically implement them within 48 hours. Reach out to the community for assistance!

## Getting started

-   [Register an Application](https://learn.microsoft.com/en-us/linkedin/shared/authentication/authorization-code-flow?tabs=HTTPS1#step-1-configure-your-application)
-   [OAuth Documentation](https://learn.microsoft.com/en-us/linkedin/shared/authentication/authorization-code-flow?context=linkedin%2Fcontext&tabs=HTTPS1)
-   [API Overview](https://learn.microsoft.com/en-us/linkedin/?context=linkedin%2Fcontext)
-   [Web API Guide](https://learn.microsoft.com/en-us/linkedin/shared/api-guide/concepts?context=linkedin%2Fconsumer%2Fcontext)

If you need guidance while getting started, feel free to ask in the community.

## API gotchas

- If your app's scope permissions change, users must re-authenticate to ensure they grant all requested permissions.
- Available scopes depend on the Products or Partner Programs your app is enrolled in.
- To receive refresh tokens, your app must request the "Advertising API" product under the "Products" tab on LinkedIn, and the app must be verified by your LinkedIn page admin.

Your contributions to improve this documentation are welcome!

