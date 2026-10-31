# CLI reference

Tidewatch 1.x has a single command.

```text
tidewatch run [options]
```

## `tidewatch run`

Start watching and run sections as files change. Runs until interrupted (++ctrl+c++).

| Option | Description |
|--------|-------------|
| `--config <path>` | Config file to load. Default: `./tidewatch.ini`. |
| `--section <name>` | Run only the named section. Repeatable. |
| `--once` | Run every section one time and exit. Exit code `1` if any section fails. *(1.1.0+)* |
| `--quiet` | Only print command output and errors. |

## `tidewatch --version`

Print the version and exit.
