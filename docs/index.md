# Tidewatch

**Tidewatch watches your folders and runs tasks when files change.** It's a single
binary with a small config file, and it's built for the inner loop: rebuild on save,
re-run tests, regenerate assets, restart a dev server.

```console
$ tidewatch watch
tidewatch 2.0.0 · loaded tidewatch.yaml (3 tasks)
[styles]  watching src/styles/**/*.scss
[tests]   watching src/**/*.py, tests/**/*.py
[server]  watching src/**/*.py
[tests]   src/parser.py changed → pytest -q  ✓ 1.8s
```

## Why Tidewatch

- **One config, many tasks.** Each task has its own paths, ignore rules and command.
- **Debounced by default.** Saving 40 files at once triggers one run, not 40.
- **Watch or run once.** `tidewatch watch` for development, `tidewatch once` for CI.
- **Plugins.** Add notifications, restart long-running processes, or filter by git status.

## Where to next

<div class="grid" markdown>

- [**Install Tidewatch**](installation.md): get the binary on your machine.
- [**Quickstart**](quickstart.md): your first watch task in two minutes.
- [**Configuration**](configuration.md): every key in `tidewatch.yaml`.
- [**Coming from v1?**](migrating-from-v1.md): convert your `tidewatch.ini`.

</div>
