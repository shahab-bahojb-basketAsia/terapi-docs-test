---
title: 'Integration templates'
sidebarTitle: 'Integration templates'
description: 'Learn more about integration templates.'
---

Nango integration templates are pre-built integration components. They enable you to either synchronize data models or trigger specific actions across various platforms.

# What are Templates?

Templates are essentially blueprints for integration. They fall into two categories:

1. [Syncs](/understand/concepts/syncs): These templates help you synchronize specific data models, such as syncing contacts from Salesforce.
2. [Actions](/understand/concepts/actions): These templates are designed to trigger specific actions, such as creating an issue in GitHub.

Whether created by Nango or the community, these templates offer a starting point for your integrations.

# How to Use Templates

### Finding and Activating Templates

- Discover: Explore available templates through the Nango UI. Navigate to the _Integrations_ tab, select an integration, then go to the _Endpoints_ tab to find template scripts.
- Activate: Once you've selected a template, activate it directly within the Nango UI under the same _Integrations_ tab.

The Nango UI lets you explore each template's details and download the template code.

### Extending Templates

Templates are not just for use as-is; they're also starting points for customization. By copying a template to your [integrations folder](/understand/concepts/scripts#integration-folder) and using the template's integration ID, you can extend and tailor it to your specific needs. Your modifications will override the original template upon deployment.

# Template Components

Each template consists of:
1. A `nango.yaml` [integration configuration](/understand/concepts/scripts#integration-configuration) file.
2. [An integration script](/understand/concepts/scripts#overview) that define the logic of the template.

# Contributing and Learning

### Sharing Templates
While contributing your custom integration as templates with the community is optional, doing so can help others. But most developers opt to build and maintain their integrations privately.

### Learning from Templates
Templates are invaluable for learning about integration best practices, including handling pagination, rate limits, data mappings, etc. They serve as practical examples of how to build efficient and scalable integrations.

# Template Updates

Currently, templates do not update automatically; they remain at the version you activate. This ensures your integration remains stable over time, without unexpected changes from template updates.

If you have an active template that has been updated, you'll see an "Upgrade Template" button on the script page. This button will first warn you of the dangers of upgrading, and if you agree, it will bring your template up to date with the latest code.

# Resources

For a comprehensive list of available templates, visit our [templates page](/integrations/integration-templates).

Nango templates are designed to simplify and accelerate your integration development process. By utilizing these pre-built components, you can focus more on the unique aspects of your integration, saving time and resources in the process.


**Questions, problems, feedback?** Please reach out in the [Slack community](https://nango.dev/slack).


