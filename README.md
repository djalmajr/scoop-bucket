# djalmajr's Scoop bucket

[![Tests](https://github.com/djalmajr/scoop-bucket/actions/workflows/ci.yml/badge.svg)](https://github.com/djalmajr/scoop-bucket/actions/workflows/ci.yml) [![Excavator](https://github.com/djalmajr/scoop-bucket/actions/workflows/excavator.yml/badge.svg)](https://github.com/djalmajr/scoop-bucket/actions/workflows/excavator.yml)

A personal bucket for [Scoop](https://scoop.sh), the Windows command-line installer.

## Install

```pwsh
scoop bucket add djalmajr https://github.com/djalmajr/scoop-bucket
scoop install ai-usagebar
```

## Manifests

| App | What it installs | Upstream |
|---|---|---|
| `ai-usagebar` | `ai-usagebar`, `ai-usagebar-tui` and `ai-usagebar-tray` on the PATH, plus an "AI Usage" Start Menu shortcut for the tray | [akitaonrails/ai-usagebar](https://github.com/akitaonrails/ai-usagebar) |

Every manifest downloads the upstream project's own GitHub release and verifies it against the
`.sha256` sidecar published next to it. Nothing here is rebuilt or repackaged.

Updates land automatically: the Excavator workflow runs `checkver` every four hours and commits
the new version and hash, so `scoop update ai-usagebar` picks a release up shortly after it is
tagged. Uninstalling with `scoop uninstall ai-usagebar` also clears the "Start with Windows"
entry and the tray-icon settings the app wrote for its install directory; config and cache stay
where they are.

## Contributing

Open an issue or a pull request with a manifest that follows the
[App Manifests](https://github.com/ScoopInstaller/Scoop/wiki/App-Manifests) wiki page. `bin/test.ps1`
runs the same checks CI does.
