---
title: 'Proxy'
sidebarTitle: 'Proxy'
description: 'Learn more about the Nango Proxy.'
---

# Overview

Nango's Proxy simplifies making authenticated requests to external APIs. It’s a tool designed to save you time and reduce complexity in your interactions with APIs.

# Key features

- **Automatic Credential Injection:** Automatically adds necessary authentication to your API requests.
- **Base URL Setup:** Automatically determines and sets the correct base URL for your API requests.
- **Effortless Pagination:** Simplifies dealing with API pagination.
- **Logs for Debugging:** Tracks your requests in the Logs tab for easy debugging.
- **Rate-limit Management:** Handles rate limits with smart retries ([step-by-step guide](/customize/guides/advanced/handle-rate-limits)).

# Use cases

The Proxy is useful to perform any individual request to external APIs, e.g.

- Fetching Data: Great for one-time data retrieval, like getting user metadata.
- Writing Data: Use it to send data back to an API, such as updating a user profile.

**Proxy vs. actions**

The Proxy works for individual API requests, while [actions](/understand/concepts/actions) handle more complex scenarios that require multiple requests or data transformations.


The Proxy is actually the default way to make API requests in integration scripts, including action scripts.


# Getting started with the Proxy


The Proxy is available for free on Nango Cloud.


Check out the Proxy [step-by-step guide](/integrate/guides/proxy-requests-to-an-api) or refer to the reference ([API](/reference/api/proxy/get) / [SDK](/reference/sdks/node#proxy)) for full details on proxy options.


**Questions, problems, feedback?** Please reach out in the [Slack community](https://nango.dev/slack).

