---
title: Klaviyo
sidebarTitle: Klaviyo
---

API configuration: [`klaviyo`](https://terapi.dev/providers.yaml), [`klaviyo-oauth`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (API Key)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | ✅  |

If you have feature requests or need enhancements, let us know in the community!

## Getting started

-   [How to generate private & public API keys in your Klaviyo account](https://developers.klaviyo.com/en/docs/retrieve_api_credentials)
-   [API documentation](https://developers.klaviyo.com/en/reference)
-   [API Key rate limiting](https://developers.klaviyo.com/en/docs/rate_limits_and_error_handling)
-   [API Key authentication documentation](https://developers.klaviyo.com/en/docs/authenticate_)
-   [API Key scopes](https://developers.klaviyo.com/en/reference/api_overview#api-key-scopes)
-   [How to generate an OAuth application](https://developers.klaviyo.com/en/docs/set_up_oauth#create-an-oauth-integration-in-klaviyo)
-   [OAuth documentation](https://developers.klaviyo.com/en/docs/set_up_oauth#oauth-authorization-code-flow)
-   [List of OAuth scopes](https://developers.klaviyo.com/en/docs/retrieve_api_credentials#scopes)

If you need assistance, feel free to reach out in the community for support.

## API gotchas

- For `API_KEY` authentication, Klaviyo requires Public and Private API Keys for different endpoints. Endpoints starting with `/api` must use the private API key, while those starting with `/client` need the public API key.
- If you want to use a specific API version other than the default set in Terapi, you can override the `revision` by including the necessary header. For more details, refer to the section on [Klaviyo API versioning](https://developers.klaviyo.com/en/docs/api_versioning_and_deprecation_policy#api-versioning).
- Rate limiting for `klaviyo-oauth` is distinct from the standard API rate limits. For more information, consult the section on [klaviyo-oauth rate limits](https://developers.klaviyo.com/en/docs/set_up_oauth#rate-limits).

You can contribute to this documentation by editing this page.

