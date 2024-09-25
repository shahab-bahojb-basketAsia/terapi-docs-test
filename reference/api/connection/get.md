---
title: 'Get connection & credentials'
openapi: 'GET /connection/'
---


  ```json Example Response

    },
    "connection_config": ,                      
    "account_id": 0,                              // ID of your Nango account (Nango Cloud only)
    "metadata": 
}                              
  ```




The response content depends on the API authentication type (OAuth 2, OAuth 1, API key, Basic auth). 

If you do not want to deal with collecting & injecting credentials in requests for multiple authentication types, use the Proxy([step-by-step guide](/integrate/guides/proxy-requests-to-an-api)).




Every time you fetch the connection with this API endpoint, Nango will check if the access token has expired. If it has, it will refresh it.

**We recommend you always fetch the token just before you use it to make sure it is fresh!**



