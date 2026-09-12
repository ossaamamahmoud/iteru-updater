# Iteru — release feed

This repository holds **only** the release packages and update channel manifests for
[Iteru — Payment Operations](https://github.com/ossaamamahmoud/iteru) (private).
There is no source code here.

## For operators

Install once from the latest release's **`Iteru-win-Setup.exe`** (per user, no administrator
rights; requires Microsoft Edge). After that the application updates itself: new versions are
downloaded quietly in the background and applied when you restart it.

The installer is not yet code-signed, so Windows SmartScreen may ask once: *More info → Run anyway*.

## How updates are trusted

Installed copies do not follow "the latest release". They follow a **channel manifest**
(`channels/stable.json`, `channels/pilot.json`) that is signed offline with a key held by the
publisher. A manifest names the exact version and the SHA-256 of every package that may be
installed; anything not covered by a valid signature is ignored. `channels/history/` keeps every
manifest that was ever promoted, which is how a release is rolled back.

| Channel | Who |
|---|---|
| `stable` | Every faculty operator |
| `pilot` | The administrator account, which sees all faculties — watched for 48 hours before a version is promoted to `stable` |

Assets in each release are produced by [Velopack](https://velopack.io): `Iteru-win-Setup.exe`,
`Iteru-win-Portable.zip`, full and delta packages (`*.nupkg`) and the feed `releases.win.json`.

---
© 2026 Osama Studios. All rights reserved. Iteru is proprietary software; the packages here are
provided for licensed operators only.
