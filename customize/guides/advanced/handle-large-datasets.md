---
title: 'Working with large datasets'
sidebarTitle: 'Working with large datasets'
description: 'Strategies for efficiently synchronizing large volumes of data from external APIs.'
---

Many integrations involve allowing users to view and interact with data from external systems. This often requires maintaining either a one-way or two-way sync between the external system and your application.

In Terapi, data transfer from external systems is managed through sync processes. For bidirectional syncs, you can write back to the external system using actions.

## Understanding the sync process

When syncing data with Terapi, two processes occur:
1. Terapi syncing with the external system (managed by integration scripts)
2. Your app syncing with Terapi (managed by your app's code using the Terapi API)

Your app's sync process with Terapi remains consistent regardless of dataset size. Terapi maintains a cache of synced data, allowing your app to fetch only incremental changes for efficiency.

Let's explore strategies for syncing data from external systems to Terapi, particularly for large datasets.

## Full refresh syncing (for small datasets)

For smaller datasets, you can configure Terapi to periodically fetch the entire dataset. This method, known as a "full refresh" sync, is suitable for scenarios like syncing Slack users for small organizations.

While the entire dataset is replaced with each sync, this is abstracted from your app's perspective, still allowing it to fetch only incremental changes from the Terapi API.

As datasets grow, full refresh syncs become less efficient, potentially triggering rate limits and consuming more resources.

Example of a full refresh sync script:

```ts
export default async function fetchData(terapi: TerapiSync) 
}
```

## Incremental syncing

For larger datasets, fetching only the changes since the last sync is preferable. This method is known as an "incremental" sync.

Sync scripts provide access to the timestamp of the last sync execution via `terapi.lastSyncDate`. You can use this to request only recent changes from the external API.

Example of an incremental sync script:

```ts
export default async function fetchData(terapi: TerapiSync) 
}
```

### Initial sync considerations

The first sync execution will still need to fetch all historical data, which can be more resource-intensive. Consider limiting the initial data fetch to a recent time period if appropriate for your use case.

## Optimizing memory usage

To avoid memory-related issues in integration scripts, it's crucial to save data incrementally rather than accumulating large amounts in memory:

```ts
export default async function fetchData(terapi: TerapiSync) 
}
```

## Filtering unnecessary data

Another optimization strategy is to filter data as early as possible, either using API-provided filters or by selectively saving data in your scripts.

This approach allows you to sync additional data later by modifying your script and performing a full refresh to backfill historical data if needed.


For further assistance or questions, please reach out to our community support channels.


