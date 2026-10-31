# CLI reference

```text
tidewatch <command> [options]
```

## Global options

| Option | Description |
|--------|-------------|
| `--config <path>` | Config file to load. Default: `./tidewatch.yaml`. |
| `--quiet` | Only print task output and errors. |
| `--version` | Print the version and exit. |

## `tidewatch watch`

Start watching and run tasks as files change. Runs until interrupted (++ctrl+c++).

| Option | Description |
|--------|-------------|
| `--only <name>` | Run only the named task. Repeatable. |
| `--initial` | Run every task once at startup before watching. |

## `tidewatch once`

Run every task one time and exit. The exit code is `0` if all tasks succeed, otherwise `1`.
Use it in CI.

| Option | Description |
|--------|-------------|
| `--only <name>` | Run only the named task. Repeatable. |
| `--parallel` | Run tasks concurrently instead of in config order. |

## `tidewatch init`

Write a starter `tidewatch.yaml` in the current directory. Refuses to overwrite an
existing file.

## `tidewatch plugins list`

List plugins that are installed and which ones the current config loads.

```console
$ tidewatch plugins list
notify      built-in   loaded
restart     built-in   loaded
git-filter  built-in   available
```
