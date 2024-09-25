---
title: 'Receive webhooks from an API'
sidebarTitle: 'Receive webhooks from an API'
description: 'Step-by-step guide on how to receive webhooks from an API.'
---


Please note that receiving webhooks in Terapi is currently only available on the Scale plan.


Terapi makes it easy to add support for webhooks coming from **any** API. If your API doesn't have off-the-shelf support, simply request it in the [community]; we can deliver them in less than 48 hours.

Terapi currently has off-the-shelf support for webhooks coming from the following APIs:
- Github
- Hubspot
- Jira
- Linear
- Salesforce
- Slack

# Configure external webhooks

To send webhooks from an external API to Terapi, configure webhooks on the external API portal, specifying the Terapi URL to receive webhooks, which is accessible in your integration settings in the Terapi UI.

# Configure webhooks from Terapi

When Terapi receives a webhook from an external API, it notifies your app with another webhook. To set this up:
1. Go to the _Environment Settings_ tab in the Terapi UI.
2. Specify a Webhook URL to which Terapi will send notifications.
3. Listen for webhooks in your backend at the specified route.

# Forward external webhooks to your app

Terapi automatically forwards all webhooks from external APIs to your app.

Terapi webhook forwards are POST requests with the following JSON body:
```json

```

# Handle external webhooks in syncs

Additionally, [syncs]() can be designed to process webhooks from external APIs.

Webhook-enabled syncs process relevant webhooks, resulting in the creation, update, and deletion of the corresponding [records]() in real-time.

Each modified record (following an external webhook) will trigger a separate webhook from Terapi to your app. The POST request has the following body:
```json
,
    "syncType": "WEBHOOK",
    "modifiedAfter": ""
}
```

Simply activate a webhook-enabled sync to benefit from these capabilities.

You can check if a sync supports external webhooks by selecting your integration, going to the _Endpoints_ tab, selecting the sync script, and checking in the sync script settings if it supports webhooks and, if so, which webhook subscription(s).


**Questions, problems, feedback?** Please reach out in the Slack community.


