# GeekEZ Browser

<div align="center">

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)
![Version](https://img.shields.io/badge/version-1.0.0-green)

**A Stealthy Anti-Detect Browser for E-Commerce & Multi-Account Management.**

[🇨🇳 中文说明 (Chinese)](README_zh.md) | [📥 Download](https://github.com/EchoHS/GeekezBrowser/releases)

</div>

---

## 📖 Introduction

**GeekEZ Browser** is built on Electron and Puppeteer, integrated with the powerful **Xray-core**. It is designed to help e-commerce operators (Amazon, TikTok, Facebook, etc.) manage multiple accounts safely by isolating browser fingerprints and IP environments.

## ✨ Key Features

### 🛡️ Fingerprint Isolation
*   **Native Code Spoofing**: Proxies `toString()` methods to bypass integrity checks (e.g., `function getParameter() { [native code] }`).
*   **Media Noise Injection**: Adds invisible noise to **Canvas** and **AudioContext** to generate unique hardware fingerprints, preventing device association.
*   **Hardware Consistency**: UserAgent strictly matches `navigator.platform` and WebGL parameters.

### 🔗 Proxy Chain (Pre-Proxy)
*   **Protocol Support**: VMess, VLESS, Trojan, Shadowsocks, Socks5, HTTP.
*   **Pre-Proxy Tunneling**: `[Local] -> [Pre-Proxy] -> [Target Proxy] -> [Web]`. Hides your real IP from the target proxy provider.
*   **Subscription Manager**: Import nodes via subscription URLs with auto-update support (24h/72h).
*   **Smart Switching**: Auto-detects latency and switches to the best pre-proxy node.

### ⚡ Optimized for E-Commerce
*   **Stealth Mode**: Automatically removes automation flags (`navigator.webdriver`, CDP traces).
*   **Platform Ready**: Tested on TikTok, Facebook, Amazon, Shopee, etc.

## 🚀 Quick Start

### Option 1: Download Release (Recommended)
Go to the [**Releases**](https://github.com/EchoHS/GeekezBrowser/releases) page and download the installer for your system (Windows `.exe` / Mac `.dmg` / Linux `.AppImage`).

### Option 2: Run from Source

**Prerequisites**: Node.js (v16+) and Git.

1.  **Clone the repository**
    ```bash
    git clone https://github.com/EchoHS/GeekezBrowser.git
    cd GeekezBrowser
    ```

2.  **Install Dependencies**
    ```bash
    npm install
    ```
    *Note: The `postinstall` script will automatically download the correct `Xray-core` binary for your OS.*

3.  **Run the App**
    ```bash
    npm start
    ```

## 🛠 Compatibility Guide

| Platform | Rating | Notes |
| :--- | :--- | :--- |
| **TikTok** | ✅ Safe | Canvas noise effectively prevents device association. Requires high-quality residential IP. |
| **Facebook** | ✅ Safe | Automation flags stripped. Avoid aggressive bot-like behavior. |
| **Shopee** | ✅ Safe | Stable fingerprint suitable for seller center operations. |
| **Amazon (Buyer)** | ✅ Safe | Sufficient isolation for buyer/reviewer accounts. |
| **Amazon (Seller)** | ⚠️ Caution | For main accounts with high assets, VPS/Physical isolation is recommended due to TLS fingerprinting risks. |

## 📦 Build

To create an executable for your platform:

```bash
# Windows
npm run build:win
```

```bash
# macOS
npm run build:mac
```

```bash
# Linux
npm run build:linux
```

## ⚠️ Disclaimer
This tool is provided for educational and research purposes only. The developers are not responsible for any account bans or legal issues resulting from the use of this software. Please comply with the terms of service of the platforms you use.