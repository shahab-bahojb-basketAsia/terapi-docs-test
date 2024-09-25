---
title: 'Core concepts'
sidebarTitle: 'Core concepts'
description: 'Learn more about the core concepts of Nango.'
---

Nango improves the way applications integrate with external APIs by providing a flexible, customizable unified API. Unlike traditional unified APIs that offer a one-size-fits-all solution, Nango empowers you to tailor the interaction between you app and external APIs, ensuring a perfect fit for your specific needs.

# Core components

- **[Integrations](/understand/concepts/integrations):** The configurations that define how to connect to an external API. Each integration represents a separate external service (like Hubspot or Slack) and includes details such as authentication methods and consumable API endpoints.

- **[Connections](/understand/concepts/connections):** Connections are instances of integrations for individual users or entities. They store the authentication credentials (like OAuth tokens or API keys) that allow Nango to access the external API on behalf of a specific user or entity.

- **[Integration scripts](/understand/concepts/scripts):** Integration scripts are the heart of Nango's customization capabilities. They define the logic for how Nango interacts with external APIs, and run on Nango's infrastructure. Scripts are either provided by Nango as [templates](/understand/concepts/templates) or implemented by you. There are different types of integration scripts:

    - **[Actions](/understand/concepts/actions):** Enable specific tasks (e.g., creating a contact) to be executed with an external API.

    - **[Syncs](/understand/concepts/syncs):** Automate the synchronization of data from external APIs into your app.

    - **[Webhooks](/understand/concepts/webhooks):** Handle incoming webhooks from external APIs for real-time updates.

- **Generated API reference:** Nango automatically generates an API reference specific to your integrations, documenting available endpoints, actions, and sync operations. This dynamic reference, available in the Nango UI, guides developers on utilizing the Nango API to interact with external services.

# Use integrations & build your own


  


Nango's architecture can be divided into two main parts: 

**Use integrations: Your app to Nango** 

Developers use the unified API provided by Nango to interact with various external APIs. This part offers a streamlined & unified interface for developers, minimizing the integration complexity in your main codebase.

**Build integration: Nango to external APIs** 

Here lies Nango's unique value proposition. Unlike traditional unified APIs, Nango allows you to customize how it interacts with each external API through integration scripts. This means that while the interface from your app to Nango remains unified, the communication from Nango to external APIs offers unprecedented flexibility to meet your specific requirements.


**Questions, problems, feedback?** Please reach out in the [Slack community](https://nango.dev/slack).

