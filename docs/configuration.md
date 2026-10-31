# Configuration

Tidewatch reads `tidewatch.ini` from the current directory. Use `--config <path>` to load
a different file.

## Full example

```ini title="tidewatch.ini"
[defaults]
delay = 0.2

[watch:styles]
paths = src/styles/**/*.scss
command = sass src/styles:dist/css

[watch:tests]
paths = src/**/*.py, tests/**/*.py
ignore = **/__pycache__/**, **/.pytest_cache/**
command = pytest -q
delay = 0.5
```

## `[defaults]` section

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| `delay` | seconds (float) | `0.2` | Wait this long after the last change before running. |

## `[watch:<name>]` sections

Each section defines one task. The part after `watch:` is the task name and log prefix.

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| `paths` | comma-separated globs | — | **Required.** Files that trigger the section. |
| `ignore` | comma-separated globs | empty | Files to exclude, even if they match `paths`. *(1.2.0+)* |
| `command` | string | — | **Required.** Shell command to run. |
| `delay` | seconds (float) | `[defaults]` value | Per-section override. |

!!! note "Glob syntax"
    `*` matches within one directory, `**` matches across directories. Paths are relative
    to the directory containing `tidewatch.ini`.
