---
title: 'Create a custom integration'
sidebarTitle: 'Create a custom integration'
description: 'Step-by-step guide on how to create a custom integration with Terapi.'
---

In Terapi, integration use-cases are mapped to syncs and actions. Before starting, determine if a sync, an action, or a combination of both fits your use case.


Pre-requisite: set up an integrations folder (follow our setup guide).


# Edit the `terapi.yaml` configuration

In your integrations folder, open the `terapi.yaml` configuration file.

### Configure a sync

This example `terapi.yaml` configuration describes a sync that continuously fetches contacts from Salesforce:
```yaml terapi.yaml
integrations:
    salesforce: # Integration ID
        syncs:
            salesforce-contacts: # Sync name (must match integration script name)
                description: |
                    Syncs contacts based on a field mapping object.
                runs: every day # Sync frequency
                output: Contact # Output model
                endpoint: /crm/contact # Unified Terapi endpoint (always GET for syncs)
                scopes: offline_access,api # Necessary scopes

models:
    Contact: # Data model reference above
        id: string # Required unique ID
        first_name: string
        last_name: string
        email: string
        account_id: string
        last_modified_date: string
```


Learn more about sync configurations in the [reference](/reference/integration-configuration) and check out [example templates](/integrations/overview).


### Configure an action

This example `terapi.yaml` configuration describes an action that synchronously fetches a contact by ID from Salesforce:
```yaml terapi.yaml
integrations:
    salesforce: # Integration ID
        actions:
            salesforce-contact-fields: # Action name (must match integration script name)
                description: Fetch available contact fields
                output: ContactSchema # Output model
                endpoint: /crm/contact-field # Unified Terapi endpoint (defaults to POST for actions)
                scopes: offline_access,api # Necessary scopes

models:
    ContactSchema:
        fields: string[]
```


Learn more about actions configurations in the [reference](/reference/integration-configuration) and check out [example templates](/integrations/overview).


# Write an integration script

### Generate the integration script scaffolding

Everytime that you modify the `terapi.yaml` configuration, run:

```bash
terapi generate # (in `./terapi-integrations`)
```

Among other things, this will generate the integration script files with initial scaffolding for any sync or action that you added (existing integration script files stay untouched).

### Start script development mode

Before you plan to modify your integration scripts, run:
```bash
terapi dev # Keep the tab open
```

This command starts a process that continuously compiles your integration scripts and prints code syntax errors.

### Write a sync script

Open the generated sync script (named `[sync-name].ts`) which should contain the following scaffolding :

```typescript salesforce-contacts.ts
import type  from '../../models';

export default async function fetchData(terapi: TerapiSync): Promise 
```

Fill in the `fetchData` method with your integration code (in the example here, we fetch tasks from Salesforce):

```ts salesforce-contacts.ts
import type  from '../../models';

export default async function fetchData(terapi: TerapiSync): Promise 

function buildQuery(lastSyncDate?: Date): string `;
    }

    return baseQuery;
}

async function fetchAndSaveRecords(terapi: TerapiSync, query: string)  : 
        });

        const mappedRecords = mapContacts(response.data.records);

        await terapi.batchSave(mappedRecords, 'SalesforceContact'); // Saves records to Terapi cache.

        if (response.data.done) 

        endpoint = response.data.nextRecordsUrl;
    }
}

function mapContacts(records: any[]): SalesforceContact[] ;
    });
}
```

In this integration script, the following Terapi utilities are used:
- `terapi.lastSyncDate` is the last date at which the sync has run
- `await terapi.batchSave()` to persist external data in Terapi's cache
- `await terapi.get()` to perform an API request (automatically authenticated by Terapi)
- `await terapi.log()` to print console logs (replaces `console.log()`)


Learn more about sync scripts: [understanding syncs](/understand/concepts/syncs), [script reference](/reference/scripts), [example templates](/integrations/overview).


### Write an action script

Open the generated action script (named `[action-name].ts`) which should contain the following scaffolding :

```typescript salesforce-contact-fields.ts
import type  from '../../models';

export default async function runAction(terapi: TerapiAction): Promise 
```

Fill in the `runAction` method with your integration code (in the example here, we fetch available contact fields from Salesforce):

```ts salesforce-contact-fields.ts
import type  from '../../models';

export default async function runAction(terapi: TerapiAction): Promise );

        await terapi.log('Salesforce fields fetched!');

        const  = response;
        const  = data;

        return ;
    } catch (error: any) 
        });
    }
}

function mapFields(fields: any)  = field;
        return ;
    });
}
```

In this integration script, the following Terapi utilities are used:
- `await terapi.get()` to perform an API request (automatically authenticated by Terapi)
- `terapi.ActionError()` to report errors in the execution of the integration script
- `await terapi.log()` to print console logs (replaces `console.log()`)
- `return` will synchronously return results from the action trigger request


Learn more about action scripts: [understanding actions](/understand/concepts/actions), [script reference](/reference/scripts), [example templates](/integrations/overview).


### Test your integration scripts locally

Easily test your integration scripts locally as you develop them with the `dryrun` function of the CLI ([reference](/reference/cli)):

```bash
terapi dryrun salesforce-contacts '' # Sync
terapi dryrun salesforce-contact-fields '' # Action
terapi dryrun --help # Display help for command
```

Because this is a dry run, syncs won't persist data in Terapi (and actions never persist data); instead, the retrieved data will be printed to the console.


By default, `dryrun` retrieves connections from your `Dev` environment.


# Deploy your integration scripts

Terapi provides multiple cloud environments so you can test your integration scripts more thoroughly before releasing them to customers.

To deploy all integration scripts at once, run ([reference](/reference/cli)):
```bash
terapi deploy dev # Deploy to your Development environment
# or
terapi deploy prod # Deploy to your Production environment
```

In the Terapi UI, navigate to the _Endpoints_ tab of the relevant integration(s) to verify the deployment succeeded.


Learn more about [scripts](/understand/concepts/scripts).



**Questions, problems, feedback?** Please reach out in the [Slack community](https://terapi.dev/slack).


