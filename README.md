# Relay

A lightweight desktop client for your self-hosted AI browser sessions.

## Download

[Download the latest Relay release](https://github.com/vivan-j/relay-releases/releases/latest).

- Apple Silicon Mac: download the `.dmg`, open it, and copy Relay to Applications.
- Intel Mac: download the `_x64.dmg` installer.
- Windows x64: download the `_x64-setup.exe` installer.

Quit an existing Relay installation before replacing it. A self-hosted Relay server with trusted HTTPS is required to connect to your AI accounts.

## Updates

From Relay 0.2.0 onward, open Settings → Software updates → Check for updates. Available updates are signed and verified before installation. Users running 0.1.0 should install 0.2.0 manually once.

This repository contains only compiled installers, signed updater artifacts, and update metadata. Relay's source code and build automation are maintained in a separate private repository. GitHub's automatic “Source code” archives for these releases contain this downloads repository's README, not the application source.

macOS builds are not currently Developer ID signed or notarized. Provider login compatibility and resource targets are not guaranteed.

## Server installation

Download `relay-server.tar.gz` and its `.sha256` file from the latest release. The package includes compiled Linux amd64/arm64 server binaries and Docker deployment files; no source access is required.

On a Linux server with Docker Engine and Compose installed:

```sh
curl -fLO https://github.com/vivan-j/relay-releases/releases/latest/download/relay-server.tar.gz
curl -fLO https://github.com/vivan-j/relay-releases/releases/latest/download/relay-server.tar.gz.sha256
sha256sum -c relay-server.tar.gz.sha256
tar -xzf relay-server.tar.gz
cd relay-server
sudo ./install.sh
```

Point a domain at your server and allow inbound TCP ports 80/443. Enter the domain when the installer asks; it configures HTTPS and prints a one-time pairing code. Connect in Relay using the HTTPS address and pairing code. The desktop setup guide is available starting with version 0.2.1.
