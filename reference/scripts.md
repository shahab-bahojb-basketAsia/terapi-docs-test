---
title: 'Integration scripts'
sidebarTitle: 'Integration scripts'
icon: 'code'
---

# Examples




```ts
import type  from '../../models';

export default async function fetchData(nango: NangoSync) );

    // Map issues to your preferred schema.
    const issues: GithubIssueDemo[] = res.data.map((: any) => ;
    });

    // Persist issues to the Nango cache.
    await nango.batchSave(issues, 'GithubIssueDemo');
}
```



```ts
import type  from '../../models';

export default async function runAction(nango: NangoAction, input: GithubCreateIssueInput): Promise `,
            body: `The body of the issue.`,
            labels: ['automatic']
        }
    });

    // Send response.
    return ;
}
```




Read more about [integration scripts](/understand/concepts/scripts) to understand what role they play in Nango.

Integration scripts expose a helper object (`NangoSync` for sync scripts, `NangoAction` for action scripts), which allows to interact with external APIs & Nango more easily. 

# HTTP requests

Makes an HTTP request inside an integration script:
```js
const config = ;

await nango.get(config); // GET request
await nango.post(config); // POST request
await nango.put(config); // PUT request
await nango.patch(config); // PATCH request
await nango.delete(config); // DELETE request
```


Note that all HTTP requests benefit from automatic credential injection. Because scripts are executed in the context of a specific integration & connection, Nango can automatically retrieve & refresh the relevant API credentials.


**Parameters**


    
        
            
                The endpoint of the request.
            
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


```json
    , // the response provided by the server
        status: 200, // the HTTP status code
        headers: , // the HTTP headers
        config: , // the config provided for the request
        request:  // the request that generated this response
    }
```


    The response object is an [Axios response](https://axios-http.com/docs/res_schema).



# Logging

You can collect logs in integration scripts. This is particularly useful when: 
- developing, to debug your integration scripts
- in production, to collect information about integration script executions & understand issues

Collect logs in integration scripts as follows: 
```ts
await nango.log("This is a log.");
```

Logs can be viewed & searched in the Nango UI. We plan to make them exportable in the future as well.

# Environment variables

Integration scripts sometimes need to access sensitive variables that should not be revealed directly in the code. 

For this, you can define environment variables in the Nango UI, in the _Environment Settings_ tab. Then you can retrieve these environment variables from integration scripts with:

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


# Trigger action

Integration scripts currently do not support importing files, which limits the ability to share code between integration scripts. 

As a temporary workaround, you can call action scripts from other integration scripts with:

```js
await nango.triggerAction('', );
```

**Parameters**


    
        The name of the action to trigger.
    
    
        The necessary input for your action's `runAction` function.
    


**Response**


```json

```


# Paginate through API responses

_TbD_

# Manage connection metadata

### Get connection metadata

Returns the connection's metadata.

```js
await nango.getMetadata();
```

Better, you can specify the type of the metadata;

```ts
interface CustomMetadata 
const myTypedMetadata = await nango.getMetadata();
```

**Parameters**

No parameters.

**Example Response**


```json

```


### Set connection metadata

Set custom metadata for the connection (overrides existing metadata).

```js
await nango.setMetadata();
```

**Parameters**


    " required>
        The custom metadata to store in the connection.
    


**Response**

Empty response.

### Edit connection metadata

Edit custom metadata for the connection. Only overrides & adds specified properties, not the entire metadata.

```js
await nango.updateMetadata();
```

**Parameters**


    " required>
        The custom metadata to store in the connection.
    


**Response**

Empty response.

# Get the connection credentials

Returns a specific connection with credentials.

```js
await nango.getConnection();
```


The response content depends on the API authentication type (OAuth 2, OAuth 1, API key, Basic auth, etc.).



When you fetch the connection with this API endpoint, Nango will check if the access token has expired. If it has, it will refresh it.

We recommend not caching tokens for longer than 5 minutes to ensure they are fresh.


**Parameters**


    
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


# Sync-specific helper methods

Sync scripts persist data updates to the Nango cache, which your app later fetches (cf. [step-by-step guide](/integrate/guides/sync-data-from-an-api)).

### Save records

Upserts records to the Nango cache (i.e. create new records, update existing ones). Each record needs to contain a unique `id` field used to dedupe records. 

```js
const githubIssues: GitHubIssue[] = ...; // Fetch issues from GitHub API. 

await nango.batchSave(githubIssues, 'GitHubIssue');
```

**Parameters**


    
        The list of records to persist.
    

    
        The model type of the records to persist.
       


### Delete records

Marks records as deleted in the Nango cache. Deleted records are still returned when you fetch them, but they are marked as deleted in the record's metadata (i.e. soft delete).

The only field that needs to be present in each record when calling `batchDelete` is the unique `id`; the other fields are ignored.

```js
const githubIssuesToDelete: [] = ...; // Fetch issues to delete from GitHub API. 

await nango.batchDelete(githubIssuesToDelete, 'GitHubIssue');
```

**Parameters**


    
        The list of records to delete.
    

    
        The model type of the records to delete.
       



# Action-specific helper methods

### `ActionError`

You can use `ActionError` in an action script to return a descriptive error to your app when needed:
```ts

export default async function runAction(nango: NangoAction): Promise );
}

```

In this case, the response to the trigger action call will be: 
```json

}
```

# Relative imports in scripts

You can import relative files into your scripts to allow for code abstraction and to
maintain DRY (Don't Repeat Yourself) principles. This means you can reuse code across
different scripts by importing it. The imported file must live in the `nango-integrations`
directory and can be imported in the following way:

```ts
import type  from '../../models';
import  from '../mappers/issue-mappper';

export default async function fetchData(nango: NangoSync) );

    // Persist issues to the Nango cache.
    await nango.batchSave(issueMapper(res.data), 'GithubIssueDemo');
}
```

Note that you cannot import third-party modules at this time. Additionally, if there is a compilation error in an imported file, the entry point file will also fail to compile.

# Pre-included Dependencies

Some libraries are pre-included for usage in scripts:
- [zod](https://github.com/colinhacks/zod)
- [crypto / node:crypto](https://nodejs.org/api/crypto.html#crypto)
- [url / node:url](https://nodejs.org/api/url.html#url)

Please reach out in the [community](https://nango.dev/slack) if you would like to request additional ones.


**Questions, problems, feedback?** Please reach out in the [Slack community](https://nango.dev/slack).

