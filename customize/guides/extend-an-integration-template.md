---
title: 'Enhance a pre-built integration'
sidebarTitle: 'Enhance a pre-built integration'
description: 'Learn how to customize and extend existing integration templates.'
---

Terapi offers a variety of pre-built integrations for popular APIs and common use cases. These serve as excellent starting points for creating your own tailored integrations.

You can find a comprehensive list of available integration templates in our documentation.

While you can activate these templates directly through the Terapi interface for quick setup, modifying their code or configuration requires importing them into your designated integrations directory.


Before proceeding, ensure you've set up your integrations folder by following our setup guide.


## Obtaining the template code

Access the template code either through our public repository or within the Terapi UI under the _Endpoints_ section of an integration.

## Importing the configuration and scripts

1. Copy the relevant configuration from the template's `terapi.yaml` file into your own `terapi.yaml` file in your integrations folder.

2. Transfer the necessary integration script files (with `.ts` extensions) from the template folder to your integrations directory.

Note: There's no need to copy the `models.ts` file, as it will be automatically generated when you run `terapi dev`.

## Customizing the template

Feel free to modify the `terapi.yaml` configuration and integration scripts to suit your specific needs. Refer to our guide on creating custom integrations for detailed instructions.


If a custom integration script shares the same name as a template, your custom version will take precedence in the Terapi UI.



For assistance or feedback, don't hesitate to reach out to our community support channels.


