# 🛠️ DeepSeek Harness Plugins

> 个人自用的 DeepSeek Harness 插件、扩展工具链与工作流集合。  
> Personal plugins, extensions, and experimental toolchains for DeepSeek Harness.

---

## 📦 插件 (Plugins)

| 仓库 | 说明 |
|---|---|
| [thinking-level-override](https://github.com/my-dsh-plugin/thinking-level-override) | 修复第三方模型思考等级预设缺失或不匹配：请求时按规则强制、默认或重映射思考等级，并提供 Web 设置页。Fixes missing or mismatched third-party thinking-level presets. |
| [session-archive-manager](https://github.com/my-dsh-plugin/session-archive-manager) | 在设置页查看并管理归档会话：取消归档、删除、批量删除、全量删除，按工作区分组展示。Manages archived sessions from Settings: view, unarchive, delete, batch delete, delete all. |
| [readonly-security-audit](https://github.com/my-dsh-plugin/readonly-security-audit) | 只读安全审计模式：系统级拦截所有写操作，逐次写入审批，强制报告交付选择；可作为 Agent 预设使用，并可迁移到任意 Harness 实例或 fork。Read-only security audit mode with system-enforced write blocking, per-write approval, and mandatory report-delivery choice. |
| [agent-mode-switcher](https://github.com/my-dsh-plugin/agent-mode-switcher) | 模型回答完毕后，可在当前会话切换 Agent 预设（标准/PTC/极简等）并继续对话；随附 Harness 核心补丁。Switches the current session's agent preset (mode) after the model answers and keeps chatting; ships a small harness core patch. |

---

## 🚀 快速开始 (Quick Start)

每个插件都是独立的 bundle-layer 插件，仓库随附预构建产物 `lib/`，消费者无需在插件仓库内构建。

通用安装方式：

```bash
cd /path/to/deepseek-harness

# 安装本地插件到 web profile
pnpm dsh plugin add --profile web /path/to/<plugin>

# 或直接 git 安装
pnpm dsh plugin add --profile web github:my-dsh-plugin/<plugin>
```

安装后重启 Harness 即可。不同插件若有额外步骤（如核心补丁、预设安装），以各插件仓库 README 为准。

---

## 🚧 状态 (Status)

- **Status**: 活跃开发中 (Active Development)
- **Goal**: 探索与构建定制化的 DeepSeek Harness 自动化工作流与功能插件，积累可复用的插件模板。

---

## 📌 规划 (Roadmap)

- [x] 思考等级覆盖插件（thinking-level-override）：引擎 + Web 设置页 + 文档
- [x] 归档会话管理插件（session-archive-manager）：设置页 UI + 核心 API 补丁
- [x] 只读安全审计插件（readonly-security-audit）：Agent 预设 + 系统强制只读 + 报告交付审批
- [x] 会话中途模式切换插件（agent-mode-switcher）：标题栏切换器 + Harness 核心补丁
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

各插件仓库按自身 LICENSE 发布；本组织页面仅作为导航与说明。
