# NAVIG — Scoop bucket

The [NAVIG](https://navig.run) CLI (`navig`) as a Scoop bucket.

```powershell
scoop bucket add navig https://github.com/navig-run/scoop-navig
scoop install navig
navig doctor
```

The CLI installs into its own Scoop app directory (`python` is the only dependency),
so `scoop uninstall navig` removes it completely. Nothing else is touched:
`%USERPROFILE%\.navig` — config, vault, sessions — is yours and survives.

The desktop apps are separate and not in this bucket:

- **NAVIG Anchor** (the hotkey palette): `winget install anchor`, or the installer on
  the [releases page](https://github.com/navig-run/core/releases)
- **NAVIG OS**: same releases page

## Manifest

`bucket/navig.json` pins the PyPI wheel and its SHA256. Regenerate it on every release
with `scripts/scoop-manifest.ps1` in the main repo — PyPI's file URLs carry a content
hash, so a hand-edited manifest is wrong the moment a new version ships.
