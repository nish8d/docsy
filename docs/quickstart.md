# Quickstart

This guide sets up a section that re-runs your tests every time a Python file changes.

## 1. Create a config

Create `tidewatch.ini` in your project root:

```ini title="tidewatch.ini"
[watch:tests]
paths = src/**/*.py, tests/**/*.py
ignore = **/__pycache__/**
command = pytest -q
```

## 2. Start watching

```console
$ tidewatch run
tidewatch 1.2.0 · loaded tidewatch.ini (1 section)
[tests] watching src/**/*.py, tests/**/*.py
```

Save any matching file and Tidewatch runs `pytest -q`, streaming its output with a
`[tests]` prefix.

## 3. Run once in CI

Add `--once` to run every section one time and exit with a non-zero code if any fails:

```console
$ tidewatch run --once
[tests] pytest -q  ✓ 2.1s
```

## Next steps

Add more sections and tune the delay in the [configuration reference](configuration.md).
