# Migrating from v1

Tidewatch 2.0 replaces the INI config with YAML and splits `tidewatch run` into two
commands. Most projects can migrate in about five minutes.

## Summary of breaking changes

| v1 | v2 |
|----|----|
| `tidewatch.ini` | `tidewatch.yaml` |
| `[watch:<name>]` section | item in the `watch:` list with `name:` |
| `command =` | `run:` |
| `delay =` (seconds) | `debounce_ms:` (milliseconds) |
| Comma-separated `paths` | YAML list |
| `tidewatch run` | `tidewatch watch` |
| `tidewatch run --once` | `tidewatch once` |

## Convert your config

=== "v1: tidewatch.ini"

    ```ini
    [watch:tests]
    paths = src/**/*.py, tests/**/*.py
    ignore = **/__pycache__/**
    command = pytest -q
    delay = 0.5
    ```

=== "v2: tidewatch.yaml"

    ```yaml
    watch:
      - name: tests
        paths: ["src/**/*.py", "tests/**/*.py"]
        ignore: ["**/__pycache__/**"]
        run: pytest -q
        debounce_ms: 500
    ```

!!! tip "Automatic conversion"
    `tidewatch init --from tidewatch.ini` reads a v1 config and writes the equivalent
    `tidewatch.yaml`. Review the output, then delete the old file.

## Update scripts and CI

Replace `tidewatch run --once` with `tidewatch once` in CI pipelines, and
`tidewatch run` with `tidewatch watch` in `Makefile`s and `package.json` scripts.

!!! warning
    v2 ignores `tidewatch.ini`. If no `tidewatch.yaml` exists, Tidewatch exits with
    `error: no tidewatch.yaml found (found tidewatch.ini — see the migration guide)`.
