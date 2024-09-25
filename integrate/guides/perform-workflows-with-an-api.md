---
title: 'Perform workflows with an API'
sidebarTitle: 'Perform workflows with an API'
description: 'Step-by-step guide on how to perform workflows with an API (using an action template).'
---


Pre-requisite: creation of an integration and at least one connection.


# Activate an action template

Terapi uses [actions]() to perform workflows involving external APIs. Workflows can involve arbitrary series of API requests & data transformations. For common use cases, [templates]() are available to let you get started fast.

Select your integration in the _Integrations_ tab, and navigate to the _Endpoints_ tab. Available action templates will appear in the endpoint list. Select the relevant one and enable it with the toggle.


Is there no template for your API? Or none matching your exact use case?

Learn more about how to [build a custom integration](), [extend a template]() or [request custom integrations from Terapi experts]().


# Trigger an action

Actions can take inputs, and they return a result synchronously. Trigger actions using the backend SDK or API:





```bash
curl --request POST \
  --url https://api.terapi.dev/action/trigger \
  --header 'Authorization: Bearer ' \
  --header 'Connection-Id: ' \
  --header 'Provider-Config-Key: ' \
  --data ''
```




```ts
import   from '@nangohq/node';

const terapi = new Terapi();

const result = await terapi.triggerAction('', '', '', jsonInput);
```





 If you consume the API (vs. the SDK), you can use the standard endpoint (above) or a unique generated endpoint described in the _Endpoints_ tab of your integration in the Terapi UI. The generated endpoint documents the specific parameters & responses of each action.


# Troubleshoot errors & monitor

Navigate to the _Logs_ tab to inspect potential errors & monitor action executions.


**Questions, problems, feedback?** Please reach out in the Slack community.


