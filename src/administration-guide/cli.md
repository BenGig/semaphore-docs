# CLI


* [Runners](./cli/runners.md)
* [Users](./cli/users.md)
* [Vaults](./cli/vaults.md)


## Common config options

| Option               | Description                               |
|----------------------|-------------------------------------------|
|`--config config.json`| Path to the configuration file.           |
|`--no-cofnig`         | Do not use any configuration file. Only environment variable will be used. |
|`--log-level ERROR`   | `DEBUG`, `INFO`, `WARN`, `ERROR`, `FATAL`, `PANIC` |

## Version

Print current version.

```bash
semaphore version
```


## Help

Print list of supported commands.

```bash
semaphore help
```

## Database migration

Update database schema to latest version.

```
semaphore migrate
```

## Interactive setup

Use this option for first time configuration.

```
semaphore setup
```

## Server mode

Start the server.

```
semaphore server
```

## Runner mode

Start the runner.

```
semaphore runner
```
