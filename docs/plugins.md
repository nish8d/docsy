# Plugins

Plugins add behaviour to tasks. Enable them in the top-level `plugins` list; some add
new task keys.

```yaml
plugins:
  - notify
  - restart
```

## notify

Shows a desktop notification when a task fails, and again when it recovers.

| Task key | Default | Description |
|----------|---------|-------------|
| `notify` | `on_failure` | One of `always`, `on_failure`, `never`. |

## restart

For long-running commands such as dev servers. Instead of starting a second copy, the
running process gets `SIGTERM` and is restarted.

| Task key | Default | Description |
|----------|---------|-------------|
| `restart` | `false` | Enable restart behaviour for this task. |
| `stop_timeout_ms` | `3000` | Time to wait before sending `SIGKILL`. |

## git-filter

Ignores changes to files that git ignores, so build output never re-triggers tasks.

| Task key | Default | Description |
|----------|---------|-------------|
| `respect_gitignore` | `true` | Skip files matched by `.gitignore`. |

!!! info "Writing your own"
    Third-party plugins are executables named `tidewatch-plugin-<name>` on your `PATH`.
    They receive events as JSON lines on stdin.
