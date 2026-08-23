# CryoZen releases

Public download channel for [CryoZen](https://cryozen.ai), the self-hosted AI workspace.
The source repository is private; this repository carries every release's installers, checksums, and the Docker Compose bundle, published automatically by the product's release pipeline.

## Download

Pick your platform on [cryozen.ai/download](https://cryozen.ai/download), or grab an asset from the [latest release](https://github.com/shreejitverma/cryozen-releases/releases/latest):

| Platform | Asset |
| --- | --- |
| macOS (Apple Silicon) | `CryoZen.dmg` |
| macOS (Intel) | `CryoZen-Intel.dmg` |
| Windows installer | `CryoZen-Setup-x64.exe` (silent: `/S`) |
| Windows portable | `CryoZen-Windows-Portable.zip` |
| Linux AppImage | `CryoZen-x86_64.AppImage` |
| Debian / Ubuntu | `cryozen_amd64.deb` |
| Fedora / RHEL | `cryozen.x86_64.rpm` |
| Linux portable | `CryoZen-Linux-Portable.tar.gz` |
| Checksums | `SHA256SUMS.txt` |

Verify a download:

```sh
sha256sum -c --ignore-missing SHA256SUMS.txt
```

## Docker

The container image is published to GitHub Container Registry for `linux/amd64` and `linux/arm64`:

```text
ghcr.io/shreejitverma/cryozen:latest
ghcr.io/shreejitverma/cryozen:<version>
```

This repository's `docker-compose.yml` runs the full stack (CryoZen, ChromaDB, SearXNG, ntfy) from that image:

```sh
git clone https://github.com/shreejitverma/cryozen-releases.git
cd cryozen-releases
cp .env.example .env
docker compose up -d
```

Then open http://localhost:7000. Data persists under `./data`.

## License

CryoZen is proprietary software. Copyright (c) 2026 Shreejit Verma. All rights reserved.
Downloading and running the binaries is permitted under the terms shown at https://cryozen.ai.
