---
title: 'Managing API rate limits'
sidebarTitle: 'Managing API rate limits'
description: 'Learn effective strategies for handling API rate limits in your integrations.'
---

Many external APIs implement rate limits to control usage. When these limits are reached, you'll typically receive HTTP 429 errors, preventing further requests until the limit resets.

To maintain data accuracy and prevent disruptions in your integration scripts, it's crucial to manage your API call volume effectively. Terapi offers built-in features to simplify this process.

## Approach 1: Retry with exponential backoff

A straightforward strategy involves retrying failed requests after a waiting period:

When configuring HTTP requests using Terapi's helper functions, you can specify the number of retries:

```ts
await terapi.get();
```

This setup enables automatic retries upon receiving a 429 status code, with increasing wait times between attempts. This method is effective because:

- It uses exponential backoff to respect the rate-limit period.
- Terapi's sync processes can run for extended periods, allowing for multiple retry attempts.
- It's a universal approach that works across different APIs without specific configurations.

## Approach 2: Utilize rate-limit headers

For APIs with stricter limits, Terapi offers a more refined approach by automatically interpreting API-specific rate-limit headers and scheduling retries accordingly:

```ts
await terapi.get();
```

If rate-limit header parsing isn't already configured for an API you're using, you can request its addition by contacting the Terapi support team.


For further assistance or questions, please reach out to our community support channels.


