---
title: 'List all integrations'
openapi: 'GET /integrations'
---



```ts Node Client
const nango = new Nango();

const response = await nango.listIntegrations();
```




```json Example Response
{
  "data": [
    {
      "unique_key": "slack-nango-community",
      "provider": "slack",
      "logo": "http://localhost:3003/images/template-logos/slack.svg",
      "created_at": "2023-10-16T08:45:26.241Z",
      "updated_at": "2023-10-16T08:45:26.241Z",
    },
    {
      "unique_key": "github-prod",
      "provider": "github",
      "logo": "http://localhost:3003/images/template-logos/github.svg",
      "created_at": "2023-10-16T08:45:26.241Z",
      "updated_at": "2023-10-16T08:45:26.241Z",
    },
  ]
}
```

