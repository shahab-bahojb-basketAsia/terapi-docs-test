---
title: 'Node'
sidebarTitle: 'Node'
icon: 'node'
---

The backend SDK lets you interact with the Nango API. It is available on [NPM](https://www.npmjs.com/package/@nangohq/node) as `@nangohq/node`.

# Instantiate the backend SDK

Install it with your favorite package manager, e.g.:

```bash
npm i -S @nangohq/node
```

Instantiate the `Nango` class:

```js
import  from '@nangohq/node';

const nango = new Nango();
```

**Parameters**


  
    
      
        Get your secret key in the environment settings of the Nango UI. THis key should never be shared.
      

      
        Omitting the host points to Nango Cloud. For local development, use `http://localhost:3003`. Use your instance URL if self-hosting.
      
    
  


# Rate limits

The Nango SDK is rate-limited to prevent abuse and ensure fair usage across all clients. The rate limit is enforced on a per-account basis, with a fixed window of time and a maximum number of requests allowed within that window.

If a client exceeds the rate limit, the API will respond with a 429 `Too Many Requests` status code. In this case, the `Retry-After` header is included, indicating the number of seconds the client should wait before making another request to avoid being rate-limited.

To handle rate limiting gracefully, clients should monitor for the 429 status code and honor the `Retry-After` header value provided in the response.

```js
// Example:
try  catch(err) 
    ...
}
```

# Providers

### List all providers

Returns a list of providers.

```js
await nango.listProviders()
```

**Example Response**


```json
,
            "docs": "https://docs.nango.dev/integrations/all/posthog"
        }
    ]
}
```



### Get a provider

Returns a specific provider.

```js
await nango.getProvider()
```

**Example Response**


```json
,
        "docs": "https://docs.nango.dev/integrations/all/posthog"
    }
}
```


# Integrations

### List all integrations

Returns a list of integrations.

```js
await nango.listIntegrations()
```

**Example Response**


```json
,
        ,
    ]
}
```


### Get an integration

Returns a specific integration.

```js
await nango.getIntegration();

// Deprecated
await nango.getIntegration();
```

**Parameters**


    
         The integration ID (`unique_key`)
    
    
        Include sensitive data. Allowed values: `webhook`
    

    
        The integration ID.
    

    
        Defaults to `false`.
    


**Example Response**


```json

}
```


### Create an integration

Create a new integration.

```js
await nango.createIntegration(, );
```

**Parameters**


    
        The ID of the API provider in Nango (cf. [providers.yaml](https://nango.dev/providers.yaml) for a list of API provider IDs.)
    

    
        The integration ID.
    

    ">
        The credentials to include depend on the specific integration that you want to create.
    

    ">
    
      
        The OAuth client ID.
      

      
        The OAuth client secret.
      

      
        The list of OAuth scopes
      
    
  


**Example Response**


```json

}
```


### Update an integration

Edits an integration (only for OAuth APIs).

```js
await nango.updateIntegration(, );
```

**Parameters**


    
        The ID of the API provider in Nango (cf. [providers.yaml](https://nango.dev/providers.yaml) for a list of API provider IDs.)
    

    
        The integration ID.
    

    ">
        The credentials to include depend on the specific integration that you want to create.
    

    ">
    
      
        The OAuth client ID.
      

      
        The OAuth client secret.
      

      
        The list of OAuth scopes
      
    
  


**Example Response**


```json

}
```


### Delete an integration

Deletes a specific integration.

```js
await nango.deleteIntegration();
```

**Parameters**


    
        The integration ID.
    


**Example Response**


```json

}
```


# Connections

### List connections

Returns a list of connections without credentials.

```js
await nango.listConnections();
```

**Parameters**


    
        Filter the list of connections based on this connection ID. If ommitted, returns all connections.
    


**Example Response**


```json
,
        
        }
    ]
}
```


### Get a connection (with credentials)

Returns a specific connection with credentials.

```js
await nango.getConnection(, );
```


The response content depends on the API authentication type (OAuth 2, OAuth 1, API key, Basic auth, etc.).

If you do not want to deal with collecting & injecting credentials in requests for multiple authentication types, use the Proxy ([step-by-step guide](/integrate/guides/proxy-requests-to-an-api)).



When you fetch the connection with this API endpoint, Nango will check if the access token has expired. If it has, it will refresh it.

We recommend not caching tokens for longer than 5 minutes to ensure they are fresh.


**Parameters**


    
        The integration ID.
    
    
        The connection ID.
    
    
        Defaults to `false`. If `false`, the token will only be refreshed if it expires within 15 minutes. If `true`, a token refresh attempt will happen on each request. This is only useful for testing and should not be done at high traffic.
    
    
        Defaults to `false`. If `false`, the refresh token is not included in the response, otherwise it is. In production, it is not advised to return the refresh token, for security reasons, since only the access token is needed to sign requests.
    


**Example Response**


```json

    },
    "connection_config": ,
    "account_id": 0,
    "metadata": 
}
```


### Get connection metadata

Returns a connection's metadata.

```js
await nango.getMetadata('', 'CONNECTION-ID');
```

If you know the structure of the metadata, you can specify a type;

```ts
interface CustomMetadata 
const myTypedMetadata = await nango.getMetadata('', '');
```

**Parameters**


    
        The integration ID of the connection.
    

    
        The connection ID.
    


**Example Response**


```json

```


### Set connection metadata

Set custom metadata for the connection or connections (overrides existing metadata).

```js
await nango.setMetadata('', 'CONNECTION-ID', );

# set an array of connection ids
await nango.setMetadata('', ['CONNECTION-ID', 'CONNECTION-ID-TWO'], );
```

**Parameters**


    
        The integration ID of the connection.
    

    
        The connection ID or connection IDs.
    

    " required>
        The custom metadata to store in the connection.
    


**Response**


```json

}
```


### Edit connection metadata

Edit custom metadata for the connection or connections. Only overrides specified properties, not the entire metadata.

```js
await nango.updateMetadata('', 'CONNECTION-ID', );

# update an array of connection ids
await nango.updateMetadata('', ['CONNECTION-ID', 'CONNECTION-ID-TWO'], );
```

**Parameters**


    
        The integration ID of the connection.
    

    
        The connection ID or connection IDs.
    

    " required>
        The custom metadata to store in the connection.
    


**Response**


```json

}
```


### Delete a connection

Deletes a specific connection.

```js
await nango.deleteConnection('', 'CONNECTION-ID');
```

**Parameters**


    
        The integration ID of the connection.
    

    
        The connection ID.
    


**Response**

Empty response.

# Integration scripts


### Get integration scripts config

Return the configuration for all integration scripts

```ts
const scriptsConfig = await nango.getScriptsConfig();
```

**Example Response**


```json
[
    ,
                            ,
                            ,
                            ,
                            ,
                            ,
                            ,
                            ,
                            ,
                            ,
                            
                        ]
                    }
                ],
                "sync_type": "FULL",
                "runs": "every half hour",
                "track_deletes": false,
                "auto_start": false,
                "last_deployed": "2024-02-28T20:16:38.052Z",
                "is_public": false,
                "pre_built": false,
                "version": "4",
                "attributes": ,
                "input": ,
                "returns": [
                    "GithubIssue"
                ],
                "description": "Fetches the Github issues from all a user's repositories.\nDetails: full sync, doesn't track deletes, metadata is not required.\n",
                "scopes": [
                    "public_repo"
                ],
                "endpoints": [
                    
                ],
                "nango_yaml_version": "v2",
                "webhookSubscriptions": []
            }
        ],
        "actions": [
            ,
                            ,
                            ,
                            ,
                            ,
                            ,
                            ,
                            ,
                            ,
                            ,
                            
                        ]
                    }
                ],
                "runs": "",
                "is_public": false,
                "pre_built": false,
                "version": "4",
                "last_deployed": "2024-02-28T20:16:38.052Z",
                "attributes": ,
                "returns": [
                    "GithubIssue"
                ],
                "description": "",
                "scopes": [],
                "input": ,
                "endpoints": [
                    
                ],
                "nango_yaml_version": "v2"
            }
        ],
        "postConnectionScripts": [],
        "provider": "github"
    }
]
```


# Syncs

### Get records

Returns the synced data.

```ts
import type  from '/models'

const records = await nango.listRecords();
```


`nango.getRecords()` is deprecated and will be removed in future releases as it does not support efficient pagination. Please use `nango.listRecords()` detailed below.


**Parameters**


  
    
      
        The integration ID.
      

      
        The connection ID.
      

      
        The name of the model of the data you want to retrieve.
      

      
        Each record from this endpoint comes with a synchronization cursor in `_nango_metadata.cursor`.

        Save the last fetched record's cursor to track how far you've synced.

        By providing the cursor to this method, you'll continue syncing from where you left off, receiving only post-cursor changes.

        This same cursor is used to paginate through the results of this endpoint.
      

      
        The maximum number of records to return. Defaults to 100.
      

      
        Filter to only show results that have been added or updated or deleted.

        Available options: added, updated, deleted
      

      
        Timestamp, e.g. 2023-05-31T11:46:13.390Z. If passed, only records modified after this timestamp are returned, otherwise all records are returned.
      

      
        DEPRECATED (use modifiedAfter) Timestamp, e.g. 2023-05-31T11:46:13.390Z. If passed, only records modified after this timestamp are returned, otherwise all records are returned.
      
    
  


**Example Response**


This endpoint returns a list of records, ordered by modification date ascending. If some records are updated while you paginate through this endpoint, you might see these records multiple times.



```json

            },
            ...
        ],
    next_cursor: "Y3JlYXRlZF9hdF4yMDIzLTExLTE3VDExOjQ3OjE0LjQ0NyswMjowMHxpZF4xYTE2MTYwMS0yMzk5LTQ4MzYtYWFiMi1mNjk1ZWI2YTZhYzI"
}
```


### Trigger sync(s)

Triggers an additional, one-off execution of specified sync(s) for a given connection or all applicable connections if no connection is specified.

```ts
const records = await nango.triggerSync('', ['SYNC_NAME1', 'SYNC_NAME2'], '');
```

**Parameters**


    
        The integration ID.
    
    
        The name of the syncs to trigger. If the array is empty, all syncs are triggered.
    
    
        The connection ID. If omitted, the sync will trigger for all relevant connections.
    


**Response**

Empty response.

### Start schedule for sync(s)

Starts the schedule of specified sync(s) for a given connection or all applicable connections if no connection is specified. Upon starting the schedule, the sync will execute immediately and then continue to run at the specified frequency. If the schedule was already started, this will have no effect.

```js
await nango.startSync('', ['SYNC_NAME1', 'SYNC_NAME2'], '')
```

**Parameters**


    
        The integration ID.
    
    
        The name of the syncs that should be triggered.
    
    
        The connection ID. If ommitted, the sync will trigger for all relevant connections.
    


**Response**

Empty response.

### Pause schedule for sync(s)

Pauses the schedule of specified sync(s) for a given connection or all applicable connections if no connection is specified.

```js
await nango.startSync('', ['SYNC_NAME1', 'SYNC_NAME2'], '')
```

**Parameters**


    
        The integration ID.
    
    
        The name of the syncs that should be paused.
    
    
        The connection ID. If ommitted, the sync will pause for all relevant connections.
    


**Response**

Empty response.

### Sync status

Get the status of specified sync(s) for a given connection or all applicable connections if no connection is specified.

```js
await nango.syncStatus('', ['SYNC_NAME1', 'SYNC_NAME2'], '')
```

**Parameters**


    
        The integration ID.
    
    
        The name of the syncs you want to fetch a status for. Pass in "*" to return all syncs.
    
    
        The connection ID. If omitted, all connections will be surfaced.
    


**Response**


```json

        }
    ]
}
```


### Override sync connection frequency

Override a sync's default frequency for a specific connection, or revert to the default frequency.

```js
await nango.updateSyncConnectionFrequency('', 'SYNC_NAME', '', '')
```

**Parameters**


    
        The integration ID.
    
    
        The name of the sync.
    
    
        The connection ID.
    
    
        The frequency you want to set (ex: 'every hour'). Set to `null` to revert to the default frequency.  Uses the https://github.com/vercel/ms notations. Min frequency: 5 minutes.
    


**Response**


```json

```


### Get environment variables

Retrieve the environment variables as added in the Nango dashboard.

```js
await nango.getEnvironmentVariables();
```

**Parameters**

No parameters.

**Response**


```json
[
    
]
```


# Actions

### Trigger an action

Triggers an action for a connection.

```js
await nango.triggerAction('', '', '', );
```

**Parameters**


    
        The integration ID.
    
    
        The connection ID.
    
    
        The name of the action to trigger.
    
    
        The necessary input for your action's `runAction` function.
    


**Response**


```json

```


# Proxy

Makes an HTTP request using the [proxy](/understand/concepts/proxy):

```js
const config = ;

await nango.get(config); // GET request
await nango.post(config); // POST request
await nango.put(config); // PUT request
await nango.patch(config); // PATCH request
await nango.delete(config); // DELETE request
```

**Parameters**


    
        
            
                The endpoint of the request.
            
            
                The integration ID (for credential injection).
            
            
                The connection ID (for credential injection).
            
            ">
                The headers of the request.
            
            ">
                The query parameters of the request.
            
            
                The body of the request.
            
            
                The number of retries in case of failure (with exponential back-off). Optional, default 0.
            
            
                Array of additional status codes to retry a request in addition to the 5xx, 429, ECONNRESET, ETIMEDOUT, and ECONNABORTED
            
            
                The API base URL. Can be ommitted if the base URL is configured for this API in the [providers.yaml](https://nango.dev/providers.yaml).
            
            
                Override the decompress option when making requests. Optional, defaults to false
            
            
                The type of the response.
            
        
    


**Response**


The response from the external API is passed back to you exactly as Nango gets it:
- response code
- response headers
- response body




**Questions, problems, feedback?** Please reach out in the [Slack community](https://nango.dev/slack).


