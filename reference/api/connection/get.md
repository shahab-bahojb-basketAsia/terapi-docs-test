---
title: 'Get connection & credentials'
openapi: 'GET /connection/'
---


  ```json Example Response
{
    "id": 18393,                                  // Nango internal connection id
    "created_at": "2023-03-08T09:43:03.725Z",     // Creation timestamp
    "updated_at": "2023-03-08T09:43:03.725Z",     // Last updated timestamp (e.g. last token refresh)
    "provider_config_key": "github",              // 
    "connection_id": "1",                         // 
    "credentials": {
        "type": "OAUTH2",                         // OAUTH2 or OAUTH1
        "access_token": "gho_tsXLG73f....",       // The current access token (refreshed if needed)
        "refresh_token": "gho_fjofu84u9....",     // Refresh token (Only returned if the REFRESH_TOKEN boolean parameter is set to true and the refresh token is available)
        "expires_at": "2024-03-08T09:43:03.725Z", // Expiration date of access token (only if refresh token is present, otherwise missing)
        "raw": {                                  // Raw token response from the OAuth provider: Contents vary!
            "access_token": "gho_tsXLG73f....",
            "refresh_token": "gho_fjofu84u9....", // Refresh token (Only returned if the REFRESH_TOKEN boolean parameter is set to true and the refresh token is available)
            "token_type": "bearer",
            "scope": "public_repo,user"
        }
    },
    "connection_config": {                        // Additional API Configuration, see OAuth guide
        "subdomain": "myshop",
        "realmId": "XXXXX",
        "instance_id": "YYYYYYY"
    },                      
    "account_id": 0,                              // ID of your Nango account (Nango Cloud only)
    "metadata": {                                 // Custom metadata stored by you
        "myProperty": "yes",
        "filter": "closed=true"
    }
}                              
  ```




The response content depends on the API authentication type (OAuth 2, OAuth 1, API key, Basic auth). 

If you do not want to deal with collecting & injecting credentials in requests for multiple authentication types, use the Proxy([step-by-step guide](/integrate/guides/proxy-requests-to-an-api)).




Every time you fetch the connection with this API endpoint, Nango will check if the access token has expired. If it has, it will refresh it.

**We recommend you always fetch the token just before you use it to make sure it is fresh!**


