<div align="center">

<!-- <img src="src/assets/icon-192.png" alt="MonitorMRR" width="100" height="100"> -->

# MonitorMRR

**A macOS menu bar app to track your revenue across Stripe, LemonSqueezy, and Gumroad.**

[![Platform](https://img.shields.io/badge/platform-macOS-lightgrey.svg)](https://developer.apple.com/macos/)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](https://github.com/codentacos/monitorMRR-Releases/releases)

[Download](https://github.com/codentacos/monitorMRR-Releases/releases) &nbsp;|&nbsp; [Report Issues](https://github.com/codentacos/monitorMRR-Releases/issues) &nbsp;|&nbsp; [Discussions](https://github.com/codentacos/monitorMRR-Releases/discussions)

</div>

---

## Overview

MonitorMRR is a lightweight macOS menu bar app that aggregates your daily revenue from Stripe, LemonSqueezy, and Gumroad into a single stacked chart. Click the menu bar icon to instantly see how your business is performing — no browser tab required.

---

## Features

### Revenue Dashboard

- Stacked area chart showing daily revenue broken down per provider for the last 30 days
- Total revenue and order count displayed at a glance
- Color-coded by provider: LemonSqueezy (yellow), Stripe (purple), Gumroad (pink)
- Refresh on demand with a single click

### Multi-Provider Support

- **Stripe** — fetches charges via the v1 API, counts only `succeeded` transactions
- **LemonSqueezy** — fetches orders via the v1 API, counts only `paid` orders
- **Gumroad** — fetches sales via the v2 API, excludes refunded and chargedback sales
- Connect any combination — only providers with a configured API key are shown

### Secure Credential Storage

- All API keys stored in the macOS system keychain via `tauri-plugin-keyring`
- Keys are never stored in plain text or sent anywhere except the provider's own API
- Add, update, or remove keys at any time from Settings

### Demo Mode

- Try the full interface without connecting any accounts
- Generates 30 days of realistic synthetic revenue across all three providers

---

## Installation

### Option 1: DMG (Recommended)

1. Download the latest DMG from [Releases](https://github.com/codentacos/monitorMRR-Releases/releases).
2. Mount the DMG file.
3. Drag `MonitorMRR.app` to your Applications folder.
4. Launch MonitorMRR from Applications.

## Gatekeeper Blocked?

Because MonitorMRR is not signed with a paid Apple Developer certificate, macOS Gatekeeper may block it on first launch.

**To bypass Gatekeeper securely:**

1. Open Terminal — press `Cmd + Space`, type **Terminal**, and hit Enter.
2. Run the following command:

```bash
xattr -rd com.apple.quarantine /Applications/MonitorMRR.app
```

3. Launch MonitorMRR normally.

---

## Usage

### Getting Started

1. Launch MonitorMRR — it lives in the menu bar, not the Dock.
2. Enter your license key when prompted to activate the app.
3. Enter at least one provider API key to start tracking revenue.
4. Click the menu bar icon at any time to view your revenue chart.

### Connecting Providers

| Provider | Where to find your key |
|---|---|
| Stripe | Dashboard → Developers → API keys → Secret key |
| LemonSqueezy | Settings → API → API keys |
| Gumroad | Settings → Advanced → Applications → Access token |

Open **Settings** (gear icon) and paste the key into the relevant section. Keys are saved to the system keychain immediately.

### Viewing Revenue

The chart shows the last 30 days of daily revenue stacked by provider. Hover over any day to see a breakdown of revenue and order count per provider. Click the refresh button in the footer to pull the latest data.

---

## System Requirements

| Requirement | Minimum |
|---|---|
| macOS | 14.0 (Sonoma) or later |
| Memory | 100 MB RAM |
| Storage | 50 MB free space |
| Processor | Apple Silicon or Intel |

---

## Privacy and Safety

- MonitorMRR collects no analytics and includes no telemetry.
- All API calls go directly from your machine to the provider's API — no proxy, no middleman.
- API keys and your license key are stored exclusively in the macOS system keychain.
- License verification only checks key validity — no personal data is transmitted.

---

## Contributing

Contributions are welcome.

### Development Setup

```bash
# Clone the repository
git clone https://github.com/codentacos/monitor-mrr.git
cd monitor-mrr

# Install dependencies
npm install

# Run in development mode
npm run tauri dev
```

---

## Bug Reports and Feature Requests

- **Bug Reports**: [File an issue](https://github.com/codentacos/monitorMRR-Releases/issues/new?template=bug_report.md)
- **Feature Requests**: [Suggest a feature](https://github.com/codentacos/monitorMRR-Releases/issues/new?template=feature_request.md)
- **Questions**: [Start a discussion](https://github.com/codentacos/monitorMRR-Releases/discussions)

---

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for a full history of changes.

