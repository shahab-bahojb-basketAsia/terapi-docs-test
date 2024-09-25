---
title: 'Frontend SDK'
sidebarTitle: 'Frontend SDK'
icon: 'js'
---

Trigger authorization flows in your frontend with this SDK. It is available on [NPM](https://www.npmjs.com/package/@nangohq/frontend) as `@nangohq/frontend`.

# Instantiate the frontend SDK

```ts
import Nango from '@nangohq/frontend';

let nango = new Nango();
```

**Parameters**


  
    
      
    Get your public key in the environment settings of the Nango UI. This is key is not sensitive.
      

      
        Omitting the host points to Nango Cloud. For local development, use `http://localhost:3003`. Use your instance URL if self-hosting. 
      

      
        For self-hosted instances only to specify a customs path for the WebSocket connection.
      

      
        Specify a specific width for the OAuth authorization modal.
      

      
        Specify a specific height for the OAuth authorization modal.
      

      
        Print additional console logs to debug authorization issues.
      
    
  



# Collect & store end-user credentials

You store end-user credentials with the `nango.auth` method. It creates a [connection](/understand/concepts/connections) in Nango.





For OAuth, this will open a modal to let the user log in to their external account.

```js
const result = await nango.auth('', '').catch((error) => );
```





For API key authorization, pass the end-user's previously-collected API key directly in the parameters.

```js
const result = await nango.auth('', '', 
}).catch((error) => );
```





For Basic Auth, pass the end-user's previously-collected username & password in the parameters.

```js
const result = nango.auth('', '', 
}).catch((error) => );
```




**Parameters**

  
    The integration ID that you can find in the integration settings on the Nango UI.
  

  
    The connection ID that you can find in the _Connections_ tab on the Nango UI.
  

  
    
      
        Specify additional [connection configuration](/integrate/guides/authorize-an-api#apis-requiring-connection-specific-configuration-for-authorization) necessary to perform the authorization request.
      

      
        HMAC key to secure the authorization flow (cf. (instructions)[TODO]).
      

      
        If `true`, `nango.auth()` would fail if the login window is closed before the authorization flow is completed.
      

      
        For OAuth, specify the query parameters of the authorization URL. 
      

      
        For Slack OAuth, specify user-specific scopes. 
      

      
        
          
            For API key authorization, pass in the user's API key.
          

          
            For Basic authorization, pass in the user's username.
          

          
            For Basic authorization, pass in the user's password.
          

          
            For OAuth 2, override the integration's client ID with a connection-level client ID. This is useful when your users bring their own OAuth 2 app (e.g. Netsuite).
          

          
            For OAuth 2, override the integration's client secret with a connection-level client secret. This is useful when your users bring their own OAuth 2 app (e.g. Netsuite).
          
        
      
    
  


**Success response**


  
    The integration ID that you can find in the integration settings on the Nango UI.
  

  
    The connection ID that you can find in the _Connections_ tab on the Nango UI.
  


**Error response**

  
    
      
        The type of error (e.g. 'authorization_cancelled').
      

      
        The detailed error message (e.g. 'Authorization fail: The user has closed the authorization modal before the process was complete.').
      
    
  



**Questions, problems, feedback?** Please reach out in the [Slack community](https://nango.dev/slack).

