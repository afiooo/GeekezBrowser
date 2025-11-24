# GeekEZ Browser

<div align="center">

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)
![Version](https://img.shields.io/badge/version-1.0.0-green)

**专为电商运营和多账号管理打造的指纹隐匿浏览器**

[🇺🇸 English](README.md) | [📥 下载安装包](https://github.com/EchoHS/GeekezBrowser/releases)

</div>

---

## 📖 简介

**GeekEZ Browser** 是一款基于 Electron 和 Puppeteer 构建的指纹浏览器，底层集成 **Xray-core** 实现强大的流量隧道管理。它致力于通过深度修改浏览器指纹和网络链路，帮助用户在 TikTok、Amazon、Facebook 等平台上安全地管理多个账号。

## ✨ 核心特性

### 🛡️ 深度指纹隔离
*   **Native Code 伪装**: 劫持 `toString()` 方法，使注入的 JS 函数显示为 `[native code]`，绕过代码完整性检测。
*   **多媒体噪音注入**: 对 **Canvas** 和 **AudioContext** 注入微小且不可见的随机噪音，生成唯一的硬件指纹，防止设备关联。
*   **硬件一致性**: 严格对应 UserAgent、系统平台 (Platform) 和显卡 (WebGL) 参数，杜绝逻辑漏洞。

### 🔗 强大的代理链路
*   **全协议支持**: 支持 VMess, VLESS, Trojan, Shadowsocks, Socks5, HTTP。
*   **前置代理 (链式代理)**: 支持 `[本机] -> [前置代理] -> [环境代理] -> [目标网站]` 架构。隐藏本机真实 IP，加密链路传输。
*   **订阅管理**: 支持导入订阅链接，支持定时自动更新 (24h/72h/自定义)。
*   **智能优选**: 一键测速并自动切换至延迟最低的前置节点。

### ⚡ 专为电商优化
*   **Stealth 模式**: 自动移除 `navigator.webdriver` 及 CDP 协议痕迹。
*   **多平台适用**: 针对 TikTok、Shopee、Amazon 等平台风控特点进行优化。

## 🚀 快速开始

### 方法 1: 下载安装包 (推荐)
前往 [**Releases**](https://github.com/EchoHS/GeekezBrowser/releases) 页面下载适配您系统的安装包直接运行。

### 方法 2: 源码运行

**前置要求**: 安装 Node.js (v16+) 和 Git。

1.  **克隆仓库**
    ```bash
    git clone https://github.com/EchoHS/GeekezBrowser.git
    cd GeekezBrowser
    ```

2.  **安装依赖**
    *推荐使用国内镜像源加速下载*
    ```bash
    npm install
    ```
    *注意：安装过程中会自动触发 `setup.js` 脚本，智能检测您的网络环境（中国/海外），并下载适配的 Xray 内核（国内自动使用加速镜像）。*

3.  **启动软件**
    ```bash
    npm start
    ```

## 🛠 平台适用性指南

| 平台 | 安全评级 | 备注建议 |
| :--- | :--- | :--- |
| **TikTok** | ✅ 安全 | Canvas 噪音有效防止设备关联。核心在于使用高质量的纯净住宅 IP。 |
| **Facebook** | ✅ 安全 | 已去除自动化特征。适合广告投放和日常养号，请避免高频机器行为。 |
| **Shopee (虾皮)** | ✅ 安全 | 指纹稳定，适合卖家后台运营。 |
| **Amazon (买家)** | ✅ 安全 | 隔离级别足以应对买家号、测评号的风控。 |
| **Amazon (卖家)** | ⚠️ 谨慎 | 对于资金巨大的主店铺，由于 TLS 指纹 (JA3) 的底层特征，建议仍使用物理隔离 (VPS) 以策万全。 |

## 📦 打包发布

如果您需要自己生成安装包：

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

## ⚠️ 免责声明
本软件仅供技术研究与教育使用。开发者不对因使用本软件导致的账号封禁、法律风险或经济损失承担任何责任。请用户严格遵守各平台的使用规则和当地法律法规。