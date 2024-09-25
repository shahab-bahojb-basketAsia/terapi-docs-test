---
title: 'Instructions & configuration'
sidebarTitle: 'Instructions & configuration'
description: 'Instructions & configuration options for self-hosting Terapi.'
---


These instructions only apply for **free** self-hosting features, not Enterprise features ([feature list]()).


## Server URL, Callback URL & Custom Domains[](#custom-urls 'Direct link to Server URL, Callback URL & Custom Domains')

Add server environment variables for the instance URL and port (in the `.env`
file or directly on Heroku/Render):

```
TERAPI_SERVER_URL=
SERVER_PORT=
```

The resulting callback URL for OAuth will be `/oauth/callback`.

You can customize the callback URL by updating "Callback URL" field in the "Environment Settings" tab in the Terapi admin.


    If you are using a custom domain, you should change the `TERAPI_SERVER_URL` server environment variable accordingly (in the `.env` file or directly on
    Heroku/Render).


## Persistent storage[](#persistent-storage 'Direct link to Persistent storage')

If deploying with Docker Compose (e.g. AWS, GCP, DO), the database is bundled in
a docker container with local storage using Docker registries. This is a no-go for production.

Connect Terapi to an external Postgres DB that lives outside the docker setup to
mitigate this.

To do so, modify the default values of the following server env variables (in
the `.env` file):

```
TERAPI_DB_USER=
TERAPI_DB_PASSWORD=
TERAPI_DB_HOST=
TERAPI_DB_PORT=
TERAPI_DB_NAME=
TERAPI_DB_SSL=true
```

Records saved by syncs can be persisted in a dedicated database. If you opt in for this setup, set the `RECORDS_DATABASE_URL` env var. Example:
```
RECORDS_DATABASE_URL=postgresql://user:password@host:port/dbname
```
Special characters in the RECORDS_DATABASE_URL should be URL encoded.
If not specified, the records will be stored in the main database.


Deploying with Render or Heroku automatically generates a persistent database
connected to your Terapi instance.

For Render, the environment variables above are automatically set for you. For
Heroku, check out our Heroku docs page for specific instructions.



## Securing your instance[](#securing-your-instance 'Direct link to Securing your instance')

### Securing the dashboard[](#securing-the-dashboard 'Direct link to Securing the dashboard')

By default, the dashboard of your Terapi instance is open to anybody who has
access to your instance URL.

You can secure it with Basic Auth by setting the following environment variables
and restarting the server:

```bash
FLAG_AUTH_ENABLED=false # This will disable regular login and signup
TERAPI_DASHBOARD_USERNAME=
TERAPI_DASHBOARD_PASSWORD=
```

### Encrypt sensitive data[](#encrypt-sensitive-data 'Direct link to Encrypt sensitive data')

You can enforce encryption of sensitive data (tokens, secret key, app secret)
using the AES-GCM encryption algorithm. To do so, generate a 256-bit base64-encoded key:

```
openssl rand -base64 32
```

And set the `TERAPI_ENCRYPTION_KEY` environment variable to the generated key:

```
TERAPI_ENCRYPTION_KEY=
```

Once you restart the Terapi server, the encryption of the database will happen
automatically. Please note that, at the current time, you cannot modify this
encryption key once you have set it.

### Custom websockets path[](#custom-websockets-path 'Direct link to Custom websockets path')

The Terapi server serves websockets from the `/` path by default for use by `@terapi/frontend` during the login flow.
If you want more isolation between websockets and the dashboard (also served from `/`), then you can set the `TERAPI_SERVER_WEBSOCKETS_PATH` environment variable to serve websockets from a different path:

```
TERAPI_SERVER_WEBSOCKETS_PATH=
```

If you do set this variable to a different path, you will need to configure the `websocketsPath` parameter when initializing the `Terapi` object in the `@terapi/frontend` SDK:

```js
import Terapi from '@terapi/frontend';

let terapi = new Terapi();
```

## Telemetry[](#telemetry 'Direct link to Telemetry')

We use telemetry to understand Terapi's usage at a high-level and improve it over
time.

Telemetry on self-hosted instances is very light by default. We only track core
actions and do not track sensitive information.

You can disable telemetry by setting the env var `TELEMETRY=false` (in the
`.env` file or directly on Heroku/Render).

## Logs[](#logs 'Direct link to Logs')

We use Elasticsearch to store Terapi's execution logs and power the logs UI.
To limit the requirements to self-host, this stack is optional and up to the developer to setup.

If you want to enable logs, you will need to:
- Host an Elasticsearch cluster
- Update your environment variables, with `TERAPI_LOGS_ENABLED=true` and add the appropriate values in `TERAPI_LOGS_ES_*`

### Hosting

To host an Elasticsearch cluster you have multiple solutions:

- Locally: uncomment the service inside `docker-compose.yml` and run `docker-compose up`
- ElasticCloud: minimal installation on Standard tier is about 20€/mo ([elastic.co](https://www.elastic.co/))
- Render: deploy a free instance ([render.com](https://docs.render.com/deploy-elasticsearch))

### Alternatives

We don't provide alternative storage for the moment.
If `TERAPI_LOGS_ENABLED` is `false`, all the logs are sent to stdout so you can always find everything in your hosts logs UI.


