# BFBTbridge

<p align="center">
  <img src="screenshots/icon.svg" alt="BFBTbridge — AI agent bridge" width="96" />
</p>

<p align="center">
  <strong>AI agent bridge</strong> · multi-agent connector · coding agent scheduler<br />
  电脑常驻 · 本机多智能体桥接 · 扫码调度 Cursor / Codex / BFBT Code
</p>

> Distribution-only repository. Installers and docs only — **no source code**.

官网：[www.dtrony.com](https://www.dtrony.com) · 文档：[安装与使用 BFBTbridge](https://www.dtrony.com/docs/agent-bridge) · [文档索引](docs/README.md) · 姊妹产品：[BFBT Code](https://github.com/dongfutong/BFBTCode) · [DTworkeasy Mobile](https://github.com/dongfutong/DTworkeasy-Mobile)

---

## What is BFBTbridge?

**BFBTbridge** is the PC-resident **AI agent bridge** from [DTrony / 东复同科技](https://www.dtrony.com): a **multi-agent connector** that attaches locally installed coding agents — **Cursor**, **Codex**, and sister product **[BFBT Code](https://github.com/dongfutong/BFBTCode)** — and a **coding agent scheduler** (in-app 调度面板) for those sessions.

Keep it running, pair with the [DTworkeasy](https://github.com/dongfutong/DTworkeasy-Mobile) mobile app via QR code, and continue the same local agent sessions from your phone. BFBTbridge does **not** provide its own large language model; models, accounts, and usage stay with each connected agent.

Using BFBTbridge requires the same trial or membership as **BFBT Code**. Official docs: [安装与使用 BFBTbridge](https://www.dtrony.com/docs/agent-bridge).

---

## 中文

### 一句话简介

**BFBTbridge** 是安装在电脑上的常驻 **AI 智能体桥接（AI agent bridge）**：把本机已安装的 **Cursor**、**Codex** 以及 **[BFBT Code](https://github.com/dongfutong/BFBTCode)** 接入同一套 **多智能体连接器（multi-agent connector）**，并在应用内「调度」面板作为 **编程智能体调度器（coding agent scheduler）** 下发任务。保持运行后，用手机端 [DTworkeasy](https://github.com/dongfutong/DTworkeasy-Mobile) 扫码配对，即可远程继续这些本机会话。

BFBTbridge **自己不提供大模型**；模型、账号和用量由已接入的编程智能体各自决定。使用需与 BFBT Code 相同的试用期或会员，详见 [会员权益](https://www.dtrony.com/docs/membership-benefits)。

### 主要特性

- 🖥️ **托盘常驻**：Windows / macOS 桌面版托盘运行；Linux 提供无桌面依赖的 CLI/TUI（`dt-bridge`）
- 📱 **扫码配对**：与 DTworkeasy 手机端同一官网账号，扫码完成设备配对
- 🤖 **多智能体连接**：暴露 Cursor CLI ACP、Codex CLI app-server 以及 BFBT Code 等本机能力
- 📋 **调度面板**：在「调度」中向本机编程智能体下发任务（见截图）
- 🔄 **应用内更新**：可检查官网新版本，落盘前校验 SHA-256
- 🔐 **签名分发**：Windows MSI 已签名；macOS DMG 已公证（notarized）；Linux 包提供 SHA256 / GPG

### 系统要求

| 平台 | 要求 |
|------|------|
| Windows | x64，推荐 Windows 10/11 |
| macOS | Apple Silicon（aarch64），macOS 13.0+ |
| Linux | x86_64，glibc ≥ 2.35（建议 Ubuntu 22.04+），无需 GTK/WebKit |

### 安装步骤

#### Windows

1. 从本仓库 [Releases](https://github.com/dongfutong/BFBTbridge/releases) 下载 `BFBTbridge_*_x64_zh-CN.msi`（与官网一致；历史 en-US MSI / setup.exe 见标签 [`v1.0.8.26101801`](https://github.com/dongfutong/BFBTbridge/releases/tag/v1.0.8.26101801)，文件名同为 `BFBTbridge_*`）
2. 双击安装。若出现「Windows 已保护你的电脑」，确认来自本仓库/官网后点「更多信息」→「仍要运行」
3. 从开始菜单打开 **BFBTbridge**，登录东复同账号并保持运行
4. 在手机 DTworkeasy 中扫码配对

#### macOS（Apple Silicon）

1. 下载 `BFBTbridge_*_aarch64.dmg`
2. 打开 DMG，将应用拖入「应用程序」
3. 首次打开若提示身份不明，到「系统设置 → 隐私与安全性」点「仍要打开」
4. 登录账号，配合手机 DTworkeasy 扫码使用

#### Linux（TUI / 无桌面服务器）

```bash
# deb
sudo dpkg -i bfbtbridge-tui_1.0.0_amd64.deb

# 或 tar.gz + 校验
sha256sum --check SHA256SUMS --ignore-missing
python3 install.py bfbtbridge-tui_1.0.0_linux_x86_64.tar.gz \
  --checksums SHA256SUMS
```

前台服务示例：

```bash
dt-bridge serve --credential-store protected-file
dt-bridge login
dt-bridge doctor --json
dt-bridge devices qr --agent opencode
dt-bridge tui
```

完整步骤见官网 [安装与使用 BFBTbridge](https://www.dtrony.com/docs/agent-bridge)。

### 下载表（Release 资源）

下列文件名与 Latest Release [`v1.0.8.26102002`](https://github.com/dongfutong/BFBTbridge/releases/tag/v1.0.8.26102002) 的资源一致（`BFBTbridge_*` / `bfbtbridge-tui_*`）。

| 平台 | 文件名 | 说明 |
|------|--------|------|
| Windows (zh-CN) | [`BFBTbridge_1.0.8.26102002_x64_zh-CN.msi`](https://github.com/dongfutong/BFBTbridge/releases/download/v1.0.8.26102002/BFBTbridge_1.0.8.26102002_x64_zh-CN.msi) | MSI 安装包（与官网一致） |
| macOS | [`BFBTbridge_1.0.8.26102001_aarch64.dmg`](https://github.com/dongfutong/BFBTbridge/releases/download/v1.0.8.26102002/BFBTbridge_1.0.8.26102001_aarch64.dmg) | Apple Silicon（已公证） |
| Linux deb | [`bfbtbridge-tui_1.0.0_amd64.deb`](https://github.com/dongfutong/BFBTbridge/releases/download/v1.0.8.26102002/bfbtbridge-tui_1.0.0_amd64.deb) | Ubuntu/Debian |
| Linux tar.gz | [`bfbtbridge-tui_1.0.0_linux_x86_64.tar.gz`](https://github.com/dongfutong/BFBTbridge/releases/download/v1.0.8.26102002/bfbtbridge-tui_1.0.0_linux_x86_64.tar.gz) | 便携包 |
| 校验 | [`SHA256SUMS`](https://github.com/dongfutong/BFBTbridge/releases/download/v1.0.8.26102002/SHA256SUMS) / [`install.py`](https://github.com/dongfutong/BFBTbridge/releases/download/v1.0.8.26102002/install.py) | 校验与安装脚本 |

> 说明：官网当前 Windows 渠道以 zh-CN MSI 为主；历史 en-US MSI / NSIS setup 仍可在旧 Release 中找到。

也可从官网下载中心获取：<https://www.dtrony.com/>

### 截图

实拍自当前已发布安装包的运行界面（非 BFBT Code）。文档中的产品名称是 **BFBTbridge**；截图像素保持实拍，未改字。

| 总览 Overview | 调度 Scheduler |
|:---:|:---:|
| ![BFBTbridge Overview — AI agent bridge dashboard](screenshots/01-desktop.png) | ![BFBTbridge Scheduler — coding agent task list](screenshots/02-agents.png) |
| **代理集 Agents** | **设置 Settings** |
| ![BFBTbridge Agents — multi-agent connector sessions](screenshots/03-pairing.png) | ![BFBTbridge Settings — local coding-agent detection](screenshots/04-settings.png) |

### 与姊妹产品的关系

```
手机 DTworkeasy  ──扫码──►  BFBTbridge（电脑常驻 AI agent bridge）
                              │
                              ├── Cursor / Codex
                              └── BFBT Code（旗舰 AI 编程助手）
```

- **BFBTbridge** 与 **BFBT Code** 采用同一规则：需处于试用期或有效会员状态方可使用；一份会员同时覆盖 **BFBT Code 与 BFBTbridge** 两者。说明见 [会员权益](https://www.dtrony.com/docs/membership-benefits)
- **DTworkeasy**（手机端）注册后即可免费使用，无需会员
- 远控电脑端 BFBT Code 时，电脑端同样须处于试用/会员可用状态

### 许可与声明

本仓库为 **发行版分发仓库**，仅包含安装包、校验文件与说明文档，**不包含源代码**。  
软件版权归 **成都东复同科技股份有限公司** 所有。更多条款见 [官网隐私政策](https://www.dtrony.com/api/legal/privacy)。

---

## English

### One-liner

**BFBTbridge** is the tray-resident **AI agent bridge** for the [DTworkeasy](https://github.com/dongfutong/DTworkeasy-Mobile) mobile app: a **multi-agent connector** and **coding agent scheduler** for local **Cursor**, **Codex**, and **[BFBT Code](https://github.com/dongfutong/BFBTCode)** agents. Keep it running on your PC, pair via QR code, and continue those sessions from your phone.

It does not ship its own LLM. See [Install and use BFBTbridge](https://www.dtrony.com/docs/agent-bridge) (Chinese official docs).

### Features

- Tray-resident on Windows / macOS; headless CLI/TUI (`dt-bridge`) on Linux (no GTK/WebKit)
- Same Dongfutong account as the website and DTworkeasy
- Multi-agent adapters (Cursor ACP, Codex app-server, BFBT Code, and more)
- In-app 调度 / Scheduler panel for dispatching tasks to local coding agents
- In-app updates with SHA-256 verification
- Signed Windows MSI; notarized macOS DMG; Linux packages with checksums / GPG

### Requirements

| Platform | Notes |
|----------|--------|
| Windows | x64, Windows 10/11 recommended |
| macOS | Apple Silicon only, macOS 13.0+ |
| Linux | x86_64, glibc ≥ 2.35 (Ubuntu 22.04+) |

### Install

**Windows:** download [`BFBTbridge_1.0.8.26102002_x64_zh-CN.msi`](https://github.com/dongfutong/BFBTbridge/releases/download/v1.0.8.26102002/BFBTbridge_1.0.8.26102002_x64_zh-CN.msi) from [Releases](https://github.com/dongfutong/BFBTbridge/releases), install, sign in, and open **BFBTbridge** from the Start Menu. Keep it running, then pair from DTworkeasy.

**macOS:** open [`BFBTbridge_1.0.8.26102001_aarch64.dmg`](https://github.com/dongfutong/BFBTbridge/releases/download/v1.0.8.26102002/BFBTbridge_1.0.8.26102001_aarch64.dmg), drag to Applications, allow in Privacy & Security if prompted, sign in, then pair.

**Linux:**

```bash
sudo dpkg -i bfbtbridge-tui_1.0.0_amd64.deb
# or verify SHA256SUMS, then:
# python3 install.py bfbtbridge-tui_1.0.0_linux_x86_64.tar.gz --checksums SHA256SUMS
dt-bridge serve --credential-store protected-file
```

Latest (`v1.0.8.26102002`) assets use `BFBTbridge_*` and `bfbtbridge-tui_*` names. Tag `v1.0.8.26101801` uses the same prefixes.

### Downloads

See the Chinese table above for exact asset filenames under [Releases](https://github.com/dongfutong/BFBTbridge/releases), or use <https://www.dtrony.com/>.

### Screenshots

Live captures of the currently published installer (not BFBT Code): 总览 Overview, 调度 Scheduler, 代理集 Agents, and 设置 Settings. These docs call the product **BFBTbridge**; screenshot pixels are left as captured. See the Chinese section above.

### Membership

**BFBTbridge** itself requires an active trial or paid membership, under the same rules as **BFBT Code** — a single membership covers **both BFBT Code and BFBTbridge**. The **DTworkeasy** mobile app remains free after registration; no membership required. Details: [Membership benefits](https://www.dtrony.com/docs/membership-benefits) (Chinese).

### License note

This repository is **distribution-only** (installers + docs, **no source**).  
© Chengdu Dongfutong Technology Co., Ltd. See [Privacy Policy](https://www.dtrony.com/api/legal/privacy).

---

## 日本語（抜粋）

**BFBTbridge** は PC 常駐の **AI agent bridge**（マルチエージェント接続 / コーディングエージェント・スケジューラ）です。スマホの DTworkeasy で QR ペアリングすると、本機の Cursor / Codex / [BFBT Code](https://github.com/dongfutong/BFBTCode) を遠隔利用できます。Windows・macOS（Apple Silicon）・Linux（TUI）に対応。利用には BFBT Code と同じくトライアル期間または有効なメンバーシップが必要です（1 つのメンバーシップで両製品をカバー）。DTworkeasy モバイルアプリは登録後無料です。配布専用リポジトリ（ソース無し）。公式サイト：https://www.dtrony.com · ドキュメント：https://www.dtrony.com/docs/agent-bridge

## 한국어（요약）

**BFBTbridge**는 PC에 상주하는 **AI agent bridge**(멀티 에이전트 커넥터 / 코딩 에이전트 스케줄러)입니다. DTworkeasy 모바일 앱에서 QR로 페어링하면 로컬 Cursor / Codex / [BFBT Code](https://github.com/dongfutong/BFBTCode) 를 원격 제어할 수 있습니다. Windows·macOS(Apple Silicon)·Linux(TUI) 지원. 사용에는 BFBT Code와 동일하게 체험 기간 또는 유효한 멤버십이 필요하며, 하나의 멤버십으로 두 제품을 모두 이용할 수 있습니다. DTworkeasy 모바일 앱은 가입 후 무료입니다. 배포 전용 저장소(소스 없음). 공식: https://www.dtrony.com · 문서: https://www.dtrony.com/docs/agent-bridge

---

**Suggested Release tag:** `v1.0.8.26102002`（Windows zh-CN） / 可同时附带 macOS `1.0.8.26102001` 与 Linux `1.0.0` 资源  
**Website:** https://www.dtrony.com  
**Docs:** https://www.dtrony.com/docs/agent-bridge · [repo docs index](docs/README.md)
