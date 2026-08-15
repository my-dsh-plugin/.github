# 🛠️ DeepSeek Harness Plugins & Presets

> 个人自用的 DeepSeek Harness 插件、Agent 预设模式、扩展工具链与工作流集合。  
> Personal plugins, agent preset modes, extensions, and experimental toolchains for DeepSeek Harness.

---

## 📦 插件 (Plugins)

| 仓库 | 说明 |
|---|---|
| [thinking-level-override](https://github.com/my-dsh-plugin/thinking-level-override) | 修复第三方模型思考等级预设缺失或不匹配：请求时按规则强制、默认或重映射思考等级，并提供 Web 设置页。Fixes missing or mismatched third-party thinking-level presets. |
| [session-archive-manager](https://github.com/my-dsh-plugin/session-archive-manager) | 在设置页查看并管理归档会话：取消归档、删除、批量删除、全量删除，按工作区分组展示。Manages archived sessions from Settings: view, unarchive, delete, batch delete, delete all. |
| [readonly-security-audit](https://github.com/my-dsh-plugin/readonly-security-audit) | 只读安全审计模式的**实验性插件版**：自动只读、工具级白名单、强制报告交付选择。日常使用推荐 [dsh-presets](https://github.com/my-dsh-plugin/dsh-presets) 中的纯预设版。Experimental plugin edition of the read-only audit mode (auto read-only, tool allowlist, mandatory delivery); the pure-preset edition lives in dsh-presets. |
| [agent-mode-switcher](https://github.com/my-dsh-plugin/agent-mode-switcher) | 模型回答完毕后，可在当前会话切换 Agent 预设（标准/PTC/极简等）并继续对话；随附 Harness 核心补丁。Switches the current session's agent preset (mode) after the model answers and keeps chatting; ships a small harness core patch. |

---

## 🎛️ 预设模式 (Agent Presets)

| 仓库 | 说明 |
|---|---|
| [dsh-presets](https://github.com/my-dsh-plugin/dsh-presets) | 可一键安装的 Agent 预设模式合集（脚本式，跨平台）：**锚定极简**（anchored-minimal，V4 Pro 锚定的极简模式，首请求极简工具对、之后完整工具集）、**只读安全审计**（readonly-audit，纯预设版）。Installable agent preset modes, one-command cross-platform installers. |

---

## 🚀 快速开始 (Quick Start)

**插件**：每个插件都是独立的 bundle-layer 插件，仓库随附预构建产物 `lib/`，消费者无需在插件仓库内构建。

```bash
cd /path/to/deepseek-harness

# 安装本地插件到 web profile
pnpm dsh plugin add --profile web /path/to/<plugin>

# 或直接 git 安装
pnpm dsh plugin add --profile web github:my-dsh-plugin/<plugin>
```

**预设模式**：纯文件、脚本式一键安装（macOS/Linux 用 bash，Windows 用 PowerShell），自动识别 `DSH_HOME`（未设置回退 `~/.dsh`），默认拒绝覆盖、`--force` 覆盖前备份。

```bash
# 锚定极简（V4 Pro 锚定）
bash -c "$(curl -fsSL https://raw.githubusercontent.com/my-dsh-plugin/dsh-presets/main/anchored-minimal/install-anchored-minimal.sh)"

# 只读安全审计（纯预设版）
bash -c "$(curl -fsSL https://raw.githubusercontent.com/my-dsh-plugin/dsh-presets/main/readonly-audit/install-readonly-audit.sh)"
```

Windows PowerShell:

```powershell
irm https://raw.githubusercontent.com/my-dsh-plugin/dsh-presets/main/anchored-minimal/install-anchored-minimal.ps1 | iex
irm https://raw.githubusercontent.com/my-dsh-plugin/dsh-presets/main/readonly-audit/install-readonly-audit.ps1 | iex
```

安装后重启 Harness 即可。不同插件若有额外步骤（如核心补丁、预设安装），以各仓库 README 为准。

---

## 🚧 状态 (Status)

- **Status**: 活跃开发中 (Active Development)
- **Goal**: 探索与构建定制化的 DeepSeek Harness 自动化工作流与功能插件，积累可复用的插件模板。

---

## 📌 规划 (Roadmap)

- [x] 思考等级覆盖插件（thinking-level-override）：引擎 + Web 设置页 + 文档
- [x] 归档会话管理插件（session-archive-manager）：设置页 UI + 核心 API 补丁
- [x] 只读安全审计（readonly-security-audit）：实验性插件版（自动只读/白名单）+ dsh-presets 纯预设版
- [x] 会话中途模式切换插件（agent-mode-switcher）：标题栏切换器 + Harness 核心补丁
- [x] 预设模式合集（dsh-presets）：锚定极简（V4 Pro 锚定）、只读安全审计纯预设版，脚本式跨平台安装
- [ ] 插件开发脚手架 / 模板项目
- [ ] 核心功能与工作流扩展（更多供应商适配、批量配置管理）
- [ ] 自动化测试与部署脚本（CI、发布流程）

---

## 📝 约定 (Conventions)

- 每个仓库保持独立，尽量不依赖本机路径。
- 默认随附 `lib/` 预构建产物，安装方不执行构建。
- README 同时提供中英文说明。
- 迁移到其他机器或 fork 的步骤写入各插件 README。

---

## 📄 License

各仓库按自身 LICENSE 发布；本组织页面仅作为导航与说明。预设组合的部分内容版权归 DeepSeek（Copyright (c) 2026 DeepSeek）。
