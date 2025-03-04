# Environment Variables

!!! note "File-based configuration"
    You can provide a [configuration file](/hosting/environment-variables/configuration-methods/) for n8n. You can also append `_FILE` to certain variables to provide their configuration in a separate file. Variables that support this have the "/`_FILE`" option listed below.

## Credentials

Enabling overwrites for credentials allows you to set default values for credentials which get automatically populated. The user can't see or change these credentials. The format is `{ CREDENTIAL_NAME: { PARAMETER: VALUE }}`.

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `CREDENTIALS_OVERWRITE_DATA`<br>/`_FILE` | * | - | Overwrites for credentials. |
| `CREDENTIALS_OVERWRITE_ENDPOINT` | String | - | The API endpoint to fetch credentials. |
| `CREDENTIALS_DEFAULT_NAME` | String | `My credentials` | The default name for credentials. |

## Database

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `DB_TYPE`<br>/`_FILE` | Enum string:<br> `sqlite`, `mariadb`, `mysqldb`, `postgresdb` | `sqlite` | The database to use. |
| `DB_TABLE_PREFIX` | * | - | Prefix to use for table names. |

### MySQL

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `DB_MYSQLDB_DATABASE`<br>/`_FILE` | String | `n8n` | The name of the MySQL database. Default value is `n8n`. |
| `DB_MYSQLDB_HOST`<br>/`_FILE` | String | `localhost` | The MySQL host. Default value is `localhost`. |
| `DB_MYSQLDB_PORT`<br>/`_FILE` | Number | `3306` | The MySQL port. Default value is `3306`. |
| `DB_MYSQLDB_USER`<br>/`_FILE` | String | `root` | The MySQL user. Default value is `root`. |
| `DB_MYSQLDB_PASSWORD`<br>/`_FILE` | String | - | The MySQL password. |

### PostgreSQL

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `DB_POSTGRESDB_DATABASE`<br>/`_FILE` | String | `n8n` | The name of the PostgreSQL database. Default value is `n8n`. |
| `DB_POSTGRESDB_HOST`<br>/`_FILE` | String | `localhost` | The PostgreSQL host. Default value is `localhost`. |
| `DB_POSTGRESDB_PORT`<br>/`_FILE` | Number | `5432` | The PostgreSQL port. Default value is `5432`. |
| `DB_POSTGRESDB_USER`<br>/`_FILE` | String | `root` | The PostgreSQL user. Default value is `root`. |
| `DB_POSTGRESDB_PASSWORD`<br>/`_FILE` | String | - | The PostgreSQL password. |
| `DB_POSTGRESDB_SCHEMA`<br>/`_FILE` | String | `public` | The PostgreSQL schema. Default value is `public`. |
| `DB_POSTGRESDB_SSL_CA`<br>/`_FILE` | String | - | The PostgreSQL SSL certificate authority. |
| `DB_POSTGRESDB_SSL_CERT`<br>/`_FILE` | String | - | The PostgreSQL SSL certificate. |
| `DB_POSTGRESDB_SSL_KEY`<br>/`_FILE` | String | - | The PostgreSQL SSL key. |
| `DB_POSTGRESDB_SSL_REJECT_UNAUTHORIZED`<br>/`_FILE` | Boolean | `true` | If n8n should reject unauthorized SSL connections (true) or not (false). |

