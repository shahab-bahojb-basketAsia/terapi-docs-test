---
title: 'Integrations'
sidebarTitle: 'Integrations'
description: 'Learn more about integrations.'
---

# Overview
An Integration within Nango is essentially your product's setup for connecting to an external API on your customers' behalf. It's how you configure Nango to interact with services like GitHub, Slack, or any other external platform that your product needs to integrate with.

# Creating integrations
Creating an integration is straightforward and only takes a few clicks in the Nango UI. Whether for GitHub, Slack, or any other service, you'll set up one integration per service.

Each integration has a unique identifier you can see and edit in the settings on the Nango UI.

# Authorization methods
Integrations define how to authenticate API access. The primary methods include:

- **OAuth:** The most common method, enabling customers to authenticate directly within your app with an embedded sign-in form from the external provider.
- **API key:** Customers provide an API key for your app to access the external service on their behalf.
- **Other methods** include basic authentication and custom methods like GitHub Apps or Stripe Apps.

For OAuth, you'll input the credentials & permissions of the OAuth app you've set up on the external service's developer portal, accessible within the integration's settings in the Nango UI ([step-by-step guide](/integrate/guides/authorize-an-api)).

# Configuration details
Beyond authorization, integrations include configurations for how your app uses the external API, such as:

- **API reference**: Found in the "Endpoint" tab, this includes information necessary for utilizing external APIs through Nango.
- **Integration scripts**: Underlying integration scripts that facilitate Nango's interaction with the external API are listed in the Endpoint tab. These [integration scripts](/understand/concepts/scripts) power the endpoints in the API reference, enabling your app to use Nango's unified API without directly dealing with the complexities of external APIs.

# Flexibility and customization
Nango stands out by not limiting you to a fixed set of endpoints & use cases. You can customize or extend the provided templates with your own integration scripts, allowing you to tailor the integration to your specific needs ([overview](/customize/overview)). This approach will enable you to focus on leveraging a unified API through Nango, streamlining the integration process with external services.

# Getting started with using Integrations

Check out the authorization [step-by-step guide](/integrate/guides/authorize-an-api) or refer to the reference ([API](/reference/api/integration/list) / [SDK](/reference/sdks/node#integrations)).

# API configurations

API configurations provide Nango with details on authorizing and communicating with external APIs. API configurations are meant to be minimal, so adding support for new APIs is trivial. As a result, many of these API configurations are contributions from our community.


You can [ask us](https://nango.dev/slack) to add new APIs in &lt;48h or contribute them yourself ([step-by-step guide](/customize/guides/contribute-an-api)).


### `providers.yaml`

Nango centralizes all API configurations in the [providers.yaml](https://nango.dev/providers.yaml) file, shared by all Nango users.

For instance, here's how an API configuration might look:
```yaml
asana:
    categories:
        - productivity
        - ticketing
    auth_mode: OAUTH2
    authorization_url: https://app.asana.com/-/oauth_authorize
    token_url: https://app.asana.com/-/oauth_token
    token_params:
        grant_type: authorization_code
    auth:
        response_type: code
    refresh_params:
        grant_type: refresh_token
    proxy:
        base_url: https://app.asana.com
    docs: https://docs.nango.dev/integrations/all/asana
```

Each API configuration in the `providers.yaml` includes several key pieces of information:

- **Authorization methods:** Whether OAuth, API key, or a custom method, Nango supports various ways to authenticate your app with external services. For multiple authorization methods, separate configurations are maintained.

- **End-user-specific data:** Nango captures and stores data specific to your users that is returned during the authorization process. This data is crucial for maintaining individual user connections to external services ([step-by-step guide](/integrate/guides/authorize-an-api#apis-requiring-connection-specific-configuration-for-authorization)).

- **Validation endpoints:** For API key and basic auth methods, configurations may specify endpoints to validate submitted credentials, ensuring they are correct before validating a connection.

- **Custom authorization systems:** APIs requiring unique authorization methods are supported with custom configurations. Nango's team is ready to implement specific handling as needed.

Consult the [reference](/reference/api-configuration) for all configuration options and [past contributions](https://github.com/NangoHQ/nango/pulls?q=is%3Apr+is%3Amerged+label%3Aapi+) for examples.


**Questions, problems, feedback?** Please reach out in the [Slack community](https://nango.dev/slack).

