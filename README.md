# Batool Cloud releases

Signed release manifests of the Batool Cloud server. This repository holds no source code.

- `latest.json` - the current release: version, release date, the server image pinned by digest (`ghcr.io/aliiqbal84-ship-it/batool-cloud-server@sha256:...`), the minimum version it updates from, and short notes.
- `latest.json.minisig` - the owner's [minisign](https://jedisct1.github.io/minisign/) signature over the exact bytes of `latest.json`.
- `release.pub` - the owner's public signing key (key id `D42112D65D5ABAC6`).

A Batool Cloud server pins `release.pub` at installation and installs only manifests whose signature matches it and whose version is higher than the running one. To check a manifest by hand:

```
minisign -Vm latest.json -p release.pub
```

The signing key never leaves the owner's PC. Nothing here is needed to read your data: a server only stores what its clients encrypted.
