# 新 Mac mini：Codex 与心绪岛接手入口

**把这个页面交给新 Mac 的 Codex，从这里接手。**

这是私人迁移入口。完整文件在下面的 Release 附件里，仓库代码区用于在线阅读说明。快照日期：2026-09-28；完整 ZIP 为 **948,200,541 字节（约 904 MiB）**。

## 在新 Mac 上怎么开始

1. 登录有权限的 GitHub 账号（所有者 `h17612764275-cloud`）。浏览器能打开本页，不代表 Codex 的 GitHub 连接器或终端已登录；读不了私有仓库时，先完成相应登录。不要把仓库改公开来绕过登录。
2. 打开 [完整迁移包下载页](https://github.com/h17612764275-cloud/codex-macmini-migration/releases/tag/migration-2026-09-28)，在 **Assets** 下载 `macmini-codex-xinxudao-20260928.zip` 和 `SHA256SUMS.txt`。
3. 校验、解压，将解压后的整个目录交给 Codex。读取 [给新 Mac 的第一条指令](docs/给新Mac的第一条指令.md)，继续执行 [Mac 配置指南](docs/01-Mac配置指南.md)。

**不要下载 GitHub 自动生成的 “Source code (zip)” 当作完整包，也不要只 clone 这个仓库。** 那些只有在线说明，没有完整 Skills、项目素材和项目 Git 历史。

终端已有 GitHub CLI 且登录成功时，可在一个新的空目录下载：

```sh
gh auth status
gh release download migration-2026-09-28 --repo h17612764275-cloud/codex-macmini-migration --pattern 'macmini-codex-xinxudao-20260928.zip' --pattern 'SHA256SUMS.txt'
shasum -a 256 -c SHA256SUMS.txt
```

没有 GitHub CLI 时用已登录浏览器下载即可。只在校验输出 `OK` 后解压到新目录；解压后进入 `Macmini-Codex-心绪岛迁移包`，有 Python 3 时运行 `python3 verify_bundle.py`，预期 `PASS: 4532 files checked`。目录已经存在时先比较，不覆盖。ZIP 内原文件名仍是中文；SHA256SUMS 对应上面的英文下载文件名，内容与本地已核验原包相同。

## 给新 Mac 的 Codex 的一句话

> 请读取这个仓库的 README 和接手文档，帮我把 Release 中的 Codex 配置、个人 Skills 与心绪岛项目恢复到这台 Mac。先核验文件和当前环境；遇到私有仓库访问问题先协助登录。迁移环境不等于批准心绪岛 UI 编码。

## 里面有什么

| 内容 | 在线说明 | 完整文件的位置 |
| --- | --- | --- |
| 中文工作规则、持续计划与 Mac 配置模板 | [Mac 配置指南](docs/01-Mac配置指南.md)；[AGENTS.md](codex/AGENTS.md) | ZIP 的 `codex/` |
| 196 个个人 Skills，含 scripts / references / assets | [完整名录及 Mac 兼容性](docs/02-Skills名录与Mac兼容性.md) | ZIP 的 `skills/` |
| 265 份独立代理角色、插件与 MCP 清单 | [插件、MCP 与其他配置](docs/04-插件MCP与其他配置.md) | ZIP 的 `codex/agents/`、`plugins-offline/` |
| 心绪岛源码、需求、设计与灵感素材、未提交文件、Git 历史 | [项目交接](docs/03-心绪岛项目交接.md) | ZIP 的 `project/心绪岛/` |
| 文件校验与尚待验证事项 | [核验与边界](docs/05-迁移核验与边界.md) | ZIP 的清单与校验器 |

## 接手边界

- 原机文件哈希、ZIP 完整性和心绪岛 Git 状态已核验。没有改原项目，没有上传登录令牌或浏览器会话；账户在新机重新登录。
- 196 个 Skills 是文件迁移：148 个以文字/素材为主，28 个依赖待核对，20 个含 Windows 调用线索待审查。Mac 执行、插件登录、Xcode 和 iPhone 实机未验证。
- 265 份角色是独立的 `agents/*.toml` 配置，不属于 Skills，也不是同时运行的 265 个程序。
- 心绪岛 App 编码仍暂停。C 版书架只是暂留候选，G0/G1/G2 未通过。先接手环境，再由用户确认具体效果与实施范围。
- 本仓库是迁移入口，不是心绪岛今后的源码主仓库。新机接手完成后若要建立开发仓库，再单独确认；保留现有未提交文件，不 reset。

SHA-256：`51edeb27ca31ce5b1b4473ee67d3d32605a165a25c2b33c4fb59d029ccd2d6ec`。

预计文件下载取决于网络；恢复规则和文件约 15–30 分钟。建议 Astra／高推理统筹，明确步骤可由 Sol／中推理执行。
