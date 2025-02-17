# 🧬 Array Driver

The default app driver used by soketi is the `array` driver. This is a static, in-memory array of app credentials that is kept in memory while the underlying uWS Server process is running. Whenever a connection is made or an event is broadcast, the app credentials will be verified against these in-memory credentials.

By default, default values are defined for the app ID, key, and secret for ease of installation and development. However, you should change these credentials before launching your application in production.

For rate limits and max connections options, setting the variable value to `-1` will disable the rate limits and / or max allowed connections.

### Environment Variables

| Name                                     | Default      | Possible values                                            | Description                                                                                                                                                                                   |
| ---------------------------------------- | ------------ | ---------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `DEFAULT_APP_ID`                         | `app-id`     | Any string                                                 | The default app id for the array driver.                                                                                                                                                      |
| `DEFAULT_APP_KEY`                        | `app-key`    | Any string                                                 | The default app key for the array driver.                                                                                                                                                     |
| `DEFAULT_APP_SECRET`                     | `app-secret` | Any string                                                 | The default app secret for the array driver.                                                                                                                                                  |
| `DEFAULT_APP_MAX_CONNS`                  | `-1`         | Any integer                                                | The default app's limit of concurrent connections.                                                                                                                                            |
| `DEFAULT_APP_ENABLE_CLIENT_MESSAGES`     | `false`      | `true`, `false`                                            | Whether client messages should be enabled for the app.                                                                                                                                        |
| `DEFAULT_APP_ENABLED`                    | `true`       | `true`, `false`                                            | Whether the app is activated. This option can be used to disable an app.                                                                                                                               |
| `DEFAULT_APP_MAX_BACKEND_EVENTS_PER_SEC` | `-1`         | Any integer                                                | The default app's limit of `/events` endpoint events broadcast per second. You can [configure rate limiting database store](../rate-limiting-and-limits/broadcast-rate-limiting.md)         |
| `DEFAULT_APP_MAX_CLIENT_EVENTS_PER_SEC`  | `-1`         | Any integer                                                | The default app's limit of client events broadcast per second by a single socket. You can [configure rate limiting database store](../rate-limiting-and-limits/broadcast-rate-limiting.md) |
| `DEFAULT_APP_MAX_READ_REQ_PER_SEC`       | `-1`         | Any integer                                                | The default app's limit of read endpoint calls per second. You can [configure rate limiting database store](../rate-limiting-and-limits/broadcast-rate-limiting.md)                           |
| `DEFAULT_APP_WEBHOOKS`                   | `[]`         | `[{"url": "string", "event_types": ["string", ...]}, ...]` | The webhooks list for the app. See below                                                                                                                                              |

### Webhooks formatting

For Webhooks, the available `event_types` values that can be defined are explained in the [webhooks documentation](../advanced-usage/app-webhooks.md):

* `client_event`
* `channel_occupied`
* `channel_vacated`
* `member_added`
* `member_removed`
