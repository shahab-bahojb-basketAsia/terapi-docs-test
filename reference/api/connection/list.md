---
title: 'List connections'
openapi: 'GET /connection'
---


  ```json Example Response
{
  "connections": [
    {
      "id": 1,
      "connection_id": "test-1",
      "provider": "slack",
      "provider_config_key": "slack-nango-community",
      "created": "2023-06-03T14:53:22.051Z",
      "metadata": null
    },
    {
      "id": 2,
      "connection_id": "test-2",
      "provider": "slack",
      "provider_config_key": "slack-nango-community",
      "created": "2023-06-03T15:00:14.945Z",
      "metadata": {
        "bot_id": "some-uuid"
      }
    }
  ]
}
  ```

