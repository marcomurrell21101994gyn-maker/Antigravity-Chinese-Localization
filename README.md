# Antigravity 中文汉化补丁

为 Google **Antigravity** 提供的非官方、非破坏性中文界面汉化补丁，让 Antigravity 的菜单、设置、权限、对话框等界面元素显示为中文。

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-informational.svg)](#安装方法)
[![Release](https://img.shields.io/github/v/release/marcomurrell21101994gyn-maker/Antigravity-Chinese-Localization?color=success)](https://github.com/marcomurrell21101994gyn-maker/Antigravity-Chinese-Localization/releases/latest)

> 如果这个项目对你有帮助，欢迎点右上角的 **Star ⭐** 支持维护，也欢迎在 [Issues](https://github.com/marcomurrell21101994gyn-maker/Antigravity-Chinese-Localization/issues) 反馈问题。

---

## 特性

- **界面汉化**：原生菜单、系统设置、权限与安全沙盒、通知、对话框、SSH 与各类工作流界面中文化；
- **非破坏性**：仅替换渲染层的叶子文本节点，不修改 React 组件结构，不破坏功能；
- **智能免疫**：模型名称、思考链、相对时间保持英文；输入框、代码编辑器、Diff 视图、AI 对话与 Markdown 正文、行内代码一律不翻译；
- **轻量**：对齐官方打包规格，仅替换 `app.asar`，并保持外部解包目录结构一致。

## 适配版本

| 客户端版本 | 补丁状态 |
| --- | --- |
| Antigravity **2.35.2** | ✅ 已适配（当前 Release） |

> 官方 2.35.1 → 2.35.2 仅 `package.json` 版本号变化，其余文件字节级一致，因此本版本无新增界面文案，翻译引擎零改动，仅升级版本指纹。

## 安装方法

### Windows（手动覆盖）

1. 彻底退出 Antigravity（含后台语言服务）；
2. 打开程序目录：`%LOCALAPPDATA%\Programs\antigravity\resources\`；
3. 把原始 `app.asar` 备份为 `app.asar.bak`；
4. 从 [Release](https://github.com/marcomurrell21101994gyn-maker/Antigravity-Chinese-Localization/releases/latest) 下载 `app.asar`，覆盖到该目录；
5. 重新启动 Antigravity。

> **关于 `app.asar.unpacked`**：`node_modules/chrome-devtools-mcp` 是外部解包模块，由官方安装包提供，**请勿删除**。若你的目录里缺少该文件夹，可下载 Release 中的完整压缩包 `Antigravity-2.35.2-zh-CN.zip`，把其中的 `app.asar.unpacked` 一并放到 `resources\` 目录。

### 校验完整性

下载后可对照 Release 中的 `SHA256SUMS.txt` 校验文件 SHA-256，确认下载无损、未被篡改。

### 还原英文

将备份的 `app.asar.bak` 复制覆盖回 `app.asar` 即可恢复官方英文界面。

### macOS 提示

替换 `app.asar` 会使 Google 原始代码签名失效，可能提示“应用已损坏”。需要保留官方签名时请勿替换；若替换后无法启动，可用官方完整安装包覆盖安装以恢复签名。

## 免责声明

本项目为社区爱好者制作的**非官方**汉化补丁，与 Google 及其 Antigravity 产品无任何隶属、赞助或背书关系。所有商标、产品名称及版权归其各自所有者所有。请在遵守 Antigravity 服务条款的前提下使用。

## License

[MIT](LICENSE)
