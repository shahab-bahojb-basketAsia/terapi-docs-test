---
title: Contentful
sidebarTitle: Contentful
---

API configurations: `contentful`

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

Need missing features? Let us know, and we can add them within 48 hours through the community.

## Getting started

-   [Register an Application](https://app.contentful.com/account/profile/developers/applications)
-   [Learn about OAuth setup](https://www.contentful.com/developers/docs/extensibility/oauth/)
-   [Explore API documentation](https://www.contentful.com/developers/docs/references/)
-   [REST API documentation](https://www.contentful.com/developers/docs/references/)

Looking for help? Check out our community for support and insights.

## API gotchas

- Contentful also allows using the authorization code flow for authentication.
- Contentful requires different subdomains depending on the API type and region, such as `cdn.eu` for the EU Content Delivery API or `api.eu` for the EU Content Management API. Refer to each API's introduction for detailed information.
- Each API type has its own rate limits. For example, the [Content Delivery API rate limit](https://www.contentful.com/developers/docs/references/content-delivery-api/#/introduction/api-rate-limits) varies from other APIs. Make sure to review the specific rate limits for the API you're using.

Add Getting Started links and Gotchas by editing this page.

