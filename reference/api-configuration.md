---
title: 'API configuration (providers.yaml)'
sidebarTitle: 'API config (providers.yaml)'
icon: 'network-wired'
---

API configurations are listed in the `providers.yaml` file, located in the [Nango GitHub repository](https://github.com/NangoHQ/nango/blob/master/packages/shared/providers.yaml). Learn more about [API configurations](/understand/concepts/integrations#api-configurations).

# Examples




```yaml
hubspot:
    categories:
        - marketing
        - support
    auth_mode: OAUTH2
    authorization_url: https://app.hubspot.com/oauth/authorize
    token_url: https://api.hubapi.com/oauth/v1/token
    connection_configuration:
        - portalId
    post_connection_script: hubspot-post-connection
    webhook_routing_script: hubspot-webhook-routing
    proxy:
        base_url: https://api.hubapi.com
        decompress: true
    docs: https://docs.nango.dev/integrations/all/hubspot
```




```yaml
salesforce:
    categories:
        - crm
    auth_mode: OAUTH2
    authorization_url: https://login.salesforce.com/services/oauth2/authorize
    token_url: https://login.salesforce.com/services/oauth2/token
    authorization_params:
        prompt: consent
    default_scopes:
        - offline_access
    token_response_metadata:
        - instance_url
    proxy:
        base_url: $
    webhook_routing_script: salesforce-webhook-routing
    post_connection_script: salesforce-post-connection
    docs: https://docs.nango.dev/integrations/all/salesforce
```




```yaml
google:
    auth_mode: OAUTH2
    authorization_url: https://accounts.google.com/o/oauth2/v2/auth
    token_url: https://oauth2.googleapis.com/token
    authorization_params:
        response_type: code
        access_type: offline
        prompt: consent
    proxy:
        base_url: https://www.googleapis.com
    docs: https://docs.nango.dev/integrations/all/google
```




```yaml
notion:
    categories:
        - knowledge-base
        - productivity
    auth_mode: OAUTH2
    authorization_url: https://api.notion.com/v1/oauth/authorize
    token_url: https://api.notion.com/v1/oauth/token
    authorization_params:
        response_type: code
        owner: user
    authorization_method: header
    body_format: json
    proxy:
        retry:
            after: 'Retry-After'
        base_url: https://api.notion.com
        headers:
            'Notion-Version': '2022-06-28'
    docs: https://docs.nango.dev/integrations/all/notion
```




```yaml
linear:
    categories:
        - productivity
        - ticketing
    auth_mode: OAUTH2
    authorization_url: https://linear.app/oauth/authorize
    token_url: https://api.linear.app/oauth/token
    scope_separator: ','
    authorization_params:
        prompt: consent
    proxy:
        base_url: https://api.linear.app
    disable_pkce: true
    webhook_routing_script: linear-webhook-routing
    post_connection_script: linear-post-connection
    webhook_user_defined_secret: true
    docs: https://docs.nango.dev/integrations/all/linear
```




```yaml
slack:
    categories:
        - productivity
    auth_mode: OAUTH2
    authorization_url: https://slack.com/oauth/v2/authorize
    token_url: https://slack.com/api/oauth.v2.access
    token_response_metadata:
        - incoming_webhook.url
        - incoming_webhook.channel
        - incoming_webhook.channel_id
        - bot_user_id
        - team.id
    proxy:
        base_url: https://slack.com/api
        paginate:
            type: cursor
            cursor_path_in_response: response_metadata.next_cursor
            cursor_name_in_request: cursor
            limit_name_in_request: limit
    webhook_routing_script: slack-webhook-routing
    docs: https://docs.nango.dev/integrations/all/slack
```





# All configuration fields

| Field | Description |
| - | - | 
| `auth_mode` | The type of authorization of the API, e.g. `OAUTH2`, `API_KEY`, `BASIC`, etc. |
| `authorization_url` | The URL to show the OAuth 2 login form to authorize the external service. |
| `token_url` | The URL to get the OAuth 2 credentials from the external API.  |
| `scope_separator` | Defaults to space, but some APIs sur `,` or `+`. |
| `authorization_params` | Query parameters of the authorization request, e.g. `response_type: code` |
| `token_params` | Query parameters of the token request, e.g. `grant_type: authorization_code` |
| `refresh_params` | Query parameters of the refresh request, e.g. `grant_type: refresh_token` |
| `proxy` | Contains the configuration to use the [proxy]().  |
| `proxy.base_url` | The base URL of the API to be used when proxying requests. |
| `proxy.headers` | The headers to include when proxying requests.  |
| `proxy.retry.after` | The name of the rate-limit header, e.g. `after: 'X-Rate-Limit-Reset'` |
| `proxy.retry.at` | The name of the rate-limit header, e.g. `at: 'x-ratelimit-reset'` |
| `docs` | The link to the API documentation (in the Nango documentation). |
| `default_scopes` | The minimum list of scopes that are necessary to connect to the API. |
| `refresh_url` | The URL to refresh the OAuth credentials (defaults to the `token_url`) |
| `disable_pkce` | Disables the [PKCE](https://oauth.net/2/pkce/) extention to the Authorization Code flow. |
| `token_request_auth_method` | The authorization method for the token request. |
| `token_response_metadata` | The metadata to capture from the token response. |
| `webhook_routing_script` | Specifies a script to handle external [webhooks](/understand/concepts/webhooks). |
| `post_connection_script` | Specifies a script to execute following each new connection. |
| `request_url` | The token request URL for OAuth 1. |
| `signature_method` | The signature method for OAuth 1 |
| `redirect_uri_metadata` | The metadata to capture from the callback request. |
| `verification` | The endpoint to verify that API key and Basic credentials are valid. |
| `categories` | The categories of the external API (e.g. CRM) for proper documentation. |
| `alias` | Allows to extend the configuration of another API. |
| `token_expiration_buffer` | The buffer between when access token expiration and refresh. |



**Questions, problems, feedback?** Please reach out in the [Slack community](https://nango.dev/slack).

