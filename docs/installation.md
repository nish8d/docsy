# Installation

Tidewatch ships as a single static binary for Linux, macOS and Windows.

=== "macOS / Linux (script)"

    ```bash
    curl -fsSL https://get.tidewatch.dev/install.sh | sh
    ```

=== "Homebrew"

    ```bash
    brew install tidewatch
    ```

=== "Cargo"

    ```bash
    cargo install tidewatch --version "^2"
    ```

=== "Windows (Scoop)"

    ```powershell
    scoop install tidewatch
    ```

## Verify the install

```console
$ tidewatch --version
tidewatch 2.0.0
```

## Requirements

| Platform | Minimum version | File events backend |
|----------|-----------------|---------------------|
| Linux    | kernel 4.9      | inotify             |
| macOS    | 12 (Monterey)   | FSEvents            |
| Windows  | 10              | ReadDirectoryChangesW |

!!! tip "Large repositories on Linux"
    inotify has a per-user watch limit. If Tidewatch logs `too many watches`, raise it:
    `sudo sysctl fs.inotify.max_user_watches=524288`.
