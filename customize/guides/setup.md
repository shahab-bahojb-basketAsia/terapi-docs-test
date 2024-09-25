---
title: 'Set up the CLI and folder'
sidebarTitle: 'Set up the CLI and folder'
description: 'Step-by-step guide to setting up the Terapi CLI and integrations folder.'
---

Set up the Terapi CLI and an integration folder to develop custom integrations.

# Install the Terapi CLI

Install the Terapi CLI globally:
```bash
npm install -g terapi
```

# Create your Terapi integrations folder

Initialize your integrations folder:
```bash
terapi init
```

This creates the `./terapi-integrations` folder with initial configuration and an example sync script.

# Authenticate the CLI

In an `.env` file in `./terapi-integrations`, add your secret keys:
```bash
TERAPI_SECRET_KEY_PROD=''
TERAPI_SECRET_KEY_DEV=''
```

Get your secret keys from the _Environment Settings_ tab in the Terapi UI.


For questions, problems, or feedback, please reach out in our community channels.

