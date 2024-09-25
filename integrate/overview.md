---
title: 'Integrate Terapi - Overview'
sidebarTitle: 'Overview'
description: 'High-level steps to ship an integration with Terapi.'
---


  


## 1. Get user permission in your app

Use the Terapi frontend SDK to get the user's permission to access their external data.

Terapi guides the user through the (O)Auth flow in a popup window.

Store the `connectionId` & `integrationId` in your database to retrieve the user's data later.

```ts Frontend: Trigger the OAuth flow.
const integrationId = 'zendesk';
const connectionId = 'user123';

// Shows authorization popup to the user.
const result = await terapi.auth(integrationId, connectionId);

if (result.ok) 
```


When a new user connects your integration, Terapi automatically starts fetching their data (e.g. issues, contacts, files, etc.) in the background.


## 2. Receive data update notifications

Terapi uses webhooks to notify your backend when external user data has been added, updated or deleted. Terapi will only alert you when there are actual changes.

```json Backend: Webhook payload with new data
,
    "modifiedAfter": "2023-05-31T11:46:13.390Z"
}
```

## 3. Collect and save the new data

When you receive the webhook, fetch the most recent data from Terapi using the backend SDK or API.

Terapi returns the data in the schema of your choice, which can be standardized across different APIs.

You can directly save this data to your database, or process it further, as needed.

```ts Backend: Fetch & save new records.
const records = await terapi.listRecords();

saveToDatabase(records);
```

## 4. Write back to external APIs

Push updates back to external APIs in a way that is:

- **Synchronous:** Have your changes immediately reflected.
- **Unified:** Benefit from standardized schemas across different APIs.
- **Customizable:** Support intricate workflows and composed API calls.

```ts Backend: Write back to external APIs.
const result = await terapi.triggerAction(
});
```


**Questions, problems, feedback?** Please reach out in the Slack community.

