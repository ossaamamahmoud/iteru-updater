Channel manifests are written by the publisher's release tooling (`promote.ps1` / `retract.ps1`),
never by hand. Each `<channel>.json` is accompanied by `<channel>.json.sig` — a Base64 ECDSA P-256
signature over the exact file bytes — and archived under `history/<channel>-<version>.json`.
