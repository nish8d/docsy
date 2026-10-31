# Changelog

## 2.0.0

**Breaking changes:** see [Migrating from v1](migrating-from-v1.md).

- Config moved from `tidewatch.ini` to `tidewatch.yaml`.
- `tidewatch run` split into `tidewatch watch` and `tidewatch once`.
- Debounce is now set in milliseconds with `debounce_ms`.
- New plugin system with built-in `notify`, `restart` and `git-filter` plugins.
- `tidewatch init --from tidewatch.ini` converts v1 configs.

## 1.2.0

- `ignore` patterns in each watch section.

## 1.1.0

- `--once` flag for CI.

## 1.0.0

- First stable release.
