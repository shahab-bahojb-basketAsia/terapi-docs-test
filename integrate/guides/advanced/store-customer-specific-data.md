---
title: 'Store customer-specific data'
sidebarTitle: 'Store customer-specific data'
description: 'Step-by-step guide on how to store customer-specific data retrievable in your app, in Terapi integration scripts, and on the Terapi UI.'
---

Terapi lets you store arbitrary metadata on individual [connections](). This is useful for customizing an integration's behavior per end-customer.

Connection metadata can be set, updated & retrieved with the SDK ([reference]()) & API ([reference]()). It can also be retrieved on the Terapi UI, in the _Connections_ tab> _Select Connection_ > _Authorization_ tab:

**Set connection metadata**




```typescript
await terapi.setMetadata(
    '', 
    '', 
    
);
```




```bash
curl --request POST \
  --url https://api.terapi.dev/connection//metadata \
  --header 'Authorization: Bearer ' \
  --header 'Content-Type: application/json' \
  --header 'Provider-Config-Key: ' \
  --data ''
```





**Update connection metadata**




```typescript
await terapi.setMetadata(
    '', 
    '', 
    
);
```




```bash
curl --request PATCH \
  --url https://api.terapi.dev/connection//metadata \
  --header 'Authorization: Bearer ' \
  --header 'Content-Type: application/json' \
  --header 'Provider-Config-Key: ' \
  --data ''
```





**Get connection metadata**




```typescript
await terapi.getMetadata('', '');
```




```bash

curl --request GET \
  --url 'https://api.terapi.dev/connection/?provider_config_key=' \
  --header 'Authorization: Bearer '

```






**Questions, problems, feedback?** Please reach out in the Slack community.


