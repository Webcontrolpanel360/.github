# 🌐 WCP360 — Web Control Panel 360

<p align="center">
  <img src="https://raw.githubusercontent.com/Webcontrolpanel360/wcp360/main/assets/logo.png" alt="WCP360 Logo" width="200">
  <br>
  <b>The modern control panel for web hosting, app management, and system control.</b>
  <br>
  <i>Fast • Modular • Built for the next generation of hosting.</i>
</p>

<p align="center">
  <img src="https://img.shields.io/github/license/Webcontrolpanel360/wcp360?style=flat-square&color=blue" alt="License">
  <img src="https://img.shields.io/github/stars/Webcontrolpanel360/wcp360?style=flat-square" alt="Stars">
  <img src="https://img.shields.io/github/issues/Webcontrolpanel360/wcp360?style=flat-square&color=orange" alt="Issues">
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square" alt="PRs Welcome">
</p>

---

<p align="center">
  <a href="https://www.wcp360.com">🌍 Website</a> • 
  <a href="https://docs.wcp360.com">📖 Documentation</a> • 
  <a href="https://forum.wcp360.com">💬 Community Forum</a> • 
  <a href="https://github.com/Webcontrolpanel360/wcp360/blob/main/ROADMAP.md">🗺️ Roadmap</a>
</p>

---

## 🚀 The Vision

WCP360 is a **free and open-source** hosting control panel designed to replace expensive, closed-source solutions. It delivers a clean, performant, and highly modular experience for sysadmins, developers, and hosting providers.

### Global Server Layer
```ascii
╔════════════════════════════════════════════════════════════════╗
║              🖥️  WCP360 SERVER (NGINX + PODMAN)               ║
╠════════════════════════════════════════════════════════════════╣
║  • 🎛️ WCP360-Panel     - User Control Panel                   ║
║  • ⚙️ WCP360-Admin     - Administration Panel                  ║
║  • 🌐 NGINX 1.30.0     - Central Reverse Proxy & SSL           ║
║  • 🔍 PowerDNS / BIND9 - DNS Server                            ║
║  • 🗄️ MariaDB 12.2.2   - Metadata & User Management           ║
║  • 🐳 Podman (rootless)- Container Orchestration & Isolation   ║
╚════════════════════════════════════════════════════════════════╝

        ┌──────────────────────────────────────────┼──────────────────────────────────────────┐
        │                                          │                                          │
        ▼                                          ▼                                          ▼
┌───────────────────────────────┐ ┌───────────────────────────────┐ ┌───────────────────────────────┐
│         👤 USER 1             │ │         👤 USER 2             │ │         👤 USER 3             │
├───────────────────────────────┤ ├───────────────────────────────┤ ├───────────────────────────────┤
│ **Web Server (Switchable)**   │ │ **Web Server (Switchable)**   │ │ **Web Server (Switchable)**   │
│ • **Default**: NGINX 1.30.0   │ │ • **Default**: NGINX 1.30.0   │ │ • **Default**: NGINX 1.30.0   │
│   + PHP-FPM                   │ │   + PHP-FPM                   │ │   + PHP-FPM                   │
│ • Option: Apache 2.4.66       │ │ • Option: Apache 2.4.66       │ │ • Option: Apache 2.4.66       │
│   (mod_php or PHP-FPM)        │ │   (mod_php or PHP-FPM)        │ │   (mod_php or PHP-FPM)        │
│ • Optional: Varnish / Redis   │ │ • Optional: Varnish / Redis   │ │ • Optional: OpenLiteSpeed     │
│                               │ │                               │ │                               │
│ **Applications**              │ │ **Applications**              │ │ **Applications**              │
│ • site1.com → PHP 8.5.5 (NGINX)│ │ • api.site.com → Go 1.26.2    │ │ • classic.com → PHP 8.4 (Apache)│
│ • site2.com → PHP 8.4 (NGINX) │ │ • main.site.com → PHP 8.5 (NGINX)│ │ • modern.com → PHP 8.3 (NGINX)│
│ • legacy.com → PHP 8.2 (Apache)│ │ • app.site.com → Node.js 22   │ │ • vintage.com → PHP 8.1 (Apache)│
│                               │ │                               │ │ • python.site.com → Python 3.12│
│                               │ │                               │ │                               │
│ **Databases**                 │ │ **Databases**                 │ │ **Databases**                 │
│ • MariaDB 12.2.2 (dedicated)  │ │ • MariaDB 12.2.2 (dedicated)  │ │ • MariaDB 12.2.2 or Percona   │
│ • phpMyAdmin / Adminer        │ │ • phpMyAdmin                  │ │ • PostgreSQL (optional)       │
├───────────────────────────────┤ ├───────────────────────────────┤ ├───────────────────────────────┤
│ **Resource Limits**           │ │ **Resource Limits**           │ │ **Resource Limits**           │
│ • CPU, RAM & Storage quotas   │ │ • CPU, RAM & Storage quotas   │ │ • CPU, RAM & Storage quotas   │
│ • Rootless Podman isolation   │ │ • Rootless Podman isolation   │ │ • Rootless Podman isolation   │
└───────────────────────────────┘ └───────────────────────────────┘ └───────────────────────────────┘

```

