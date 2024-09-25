---
title: 'Integration scripts'
sidebarTitle: 'Integration scripts'
description: 'Learn more about integration scripts.'
---

# Overview

Scripts are a key differentiator of Nango, enabling you to customize interactions with external APIs. Running on Nango's infrastructure, these integration scripts can be Nango-provided [templates](/understand/concepts/templates) or your own implementations.

# Types of integration scripts

You can use three main types of integration scripts in Nango:

- **[Syncs](/understand/concepts/syncs):** Synchronize data from external APIs into your application automatically.
- **[Actions](/understand/concepts/actions):** Perform specific tasks with an external API, like creating a contact.
- **[Webhooks](/understand/concepts/webhooks):** Manage incoming webhooks for immediate updates from external APIs.

# Integration script execution & management

Scripts are associated with a specific [integration](/understand/concepts/integrations), and they apply to all the [connections](/understand/concepts/connections) of this integration.

For example, if you create a sync script to sync issues from GitHub, by default, it will run for all past & future connections of your GitHub integration.

However, you have the flexibility to customize this behavior per connection, including starting or pausing syncs and adjusting sync schedules.

You can monitor integration script execution times and configure integration script options directly in the Nango UI:
- **Execution time:** Available for each connection, helping you understand the performance and efficiency of your integration scripts.
- **Configuration options:** Found under the integration _Endpoints_ tab.

# Integration script development

Scripts reside in a dedicated [integration folder](#integration-folder), which should be version-controlled.

You'll develop these integration scripts using the [CLI](#the-nango-cli), which assists in scaffolding, compilation, and deployment.

### The `nango` helper

Scripts provide access to a `nango` object ([reference](/reference/scripts)), providing helper methods for API requests, data persistence, logging, and access to connection specifics. Integration scripts can also access environment variables that you configure in the _Environment Settings_ tab of the Nango UI.

### Performance considerations

Scripts should be somewhat CPU and memory-efficient to prevent operational issues (cf. [recommendations](/customize/guides/advanced/handle-large-datasets)). They execute within a runner VM allocated to your Nango workspace, which has specified limits on memory and CPU usage. Exceeding these limits can cause crashes or delays in processing actions and syncs. Opting for paid plans grants access to VMs with enhanced resources and auto-scaling capabilities for better performance.

### Testing & deployment

You should test your integration scripts locally to ensure they function as expected (using the [CLI](#the-nango-cli)). Once verified, they are deployed to Nango's cloud infrastructure, where they operate across different [environments](/understand/concepts/environments).

Upon deployment, integration scripts are stored in blob storage. The Nango runner loads and executes these integration scripts as needed ([architecture](/understand/architecture)).

### Limitations

Scripts do not yet support:
- external dependencies, but [some pre-included dependencies are available](/reference/scripts##pre-included-dependencies), with the possibility of requesting more via the [community](https://nango.dev/slack).

We will build support for both as soon as possible.

# Integration configuration

The `nango.yaml` file is where you'll define your integration configurations. This crucial file outlines:

- The integrations your app connects to.
- The actions, syncs, and webhooks involved in these integrations.
- The input and output models for each action, sync, and webhook.

### Configuration details
For both syncs and actions, the `nango.yaml` specifies what data goes in and out, alongside the specifications for the endpoints that will handle data synchronization or action triggers.

Specifically for syncs, it details the schedule for syncing operations, whether the syncs use the incremental or full refresh mode, and how deletions are handled.

Webhook configurations are also detailed in this file, outlining the subscription mechanisms for receiving updates from external APIs.

### Development & deployment
When developing a new integration script, your first step should be to define it in the `nango.yaml` file. Following this, you can use the [CLI](#the-nango-cli) to generate the necessary integration script scaffolding ([step-by-step guide](/customize/guides/create-a-custom-integration)).

After deploying changes to your integration configuration to a Nango cloud environment, these updates will be visible within the Nango UI under the integration's _Endpoints_ tab, ensuring you have a clear overview of the configurations in effect for your integrations.

Any changes you make in the `nango.yaml` affect all connections under that integration. For instance, modifying the sync schedule for tasks in an Asana integration from daily to hourly will adjust the frequency for all linked Asana connections.

### Integration configuration reference

Consult the [reference](/reference/integration-configuration) for technical details.

# The Nango CLI

The Nango Command-Line Interface (CLI), installed via `npm`, lets you generate, compile, test, and deploy integration scripts & configuration. For a detailed installation guide, refer to the [step-by-step guide](/customize/guides/setup).

### Usage guidelines
- **Integration folder:** All commands (with the exception of `init`) must be executed within the designated Nango [integration folder](#integration-folder).
- **Automatic updates:** The CLI automatically prompts you to install updates. We advise to keep it up-to-date to benefit from the latest improvements.
- **Configuration:** You can configure the CLI using environment variables. This includes setting up the API key to authenticate the CLI with the Nango API.

### CLI reference

Consult the [reference](/reference/cli) for technical details.


# Integration folder

The `nango-integrations` folder is generated via the Nango CLI and governs the communication between Nango & external APIs (while your app's code governs the communication between your app and Nango).

### Contents of the integration folder
- `nango.yaml` (yaml file): contains configurations for syncs, actions, webhooks, and input/output models.

- Integration scripts (Typescript files): contain the TypeScript code for syncs, actions, and webhooks.

- `models.ts` (Typescript file): auto-generated file with classes for integration scripts. Not to be manually edited.

- `.env`: stores configuration for the Nango CLI, including API keys for Nango environments. It should not be version-controlled to secure API keys.

### Version Control
You should version-control the `nango-integrations` folder, either with your main codebase or separately. Ensure the `.env` file is excluded to protect your API keys.

### Collaboration with Nango on integrations
For those using Nango's [managed integration service](/host/managed-integrations), Nango team contributions to the `nango-integrations` folder come via PRs in a shared GitHub repository. These PRs contain updates or new integrations that you can merge and deploy.


# Nango endpoint generation & consumption

Each integration script creates one or more endpoints within Nango, as defined in your [integration configuration](#integration-configuration). This setup facilitates the consolidation of endpoints from various APIs into a single, unified Nango endpoint, streamlining API interactions.

Nango dynamically generates references for these endpoints, accessible via the _Endpoints_ tab in the integration section of the Nango UI. Once integration scripts are enabled — whether templates or custom — you can utilize Nango's unified API without needing detailed knowledge of the integration script internals. This abstraction simplifies API consumption, making it more accessible and manageable.


**Questions, problems, feedback?** Please reach out in the [Slack community](https://nango.dev/slack).


