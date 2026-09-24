# Jarod-Pi · Agent resources

[简体中文](README.md) · [English](README.en.md) · [Jarod-Pi application](https://github.com/jarodfund/jarod-pi)

Versioned agent-resource catalogs, provenance and publication notes for **学术派 / Jarod-Pi**. Resource archives belong in GitHub Releases, not in Git history.

## For users

Choose an agent in Jarod-Pi. The client downloads missing dependencies on demand and reuses shared resources. There is no need to clone each upstream project or download the entire collection.

This is not the desktop application download. See the [product repository](https://github.com/jarodfund/jarod-pi) for client status. **Resource Release 2 is live; client 0.2.5 is recommended.** Client ZIPs are not published in the product repository yet. Available resources do not imply available client downloads or online application updates.

The release contains four signed platform catalogs, 30 ZIPs and a public key: 35 assets with verified remote sizes and SHA-256 digests. Unauthenticated downloads passed catalog signature checks and Range/206 checks for every ZIP. The actual Windows 0.2.5 package installed and selected academic and openresearch using a clean profile, including verification of the research-cli dependency. Recovery after a 404 and resumable download were also verified. No paid model requests were made; this was not a task-by-task test of every agent.

Version 0.2.4 is catalog-compatible but does not use the system proxy for resource downloads; 0.2.5 fixes that separate issue. Version 0.2.3 still points to the retired server and is not recommended for distribution.

## Repository roles

| Layer | Contents | Purpose |
| :--- | :--- | :--- |
| Upstream forks | Original code, skills and notices | Track provenance and maintain adaptations |
| This repository | Adapted resources, pinned versions and signed catalogs | Install verified combinations |
| Product repository | Desktop code and client ZIPs | Download and use the application |

An upstream source ZIP is not an adapted resource package and must not replace a pinned bundle.

## Downloads and verification

Clients request their platform catalog: `portable-windows-x64.json`, `portable-linux-x64.json`, `portable-macos-arm64.json` or `portable-macos-x64.json`.

- Catalogs are signed with Ed25519. Clients contain the public key; the private key is never distributed.
- Archives are named by SHA-256. Their sizes and digests are constrained by the signed catalog.
- The canonical catalog path `packages/<sha256>.zip` maps to the flat GitHub Release asset `<sha256>.zip`.
- The client supports resumable downloads, verifies digests before extraction, and rejects unsafe paths and incomplete resources.
- No mainland-China mirror is configured yet. The client does not assume that IP geolocation guarantees speed or use unreviewed public proxies by default.

Platform catalogs record capability limits. Some Linux/macOS native dependencies still require builds and native-machine validation; Windows resources cannot simply be reused on those platforms.

## Maintenance and provenance

[Publication notes](PUBLISHING.md) · [Upstream projects](UPSTREAMS.md)

Resource preparation, deterministic packaging, signing and validation scripts live in the product repository under `desktop/scripts/`. This repository records distribution results rather than maintaining a second copy of runtime code.

## Licenses

Each upstream project and dependency retains its own license and notices. The complete resource collection is not uniformly MIT-licensed. Forking a repository does not change its license; local snapshots without a confirmed redistribution grant are not assumed to be publishable.
