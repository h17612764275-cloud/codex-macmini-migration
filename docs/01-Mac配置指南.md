# Mac mini 配置指南

这是给新电脑 Codex 和操作者的恢复步骤。源快照来自 2026-09-28 的 Windows；Mac 操作尚未执行。推荐先完成“规则与项目接手”，再按当前任务启用工具，避免一次安装全部创作软件。

## 1. 检查机器并安装桌面端

在 Mac 终端记录：

```sh
uname -m
sw_vers
xcode-select -p
git --version
node --version
npm --version
python3 --version
```

缺少某个命令即记录为待安装，不代表迁移包损坏。`arm64` 对应 Apple Silicon；若显示 `x86_64`，先确认是否 Intel 或终端运行于 Rosetta，再选择对应软件架构。新 Mac 的芯片与 macOS 版本尚未由本次任务确认。

从[官方桌面端入口](https://learn.chatgpt.com/docs/app)下载当前提供的 macOS 客户端并登录同一 ChatGPT 账号。2026-09-28 官方入口标题为 ChatGPT desktop app，在其中选择 Codex；以当前下载页和实际界面为准。重新授权所需系统权限和连接器。不要用 Windows `auth.json` 或浏览器资料代替登录。

Codex CLI 是可选项，桌面端接手项目不以全局 npm 安装 CLI 为前提。只在后续确实使用 CLI 时按官方说明安装。

## 2. 放置全局规则、角色与 Skills

退出目标 Mac 的 Codex 客户端后操作。先备份目标机现有的 `~/.codex/AGENTS.md`、`PLANS.md`、`config.toml`、`agents/` 和两处 Skills 目录（如存在），放入带日期的备份目录。若目标已有同名而不同内容的文件，先比较，不覆盖。

| 包内来源 | Mac 目标 |
| --- | --- |
| `codex/AGENTS.md` | `~/.codex/AGENTS.md` |
| `codex/PLANS.md` | `~/.codex/PLANS.md` |
| `codex/agents/*.toml` | `~/.codex/agents/` |
| `skills/agents/` 的内容 | `~/.agents/skills/` |
| `skills/codex/` 的内容 | `~/.codex/skills/`，先保留旧布局，按下文核对发现路径 |

`AGENTS.md` 保留中文输出、ADHD 模式、Astra 默认流程、可见进度、设计确认和个人 Skill 简介规范。只有 PLANS 路径由 `C:/Users/Administra/.codex/PLANS.md` 改为 `~/.codex/PLANS.md`。若有 `~/.codex/AGENTS.override.md`，核对它是否遮住规则；官方描述了[全局与项目规则的加载顺序](https://learn.chatgpt.com/docs/agent-configuration/agents-md)。

官方当前列出的用户 Skills 发现路径是 `~/.agents/skills`，支持符号链接；Windows 本机也使用了 `~/.codex/skills`。先恢复原布局并检查新版本是否识别 `i-have-adhd`、`h3-prompt-writing` 等来自旧路径的 Skill。若没有识别，再将 `~/.codex/skills` 的各顶级包链接到 `~/.agents/skills`，保留原文件位置。逐个检查目标不存在，不覆盖已有包；已经识别时不要额外建重复入口。[Skills 官方说明](https://learn.chatgpt.com/docs/build-skills)

Skills 名称、原 `display_name`、`short_description`、脚本和说明此次未修改。当前发现 `lieflat-less-ai-tone` 缺少 `agents/openai.yaml`；这是源状态，已保留，不在备份中悄悄补写。Mac 恢复后按用户规则检查全部恢复的个人 Skill：YAML、UTF-8、简介格式、缺少 metadata、技能页面显示。若需要修简介或补 metadata，先给完整清单并获得确认，不批量重写。

265 份角色定义只有 `name`、`description`、`developer_instructions` 等实际文件字段；文件备份不等于工具授权或账号权限。角色目录由[自定义代理官方说明](https://learn.chatgpt.com/docs/agent-configuration/subagents)支持。

## 3. 配置模型与插件

参考 `codex/config.mac.example.toml`，按目标机已有配置逐项合并。不要整份覆盖目标 `config.toml`。示例保留原文件默认的 `gpt-6-astra / ultra / pragmatic`；这只说明原机配置值，不证明任意会话实际采用它，也不保证新账号显示同一模型。不可用时先报告实际模型列表，由用户决定。

原机还设置过 `model_context_window=872000`、`model_auto_compact_token_limit=800000` 和 `danger-full-access`；记录在配置盘点中，未作为 Mac 默认强行启用。上下文大小随模型和客户端变化；权限应在新机按实际信任范围设置。示例用注释保留原权限值，桌面主题、字体和通知则在 UI 中按 [04](04-插件MCP与其他配置.md) 恢复。[官方配置说明](https://learn.chatgpt.com/docs/config-file/config-basic)

先恢复 Astra advisor 与 Ponytail；检查插件的安装状态、实际 callable 工具/Skills、可用模型。个人 Skills 无需把所有相关插件一次性安装。连接器使用同一账号重新确认登录，Windows 插件缓存中的 exe、临时目录和管道值不应覆盖 Mac 自带运行时。

## 4. 放置心绪岛并准备开发依赖

建议路径 `~/Developer/心绪岛`。把包内 **整个** `project/心绪岛/` 复制过去，包含隐藏的 `mobile/.git`、`.gitignore`。不要只复制 mobile，不要通过一次 git clone 代替工作区复制。项目根目录不在 Git 内，mobile 无远程，存在 4 个已跟踪修改和 33 个未跟踪文件。

先读项目 `AGENTS.md`、`PROJECT_STATE.md` 和本包 [项目交接](03-心绪岛项目交接.md)。旧文档里的“Mac 尚未到货”是历史记录；这次已授权新机迁移和环境核验，未授权进入尚未确认的 UI 编码。

项目锁定 Expo 57.0.24 / React Native 0.86.3 / React 19.2.3 / TypeScript 6.0.3。查得 Expo SDK 57 的最低 Node 为 22.13.x、iOS 为 16.4+、Xcode 为 26.4+；目标 Mac 需安装能够承载相应 Xcode 的系统，实际兼容以安装当日与机器核验为准。[Expo 版本表](https://docs.expo.dev/versions/latest/)

在符合约束的 Node 环境中，从项目 `mobile/` 执行：

```sh
cd "$HOME/Developer/心绪岛/mobile"
npm ci
npm run typecheck
npm test
npm run build:web
```

本次在 Windows 打包时未运行这些 App 检查；这些是 **Mac 待执行步骤**。如 `npm ci` 失败，先记录 Node/npm 版本及首个错误，勿直接升级依赖或重新生成锁文件。通过后需要查看旧基线时运行 `npm run web -- --localhost --port 11335`。测试使用 Node 的 `--experimental-strip-types`，Node 版本不满足时先修环境。

`npm run ios` 只是已存在的 Expo 启动入口；不要把它当成独立安装包构建已经完成。原生工程、Xcode 签名、真机安装和 Widget 仍未实现/验证。按现有 iOS 子计划接手；此次不要自动执行 prebuild、签名、发布或改 UI。

## 5. 最短验收

1. 包校验通过；项目 176 个核心文件及 43 个 Git 文件完整；`git --no-optional-locks -C ~/Developer/心绪岛/mobile status --short` 与包内状态记录对应。
2. 新对话能正确复述全局中文规则、项目 UI 确认门禁；不被旧机器路径引导到不存在的位置。
3. Skills 页面能发现关键 Skill；先读 `i-have-adhd` 做纯文本响应，再按真实任务分别验脚本依赖。
4. Astra advisor、Ponytail、所需 MCP 各有一次真实读取/能力响应；只看到“安装成功”不能当可用。
5. 环境获准就绪后执行上述项目检查，保存真实结果；将“迁移完成”“Web 检查通过”“iOS 验证通过”分开报告。

预计：规则与文件恢复 15–30 分钟；依赖安装与 Web 检查 15–40 分钟，受网络影响；Xcode 下载和 iOS 签名另计。适合 Astra／高推理接手，Sol／中推理执行明确的安装核验。
