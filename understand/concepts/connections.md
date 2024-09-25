---
title: 'Connections'
sidebarTitle: 'Connections'
description: 'Learn more about connections.'
---

# Overview
Connections link your customers and the APIs they've authorized access to, associated directly with an [integration](/understand/concepts/integrations) in Nango. Each connection embodies the credentials needed for your app to interact with an external API on behalf of a specific customer.

# Credential management
The type of credentials stored within a connection depends on the integration's authorization method (OAuth, API Key, Basic Auth, Custom). For OAuth, for instance, the connection will hold the access token, refresh token, access token expiration date, among other details, enabling API requests on behalf of the customer.

Connections also maintain the raw credentials as returned by the external API, which may include additional API-specific information. These raw credentials can be viewed or fetched through the Nango UI and [API](/reference/overview).

# Connection identifier
When setting up a connection, you'll specify an identifier (often the customer ID) to later retrieve the connection. This ID is unique within an integration context but can be reused across different integrations.

# Storing customer-specific information

### Connection metadata

A key feature of connections is the metadata, a JSON object that you can programmatically edit. This can be done from your application ([step-by-step guide](/integrate/guides/advanced/store-customer-specific-data)) or from within an [integration script](/understand/concepts/scripts). This metadata is designed to store and transmit customer-specific information, facilitating personalized integration experiences.

Connection metadata is heavily used in [syncs](/understand/concepts/syncs). Executed as per a schedule and not in real-time, sync scripts cannot directly receive parameters due to their asynchronous nature. Instead, they utilize connection metadata for accessing customer-specific information. [Actions](/understand/concepts/actions) allow for the direct passing of parameters in addition to leveraging connection metadata.

### Connection configuration

Besides metadata, connections also include configuration details—set either by Nango during the authorization process or supplied by you ([step-by-step guide](/integrate/guides/authorize-an-api#apis-requiring-connection-specific-configuration-for-authorization)). This includes critical information for the authorization flow, like customer-specific domains required by some external APIs. This configuration ensures smooth authorization and subsequent API interactions, tailored to each customer's specifics.

# Getting started with using Connections

Check out the authorization [step-by-step guide](/integrate/guides/authorize-an-api) or refer to the reference ([API](/reference/api/connection/list) / [SDK](/reference/sdks/node#connections)).


**Questions, problems, feedback?** Please reach out in the [Slack community](https://nango.dev/slack).

