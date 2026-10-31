# Installation

Tidewatch 1.x ships as a single static binary for Linux and macOS.

=== "macOS / Linux (script)"

    ```bash
    curl -fsSL https://get.tidewatch.dev/install.sh | sh -s -- --version 1.2.0
    ```

=== "Homebrew"

    ```bash
    brew install tidewatch@1
    ```

=== "Cargo"

    ```bash
    cargo install tidewatch --version "^1"
    ```

## Verify the install

```console
$ tidewatch --version
tidewatch 1.2.0
```

## Requirements

| Platform | Minimum version | File events backend |
|----------|-----------------|---------------------|
| Linux    | kernel 4.9      | inotify             |
| macOS    | 11 (Big Sur)    | FSEvents            |

!!! note "Windows"
    Windows is not supported in 1.x.

!!! tip "Large repositories on Linux"
    inotify has a per-user watch limit. If Tidewatch logs `too many watches`, raise it:
    `sudo sysctl fs.inotify.max_user_watches=524288`.
