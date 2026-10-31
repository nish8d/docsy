# Quickstart

This guide sets up a task that re-runs your tests every time a Python file changes.

## 1. Create a config

Run `tidewatch init` in your project root. It writes a starter `tidewatch.yaml`:

```yaml title="tidewatch.yaml"
watch:
  - name: tests
    paths: ["src/**/*.py", "tests/**/*.py"]
    ignore: ["**/__pycache__/**"]
    run: pytest -q
```

## 2. Start watching

```console
$ tidewatch watch
tidewatch 2.0.0 · loaded tidewatch.yaml (1 task)
[tests] watching src/**/*.py, tests/**/*.py
```

Save any matching file and Tidewatch runs `pytest -q`, streaming its output with a
`[tests]` prefix.

## 3. Run once in CI

In CI you don't want a long-running watcher. `tidewatch once` runs every task one time and
exits with a non-zero code if any task fails:

```console
$ tidewatch once
[tests] pytest -q  ✓ 2.1s
```

## Next steps

- Add more tasks and tune debouncing in the [configuration reference](configuration.md).
- Get desktop notifications with the [`notify` plugin](plugins.md#notify).
