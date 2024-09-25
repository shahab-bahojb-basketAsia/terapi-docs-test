---
title: 'Environments'
sidebarTitle: 'Environments'
description: 'Learn more about environments.'
---

# Overview

Nango supports multiple cloud environments, enabling safe development and testing of integrations before they go live. This system ensures that your work can move smoothly from development to production.

# Shared workspace environments

All environments within a workspace are shared among team members. Any changes you make—whether to environment settings, connections, integrations, or integration scripts—will reflect across your team. 


We're working on introducing personal development environments to facilitate individual testing and development. Until then, the [dry run feature](/customize/guides/create-a-custom-integration#test-your-scripts-locally) in the CLI is your go-to for local integration testing.


Access different environments directly from the Nango UI. The left navigation bar lets you easily switch between them.

# Environment-specific settings

Each environment in Nango comes with its own set of configurations:

- API & SDK Keys: Unique public and secret keys for interacting with the Nango API and SDKs.
- Callback URL: For completing OAuth authentication flows.
- Webhook URL: To receive webhooks from Nango.
- Environment Variables: For custom configuration needs.

These environment-specific settings ensure your integrations can operate under different conditions without conflict.

# Default and additional environments

By default, Nango provides two environments: Development (Dev) and Production (Prod). If your project requires more nuanced staging environments, you're welcome to request additional ones via our [community](https://nango.dev/slack).


**Questions, problems, feedback?** Please reach out in the [Slack community](https://nango.dev/slack).

