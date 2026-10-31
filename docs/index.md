# Tidewatch

**Tidewatch watches your folders and runs tasks when files change.** It's a single
binary with a small config file, and it's built for the inner loop: rebuild on save,
re-run tests, regenerate assets.

```console
$ tidewatch run
tidewatch 1.2.0 · loaded tidewatch.ini (2 sections)
[styles]  watching src/styles/**/*.scss
[tests]   watching src/**/*.py, tests/**/*.py
[tests]   src/parser.py changed → pytest -q  ✓ 1.8s
```

## Why Tidewatch

- **One config, many tasks.** Each `[watch:<name>]` section has its own paths and command.
- **Delayed runs.** Saving 40 files at once triggers one run, not 40.
- **CI friendly.** `tidewatch run --once` runs every section one time and exits.

## Where to next

<div class="grid" markdown>

- [**Install Tidewatch**](installation.md): get the binary on your machine.
- [**Quickstart**](quickstart.md): your first watch section in two minutes.
- [**Configuration**](configuration.md): every key in `tidewatch.ini`.
- [**CLI reference**](cli.md): `tidewatch run` and its flags.

</div>
