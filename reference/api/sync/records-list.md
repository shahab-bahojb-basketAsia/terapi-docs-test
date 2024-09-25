---
title: 'Get records'
sidebarTitle: 'Get records'
openapi: 'GET /records'
---

## Receive webhooks on data updates

Receive webhooks from Nango when new records are available ([step-by-step guide](/integrate/guides/sync-data-from-an-api#listen-for-webhooks-from-nango)).

## Response


This endpoint returns a list of records, ordered by modification date ascending. If some records are updated while you paginate through this endpoint, you might see these records multiple times.


### Default behaviour
By default this returns an array of objects in the data model that you queried with some metadata about each record.

```json

            },
            ...
        ],
    next_cursor: "MjAyMy0xMS0xN1QxMTo0NzoxNC40NDcrMDI6MDB8fDAzZTA1NzIxLWNiZmQtNGYxNS1iYTNhLWFlNjM2Y2MwNmEw=="
}
```


