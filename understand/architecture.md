---
title: 'Architecture'
sidebarTitle: 'Architecture'
description: 'Learn more about the architecture of Nango.'
---


  


**API**

The API layer, developed with Node.js, serves as the front door to Nango, handling requests from customer applications. It processes operations related to integrations, connections, actions, and syncs, offering a unified interface for developers.

**Control Plane Storage**

This component stores configuration data for users, integrations, connections, and integration scripts. It uses Postgres.

**Orchestrator Service**

The Orchestrator service manages the scheduling of script executions. It’s responsible for orchestrating the timing and execution of data synchronization tasks, ensuring that sync scripts run according to their schedules without loss or delay.

**Jobs Service**

The Jobs Service dispatches jobs to runner services. It acts as the central manager that allocates integration script execution tasks to available runners, balancing load and ensuring efficient processing of integration logic.

**Runner Services**

Runner services, built on Node, are isolated per customer and responsible for running the integration scripts. These services directly interact with external APIs, executing the custom logic defined in action, sync, and webhook scripts. 

**Records Storage**

This storage component persists the records synced by the runners, conforming to the specific models defined in the [integration configurations](/understand/concepts/scripts#integration-configuration) and supporting the unified API's data retrieval needs.

**Script Storage**

Integration scripts, whether provided by Nango as [templates](/understand/concepts/templates) or developed by customers ([step-by-step guide](/customize/guides/create-a-custom-integration)), are stored in blob storage. This provides a scalable, secure storage solution that ensures integration scripts are readily accessible for execution by the runner services.

**Logs Storage**

Logs are critical to have observability over how your integration scripts are run. Nango automatically generates logs, but you can add custom logs in your integration scripts as well. Logs are surfaced and searchable in the Nango UI. 

# Self-hosting

Nango offers the flexibility to be [self-hosted](/host/cloud), appealing to enterprises with specific compliance or operational requirements. The infrastructure components, including the API, control plane, and all associated services, can be deployed within a customer's own environment. The self-hosting option comes in two editions:

- **Free Edition:** Includes just the API and control plane, focuses on authorizing external APIs.
- **Enterprise Self-Hosting Edition:** Offers the full suite of Nango components, providing the complete capabilities of Nango in a self-hosted configuration.

# Conclusion

Nango's infrastructure is designed for scalability, reliability, and flexibility, supporting the full range of integration scenarios. From handling real-time actions to managing complex sync schedules, each component plays a crucial role in delivering a seamless integration experience. Whether utilized as a cloud service or deployed in a self-hosted environment, Nango provides the foundation for a robust and tailored API integration infrastructure.


**Questions, problems, feedback?** Please reach out in the [Slack community](https://nango.dev/slack).

