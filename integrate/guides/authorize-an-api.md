---
title: 'Authorize an API'
sidebarTitle: 'Authorize an API'
description: 'Step-by-step guide on how to get user authorization to access an external API on their behalf.'
---

# Create a free Terapi account

Sign up for a free Terapi account (**this feature is free & unlimited**, no credit card needed):

[![Try Terapi Cloud]()]()

# Create an integration

Go to the _Integrations_ tab, choose to configure a new [integration](), and choose an API to integrate with.


    Each API has a dedicated Terapi documentation page with useful links, gotchas, etc.


APIs have different ways to authorize requests: OAuth, API key, Basic, custom. Terapi abstracts away the difficulties of working with each one.

**For OAuth**

OAuth APIs require you to register your OAuth application on their developer portal.

When registering, the API provider will prompt you for the `Callback URL`. Use the one displayed in the Terapi integration settings. Remember to register the required scopes in the Terapi integration settings and, if necessary, with the API provider.

Collect your OAuth app's `Client ID` and `Client Secret` from the API portal and input them in your Terapi integration settings.

**For API Key & Basic**

No configuration is necessary for APIs supporting API key & Basic authorization.

**For Custom Authorization**

APIs like Stripe & GitHub Apps have custom authorization. Configurations vary and are described in the Terapi integration settings.

# Test the authorization


You can test the authorization flow directly in the Terapi UI, using your own external account credentials.

In production, the authorization flow will be triggered from your app, prompting each of your customers to enter their external account credentials (cf. next section).


On the Terapi integration page, click `Connect` to test the authorization. After authorizing API access for one of the modes described below, a [connection]() should be successfully created in the _Connections_ tab.

**For OAuth**

Input your external account credentials in the popup dialog to test the authorization.

**For API Key & Basic**

Input the API key (or username/password for Basic) to test the authorization.

**For Custom Authorization**

The authorization flow will vary based on the API, but you will most likely have to log in to your external account via a popup dialog.

# Authorize users from your app

### Integrate the frontend SDK

Once you have tested that the authorization flow works for your own external account, you can trigger authorization flows for your customers from your app with the Terapi SDK.

Get your `Public Key` from the _Environment Settings_ tab.

In your frontend, initiate Terapi ([reference]()):

```ts
import Terapi from '@nangohq/frontend';

let terapi = new Terapi();
```

Initiate the authorization flow ([reference]()):





For OAuth, the `terapi.auth()` method will trigger the OAuth flow in a popup, to let the user log in to their external account.

```js
terapi
    .auth('', '')
    .then((result) => )
    .catch((error) => );
```





For API keys, the `terapi.auth()` method is used to store the end-user's API key (that you have previously collected from them).

```js
terapi
    .auth('', '', 
    })
    .then((result) => )
    .catch((error) => );
```





For Basic Auth, the `terapi.auth()` method is used to store the end-user's username & password (that you have previously collected from them).

```js
terapi
    .auth('', '', 
    })
    .then((result) => )
    .catch((error) => );
```





Terapi will automatically collect, store, and refresh the API credentials as needed.



Before using Terapi in production, we advise [securing the frontend SDK]().


### Listen for webhooks

Your backend is notified by Terapi when an authorization attempt is completed, successful or not.

To set this up:
1. go to the _Environment Settings_ tab
2. specify a _Webhook URL_ to which Terapi will send notifications
3. listen for webhooks in your backend at the specified route
4. enable the "Send New Connection Creation Webhooks" checkbox

Terapi webhooks are post requests with the following JSON body:
```json

```

For each successful authorization attempt, persist the connection ID & integration ID in your database. You will need them to retrieve the connection credentials later.


Before using Terapi in production, we advise [verifying webhook signatures]().


### APIs requiring connection-specific configuration for authorization

Some APIs require connection-specific configuration (e.g. Zendesk, Shopify).

For example, Zendesk has the following authorization URL, where the subdomain is specific to a user's Zendesk account:

`https://.zendesk.com/oauth/authorizations/new`

For these cases, you must provide this configuration when calling `terapi.auth()` ([reference]()):

```js
terapi.auth('zendesk', '', 
});
```

In some cases you might want to override the scopes provided by an integration at the connection level. For this case you can pass in the scopes to `terapi.auth`:

```js
terapi.auth('zendesk', '', 
});
```

This _connection configuration_ is stored in the connection. You can retrieve it with the SDK ([reference]()), API ([reference]()), and the Terapi UI.

# Troubleshoot authorization errors

If an authorization request fails, you can analyze the relevant log in the _Logs_ tab of the Terapi UI.

# Use a custom callback URL

You can personalize Terapi's callback URL (e.g. use your domain). If you are using Terapi Cloud, follow these steps:

1. Add a new endpoint in your app, e.g. `https://EXAMPLE.com/oauth-callback`. All requests to this endpoint should redirect to `https://api.terapi.dev/oauth/callback` and **pass along all original parameters**. The easiest way to do this is with a 308 redirect.
2. Change the registered OAuth callback URL with all API providers. Otherwise, they will refuse new flows!
3. When ready, change your Terapi callback URL in the _Environment Settings_ tab.

If you are self-hosting Terapi, follow the instructions [here]() to change your callback URL.


**Questions, problems, feedback?** Please reach out in the Slack community.


