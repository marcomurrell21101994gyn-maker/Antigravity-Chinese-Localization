# v2.35.2 发布说明 — 同步适配官方 Antigravity 2.35.2

## 适配结论

本版本为**官方客户端版本号同步适配版**。经对官方 `2.35.1` 与 `2.35.2` 原版 `app.asar` 逐文件（共 1167 个文件）哈希比对核验：

- 两个版本之间**仅 `package.json` 的 `version` 字段由 `2.35.1` 变为 `2.35.2`**；
- 其余全部文件（含 `dist/` 主进程、渲染层、`node_modules/` 等）**字节级完全一致，无新增、删除或修改**；
- 因此本版本**没有新增或变更的界面文案**，汉化词典沿用 v2.35.1 的 4,923 键基线，翻译引擎与免疫逻辑零改动，仅升级版本指纹以通过客户端版本门禁。

## 产物信息

| 项目 | 值 |
| --- | --- |
| 适配客户端版本 | Antigravity **2.35.2** |
| 文件 | `app.asar` |
| 大小 | 7,945,901 字节（约 7.58 MiB） |
| SHA-256 | `ead3cea5947497801ef99407a3eeaf49de53c0fe06a465c8b854bbc7816ba2c9` |
| 解包（unpacked）文件 | 377 个，全部位于 `node_modules/chrome-devtools-mcp/`，标记与官方完全一致（0 处差异） |

## 安装方法（Windows 手动覆盖）

1. 彻底退出正在运行的 Antigravity（含后台语言服务）；
2. 打开程序目录：`%LOCALAPPDATA%\Programs\antigravity\resources\`；
3. 将原始 `app.asar` 备份为 `app.asar.bak`（若已存在可跳过）；
4. 用本发布的 `app.asar` 覆盖；
5. 重新启动 Antigravity。

> 注意：`node_modules/chrome-devtools-mcp` 为外部解包模块，位于 `resources\app.asar.unpacked\`，由官方安装包提供，**请勿删除**；本汉化包不修改该目录内容。

## 安全与免疫边界（沿用）

- 模型名称（Gemini / Orchestrator / Claude 等）、相对时间、思考链（Thinking/Thought）保持官方英文；
- 输入框、Monaco 代码编辑器、Diff 视图、用户与 AI 对话气泡、Markdown 正文及行内代码均不翻译，仅替换 DOM 叶子文本节点，不破坏 React Fiber 子树。

## 还原方法

将备份的官方 `app.asar.bak` 复制覆盖回 `app.asar` 即可恢复英文原版。

## macOS 提示

替换 `app.asar` 会使 Google 原始代码签名失效，可能提示“应用已损坏”。需保留官方签名时请勿替换；如替换后无法启动，可用官方完整安装包覆盖安装以恢复签名。
