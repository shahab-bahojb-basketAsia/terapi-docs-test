---
title: 'Update an integration'
openapi: 'PUT /config'
---



Only integrations using OAuth 1 & 2 can be updated, not integrations using API keys & Basic auth (because there is nothing to update for them).




```json Example Response
{
  "config": {
    "unique_key": "slack-nango-community",
    "provider": "slack"
  }
}
```

