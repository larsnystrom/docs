# 🧠 Redis Configuration

If you choose to use the `redis` driver for horizontal scalability, rate limiting data storage, or queue support, you will need to configure additional environment variables to instruct soketi how to connect to Redis. If you are not using Redis for rate limiting or queues, these environment variables are not required.

### Environment Variables

| Name                | Default     | Possible values | Description                                                    |
| ------------------- | ----------- | --------------- | -------------------------------------------------------------- |
| `DB_REDIS_HOST`     | `127.0.0.1` | Any string      | The Redis host.                        |
| `DB_REDIS_PORT`     | `6379`      | Any integer     | The Redis port.                        |
| `DB_REDIS_DB`       | `0`         | Any integer     | The Redis database.                    |
| `DB_REDIS_USERNAME` | `null`      | Any string      | The Redis username. |
| `DB_REDIS_PASSWORD` | `null`      | Any string      | The Redis password. |
| `DB_REDIS_PREFIX`   | `soketi`    | Any string      | The Redis key prefix that should be utilized.          |

### Redis Sentinel

The following additional options are available when connecting to Redis through one or more Sentinels.

{% hint style="info" %}
Please be aware that utilizing the Sentinel options will override some of the other options like `DB_REDIS_HOST` and `DB_REDIS_PORT`, but not `DB_REDIS_DB` or `DB_REDIS_PASSWORD`. More details can be found in the [`ioredis` documentation for Redis Sentinel](https://github.com/luin/ioredis#sentinel).
{% endhint %}

| Name                         | Default    | Possible values | Description                                                                                                                             |
| ---------------------------- | ---------- | --------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| `DB_REDIS_SENTINELS`         | `null`     | Any string      | A JSON-encoded array of objects with `host` and `port` of Sentinels to connect to.
| `DB_REDIS_SENTINEL_PASSWORD` | `null`     | Any string      | The (optional) password that is used to authenticate with the Sentinels.                                   |
| `DB_REDIS_INSTANCE_NAME`     | `mymaster` | Any string      | The name of the Redis instance to which a connection should be established through the configured Sentinels. |
