# Configuration

Tidewatch reads `tidewatch.yaml` from the current directory. Use `--config <path>` to load
a different file.

## Full example

```yaml title="tidewatch.yaml"
debounce_ms: 200          # global default

plugins:
  - notify
  - restart

watch:
  - name: styles
    paths: ["src/styles/**/*.scss"]
    run: sass src/styles:dist/css

  - name: tests
    paths: ["src/**/*.py", "tests/**/*.py"]
    ignore: ["**/__pycache__/**", "**/.pytest_cache/**"]
    run: pytest -q
    debounce_ms: 500

  - name: server
    paths: ["src/**/*.py"]
    run: python -m app
    restart: true          # provided by the restart plugin
```

## Top-level keys

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| `debounce_ms` | integer | `200` | Wait this long after the last change before running a task. |
| `plugins` | list of strings | `[]` | Plugins to load. See [Plugins](plugins.md). |
| `watch` | list of tasks | — | **Required.** The tasks to run. |

## Task keys

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| `name` | string | — | **Required.** Unique task name, used as the log prefix. |
| `paths` | list of globs | — | **Required.** Files that trigger the task. |
| `ignore` | list of globs | `[]` | Files to exclude, even if they match `paths`. |
| `run` | string | — | **Required.** Shell command to run. |
| `debounce_ms` | integer | global value | Per-task override. |
| `cwd` | string | config directory | Working directory for `run`. |
| `env` | map | `{}` | Extra environment variables for `run`. |

!!! note "Glob syntax"
    `*` matches within one directory, `**` matches across directories. Paths are relative
    to the directory containing `tidewatch.yaml`.