### Key Features

- **Central Reverse Proxy**: NGINX 1.30.0 (latest stable) handles SSL termination, routing, security, and performance optimization.
- **Flexible Web Server**: Each user can choose **NGINX** (default, recommended) or **Apache 2.4.66** per site.
- **Container Technology**: Rootless **Podman** for secure, daemonless isolation.
- **Latest Stable Versions**:
  - NGINX: **1.30.0**
  - Apache: **2.4.66**
  - PHP: **8.5.5** (with multi-version support)
  - MariaDB: **12.2.2**
  - Go: **1.26.2**

Would you like me to also add a **"Key Benefits"** section or a **"Service Management Capabilities"** table below this diagram?

---

## 📦 Project Structure

WCP360 is organized as a clear ecosystem under the **Webcontrolpanel360** GitHub organization:

| Repository                        | Description |
|-----------------------------------|-----------|
| **[wcp360](https://github.com/Webcontrolpanel360/wcp360)** | Main umbrella repository – project overview, roadmap, and central documentation |
| **[wcp360-core](https://github.com/Webcontrolpanel360/wcp360-core)** | Backend engine (**Rust + Python** via PyO3) – API, security, modules, and business logic |
| **[wcp360-ui](https://github.com/Webcontrolpanel360/wcp360-ui)** | Modern responsive frontend (TypeScript/React or similar) |
| **[wcp360-docs](https://github.com/Webcontrolpanel360/wcp360-docs)** | Official documentation for users and developers |
| **[wcp360.website](https://github.com/Webcontrolpanel360/wcp360.website)** | Official marketing website and landing page |
| **[wcp360-cli](https://github.com/Webcontrolpanel360/wcp360-cli)** | Command-line tool to install, manage, update, backup, and deploy WCP360 |
| **[wcp360-plugins](https://github.com/Webcontrolpanel360/wcp360-plugins)** | Plugin system, base templates, and community extensions |
| **[wcp360-examples](https://github.com/Webcontrolpanel360/wcp360-examples)** | Example configurations, dashboard templates, and use cases |
| **[wcp360-docker](https://github.com/Webcontrolpanel360/wcp360-docker)** | Official Docker images and Docker Compose setups |
| **[wcp360-api-client](https://github.com/Webcontrolpanel360/wcp360-api-client)** | Official API clients (JavaScript/TypeScript, Python, etc.) |
| **[wcp360-theme-default](https://github.com/Webcontrolpanel360/wcp360-theme-default)** | Default theme and styling system (design tokens, CSS variables, light/dark support) |

---

## 🛠 Developer Quickstart

We are actively looking for contributors!

1. Browse open issues labeled **`good first issue`** or **`help wanted`**
2. Fork the relevant repository and create a feature branch
3. Follow our [CONTRIBUTING.md](CONTRIBUTING.md) and [Conventional Commits](https://www.conventionalcommits.org/)
4. Open a Pull Request against the `develop` branch

See the full [Developer Guide](https://docs.wcp360.com) for detailed setup instructions.

---

## 🤝 Contributing

Contributions of all kinds are welcome — code, documentation, design, testing, translations, or just spreading the word.

- Fork the repo
- Create a branch: `git checkout -b feature/amazing-feature`
- Commit your changes: `git commit -m 'feat: add amazing feature'`
- Push to the branch: `git push origin feature/amazing-feature`
- Open a Pull Request

Please read our [CONTRIBUTING.md](CONTRIBUTING.md) before submitting your first PR.

---

## 💬 Connect With Us

- **Discord** → [Join the 360° Community](https://discord.gg/wcp360)
- **X / Twitter** → [@WCP360_Official](https://twitter.com/wcp360)
- **Email** → support@wcp360.com
- **Forum** → [forum.wcp360.com](https://forum.wcp360.com)

---

> **"Server management shouldn't be a headache. Get the 360° view your infrastructure deserves."**

---

**License:** [GPL-3.0](LICENSE)

Made with ❤️ for the open-source community.
