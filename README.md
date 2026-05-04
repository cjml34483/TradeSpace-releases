# TradeSpace-releases (legacy stub for ASA Terminal auto-updater)

This repo is a thin shim. The active releases repo is
[cjml34483/ASA-releases](https://github.com/cjml34483/ASA-releases).

Binaries v1.0.30 -> v1.0.42 baked the URL
`https://raw.githubusercontent.com/cjml34483/TradeSpace-releases/main/latest.json`
into `tauri.conf.json` updater.endpoints. After the v1.0.43 rebrand, the
source repo and the releases repo were renamed; `raw.githubusercontent.com`
follows GitHub repo-rename redirects for git operations but NOT for serving
file content (verified during v1.0.43 publish). So this repo exists to keep
the legacy URL alive for the installed base. `release.ps1` can mirror-push
`latest.json` here on every release via its `-LegacyReleasesRepo` parameter.

The `url` field inside `latest.json` here points at the
`cjml34483/ASA-releases` releases binary, which exists, is signed, and
verifies against the same minisign pubkey baked into every v1.0.30+ client.