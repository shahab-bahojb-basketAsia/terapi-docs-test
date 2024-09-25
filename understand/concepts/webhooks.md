---
title: 'Webhooks'
sidebarTitle: 'Webhooks'
description: 'Learn more about how Nango lets you process webhooks.'
---

There are two types of webhooks in Nango: webhooks from Nango (to your app) and webhooks from external APIs (to Nango).

# Webhooks from Nango

Nango sends webhook notifications to your backend in different cases:
- **Sync webhook**: new data from syncs is available ([step-by-step guide](/integrate/guides/sync-data-from-an-api#listen-for-webhooks-from-nango))
- **Authorization webhook**: an authorization flow completes ([step-by-step guide](/integrate/guides/authorize-an-api#listen-for-webhooks))
- **Webhook forward**: an external API webhook is forwarded to your app ([step-by-step guide](/integrate/guides/receive-webhooks-from-an-api#configure-webhooks-from-nango))


Nango retries (with exponential backoff) webhooks with non-2xx responses.


Webhooks from Nango are POST requests with the following JSON body.

# Webhooks from external APIs

Nango makes it easy to process webhooks from external APIs ([step-by-step guide](/integrate/guides/receive-webhooks-from-an-api)).



**Questions, problems, feedback?** Please reach out in the [Slack community](https://nango.dev/slack).

