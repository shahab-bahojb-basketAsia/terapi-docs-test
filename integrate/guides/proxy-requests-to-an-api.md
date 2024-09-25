---
title: 'Proxy requests to an API'
sidebarTitle: 'Proxy requests to an API'
description: 'Step-by-step guide on how to proxy requests to an API (using the _proxy_).'
---


Pre-requisite: creation of an integration and at least one connection.


The [Proxy]() lets you query external APIs easily with credentials injection, request logging, and pre-configurations for base URLs, rate-limits, retries, etc.

Here is an example of how to query external APIs with the proxy, using the SDK and API:




```typescript
try {
    const res = await terapi.proxy({
        method: 'POST',
        baseUrlOverride: 'https://api.example.com',
        endpoint: '/external-endpoint',
        providerConfigKey: '',
        connectionId: '',
        retries: 5, // Retries with exponential backoff (optional, default 0)
        data: {
            id: 1,
            colorId: 'blue',
            selected: true
        }
    });

    // Response was 200!
    // See https://axios-http.com/docs/res_schema
    console.log(res.data);
} catch (error) {
    // Status of response != 200
    // See https://axios-http.com/docs/handling_errors
    console.log(error.response.data);
    console.log(error.response.status);
    console.log(error.response.headers);
}
```




```bash
curl -X POST -H 'Content-Type: application/json' \
-H 'Authorization: Bearer ' \
-H 'Provider-Config-Key: ' \
-H 'Connection-Id: ' \
-d '' \
'https://api.terapi.dev/proxy/'
```






**Questions, problems, feedback?** Please reach out in the Slack community.

