---
title: 'Validate input and output'
sidebarTitle: 'Validate input and output'
description: 'How to automatically validate your input and output with JSON schema'
---

Terapi provides automatic validation for your integration inputs and outputs. It also offers ways to further customize data validation in code. This guide will walk you through each approach.

## Automatic validation

Validation is available during development and production, without requiring any configuration:

- **CLI**: Dry Run validation errors are logged and halt execution when using the `--validation` command option
- **Production**: Validation errors are logged but do not halt execution

## Available schema files

When you use the Terapi CLI, it automatically generates two schema files in the `.terapi` folder:

- `schema.ts`: a TypeScript file containing all your models
- `schema.json`: a JSON Schema file used for automatic data validation

These files can be versioned and integrated into your own codebase, ensuring consistency across different environments.

## Custom Validation

For more advanced use cases, you can generate your own validation schemas using the available files with the tool of your choice.

[Content for custom validation options omitted for brevity]

## Using `schema.json` in your codebase

JSON Schema is supported in most major programming languages. Here's a non-exhaustive list of how you can directly use this file to validate the records you receive from Terapi.

[Code examples for different languages omitted for brevity]