### SQLite

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `DB_SQLITE_VACUUM_ON_STARTUP` | Boolean | `false` | Runs [VACUUM](https://www.sqlite.org/lang_vacuum.html){:target="_blank" .external-link} operation on startup to rebuild the database. Reduces file size and optimizes indexes. This is a long running blocking operation and increases start-up time. |

## Deployment

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `N8N_EDITOR_BASE_URL` | String | - | Public URL where users can access the editor. Also used for emails sent from n8n. |
| `N8N_CONFIG_FILES` | String | - | Use to provide the path to any JSON [configuration file](/hosting/environment-variables/configuration-methods/). |
| `N8N_DISABLE_UI` | Boolean | `false` | Disable the UI (true) or not (false). |
| `N8N_TEMPLATES_ENABLED` | Boolean | `true` | Enable workflow templates (true) or disable (false). |
| `N8N_TEMPLATES_HOST` | String | `https://api.n8n.io` | Change this if creating your own workflow template library. |
| `N8N_ENCRYPTION_KEY` | String | Random key generated by n8n | Provide a custom key used to encrypt credentials in the n8n database. By default n8n generates a random key on first launch. |
| `N8N_USER_FOLDER` | String | `user-folder` | Provide the path where n8n will create the `.n8n` folder. This directory stores user-specific data, such as database file and encryption key. |
| `N8N_PATH` | String | `/` | The path n8n deploys to. |
| `N8N_HOST` | String | `localhost` | Host name n8n runs on. |
| `N8N_PORT` | Number | `5678` | The HTTP port n8n runs on. |
| `N8N_LISTEN_ADDRESS` | String | `0.0.0.0` | The IP address n8n should listen on. |
| `N8N_PROTOCOL` | Enum string: `http`, `https` | `http` | The protocol used to reach n8n. |
| `N8N_SSL_KEY` | String | - | The SSL key for HTTPS protocol. |
| `N8N_SSL_CERT` | String | - | The SSL certificate for HTTPS protocol. |
| `N8N_PERSONALIZATION_ENABLED` | Boolean | `true` | Whether to ask users personalisation questions and then customise n8n accordingly. |
| `N8N_VERSION_NOTIFICATIONS_ENABLED` | Boolean | `true` | When enabled, n8n sends notifications of new versions and security updates. |
| `N8N_VERSION_NOTIFICATIONS_ENDPOINT` | String | `https://api.n8n.io/versions/` | The endpoint to retrieve where version information. |
| `N8N_VERSION_NOTIFICATIONS_INFO_URL` | String | `https://docs.n8n.io/getting-started/installation/updating.html` | The URL displayed in the New Versions panel for additional information. |
| `N8N_DIAGNOSTICS_ENABLED` | Boolean | `true` | Whether to share selected, anonymous [telemetry](/reference/data-collection/) with n8n |
| `N8N_DIAGNOSTICS_CONFIG_FRONTEND` | String | `1zPn9bgWPzlQc0p8Gj1uiK6DOTn;https://telemetry.n8n.io` | Telemetry configuration for the frontend. |
| `N8N_DIAGNOSTICS_CONFIG_BACKEND` | String | `1zPn7YoGC3ZXE9zLeTKLuQCB4F6;https://telemetry.n8n.io/v1/batch` | Telemetry configuration for the backend. |
| `N8N_PUSH_BACKEND` | String | `sse` | Choose whether the n8n backend uses server-sent events (`sse`) or WebSockets (`websocket`) to send changes to the UI. |
| `VUE_APP_URL_BASE_API` | String | `http://localhost:5678/` | Used when building the `n8n-editor-ui` package manually to set how the frontend can reach the backend API. |
| `N8N_HIRING_BANNER_ENABLED` | Boolean | `true` | Whether to show the n8n hiring banner in the console (true) or not (false). |

## Binary data

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `N8N_AVAILABLE_BINARY_DATA_MODES` | String | `filesystem` | A comma separated list of available binary data modes. |
| `N8N_BINARY_DATA_STORAGE_PATH` | String | `N8N_USE_FOLDER/binaryData` | The path where n8n stores binary data. |
| `N8N_BINARY_DATA_TTL` | Number | `60` | Time to live (in minutes) for binary data of unsaved executions. |
| `N8N_DEFAULT_BINARY_DATA_MODE` | String | `default` | The default binary data mode. `default` keeps binary data in memory. Set to `filesystem` to use the filesystem. |
| `N8N_PERSISTED_BINARY_DATA_TTL` | Number | `1440` | Time to live (in minutes) for persisted data. |

## User management and SMTP

Refer to [User management](/hosting/authentication/user-management-self-hosted/) for more information on setting up user management and emails.

| Variable | Type | Default | Description |
| :------- | :--- | :------ | :---------- |
| `N8N_USER_MANAGEMENT_DISABLED` | Boolean | `false` | Set to `true` to disable the [user management](/hosting/authentication/user-management-self-hosted/) feature. Note that n8n ignores this environment variable if you have already set up an owner account.|
| `N8N_EMAIL_MODE` | String | `smtp` | Enable emails. |
| `N8N_SMTP_HOST` | String | - | _your_SMTP_server_name_ |
| `N8N_SMTP_PORT` | Number | - | _your_SMTP_server_port_ |
| `N8N_SMTP_USER` | String | - | _your_SMTP_username_ |
| `N8N_SMTP_PASS` | String | - | _your_SMTP_password_ |
| `N8N_SMTP_SENDER` | String | - | Sender email address. You can optionally include the sender name. Example with name: _N8N `<contact@n8n.com>`_ |
| `N8N_SMTP_SSL` | Boolean | `true` | Whether to use SSL for SMTP (true) or not (false). |
| `N8N_UM_EMAIL_TEMPLATES_INVITE` | String | - | Full path to your HTML email template. This overrides the default template for invite emails. |
| `N8N_UM_EMAIL_TEMPLATES_PWRESET` | String | - | Full path to your HTML email template. This overrides the default template for password reset emails. |
| `N8N_USER_MANAGEMENT_JWT_SECRET` | String | - | Set a specific JWT secret. By default, n8n generates one on start. |

## Endpoints

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `N8N_PAYLOAD_SIZE_MAX` | Number | `16` | The maximum payload size in MB. |
| `N8N_METRICS` | Boolean | `false` | Whether to enable the `/metrics` endpoint. |
| `N8N_METRICS_PREFIX` | String | `n8n_` | Optional prefix for n8n specific metrics names. |
| `N8N_METRICS_INCLUDE_DEFAULT_METRICS` | Boolean | `true` | Whether to expose default system and node.js metrics. |
| `N8N_METRICS_INCLUDE_WORKFLOW_ID_LABEL` | Boolean | `false` | Whether to include a label for the workflow ID on workflow metrics. |
| `N8N_METRICS_INCLUDE_NODE_TYPE_LABEL` | Boolean | `false` | Whether to include a label for the node type on node metrics. |
| `N8N_METRICS_INCLUDE_CREDENTIAL_TYPE_LABEL` | Boolean | `false` | Whether to include a label for the credential type on credential metrics. |
| `N8N_METRICS_INCLUDE_API_ENDPOINTS` | Boolean | `false` | Whether to expose metrics for API endpoints. |
| `N8N_METRICS_INCLUDE_API_PATH_LABEL` | Boolean | `false` | Whether to include a label for the path of API invocations. |
| `N8N_METRICS_INCLUDE_API_METHOD_LABEL` | Boolean | `false` | Whether to include a label for the HTTP method (GET, POST, ...) of API invocations. |
| `N8N_METRICS_INCLUDE_API_STATUS_CODE_LABEL` | Boolean | `false` | Whether to include a label for the HTTP status code (200, 404, ...) of API invocations. |
| `N8N_ENDPOINT_REST` | String | `rest` | The path used for REST endpoint. |
| `N8N_ENDPOINT_WEBHOOK` | String | `webhook` | The path used for webhook endpoint. |
| `N8N_ENDPOINT_WEBHOOK_TEST` | String | `webhook-test` | The path used for test-webhook endpoint. |
| `N8N_ENDPOINT_WEBHOOK_WAIT` | String | `webhook-waiting` | The path used for waiting-webhook endpoint. |
| `WEBHOOK_URL` | String | - | Used to manually provide the Webhook URL when running n8n behind a reverse proxy. See [here](/hosting/environment-variables/configuration-methods/#webhook-url) for more details. |
| `N8N_DISABLE_PRODUCTION_MAIN_PROCESS` | Boolean | `false` | Disable production webhooks from main process. This helps ensure no HTTP traffic load to main process when using webhook-specific processes. |
| `N8N_SKIP_WEBHOOK_DEREGISTRATION_SHUTDOWN` | Boolean | `false` | Only de-register webhooks on external services when workflows are deactivated. |

## External hooks

| Variable | Type  | Description |
| :------- | :---- | :---------- |
| `EXTERNAL_HOOK_FILES` | String | Files containing external hooks. Provide multiple files as a colon-separated list ("`:`"). |

## Executions

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `EXECUTIONS_PROCESS` | Enum string: `main`, `own` | `own` | Whether n8n executions run in their own process or the main process. <br><br>Refer to [Execution modes and processes](/hosting/scaling/execution-modes-processes/) for more details. |
| `EXECUTIONS_MODE` | Enum string: `regular`, `queue` | `regular` | Whether executions should run directly or using queue.<br><br>Refer to [Execution modes and processes](/hosting/scaling/execution-modes-processes/) for more details. |
| `EXECUTIONS_TIMEOUT` | Number | `-1` | The maximum run time (in seconds) before stopping a workflow execution. Set to `-1` to disable. |
| `EXECUTIONS_TIMEOUT_MAX` | Number | `3600` | The maximum execution time (in seconds) for an individual workflow. |
| `EXECUTIONS_DATA_SAVE_ON_ERROR` | Enum string: `all`, `none` | `all` | Whether n8n saves execution data on error. |
| `EXECUTIONS_DATA_SAVE_ON_SUCCESS` | Enum string: `all`, `none` | `all` | Whether n8n saves execution data on success. |
| `EXECUTIONS_DATA_SAVE_ON_PROGRESS` | Boolean | `false` | Whether to save progress for each node executed (true) or not (false). |
| `EXECUTIONS_DATA_SAVE_MANUAL_EXECUTIONS` | Boolean | `false` | Whether to save data of executions when started manually. |
| `EXECUTIONS_DATA_PRUNE` | Boolean | `false` | Whether to delete data of past executions on a rolling basis. |
| `EXECUTIONS_DATA_MAX_AGE` | Number | `336` | The execution age (in hours) before it's deleted. |
| `EXECUTIONS_DATA_PRUNE_TIMEOUT` | Number | `3600` | The timeout (in seconds) after n8n prunes execution data. |
| `EXECUTIONS_DATA_PRUNE_MAX_COUNT` | Number | `0` (no limit) | Maximum number of executions to keep in the database. |

## Logs

### n8n logs

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `N8N_LOG_LEVEL` | Enum string: `info`, `warn`, `error`, `verbose`, `debug` | `info` | Log output level. |
| `N8N_LOG_OUTPUT` | Enum string: `console`, `file` | `console` | Where to output logs. Provide multiple values as a comma-seperated list. |
| `N8N_LOG_FILE_COUNT_MAX` | Number | `100` | Max number of log files to keep. |
| `N8N_LOG_FILE_SIZE_MAX` | Number | `16` | Max size of each log file in MB. |
| `N8N_LOG_FILE_LOCATION` | String | `file` | Log file location. Requires N8N_LOG_OUTPUT set to `file`. |
| `DB_LOGGING_ENABLED` | Boolean | `false` | Whether to enable database-specific logging. |
| `DB_LOGGING_OPTIONS` | Enum string: `query`, `error`, `schema`, `warn`, `info`, `log`  | `error` | Database log output level. To enable all logging, specify `all`. |
| `DB_LOGGING_MAX_EXECUTION_TIME` | Number | `1000` | Maximum execution time (in milliseconds) before n8n logs a warning. Set to `0` to disable long running query warning. |

### Log streaming

Refer to [Log streaming](/log-streaming/) for more information on this feature.

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `N8N_EVENTBUS_CHECKUNSENTINTERVAL` | Number | `0` | How often (in milliseconds) to check for unsent event messages. Can in rare cases cause a message to be sent twice. Set to `0` to disable it. |
| `N8N_EVENTBUS_LOGWRITER_SYNCFILEACCESS` | Boolean | `false` | Whether all file access happens synchronously within the thread (true) or not (false). |
| `N8N_EVENTBUS_LOGWRITER_KEEPLOGCOUNT` | Number | `3` | How many event log files to keep. |
| `N8N_EVENTBUS_LOGWRITER_MAXFILESIZEINKB` | Number | `102400` | Maximum size (in bytes) of an event log file before a new one is started. |
| `N8N_EVENTBUS_LOGWRITER_LOGBASENAME` | String | `n8nEventLog` | Basename of the event log file. |

## Nodes

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `NODES_INCLUDE` | String | - | Specify which nodes to load. |
| `NODES_EXCLUDE` | String | - | Specify which nodes not to load. |
| `NODE_FUNCTION_ALLOW_BUILTIN` | String | - | Permit users to import specific built-in modules in the Code node. Use * to allow all. n8n disables importing modules by default. |
| `NODE_FUNCTION_ALLOW_EXTERNAL` | String | - | Permit users to import specific external modules (from `n8n/node_modules`) in the Code node. n8n disables importing modules by default. |
| `NODES_ERROR_TRIGGER_TYPE` | String | `n8n-nodes-base.errorTrigger` | Specify which node type to use as Error Trigger. |
| `N8N_CUSTOM_EXTENSIONS` | String | - | Specify the path to additional directories containing your custom nodes. |

## Queues

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `QUEUE_BULL_PREFIX` | String | - | Prefix to use for all queue keys. |
| `QUEUE_BULL_REDIS_DB` | Number | `0` | The Redis database used. |
| `QUEUE_BULL_REDIS_HOST` | String | `localhost` | The Redis host. |
| `QUEUE_BULL_REDIS_PORT` | Number | `6379` | The Redis port used. |
| `QUEUE_BULL_REDIS_USERNAME` | String | - | The Redis username (needs Redis version 6 or above). Don't define it for Redis < 6 compatibility |
| `QUEUE_BULL_REDIS_PASSWORD` | String | - | The Redis password. |
| `QUEUE_BULL_REDIS_TIMEOUT_THRESHOLD` | Number | `10000` | The Redis timeout threshold (in seconds). |
| `QUEUE_RECOVERY_INTERVAL` | Number | `60` | Interval (in seconds) for active polling to the queue to recover from Redis crashes. `0` disables recovery. May increase Redis traffic significantly. |
| `QUEUE_WORKER_TIMEOUT` | Number | `30` | How long should n8n wait (seconds) for running executions before exiting worker process on shutdown. |
| `QUEUE_HEALTH_CHECK_ACTIVE` | Boolean | `false` | Whether to enable health checks (true) or disable (false). |
| `QUEUE_HEALTH_CHECK_PORT` | Number | - | The port to serve health checks on. |

## Security

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `N8N_AUTH_EXCLUDE_ENDPOINTS` | String | - | Exclude endpoints from authentication checks. Provide multiple endpoints as a colon-seperated list ("`:`"). The endpoints must not start with a forward slash ("`/`"). |
| `N8N_BASIC_AUTH_ACTIVE` | Boolean | `false` | Whether n8n should activate basic auth for editor and REST-API access. |
| `N8N_BASIC_AUTH_USER`<br>/`_FILE` | String | - | The name of the n8n user for basic authentication. |
| `N8N_BASIC_AUTH_PASSWORD`<br>/`_FILE` | String | - | The password of the n8n user for basic authentication. |
| `N8N_BASIC_AUTH_HASH`<br>/`_FILE` | Boolean | `false` | Whether to hash the basic authentication password. |
| `N8N_BLOCK_ENV_ACCESS_IN_NODE` | Boolean | `false` | Whether to allow users to access environment variables in expressions and the Code node (false) or not (true). |
| `N8N_JWT_AUTH_ACTIVE` | Boolean | `false` | Whether n8n should activate JWT authentication for editor and REST-API access. |
| `N8N_JWT_AUTH_HEADER`<br>/`_FILE` | String | - | The request header containing a signed JWT. |
| `N8N_JWT_AUTH_HEADER_VALUE_PREFIX`<br>/`_FILE` | String | - | Optional. The request header value prefix to strip. |
| `N8N_JWKS_URI`<br>/`_FILE` | String | - | The URI to fetch JWK Set for JWT authentication. |
| `N8N_JWT_ISSUER`<br>/`_FILE` | String | - | Optional. The expected JWT issuer. |
| `N8N_JWT_NAMESPACE`<br>/`_FILE` | String | - | Optional. The expected JWT namespace. |
| `N8N_JWT_ALLOWED_TENANT`<br>/`_FILE` | String | - | Optional. The allowed JWT tenant. |
| `N8N_JWT_ALLOWED_TENANT_KEY`<br>/`_FILE` | String | - | Optional. The JWT tenant key name to inspect within the JWT namespace. |

## Timezone and localization

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `GENERIC_TIMEZONE` | * | `America/New_York` |The n8n instance timezone. Important for schedule nodes (such as Cron). |
| `N8N_DEFAULT_LOCALE` | String | `en` | A locale identifier, compatible with the [Accept-Language header](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Language){:target="_blank" .external-link}. n8n doesn't support regional identifiers, such as `de-AT`. When running in a locale other than the default, n8n displays UI strings in the selected locale, and falls back to `en` for any untranslated strings. |

## Workflows

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `WORKFLOWS_DEFAULT_NAME` | String | `My workflow` | The default name used for new workflows. |
| `N8N_ONBOARDING_FLOW_DISABLED` | Boolean | `false` | Whether to show onboarding tips when creating a new workflow (true) or not (false). |
| `N8N_WORKFLOW_TAGS_DISABLED` | Boolean | `false` | Whether to disable workflow tags (true) or enable tags (false). |
| `N8N_WORKFLOW_CALLER_POLICY_DEFAULT_OPTION` | String | `workflowsFromSameOwner` | Which workflows can call a workflow. Options are: `any`, `none`, `workflowsFromAList`, `workflowsFromSameOwner`. This feature requires [Workflow sharing](/workflows/sharing/). |

## License

| Variable | Type  | Default  | Description |
| :------- | :---- | :------- | :---------- |
| `N8N_HIDE_USAGE_PAGE` | boolean | `false` | Hide the usage and plans page in the app. |
| `N8N_LICENSE_ACTIVATION_KEY` | String | `''` | Activation key to initialize license. Not applicable if the n8n instance was already activated. |
| `N8N_LICENSE_AUTO_RENEW_ENABLED` | Boolean | `true` | Whether autorenew for licenses is enabled (true) or not (false). |
| `N8N_LICENSE_AUTO_RENEW_OFFSET` | Number | `60 * 60 * 72` (72 hours) | How many seconds before expiry a license should automatically renew. |
| `N8N_LICENSE_SERVER_URL` | String | `http://license.n8n.io/v1` | Server URL to retrieve license. |
