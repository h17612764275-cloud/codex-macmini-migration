# Mac mini · Codex 与心绪岛迁移包

快照日期：2026-09-28。先把整个 ZIP 复制到 Mac 并解压，再把 [给新Mac的第一条指令.md](给新Mac的第一条指令.md) 交给新电脑的 Codex。

## 三步开始

1. **核验文件**：在解压目录运行 `python3 verify_bundle.py`，应输出 `PASS`。Python 尚未安装时先按配置指南准备；也可先校验 ZIP 旁的 SHA-256 文件。
2. **恢复工作习惯**：按 [01-Mac配置指南.md](01-Mac配置指南.md) 恢复全局规则、个人 Skills 与角色，登录账号，检查实际可用插件。
3. **接手心绪岛**：读 [03-心绪岛项目交接.md](03-心绪岛项目交接.md)，把 `project/心绪岛` 整个目录放到 Mac 工作区。当前授权到迁移与环境核验；UI 编码仍需具体效果确认。

## 包里有什么

| 位置 | 内容 |
| --- | --- |
| `codex/AGENTS.md`、`codex/PLANS.md` | Mac 全局规则与持续计划约定；AGENTS 只替换了原 Windows 的 PLANS 路径。原文在 `codex/original-windows/`。文件名是 **AGENTS.md**，不是 agent.md。 |
| `skills/codex/`、`skills/agents/` | 196 个个人 Skill，分属 170 个顶级目录；保留 scripts、references、assets、示例及本地改动。 |
| `codex/agents/` | 265 份自定义角色 TOML，原样保留。 |
| `plugins-offline/` | Astra advisor 0.2.0 与 Ponytail 4.10.0 的本机文件快照，供回溯和本地安装核对；其他插件在新电脑恢复。 |
| `project/心绪岛/` | 整个项目的有效文件，包含需求、计划、设计候选、灵感原图、代码、测试、资源、锁文件及 `mobile/.git`。 |

详细名录见 [02-Skills名录与Mac兼容性.md](02-Skills名录与Mac兼容性.md)、[04-插件MCP与其他配置.md](04-插件MCP与其他配置.md)。核验结果见 [05-迁移核验与边界.md](05-迁移核验与边界.md)。

## 这份包的边界

本包是工作资料迁移包，不是旧电脑系统镜像。登录令牌、真实密钥、浏览器会话、Codex 历史数据库、运行中的自动任务、Windows 可执行程序和 `node_modules` 不随包恢复。用户已确认心绪岛没有需要另行转移的真实日记、碎碎念或荣誉记录。

Skills 文件已整理，不代表 196 项均已在 Mac 运行。已做静态分类：148 项文档/素材、28 项依赖待核对、20 项含 Windows 线索待适配审查。Mac 机型、系统版本、Xcode、插件登录和 iPhone 实测都要在目标电脑核验。
