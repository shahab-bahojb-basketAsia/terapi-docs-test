---
title: 'Use custom field mappings'
sidebarTitle: 'Use custom field mappings'
description: 'Step-by-step guide on how to support custom fields using field mappings.'
---

Field mappings are necessary when a [sync]() needs to access information stored in external custom fields. Terapi provides dedicated tools to support complex field mappings.

# Prompt your customers for field mappings

In your app:
- fetch the list of custom fields available from the external API using an action
- display the full list of external custom fields to the user
- prompt the user to associate the data you need to collect to the relevant external custom fields

The output of this step should be a field mapping object such as: 
```json
 
```

# Store field mappings in the connection metadata

Update the relevant connection's metadata with the obtained field mapping object with the SDK or API: 



```typescript
await terapi.setMetadata('', '', );
```




```bash
curl --request PATCH \
  --url https://api.terapi.dev/connection//metadata \
  --header 'Authorization: Bearer ' \
  --header 'Content-Type: application/json' \
  --header 'Provider-Config-Key: ' \
  --data ''
```





# Start the sync for each connection

Start the _sync_ schedule programmatically for this connection with the SDK or API: 



```typescript
await terapi.startSync('', ['hubspot-sync'], '');
```


```bash
curl --request POST \
  --url https://api.terapi.dev/sync/start \
  --header 'Authorization: Bearer ' \
  --header 'Content-Type: application/json' \
  --data ''
```



The sync's internal logic will use the field mappings to fetch the relevant data from custom fields.


**Questions, problems, feedback?** Please reach out in the Slack community.


