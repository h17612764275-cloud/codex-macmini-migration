# 插件、MCP 与容易遗漏的配置

以下来自本机配置和缓存清单。**缓存存在、配置 enabled、工具真正可调用是不同状态**；这份名录不是所有插件已登录的证明。

## 先恢复的工作方式

| 项目 | 原状态 | Mac 处理 |
| --- | --- | --- |
| Astra advisor | 0.2.0，配置 enabled | 原来源 `https://github.com/DannyMac180/astra-advisor.git`；本地快照保留修改后的流程。先比较当前上游与包内版本，避免覆盖本地自定义。 |
| Ponytail | 4.10.0，配置 enabled | 原来源 `https://github.com/DietrichGebert/ponytail.git`；本聊天 full 模式，是否每个新会话自动注入须在 Mac 实测 hook。 |
| i-have-adhd | 全局 AGENTS 默认启用 | 已作为个人 Skill 携带，恢复后实际调用一次；支持用户停止口令。 |
| 自定义代理 | 265 份 TOML | 全部备份在 `codex/agents/`；精确名录见下表。 |

两份 `plugins-offline/` 是源文件快照，并非要求把缓存目录直接粘贴进新机缓存。可根据目标版本支持的本地插件/marketplace 机制注册快照，或从原来源安装后比较本地定制。不要擅自升级、重新启用已关闭的插件。原机 `codex-storyboard` 为 disabled，本包只记名录。

## MCP

| 服务 | 旧机实际配置 | Mac 恢复方式 |
| --- | --- | --- |
| `codebase-memory-mcp` | `C:/Users/Administra/.local/bin/codebase-memory-mcp.exe` | 从[原项目](https://github.com/DeusData/codebase-memory-mcp)选择匹配架构的 macOS 发行包；安装、校验后将实际绝对路径填入配置。旧 Windows exe 不可用；图索引在新项目路径重建。 |
| `wigolo` | `npx -y wigolo` | 先确认 Node/npx 可用；按需要启用，首次会获取依赖。测试一次只读响应，不能仅以配置条目为成功。 |
| `node_repl`／浏览器／computer-use | Windows 桌面运行时 exe、pipe 及机器环境值 | 由新 Mac 客户端和对应插件提供；不复制旧运行时路径、notify 或管道配置。 |

codebase-memory 工具缺失或索引不适用时按原规则回退到 rg；不因一个可选 MCP 没就阻塞文档和文件迁移。

## 可见偏好与附加资料

原配置文件默认：Astra / ultra，pragmatic；中文界面，暗色外观，正文 15、代码 12、终端默认右侧、显示上下文占用、纯文本输入模式、完成通知 always。仅供新机按偏好恢复，不包括麦克风设备 ID、旧项目信任目录、Windows sandbox、临时 runtime paths。

原机另有 1 项自动任务：“检查 MiniMax H3 Prompt Skill 更新”，原计划每周一 09:00，时区需在新机核对，原状态 ACTIVE。只检查官方文件变化并保留本地中文简介，更新须用户确认。本包未启用或迁移它；新机需要时再创建，避免两台机器重复执行。不要直接搬含旧 thread ID 的 automation.toml。

未迁移 `auth.json`、浏览器登录、API keys、`rules/default.rules` 既有命令批准记录、Codex SQLite/历史会话/运行锁、MCP 索引、Windows 工具与 Python/Node 虚拟环境。旧快捷键中的 Ctrl/Alt 和硬件项不照抄；在 Mac 用界面设置适配 Cmd/Option。

若以后需要完整旧聊天、其余个人记忆、自动任务、远程控制或 Windows 本地 AI 环境，那是可选后续迁移，先列范围再授权。本次已保留心绪岛必要项目决策，并明确不需要真实用户记录数据。

## 插件缓存名录

37 个缓存版本、36 个不同 marketplace/name；Chrome 同时有具体版本和 latest 路径，不能当成两个插件。配置未列条目并不意味着没有账号连接；状态以 Mac 实际读取为准。

| 插件／连接器 | marketplace | 本机缓存版本 | 配置记录 | 插件内 Skill 数 |
| --- | --- | --- | --- | ---: |
| astra-advisor | `astra-advisor` | `0.2.0` | enabled | 1 |
| codex-storyboard | `codex-storyboard` | `0.6.7+codex.20260914224348` | disabled | 2 |
| browser | `openai-bundled` | `26.924.22138` | enabled | 0 |
| chrome | `openai-bundled` | `26.924.22138` | enabled | 0 |
| chrome | `openai-bundled` | `latest` | enabled | 0 |
| codex-app-tools | `openai-bundled` | `0.1.5` | enabled | 0 |
| computer-use | `openai-bundled` | `26.924.22138` | enabled | 1 |
| unified-computer-use | `openai-bundled` | `26.924.22138` | enabled | 0 |
| visualize | `openai-bundled` | `1.0.41` | enabled | 1 |
| remotion | `openai-curated` | `bd2122cb` | enabled | 1 |
| Adobe | `openai-curated-remote` | `9.0.0` | 未在本地 plugins 表记录 | 7 |
| Astrology（以目标界面名称为准） | `openai-curated-remote` | `1.0.0` | 未在本地 plugins 表记录 | 0 |
| Gamma | `openai-curated-remote` | `6.0.0` | 未在本地 plugins 表记录 | 0 |
| Mobbin | `openai-curated-remote` | `3.0.0` | 未在本地 plugins 表记录 | 0 |
| Tarot Reading | `openai-curated-remote` | `1.0.0` | 未在本地 plugins 表记录 | 0 |
| build-web-apps | `openai-curated-remote` | `0.1.2` | 未在本地 plugins 表记录 | 6 |
| canva | `openai-curated-remote` | `16.0.0` | 未在本地 plugins 表记录 | 8 |
| codex-security | `openai-curated-remote` | `0.1.31` | 未在本地 plugins 表记录 | 15 |
| data-analytics | `openai-curated-remote` | `1.0.11` | 未在本地 plugins 表记录 | 20 |
| fal | `openai-curated-remote` | `1.1.0` | 未在本地 plugins 表记录 | 15 |
| figma | `openai-curated-remote` | `13.0.0` | 未在本地 plugins 表记录 | 14 |
| github | `openai-curated-remote` | `0.1.12-5f7cd798dc99` | 未在本地 plugins 表记录 | 0 |
| gmail | `openai-curated-remote` | `0.1.10` | 未在本地 plugins 表记录 | 0 |
| hugging-face | `openai-curated-remote` | `1.0.0` | 未在本地 plugins 表记录 | 11 |
| lovable | `openai-curated-remote` | `3.0.0` | 未在本地 plugins 表记录 | 0 |
| notion | `openai-curated-remote` | `0.1.8` | 未在本地 plugins 表记录 | 4 |
| openai-developers | `openai-curated-remote` | `1.3.0` | 未在本地 plugins 表记录 | 5 |
| openai-templates | `openai-curated-remote` | `0.1.1` | 未在本地 plugins 表记录 | 20 |
| plugin-management | `openai-curated-remote` | `0.1.0` | 未在本地 plugins 表记录 | 1 |
| product-design | `openai-curated-remote` | `0.1.56` | 未在本地 plugins 表记录 | 10 |
| sites | `openai-curated-remote` | `0.1.71` | 未在本地 plugins 表记录 | 3 |
| documents | `openai-primary-runtime` | `26.904.11930` | enabled | 1 |
| pdf | `openai-primary-runtime` | `26.904.11930` | enabled | 1 |
| presentations | `openai-primary-runtime` | `26.904.11930` | enabled | 1 |
| spreadsheets | `openai-primary-runtime` | `26.904.11930` | enabled | 2 |
| template-creator | `openai-primary-runtime` | `26.904.11930` | enabled | 1 |
| ponytail | `ponytail` | `4.10.0` | enabled | 12 |

## 插件内 Skills 完整路径名录

此处只列本机缓存中的 Skill 文件路径；除 Astra/Ponytail 快照外，插件文件由新机安装提供。

### astra-advisor · 0.2.0

- `skills/orchestration/SKILL.md`

### codex-storyboard · 0.6.7+codex.20260914224348

- `skills/manage-storyboard-projects/SKILL.md`
- `skills/process-storyboard-tasks/SKILL.md`

### computer-use · 26.924.22138

- `skills/computer-use/SKILL.md`

### visualize · 1.0.41

- `skills/visualize/SKILL.md`

### remotion · bd2122cb

- `skills/remotion/SKILL.md`

### Adobe · 9.0.0

- `skills/adobe-batch-edit-photos/SKILL.md`
- `skills/adobe-create-mockups/SKILL.md`
- `skills/adobe-create-social-variations/SKILL.md`
- `skills/adobe-design-from-template/SKILL.md`
- `skills/adobe-edit-quick-cut/SKILL.md`
- `skills/adobe-fonts/SKILL.md`
- `skills/adobe-retouch-portraits/SKILL.md`

### build-web-apps · 0.1.2

- `skills/frontend-app-builder/SKILL.md`
- `skills/frontend-testing-debugging/SKILL.md`
- `skills/react-best-practices/SKILL.md`
- `skills/shadcn-best-practices/SKILL.md`
- `skills/stripe-best-practices/SKILL.md`
- `skills/supabase-best-practices/SKILL.md`

### canva · 16.0.0

- `skills/canva-brand-check/SKILL.md`
- `skills/canva-branded-presentation/SKILL.md`
- `skills/canva-bulk-create/SKILL.md`
- `skills/canva-design-feedback/SKILL.md`
- `skills/canva-edit-design/SKILL.md`
- `skills/canva-implement-feedback/SKILL.md`
- `skills/canva-resize-for-social-media/SKILL.md`
- `skills/canva-translate-design/SKILL.md`

### codex-security · 0.1.31

- `skills/assess-patch-risk/SKILL.md`
- `skills/attack-path-analysis/SKILL.md`
- `skills/deep-security-scan/SKILL.md`
- `skills/define-security-policy/SKILL.md`
- `skills/finding-discovery/SKILL.md`
- `skills/fix-finding/SKILL.md`
- `skills/propose-security-hardening/SKILL.md`
- `skills/security-diff-scan/SKILL.md`
- `skills/security-scan/SKILL.md`
- `skills/threat-model/SKILL.md`
- `skills/track-findings/SKILL.md`
- `skills/triage-finding/SKILL.md`
- `skills/validation/SKILL.md`
- `skills/verify-fix/SKILL.md`
- `skills/vulnerability-writeup/SKILL.md`

### data-analytics · 1.0.11

- `skills/analyze-data-quality/SKILL.md`
- `skills/build-dashboard/SKILL.md`
- `skills/build-report/SKILL.md`
- `skills/convert-to-doc/SKILL.md`
- `skills/convert-to-slides/SKILL.md`
- `skills/create-data-context/SKILL.md`
- `skills/design-kpis/SKILL.md`
- `skills/gather-business-context/SKILL.md`
- `skills/index/SKILL.md`
- `skills/jupyter-notebooks/SKILL.md`
- `skills/kpi-reporting/SKILL.md`
- `skills/market-sizing/SKILL.md`
- `skills/metric-diagnostics/SKILL.md`
- `skills/product-business-analysis/SKILL.md`
- `skills/publish-artifact-to-sites/SKILL.md`
- `skills/report-to-pdf/SKILL.md`
- `skills/schedule-refresh-jobs/SKILL.md`
- `skills/share-artifact-summary/SKILL.md`
- `skills/validate-data/SKILL.md`
- `skills/visualize-data/SKILL.md`

### fal · 1.1.0

- `skills/character-design/SKILL.md`
- `skills/cinematography/SKILL.md`
- `skills/commercial/SKILL.md`
- `skills/fal-gamedev/SKILL.md`
- `skills/fal-media/SKILL.md`
- `skills/fal-models-catalog/SKILL.md`
- `skills/fal-prompting/SKILL.md`
- `skills/fal-recipes/SKILL.md`
- `skills/fal-regenerate-3d/SKILL.md`
- `skills/fal-workflow/SKILL.md`
- `skills/fan-cam/SKILL.md`
- `skills/marketing/SKILL.md`
- `skills/model-routing/SKILL.md`
- `skills/storytelling/SKILL.md`
- `skills/ugc/SKILL.md`

### figma · 13.0.0

- `skills/figma-code-connect/SKILL.md`
- `skills/figma-create-new-file/SKILL.md`
- `skills/figma-design-to-code/SKILL.md`
- `skills/figma-generate-design/SKILL.md`
- `skills/figma-generate-diagram/SKILL.md`
- `skills/figma-generate-library/SKILL.md`
- `skills/figma-generative-plugins/SKILL.md`
- `skills/figma-implement-motion/SKILL.md`
- `skills/figma-shaders/SKILL.md`
- `skills/figma-swiftui/SKILL.md`
- `skills/figma-use/SKILL.md`
- `skills/figma-use-figjam/SKILL.md`
- `skills/figma-use-motion/SKILL.md`
- `skills/figma-use-slides/SKILL.md`

### hugging-face · 1.0.0

- `skills/cli/SKILL.md`
- `skills/community-evals/SKILL.md`
- `skills/datasets/SKILL.md`
- `skills/gradio/SKILL.md`
- `skills/jobs/SKILL.md`
- `skills/llm-trainer/SKILL.md`
- `skills/paper-publisher/SKILL.md`
- `skills/papers/SKILL.md`
- `skills/trackio/SKILL.md`
- `skills/transformers.js/SKILL.md`
- `skills/vision-trainer/SKILL.md`

### notion · 0.1.8

- `skills/notion-knowledge-capture/SKILL.md`
- `skills/notion-meeting-intelligence/SKILL.md`
- `skills/notion-research-documentation/SKILL.md`
- `skills/notion-spec-to-implementation/SKILL.md`

### openai-developers · 1.3.0

- `skills/agents/SKILL.md`
- `skills/build-chatgpt-app/SKILL.md`
- `skills/chatgpt-app-submission/SKILL.md`
- `skills/openai-api-troubleshooting/SKILL.md`
- `skills/openai-platform-api-key/SKILL.md`

### openai-templates · 0.1.1

- `skills/artifact-template-analytics-dashboard/SKILL.md`
- `skills/artifact-template-business-review/SKILL.md`
- `skills/artifact-template-design-report/SKILL.md`
- `skills/artifact-template-experiment-analysis/SKILL.md`
- `skills/artifact-template-financial-budget/SKILL.md`
- `skills/artifact-template-investment-committee-memo/SKILL.md`
- `skills/artifact-template-legal-memorandum/SKILL.md`
- `skills/artifact-template-market-trends-report/SKILL.md`
- `skills/artifact-template-minimal-letterhead/SKILL.md`
- `skills/artifact-template-operating-calendar/SKILL.md`
- `skills/artifact-template-operating-review/SKILL.md`
- `skills/artifact-template-project-kickoff/SKILL.md`
- `skills/artifact-template-project-tracker/SKILL.md`
- `skills/artifact-template-sales-pipeline/SKILL.md`
- `skills/artifact-template-simple-dark-mode/SKILL.md`
- `skills/artifact-template-simple-light-mode/SKILL.md`
- `skills/artifact-template-strategy-memorandum/SKILL.md`
- `skills/artifact-template-system-design/SKILL.md`
- `skills/artifact-template-team-alignment/SKILL.md`
- `skills/artifact-template-three-statement-forecast/SKILL.md`

### plugin-management · 0.1.0

- `skills/plugin-management/SKILL.md`

### product-design · 0.1.56

- `skills/audit/SKILL.md`
- `skills/design-qa/SKILL.md`
- `skills/get-context/SKILL.md`
- `skills/ideate/SKILL.md`
- `skills/image-to-code/SKILL.md`
- `skills/index/SKILL.md`
- `skills/research/SKILL.md`
- `skills/share/SKILL.md`
- `skills/url-to-code/SKILL.md`
- `skills/user-context/SKILL.md`

### sites · 0.1.71

- `skills/sites-building/SKILL.md`
- `skills/sites-hosting/SKILL.md`
- `skills/sites-preview-troubleshooting/SKILL.md`

### documents · 26.904.11930

- `skills/documents/SKILL.md`

### pdf · 26.904.11930

- `skills/pdf/SKILL.md`

### presentations · 26.904.11930

- `skills/presentations/SKILL.md`

### spreadsheets · 26.904.11930

- `skills/excel-live-control/SKILL.md`
- `skills/spreadsheets/SKILL.md`

### template-creator · 26.904.11930

- `skills/template-creator/SKILL.md`

### ponytail · 4.10.0

- `skills/ponytail/SKILL.md`
- `skills/ponytail-audit/SKILL.md`
- `skills/ponytail-debt/SKILL.md`
- `skills/ponytail-gain/SKILL.md`
- `skills/ponytail-help/SKILL.md`
- `skills/ponytail-review/SKILL.md`
- `.openclaw/skills/ponytail/SKILL.md`
- `.openclaw/skills/ponytail-audit/SKILL.md`
- `.openclaw/skills/ponytail-debt/SKILL.md`
- `.openclaw/skills/ponytail-gain/SKILL.md`
- `.openclaw/skills/ponytail-help/SKILL.md`
- `.openclaw/skills/ponytail-review/SKILL.md`

## 自定义代理名录

| 角色原名 | 文件 | 原简介 |
| --- | --- | --- |
| 3D & Scene Developer | `codex/agents/3d-scene-developer.toml` | Web 3D visualization specialist who creates immersive 3D scenes, terrain models, point cloud visualizations, and interactive web experiences using Cesium, ArcGIS Scene Viewer, and modern 3D web frameworks. |
| Accessibility Auditor | `codex/agents/accessibility-auditor.toml` | Expert accessibility specialist who audits interfaces against WCAG standards, tests with assistive technologies, and ensures inclusive design. Defaults to finding barriers — if it's not tested with a screen reader, it's not accessible. |
| Account Strategist | `codex/agents/account-strategist.toml` | Expert post-sale account strategist specializing in land-and-expand execution, stakeholder mapping, QBR facilitation, and net revenue retention. Turns closed deals into long-term platform relationships through systematic expansion planning and multi-threaded account development. |
| Accounts Payable Agent | `codex/agents/accounts-payable-agent.toml` | Autonomous payment processing specialist that executes vendor payments, contractor invoices, and recurring bills across any payment rail — crypto, fiat, stablecoins. Integrates with AI agent workflows via tool calls. |
| Ad Creative Strategist | `codex/agents/ad-creative-strategist.toml` | Paid media creative specialist focused on ad copywriting, RSA optimization, asset group design, and creative testing frameworks across Google, Meta, Microsoft, and programmatic platforms. Bridges the gap between performance data and persuasive messaging. |
| AEO Foundations Architect | `codex/agents/aeo-foundations-architect.toml` | Expert in AI Engine Optimization infrastructure — implements llms.txt, AI-aware robots.txt, token-budgeted content, structured Markdown availability, and agent discovery files so AI crawlers, citation engines, and browsing agents can find, parse, and act on your site |
| Agentic Identity & Trust Architect | `codex/agents/agentic-identity-trust-architect.toml` | Designs identity, authentication, and trust verification systems for autonomous AI agents operating in multi-agent environments. Ensures agents can prove who they are, what they're authorized to do, and what they actually did. |
| Agentic Search Optimizer | `codex/agents/agentic-search-optimizer.toml` | Expert in WebMCP readiness and agentic task completion — audits whether AI agents can actually accomplish tasks on your site (book, buy, register, subscribe), implements WebMCP declarative and imperative patterns, and measures task completion rates across AI browsing agents |
| Agents Orchestrator | `codex/agents/agents-orchestrator.toml` | Autonomous pipeline manager that orchestrates the entire development workflow. You are the leader of this process. |
| Aging Parent Care Companion | `codex/agents/aging-parent-care-companion.toml` | Compassionate, HIPAA-aligned care coordination and decision-support agent for family caregivers managing an aging parent's appointments, medications, care team communication, and their own caregiver wellbeing |
| AI Citation Strategist | `codex/agents/ai-citation-strategist.toml` | Expert in AI recommendation engine optimization (AEO/GEO) — audits brand visibility across ChatGPT, Claude, Gemini, and Perplexity, identifies why competitors get cited instead, and delivers content fixes that improve AI citations |
| AI Data Remediation Engineer | `codex/agents/ai-data-remediation-engineer.toml` | "Specialist in self-healing data pipelines — uses air-gapped local SLMs and semantic clustering to automatically detect, classify, and fix data anomalies at scale. Focuses exclusively on the remediation layer: intercepting bad data, generating deterministic fix logic via Ollama, and guaranteeing zero data loss. Not a general data engineer — a surgical specialist for when your data is broken and the pipeline can't stop." |
| AI Engineer | `codex/agents/ai-engineer.toml` | Expert AI/ML engineer specializing in machine learning model development, deployment, and integration into production systems. Focused on building intelligent features, data pipelines, and AI-powered applications with emphasis on practical, scalable solutions. |
| AI-Generated Code Security Auditor | `codex/agents/ai-generated-code-security-auditor.toml` | Security reviewer for AI-generated and vibe-coded apps — hunts the hardcoded secrets, broken row-level security, and prompt-injection sinks that coding assistants ship by default, then drives a scan, fix, and rescan loop with honest, CWE-mapped findings. |
| Analytics Reporter | `codex/agents/analytics-reporter.toml` | Expert data analyst transforming raw data into actionable business insights. Creates dashboards, performs statistical analysis, tracks KPIs, and provides strategic decision support through data visualization and reporting. |
| Anthropologist | `codex/agents/anthropologist.toml` | Expert in cultural systems, rituals, kinship, belief systems, and ethnographic method — builds culturally coherent societies that feel lived-in rather than invented |
| API Platform Engineer | `codex/agents/api-platform-engineer.toml` | Expert API platform engineer for public and partner APIs — contract-first design (OpenAPI/gRPC), versioning and deprecation policy, SDK generation, API gateway concerns (auth, rate limiting, quotas), and developer-portal DX. |
| API Tester | `codex/agents/api-tester.toml` | Expert API testing specialist focused on comprehensive API validation, performance testing, and quality assurance across all systems and third-party integrations |
| App Store Optimizer | `codex/agents/app-store-optimizer.toml` | Expert app store marketing specialist focused on App Store Optimization (ASO), conversion rate optimization, and app discoverability |
| Application Security Engineer | `codex/agents/application-security-engineer.toml` | AppSec specialist who secures the software development lifecycle through threat modeling, secure code review, SAST/DAST integration, and developer security education that makes secure code the default. |
| Automation Governance Architect | `codex/agents/automation-governance-architect.toml` | Governance-first architect for business automations (n8n-first) who audits value, risk, and maintainability before implementation. |
| Autonomous Optimization Architect | `codex/agents/autonomous-optimization-architect.toml` | Intelligent system governor that continuously shadow-tests APIs for performance while enforcing strict financial and security guardrails against runaway costs. |
| Backend Architect | `codex/agents/backend-architect.toml` | Senior backend architect specializing in scalable system design, database architecture, API development, and cloud infrastructure. Builds robust, secure, performant server-side applications and microservices |
| Baidu SEO Specialist | `codex/agents/baidu-seo-specialist.toml` | Expert Baidu search optimization specialist focused on Chinese search engine ranking, Baidu ecosystem integration, ICP compliance, Chinese keyword research, and mobile-first indexing for the China market. |
| Behavioral Nudge Engine | `codex/agents/behavioral-nudge-engine.toml` | Behavioral psychology specialist that adapts software interaction cadences and styles to maximize user motivation and success. |
| Bilibili Content Strategist | `codex/agents/bilibili-content-strategist.toml` | Expert Bilibili marketing specialist focused on UP主 growth, danmaku culture mastery, B站 algorithm optimization, community building, and branded content strategy for China's leading video community platform. |
| BIM/GIS Specialist | `codex/agents/bim-gis-specialist.toml` | Integration specialist who bridges Building Information Modeling and Geographic Information Systems — Revit/IFC data conversion, indoor mapping, digital twin architecture, and facility management data models. |
| Blender Add-on Engineer | `codex/agents/blender-add-on-engineer.toml` | Blender tooling specialist - Builds Python add-ons, asset validators, exporters, and pipeline automations that turn repetitive DCC work into reliable one-click workflows |
| Blockchain Security Auditor | `codex/agents/blockchain-security-auditor.toml` | Expert smart contract security auditor specializing in vulnerability detection, formal verification, exploit analysis, and comprehensive audit report writing for DeFi protocols and blockchain applications. |
| Book Co-Author | `codex/agents/book-co-author.toml` | Strategic thought-leadership book collaborator for founders, experts, and operators turning voice notes, fragments, and positioning into structured first-person chapters. |
| Bookkeeper & Controller | `codex/agents/bookkeeper-controller.toml` | Expert bookkeeper and controller specializing in day-to-day accounting operations, financial reconciliations, month-end close processes, and internal controls. Ensures the accuracy, completeness, and timeliness of financial records while maintaining GAAP compliance and audit readiness at all times. |
| Brand Guardian | `codex/agents/brand-guardian.toml` | Expert brand strategist and guardian specializing in brand identity development, consistency maintenance, and strategic brand positioning |
| Business Strategist | `codex/agents/business-strategist.toml` | Senior management consulting specialist for competitive analysis, market entry strategy, business model design, growth planning, organizational strategy, and strategic decision-making — translating complex market dynamics into clear, actionable strategies that create sustainable competitive advantage |
| Carousel Growth Engine | `codex/agents/carousel-growth-engine.toml` | Autonomous TikTok and Instagram carousel generation specialist. Analyzes any website URL with Playwright, generates viral 6-slide carousels via Gemini image generation, publishes directly to feed via Upload-Post API with auto trending music, fetches analytics, and iteratively improves through a data-driven learning loop. |
| Cartography Designer | `codex/agents/cartography-designer.toml` | Map aesthetics specialist who designs beautiful, readable, and effective maps — color theory, typography, label placement, basemap selection, and visual hierarchy for both print and web. |
| Change Management Consultant | `codex/agents/change-management-consultant.toml` | Expert change management specialist using ADKAR, Kotter, and Prosci frameworks to guide organizations through technology implementations, restructuring, culture transformation, and M&A integration — managing resistance, building adoption, and ensuring changes stick long after go-live |
| Chief Financial Officer | `codex/agents/chief-financial-officer.toml` | Strategic finance executive who governs capital allocation, treasury operations, financial planning, M&A finance, investor relations, and board reporting — translating financial complexity into clear decisions that drive business performance and stakeholder confidence. |
| Chief of Staff | `codex/agents/chief-of-staff.toml` | Master coordinator for founders and executives — filters noise, owns processes, enforces consistency, routes decisions, and positions outputs for impact so the boss can think clearly. |
| China E-Commerce Operator | `codex/agents/china-e-commerce-operator.toml` | Expert China e-commerce operations specialist covering Taobao, Tmall, Pinduoduo, and JD ecosystems with deep expertise in product listing optimization, live commerce, store operations, 618/Double 11 campaigns, and cross-platform strategy. |
| China Market Localization Strategist | `codex/agents/china-market-localization-strategist.toml` | Full-stack China market localization expert who transforms real-time trend signals into executable go-to-market strategies across Douyin, Xiaohongshu, WeChat, Bilibili, and beyond |
| Civil Engineer | `codex/agents/civil-engineer.toml` | Expert civil and structural engineer with global standards coverage — Eurocode, DIN, ACI, AISC, ASCE, AS/NZS, CSA, GB, IS, AIJ, and more. Specializes in structural analysis, geotechnical design, construction documentation, building code compliance, and multi-standard international projects. |
|        Clinical Evidence Agent | `codex/agents/clinical-evidence-agent.toml` | Evidence standards and clinical credibility framework for AI agents |
| Cloud Security Architect | `codex/agents/cloud-security-architect.toml` | Cloud-native security specialist designing zero trust architectures, implementing defense-in-depth across AWS, Azure, and GCP, and securing infrastructure-as-code pipelines from day one. |
| CMS Developer | `codex/agents/cms-developer.toml` | Drupal and WordPress specialist for theme development, custom plugins/modules, content architecture, and code-first CMS implementation |
| Code Reviewer | `codex/agents/code-reviewer.toml` | Expert code reviewer who provides constructive, actionable feedback focused on correctness, maintainability, security, and performance — not style preferences. |
| Codebase Archaeologist | `codex/agents/codebase-archaeologist.toml` | Multi-session, multi-tool drift detection specialist who audits codebases touched by several AI coding tools (Claude, Cursor, Copilot, Windsurf, etc.) over time, finding silent logic mismatches, dead code, and doc-vs-code divergence that no single session would ever notice on its own. |
| Codebase Onboarding Engineer | `codex/agents/codebase-onboarding-engineer.toml` | Expert developer onboarding specialist who helps new engineers understand unfamiliar codebases fast by reading source code, tracing code paths, and stating only facts grounded in the code. |
| Compliance Auditor | `codex/agents/compliance-auditor.toml` | Expert technical compliance auditor specializing in SOC 2, ISO 27001, HIPAA, and PCI-DSS audits — from readiness assessment through evidence collection to certification. |
| Content Creator | `codex/agents/content-creator.toml` | Expert content strategist and creator for multi-platform campaigns. Develops editorial calendars, creates compelling copy, manages brand storytelling, and optimizes content for engagement across all digital channels. |
| Corporate Training Designer | `codex/agents/corporate-training-designer.toml` | Expert in enterprise training system design and curriculum development — proficient in training needs analysis, instructional design methodology, blended learning program design, internal trainer development, leadership programs, and training effectiveness evaluation and continuous optimization. |
| Cross-Border E-Commerce Specialist | `codex/agents/cross-border-e-commerce-specialist.toml` | Full-funnel cross-border e-commerce strategist covering Amazon, Shopee, Lazada, AliExpress, Temu, and TikTok Shop operations, international logistics and overseas warehousing, compliance and taxation, multilingual listing optimization, brand globalization, and DTC independent site development. |
| Cultural Intelligence Strategist | `codex/agents/cultural-intelligence-strategist.toml` | CQ specialist that detects invisible exclusion, researches global context, and ensures software resonates authentically across intersectional identities. |
| Customer Service | `codex/agents/customer-service.toml` | Friendly, professional customer service specialist for any industry — handling inquiries, complaints, account support, FAQs, and seamless escalation with warmth, efficiency, and a genuine commitment to customer satisfaction |
| Customer Success Manager | `codex/agents/customer-success-manager.toml` | Strategic customer success specialist for onboarding, health scoring, QBR facilitation, churn prevention, expansion identification, and renewal management — driving net revenue retention by turning customers into long-term partners who achieve measurable outcomes |
| Data Consolidation Agent | `codex/agents/data-consolidation-agent.toml` | AI agent that consolidates extracted sales data into live reporting dashboards with territory, rep, and pipeline summaries |
| Data Engineer | `codex/agents/data-engineer.toml` | Expert data engineer specializing in building reliable data pipelines, lakehouse architectures, and scalable data infrastructure. Masters ETL/ELT, Apache Spark, dbt, streaming systems, and cloud data platforms to turn raw data into trusted, analytics-ready assets. |
| Data Privacy Officer | `codex/agents/data-privacy-officer.toml` | Corporate data privacy specialist and DPO who builds GDPR, CCPA, and global privacy compliance programs — covering data mapping, privacy impact assessments, consent management, breach response, vendor due diligence, and regulatory engagement. |
| Database Optimizer | `codex/agents/database-optimizer.toml` | Expert database specialist focusing on schema design, query optimization, indexing strategies, and performance tuning for PostgreSQL, MySQL, and modern databases like Supabase and PlanetScale. |
| Database Reliability Engineer | `codex/agents/database-reliability-engineer.toml` | Expert database reliability engineer (DBRE) — high availability and replication, automated failover, backup and point-in-time recovery, zero-downtime online schema migrations, connection pooling, and disaster-recovery drills. Focused on keeping data safe and available, not query tuning. |
| Deal Strategist | `codex/agents/deal-strategist.toml` | Senior deal strategist specializing in MEDDPICC qualification, competitive positioning, and win planning for complex B2B sales cycles. Scores opportunities, exposes pipeline risk, and builds deal strategies that survive forecast review. |
| Desktop App Engineer | `codex/agents/desktop-app-engineer.toml` | Expert desktop application engineer for Electron and Tauri — secure IPC and process isolation, code signing and notarization, auto-update pipelines, native OS integration, and resource-footprint discipline. |
| Developer Advocate | `codex/agents/developer-advocate.toml` | Expert developer advocate specializing in building developer communities, creating compelling technical content, optimizing developer experience (DX), and driving platform adoption through authentic engineering engagement. Bridges product and engineering teams with external developers. |
| Developer Tooling Engineer | `codex/agents/developer-tooling-engineer.toml` | Expert developer-tooling and CLI engineer — building command-line tools and internal developer platforms with great DX: intuitive command design, helpful errors, shell completions, fast startup, cross-platform distribution, and scriptable, composable interfaces. |
| DevOps Automator | `codex/agents/devops-automator.toml` | Expert DevOps engineer specializing in infrastructure automation, CI/CD pipeline development, and cloud operations |
| Discovery Coach | `codex/agents/discovery-coach.toml` | Coaches sales teams on elite discovery methodology — question design, current-state mapping, gap quantification, and call structure that surfaces real buying motivation. |
| Document Generator | `codex/agents/document-generator.toml` | Expert document creation specialist who generates professional PDF, PPTX, DOCX, and XLSX files using code-based approaches with proper formatting, charts, and data visualization. |
| Douyin Strategist | `codex/agents/douyin-strategist.toml` | Short-video marketing expert specializing in the Douyin platform, with deep expertise in recommendation algorithm mechanics, viral video planning, livestream commerce workflows, and full-funnel brand growth through content matrix strategies. |
| Drone/Reality Mapping Specialist | `codex/agents/drone-reality-mapping-specialist.toml` | Photogrammetry and reality capture expert who processes drone imagery into orthomosaics, digital terrain models, point clouds, and 3D meshes — bridging field capture and GIS-ready products. |
| Drupal Performance Engineer | `codex/agents/drupal-performance-engineer.toml` | Expert Drupal 10/11 performance engineer specializing in Core Web Vitals, render and dynamic page caching, BigPipe, cache tags and contexts, database query and Views optimization, CSS/JS aggregation, responsive images and lazy loading, CDN integration, and opcache/PHP-FPM tuning for fast, audit-passing sites |
| Drupal Shopping Cart Engineer | `codex/agents/drupal-shopping-cart-engineer.toml` | Expert Drupal e-commerce engineer specializing in Drupal Commerce for product catalog management, payment gateway integration, checkout workflow design, order management, tax and promotion configuration, and high-reliability storefront delivery on Drupal 10/11 |
| Email Intelligence Engineer | `codex/agents/email-intelligence-engineer.toml` | Expert in extracting structured, reasoning-ready data from raw email threads for AI agents and automation systems |
| Email Marketing Strategist | `codex/agents/email-marketing-strategist.toml` | Expert email marketing strategist for CRM-driven campaigns, lifecycle automation, segmentation architecture, and deliverability. Designs sequences (welcome, nurture, reactivation, win-back, review, referral) grounded in 2025-2026 benchmarks, AI-driven personalization, and post-Apple MPP measurement. |
| Embedded Firmware Engineer | `codex/agents/embedded-firmware-engineer.toml` | Specialist in bare-metal and RTOS firmware - ESP32/ESP-IDF, PlatformIO, Arduino, ARM Cortex-M, STM32 HAL/LL, Nordic nRF5/nRF Connect SDK, FreeRTOS, Zephyr |
| ESG & Sustainability Officer | `codex/agents/esg-sustainability-officer.toml` | Corporate sustainability strategist and ESG reporting specialist who builds environmental, social, and governance programs, manages disclosures, drives decarbonization initiatives, and aligns business strategy with stakeholder and regulatory expectations. |
| Evidence Collector | `codex/agents/evidence-collector.toml` | Screenshot-obsessed, fantasy-allergic QA specialist - Default to finding 3-5 issues, requires visual proof for everything |
| Executive Summary Generator | `codex/agents/executive-summary-generator.toml` | Consultant-grade AI specialist trained to think and communicate like a senior strategy consultant. Transforms complex business inputs into concise, actionable executive summaries using McKinsey SCQA, BCG Pyramid Principle, and Bain frameworks for C-suite decision-makers. |
| Experiment Tracker | `codex/agents/experiment-tracker.toml` | Expert project manager specializing in experiment design, execution tracking, and data-driven decision making. Focused on managing A/B tests, feature experiments, and hypothesis validation through systematic experimentation and rigorous analysis. |
| FedRAMP & RMF Compliance Engineer | `codex/agents/fedramp-rmf-compliance-engineer.toml` | Expert FedRAMP and NIST Risk Management Framework compliance engineer specializing in both FedRAMP authorization pathways — the traditional Rev5 path (NIST 800-53 Rev 5 control implementation, System Security Plans, 3PAO assessment, agency authorization) and the modernized FedRAMP 20x path (Key Security Indicators, automated machine-readable validation, compliance-as-code) — plus the ATO process, continuous monitoring (ConMon), POA&M management, FIPS 199 categorization, authorization boundary diagrams, OSCAL machine-readable packages, and cloud security compliance for government and regulated industries |
| Feedback Synthesizer | `codex/agents/feedback-synthesizer.toml` | Expert in collecting, analyzing, and synthesizing user feedback from multiple channels to extract actionable product insights. Transforms qualitative feedback into quantitative priorities and strategic recommendations. |
| Feishu Integration Developer | `codex/agents/feishu-integration-developer.toml` | Full-stack integration expert specializing in the Feishu (Lark) Open Platform — proficient in Feishu bots, mini programs, approval workflows, Bitable (multidimensional spreadsheets), interactive message cards, Webhooks, SSO authentication, and workflow automation, building enterprise-grade collaboration and automation solutions within the Feishu ecosystem. |
| Filament Optimization Specialist | `codex/agents/filament-optimization-specialist.toml` | Expert in restructuring and optimizing Filament PHP admin interfaces for maximum usability and efficiency. Focuses on impactful structural changes — not just cosmetic tweaks. |
| Finance Tracker | `codex/agents/finance-tracker.toml` | Expert financial analyst and controller specializing in financial planning, budget management, and business performance analysis. Maintains financial health, optimizes cash flow, and provides strategic financial insights for business growth. |
| Financial Analyst | `codex/agents/financial-analyst.toml` | Expert financial analyst specializing in financial modeling, forecasting, scenario analysis, and data-driven decision support. Transforms raw financial data into actionable business intelligence that drives strategic planning, investment decisions, and operational optimization. |
| FinOps Engineer | `codex/agents/finops-engineer.toml` | Expert cloud cost engineer for AWS/GCP/Azure — cost allocation and tagging, rightsizing, commitment planning (reserved instances/savings plans), egress and storage optimization, and unit-economics dashboards that tie spend to business value. |
| FP&A Analyst | `codex/agents/fp-a-analyst.toml` | Expert Financial Planning & Analysis (FP&A) analyst specializing in budgeting, variance analysis, financial planning, rolling forecasts, and strategic decision support. Bridges the gap between the numbers and the business narrative to drive operational performance and strategic resource allocation. |
| French Consulting Market Navigator | `codex/agents/french-consulting-market-navigator.toml` | Navigate the French ESN/SI freelance ecosystem — margin models, platform mechanics (Malt, collective.work), portage salarial, rate positioning, and payment cycle realities |
| Frontend Developer | `codex/agents/frontend-developer.toml` | Expert frontend developer specializing in modern web technologies, React/Vue/Angular frameworks, UI implementation, and performance optimization |
| Game Audio Engineer | `codex/agents/game-audio-engineer.toml` | Interactive audio specialist - Masters FMOD/Wwise integration, adaptive music systems, spatial audio, and audio performance budgeting across all game engines |
| Game Designer | `codex/agents/game-designer.toml` | Systems and mechanics architect - Masters GDD authorship, player psychology, economy balancing, and gameplay loop design across all engines and genres |
| GaussDB Expert Engineer | `codex/agents/gaussdb-expert-engineer.toml` | Expert database specialist focusing on GaussDB OLTP — Huawei's self-developed enterprise-grade relational database (NOT GaussDB(DWS) OLAP, NOT GaussDB(for openGauss) cloud service, NOT GaussDB(for MySQL)). Covers schema design, distributed table design, query optimization, indexing, Ustore engine, and performance tuning for both distributed and centralized deployments. |
| GeoAI/ML Engineer | `codex/agents/geoai-ml-engineer.toml` | Geospatial machine learning specialist who builds models for feature extraction, object detection, image segmentation, and land cover classification from satellite and aerial imagery. |
| Geographer | `codex/agents/geographer.toml` | Expert in physical and human geography, climate systems, cartography, and spatial analysis — builds geographically coherent worlds where terrain, climate, resources, and settlement patterns make scientific sense |
| Geoprocessing Specialist | `codex/agents/geoprocessing-specialist.toml` | ArcPy and Python toolbox expert who automates spatial workflows — builds .pyt toolboxes, Model Builder processes, batch geoprocessing automation, and custom analysis scripts for ArcGIS Pro. |
| GIS Analyst | `codex/agents/gis-analyst.toml` | Day-to-day GIS operator who creates maps, manages layers, performs spatial queries, and maintains geospatial data integrity across desktop and web environments. |
| GIS QA Engineer | `codex/agents/gis-qa-engineer.toml` | Quality assurance specialist who validates geospatial data integrity — topology checks, metadata audits, CRS consistency, accuracy assessment, and compliance verification. |
| Git Workflow Master | `codex/agents/git-workflow-master.toml` | Expert in Git workflows, branching strategies, and version control best practices including conventional commits, rebasing, worktrees, and CI-friendly branch management. |
| Global Podcast Strategist | `codex/agents/global-podcast-strategist.toml` | Expert podcast growth specialist focused on show positioning, audience development, content strategy, and monetisation. Transforms raw ideas into authoritative audio brands that compound listeners and revenue over time on Spotify, Apple Podcasts, and YouTube. |
| Godot Gameplay Scripter | `codex/agents/godot-gameplay-scripter.toml` | Composition and signal integrity specialist - Masters GDScript 2.0, C# integration, node-based architecture, and type-safe signal design for Godot 4 projects |
| Godot Multiplayer Engineer | `codex/agents/godot-multiplayer-engineer.toml` | Godot 4 networking specialist - Masters the MultiplayerAPI, scene replication, ENet/WebRTC transport, RPCs, and authority models for real-time multiplayer games |
| Godot Shader Developer | `codex/agents/godot-shader-developer.toml` | Godot 4 visual effects specialist - Masters the Godot Shading Language (GLSL-like), VisualShader editor, CanvasItem and Spatial shaders, post-processing, and performance optimization for 2D/3D effects |
| Government Digital Presales Consultant | `codex/agents/government-digital-presales-consultant.toml` | Presales expert for China's government digital transformation market (ToG), proficient in policy interpretation, solution design, bid document preparation, POC validation, compliance requirements (classified protection/cryptographic assessment/Xinchuang domestic IT), and stakeholder management — helping technical teams efficiently win government IT projects. |
| Grant Writer | `codex/agents/grant-writer.toml` | Expert grant writing specialist for nonprofits, research institutions, and social enterprises — covering prospect research, letter of inquiry writing, full proposal development, budget narratives, federal and foundation grants, and post-award reporting to maximize funding success |
| Growth Hacker | `codex/agents/growth-hacker.toml` | Expert growth strategist specializing in rapid user acquisition through data-driven experimentation. Develops viral loops, optimizes conversion funnels, and finds scalable growth channels for exponential business growth. |
| Healthcare Customer Service | `codex/agents/healthcare-customer-service.toml` | Empathetic healthcare customer service specialist for patient support, billing inquiries, appointment management, insurance questions, complaint resolution, and seamless escalation to clinical or administrative staff |
|        Healthcare Innovation Strategist | `codex/agents/healthcare-innovation-strategist.toml` | Strategic narrative architect for healthcare founders operating at |
| Healthcare Marketing Compliance Specialist | `codex/agents/healthcare-marketing-compliance-specialist.toml` | Expert in healthcare marketing compliance in China, proficient in the Advertising Law, Medical Advertisement Management Measures, Drug Administration Law, and related regulations — covering pharmaceuticals, medical devices, medical aesthetics, health supplements, and internet healthcare across content review, risk control, platform rule interpretation, and patient privacy protection, helping enterprises conduct effective health marketing within legal boundaries. |
| Historian | `codex/agents/historian.toml` | Expert in historical analysis, periodization, material culture, and historiography — validates historical coherence and enriches settings with authentic period detail grounded in primary and secondary sources |
| Hospitality Guest Services | `codex/agents/hospitality-guest-services.toml` | Comprehensive hospitality guest services specialist for hotels, resorts, restaurants, and event venues — covering reservations, check-in/check-out, concierge services, guest complaint resolution, loyalty program management, and post-stay follow-up to deliver exceptional guest experiences that drive loyalty and revenue |
| HR Onboarding | `codex/agents/hr-onboarding.toml` | Comprehensive HR onboarding specialist for employee orientation, documentation management, compliance tracking, benefits enrollment, culture integration, and new hire support — delivering a seamless first-day-to-first-year experience that drives retention and productivity |
| Identity & Access Engineer | `codex/agents/identity-access-engineer.toml` | Expert identity engineer for OAuth 2.0/OIDC flows, enterprise SSO (SAML/OIDC) and SCIM provisioning, passkeys/WebAuthn, session architecture, and multi-tenant authorization with RBAC/ABAC. |
| Identity Graph Operator | `codex/agents/identity-graph-operator.toml` | Operates a shared identity graph that multiple AI agents resolve against. Ensures every agent in a multi-agent system gets the same canonical answer for "who is this entity?" - deterministically, even under concurrent writes. |
| Image Prompt Engineer | `codex/agents/image-prompt-engineer.toml` | Expert photography prompt engineer specializing in crafting detailed, evocative prompts for AI image generation. Masters the art of translating visual concepts into precise language that produces stunning, professional-quality photography through generative AI tools. |
| Incident Responder | `codex/agents/incident-responder.toml` | Digital forensics and incident response specialist who leads breach investigations, contains active threats, coordinates crisis response, and writes post-mortems that prevent recurrence. |
| Incident Response Commander | `codex/agents/incident-response-commander.toml` | Expert incident commander specializing in production incident management, structured response coordination, post-mortem facilitation, SLO/SLI tracking, and on-call process design for reliable engineering organizations. |
| Inclusive Visuals Specialist | `codex/agents/inclusive-visuals-specialist.toml` | Representation expert who defeats systemic AI biases to generate culturally accurate, affirming, and non-stereotypical images and video. |
| Infrastructure Maintainer | `codex/agents/infrastructure-maintainer.toml` | Expert infrastructure specialist focused on system reliability, performance optimization, and technical operations management. Maintains robust, scalable infrastructure supporting business operations with security, performance, and cost efficiency. |
| Instagram Curator | `codex/agents/instagram-curator.toml` | Expert Instagram marketing specialist focused on visual storytelling, community building, and multi-format content optimization. Masters aesthetic development and drives meaningful engagement. |
| Internationalization Engineer | `codex/agents/internationalization-engineer.toml` | Expert i18n engineer for ICU MessageFormat, CLDR plural rules, RTL and bidirectional layouts, locale-aware date/number/currency formatting, string extraction pipelines, and pseudo-localization testing. |
| Investment Researcher | `codex/agents/investment-researcher.toml` | Expert investment researcher specializing in market research, due diligence, portfolio analysis, and asset valuation. Conducts rigorous fundamental and quantitative analysis to identify investment opportunities, assess risks, and support data-driven portfolio decisions across public equities, private markets, and alternative assets. |
| IoT Fleet Engineer | `codex/agents/iot-fleet-engineer.toml` | Expert IoT and edge fleet engineer — device provisioning and identity, MQTT/telemetry pipelines, staged over-the-air (OTA) firmware updates with rollback, edge compute, and observability across fleets of unreliable, intermittently-connected devices. |
| IT Service Manager | `codex/agents/it-service-manager.toml` | Expert IT service management specialist using ITIL 4 framework for service catalog design, incident and problem management, change control, SLA governance, CMDB maintenance, and continual service improvement — ensuring IT delivers reliable, measurable business value across any organization size |
| Jira Workflow Steward | `codex/agents/jira-workflow-steward.toml` | Expert delivery operations specialist who enforces Jira-linked Git workflows, traceable commits, structured pull requests, and release-safe branch strategy across software teams. |
| Korean Business Navigator | `codex/agents/korean-business-navigator.toml` | Korean business culture for foreign professionals — 품의 decision process, nunchi reading, KakaoTalk business etiquette, hierarchy navigation, and relationship-first deal mechanics |
| Kuaishou Strategist | `codex/agents/kuaishou-strategist.toml` | Expert Kuaishou marketing strategist specializing in short-video content for China's lower-tier city markets, live commerce operations, community trust building, and grassroots audience growth on 快手. |
| Language Translator | `codex/agents/language-translator.toml` | Real-time Spanish ↔ English translation specialist with cultural context, regional dialect awareness, travel phrase guidance, and tone-appropriate communication for everyday, business, and emergency situations |
| Legal Billing & Time Tracking | `codex/agents/legal-billing-time-tracking.toml` | Comprehensive legal billing and time tracking specialist for accurate time capture, invoice generation, billing narrative writing, collections management, trust account compliance, and billing analysis — maximizing revenue recovery while maintaining client relationships and ethical compliance across any firm size or billing model |
| Legal Client Intake | `codex/agents/legal-client-intake.toml` | Comprehensive legal client intake specialist for qualifying prospects, collecting case information, scheduling consultations, managing conflict checks, and delivering attorney-ready intake summaries across any practice area and firm size |
| Legal Compliance Checker | `codex/agents/legal-compliance-checker.toml` | Expert legal and compliance specialist ensuring business operations, data handling, and content creation comply with relevant laws, regulations, and industry standards across multiple jurisdictions. |
| Legal Document Review | `codex/agents/legal-document-review.toml` | Comprehensive legal document review specialist for contracts, litigation documents, and real estate agreements — summarizing documents, flagging risk clauses, comparing contract versions, and checking compliance across any law firm size or practice area |
| Level Designer | `codex/agents/level-designer.toml` | Spatial storytelling and flow specialist - Masters layout theory, pacing architecture, encounter design, and environmental narrative across all game engines |
| LinkedIn Content Creator | `codex/agents/linkedin-content-creator.toml` | Expert LinkedIn content strategist focused on thought leadership, personal brand building, and high-engagement professional content. Masters LinkedIn's algorithm and culture to drive inbound opportunities for founders, job seekers, developers, and anyone building a professional presence. |
| Livestream Commerce Coach | `codex/agents/livestream-commerce-coach.toml` | Veteran livestream e-commerce coach specializing in host training and live room operations across Douyin, Kuaishou, Taobao Live, and Channels, covering script design, product sequencing, paid-vs-organic traffic balancing, conversion closing techniques, and real-time data-driven optimization. |
| Loan Officer Assistant | `codex/agents/loan-officer-assistant.toml` | Comprehensive loan officer assistant for mortgage and lending professionals — covering borrower intake, pre-qualification, document collection, pipeline management, compliance tracking, rate quoting, and closing coordination across residential, commercial, and consumer lending |
| LSP/Index Engineer | `codex/agents/lsp-index-engineer.toml` | Language Server Protocol specialist building unified code intelligence systems through LSP client orchestration and semantic indexing |
| M&A Integration Manager | `codex/agents/m-a-integration-manager.toml` | Mergers and acquisitions integration specialist who designs and executes post-merger integration programs — covering Day 1 readiness, 100-day planning, synergy tracking, cultural integration, functional workstream coordination, and transition service agreement management. |
| macOS Spatial/Metal Engineer | `codex/agents/macos-spatial-metal-engineer.toml` | Native Swift and Metal specialist building high-performance 3D rendering systems and spatial computing experiences for macOS and Vision Pro |
| MCP Builder | `codex/agents/mcp-builder.toml` | Expert Model Context Protocol developer who designs, builds, and tests MCP servers that extend AI agent capabilities with custom tools, resources, and prompts. |
| Medical Billing & Coding Specialist | `codex/agents/medical-billing-coding-specialist.toml` | Expert medical billing and coding specialist for ICD-10-CM/PCS, CPT, and HCPCS coding, claim submission, denial management, revenue cycle optimization, compliance auditing, and payer contract analysis — maximizing clean claim rates and revenue recovery for healthcare providers of all sizes |
| Meeting Notes Specialist | `codex/agents/meeting-notes-specialist.toml` | Extract structured decisions, action items, and open questions from meeting transcripts or rough notes into a clean 4-section summary. |
| Minimal Change Engineer | `codex/agents/minimal-change-engineer.toml` | Engineering specialist focused on minimum-viable diffs — fixes only what was asked, refuses scope creep, prefers three similar lines over a premature abstraction. The discipline that prevents bug-fix PRs from becoming refactor avalanches. |
| Mobile App Builder | `codex/agents/mobile-app-builder.toml` | Specialized mobile application developer with expertise in native iOS/Android development and cross-platform frameworks |
| Mobile Release Engineer | `codex/agents/mobile-release-engineer.toml` | Expert mobile release and distribution engineer for iOS and Android — code signing, provisioning, fastlane pipelines, App Store Connect and Play Console submission, phased rollouts, and crash-triaged release health. |
| Model QA Specialist | `codex/agents/model-qa-specialist.toml` | Independent model QA expert who audits ML and statistical models end-to-end - from documentation review and data reconstruction to replication, calibration testing, interpretability analysis, performance monitoring, and audit-grade reporting. |
| Multi-Agent Systems Architect | `codex/agents/multi-agent-systems-architect.toml` | Systems architect specializing in the design, coordination, and governance of multi-agent AI pipelines — covering topology selection, context management, inter-agent trust, failure recovery, human-in-the-loop gating, and observability for production-grade agent systems. |
| Multi-Platform Publisher | `codex/agents/multi-platform-publisher.toml` | Expert orchestrator for one-click Chinese blog publishing. Routes a single article to 知乎 / 小红书 / CSDN / B站 / 公众号 / 掘金 via Wechatsync (main channel) with xhs-mcp and biliup as specialized fallbacks. Handles per-platform content adaptation, draft-first publishing, rate control, and risk-avoidance. Does NOT auto-publish — always stops at draft for human review. |
| Narrative Designer | `codex/agents/narrative-designer.toml` | Story systems and dialogue architect - Masters GDD-aligned narrative design, branching dialogue, lore architecture, and environmental storytelling across all game engines |
| Narratologist | `codex/agents/narratologist.toml` | Expert in narrative theory, story structure, character arcs, and literary analysis — grounds advice in established frameworks from Propp to Campbell to modern narratology |
| Network Engineer | `codex/agents/network-engineer.toml` | Expert network engineer for Cisco IOS/IOS-XE, Cisco ASA/FTD, Juniper Junos, and Palo Alto PAN-OS routing, switching, firewalling, and troubleshooting. |
| Offer & Lead Gen Strategist | `codex/agents/offer-lead-gen-strategist.toml` | Top-of-funnel architect who designs irresistible offers and lead magnets that attract qualified buyers at scale. Specializes in value-equation offer construction, lead magnet typology, multi-channel lead generation, and compounding reach through customers, employees, agencies, and affiliates. |
| Operations Manager | `codex/agents/operations-manager.toml` | Business operations specialist who applies Lean, Six Sigma, and systems thinking to process mapping, capacity planning, KPI governance, vendor management, and organizational efficiency — turning operational complexity into repeatable, measurable performance. |
| Organizational Psychologist | `codex/agents/organizational-psychologist.toml` | Applied organizational psychologist who diagnoses team dynamics, psychological safety, burnout risk, and culture health — using evidence-based frameworks to help leaders build high-performing, resilient, and psychologically safe organizations. |
| OrgScript Engineer | `codex/agents/orgscript-engineer.toml` | Expert in designing, parsing, and implementing OrgScript grammar, AST validation, and business logic definitions. |
| Outbound Strategist | `codex/agents/outbound-strategist.toml` | Signal-based outbound specialist who designs multi-channel prospecting sequences, defines ICPs, and builds pipeline through research-driven personalization — not volume. |
| Paid Media Auditor | `codex/agents/paid-media-auditor.toml` | Comprehensive paid media auditor who systematically evaluates Google Ads, Microsoft Ads, and Meta accounts across 200+ checkpoints spanning account structure, tracking, bidding, creative, audiences, and competitive positioning. Produces actionable audit reports with prioritized recommendations and projected impact. |
| Paid Social Strategist | `codex/agents/paid-social-strategist.toml` | Cross-platform paid social advertising specialist covering Meta (Facebook/Instagram), LinkedIn, TikTok, Pinterest, X, and Snapchat. Designs full-funnel social ad programs from prospecting through retargeting with platform-specific creative and audience strategies. |
| Payments & Billing Engineer | `codex/agents/payments-billing-engineer.toml` | Expert payments engineer for PSP integrations (Stripe, Adyen, Braintree, PayPal), idempotent payment flows, webhook processing, subscription billing, SCA/3DS, PCI scope reduction, and financial reconciliation. |
| Penetration Tester | `codex/agents/penetration-tester.toml` | Offensive security specialist conducting authorized penetration tests, red team operations, and vulnerability assessments across networks, web applications, and cloud infrastructure. |
| Performance Benchmarker | `codex/agents/performance-benchmarker.toml` | Expert performance testing and optimization specialist focused on measuring, analyzing, and improving system performance across all applications and infrastructure |
| Persona Walkthrough Specialist | `codex/agents/persona-walkthrough-specialist.toml` | Simulate cognitive walkthroughs of web pages from a defined persona's psychological perspective — captures emotional reactions and rational thought at each scroll position, then delivers structured CRO reports grounded in LIFT, Cialdini, and Fogg frameworks |
| Personal Growth Mentor | `codex/agents/personal-growth-mentor.toml` | Cross-domain personal development mentor for goal clarity, habit design, strategic decisions, and accountability without motivational fluff. |
| Pipeline Analyst | `codex/agents/pipeline-analyst.toml` | Revenue operations analyst specializing in pipeline health diagnostics, deal velocity analysis, forecast accuracy, and data-driven sales coaching. Turns CRM data into actionable pipeline intelligence that surfaces risks before they become missed quarters. |
| Podcast Strategist | `codex/agents/podcast-strategist.toml` | Content strategy and operations expert for the Chinese podcast market, with deep expertise in Xiaoyuzhou, Ximalaya, and other major audio platforms, covering show positioning, audio production, audience growth, multi-platform distribution, and monetization to help podcast creators build sticky audio content brands. |
| PPC Campaign Strategist | `codex/agents/ppc-campaign-strategist.toml` | Senior paid media strategist specializing in large-scale search, shopping, and performance max campaign architecture across Google, Microsoft, and Amazon ad platforms. Designs account structures, budget allocation frameworks, and bidding strategies that scale from $10K to $10M+ monthly spend. |
| PR & Communications Manager | `codex/agents/pr-communications-manager.toml` | Strategic public relations and communications specialist for media relations, press releases, crisis communications, executive thought leadership, brand reputation management, and integrated communications planning — building and protecting reputations through earned media, storytelling, and proactive narrative control |
| Pricing Analyst | `codex/agents/pricing-analyst.toml` | Specialized pricing analyst who develops optimal pricing models through market research, competitor analysis, cost structure evaluation, and margin optimization — turning pricing from guesswork into a data-driven competitive advantage. |
| Privacy Engineer | `codex/agents/privacy-engineer.toml` | Expert privacy engineer who implements privacy in code — PII discovery and classification, data minimization, consent enforcement at the API layer, automated DSAR and deletion across services, pseudonymization/tokenization, and retention automation. Builds the technical controls a privacy policy only promises. |
| Private Domain Operator | `codex/agents/private-domain-operator.toml` | Expert in building enterprise WeChat (WeCom) private domain ecosystems, with deep expertise in SCRM systems, segmented community operations, Mini Program commerce integration, user lifecycle management, and full-funnel conversion optimization. |
| Product Manager | `codex/agents/product-manager.toml` | Holistic product leader who owns the full product lifecycle — from discovery and strategy through roadmap, stakeholder alignment, go-to-market, and outcome measurement. Bridges business goals, user needs, and technical reality to ship the right thing at the right time. |
| Programmatic & Display Buyer | `codex/agents/programmatic-display-buyer.toml` | Display advertising and programmatic media buying specialist covering managed placements, Google Display Network, DV360, trade desk platforms, partner media (newsletters, sponsored content), and ABM display strategies via platforms like Demandbase and 6Sense. |
| Project Shepherd | `codex/agents/project-shepherd.toml` | Expert project manager specializing in cross-functional project coordination, timeline management, and stakeholder alignment. Focused on shepherding projects from conception to completion while managing resources, risks, and communications across multiple teams and departments. |
| Prompt Engineer | `codex/agents/prompt-engineer.toml` | Specialist in crafting, testing, and systematically optimizing prompts for LLMs — turning vague instructions into reliable, production-grade AI behaviors. |
| Proposal Strategist | `codex/agents/proposal-strategist.toml` | Strategic proposal architect who transforms RFPs and sales opportunities into compelling win narratives. Specializes in win theme development, competitive positioning, executive summary craft, and building proposals that persuade rather than merely comply. |
| Psychologist | `codex/agents/psychologist.toml` | Expert in human behavior, personality theory, motivation, and cognitive patterns — builds psychologically credible characters and interactions grounded in clinical and research frameworks |
| RAG Pipeline Engineer | `codex/agents/rag-pipeline-engineer.toml` | Production RAG specialist focused on chunking strategy, retrieval quality, hybrid search, re-ranking, and eval-driven iteration. Builds pipelines that actually retrieve the right context — not just pipelines that run. |
| Rapid Prototyper | `codex/agents/rapid-prototyper.toml` | Specialized in ultra-fast proof-of-concept development and MVP creation using efficient tools and frameworks |
| Real Estate Buyer & Seller | `codex/agents/real-estate-buyer-seller.toml` | Comprehensive real estate agent assistant for buyer representation, seller representation, listing management, offer negotiation, transaction coordination, and closing support — delivering a world-class client experience from first showing to final closing across residential and investment real estate |
| Reality Checker | `codex/agents/reality-checker.toml` | Stops fantasy approvals, evidence-based certification - Default to "NEEDS WORK", requires overwhelming proof for production readiness |
| Realtime Collaboration Engineer | `codex/agents/realtime-collaboration-engineer.toml` | Expert realtime systems engineer for WebSocket/SSE infrastructure, presence, CRDT and OT-based collaborative editing, offline-first sync engines, and fan-out scaling with reconnect-safe protocols. |
| Recruitment Specialist | `codex/agents/recruitment-specialist.toml` | Expert recruitment operations and talent acquisition specialist — skilled in China's major hiring platforms, talent assessment frameworks, and labor law compliance. Helps companies efficiently attract, screen, and retain top talent while building a competitive employer brand. |
| Reddit Community Builder | `codex/agents/reddit-community-builder.toml` | Expert Reddit marketing specialist focused on authentic community engagement, value-driven content creation, and long-term relationship building. Masters Reddit culture navigation. |
| Report Distribution Agent | `codex/agents/report-distribution-agent.toml` | AI agent that automates distribution of consolidated sales reports to representatives based on territorial parameters |
| Resume Tailor | `codex/agents/resume-tailor.toml` | Candidate-side resume optimization specialist who analyzes job descriptions, maps real experience to role requirements, improves ATS keyword alignment, and rewrites bullets without fabricating qualifications. |
| Retail Customer Returns | `codex/agents/retail-customer-returns.toml` | Comprehensive retail customer returns specialist for processing returns, exchanges, and refunds across in-store, online, and omnichannel retail — handling policy enforcement, fraud prevention, customer retention, vendor returns, and returns analytics to maximize recovery while preserving customer loyalty |
| Roblox Avatar Creator | `codex/agents/roblox-avatar-creator.toml` | Roblox UGC and avatar pipeline specialist - Masters Roblox's avatar system, UGC item creation, accessory rigging, texture standards, and the Creator Marketplace submission pipeline |
| Roblox Experience Designer | `codex/agents/roblox-experience-designer.toml` | Roblox platform UX and monetization specialist - Masters engagement loop design, DataStore-driven progression, Roblox monetization systems (Passes, Developer Products, UGC), and player retention for Roblox experiences |
| Roblox Systems Scripter | `codex/agents/roblox-systems-scripter.toml` | Roblox platform engineering specialist - Masters Luau, the client-server security model, RemoteEvents/RemoteFunctions, DataStore, and module architecture for scalable Roblox experiences |
| Sales Coach | `codex/agents/sales-coach.toml` | Expert sales coaching specialist focused on rep development, pipeline review facilitation, call coaching, deal strategy, and forecast accuracy. Makes every rep and every deal better through structured coaching methodology and behavioral feedback. |
| Sales Data Extraction Agent | `codex/agents/sales-data-extraction-agent.toml` | AI agent specialized in monitoring Excel files and extracting key sales metrics (MTD, YTD, Year End) for internal live reporting |
| Sales Engineer | `codex/agents/sales-engineer.toml` | Senior pre-sales engineer specializing in technical discovery, demo engineering, POC scoping, competitive battlecards, and bridging product capabilities to business outcomes. Wins the technical decision so the deal can close. |
| Sales Outreach | `codex/agents/sales-outreach.toml` | Consultative B2B sales outreach specialist for cold prospecting, lead follow-up, objection handling, proposal writing, and pipeline management — combining data-driven targeting with genuine relationship-building to open doors and close deals |
| Salesforce Architect | `codex/agents/salesforce-architect.toml` | Solution architecture for Salesforce platform — multi-cloud design, integration patterns, governor limits, deployment strategy, and data model governance for enterprise-scale orgs |
| Search Query Analyst | `codex/agents/search-query-analyst.toml` | Specialist in search term analysis, negative keyword architecture, and query-to-intent mapping. Turns raw search query data into actionable optimizations that eliminate waste and amplify high-intent traffic across paid search accounts. |
| Search Relevance Engineer | `codex/agents/search-relevance-engineer.toml` | Expert search engineer for Elasticsearch and OpenSearch — index and analyzer design, BM25 query tuning, hybrid lexical+vector retrieval, and judgment-based relevance evaluation with nDCG and online experiments. |
| Secrets & Credential Hygiene Engineer | `codex/agents/secrets-credential-hygiene-engineer.toml` | Owns the full lifecycle of secrets and credentials — detection, prevention, vaulting, rotation, and leak response — so an application runs on short-lived, least-privilege credentials that are never in the code and are already rotated by the time a leak is found. |
| Section 508 Accessibility Specialist | `codex/agents/section-508-accessibility-specialist.toml` | Expert U.S. federal Section 508 accessibility engineer (the 508 legal baseline is WCAG 2.0 Level AA; WCAG 2.1/2.2 AA are recommended best practice, and ADA Title II requires WCAG 2.1 AA for state/local government) specializing in accessible web development, ARIA implementation, screen reader testing (JAWS/NVDA/VoiceOver), keyboard navigation, color contrast, accessible forms and PDFs, VPAT/ACR authoring, automated and manual auditing (axe/WAVE/Lighthouse), and remediation for government and enterprise sites |
| Security Architect | `codex/agents/security-architect.toml` | Expert security architect specializing in threat modeling, secure-by-design architecture, trust-boundary analysis, defense-in-depth, and risk-based security reviews across web, API, cloud-native, and distributed systems. Designs the security model; hands code-level SAST/DAST and SDLC work to the AppSec Engineer. |
| Senior Developer | `codex/agents/senior-developer.toml` | Premium implementation specialist - Masters Laravel/Livewire/FluxUI, advanced CSS, Three.js integration |
| Senior Project Manager | `codex/agents/senior-project-manager.toml` | Converts specs to tasks and remembers previous projects. Focused on realistic scope, no background processes, exact spec requirements |
| Senior SecOps Engineer | `codex/agents/senior-secops-engineer.toml` | Defensive application security specialist who scans every code submission for secrets and sensitive data exposure before anything else, then implements or audits security controls following the organization's security standard — covering authentication, authorization, tokens, cookies, HTTP headers, CORS, rate limiting, CSP, secrets management, input validation, and secure logging. |
| SEO Specialist | `codex/agents/seo-specialist.toml` | Expert search engine optimization strategist specializing in technical SEO, content optimization, link authority building, and organic search growth. Drives sustainable traffic through data-driven search strategies. |
| Short-Video Editing Coach | `codex/agents/short-video-editing-coach.toml` | Hands-on short-video editing coach covering the full post-production pipeline, with mastery of CapCut Pro, Premiere Pro, DaVinci Resolve, and Final Cut Pro across composition and camera language, color grading, audio engineering, motion graphics and VFX, subtitle design, multi-platform export optimization, editing workflow efficiency, and AI-assisted editing. |
| Social Media Strategist | `codex/agents/social-media-strategist.toml` | Expert social media strategist for LinkedIn, Twitter, and professional platforms. Creates cross-platform campaigns, builds communities, manages real-time engagement, and develops thought leadership strategies. |
| Software Architect | `codex/agents/software-architect.toml` | Expert software architect specializing in system design, domain-driven design, architectural patterns, and technical decision-making for scalable, maintainable systems. |
| Solidity Smart Contract Engineer | `codex/agents/solidity-smart-contract-engineer.toml` | Expert Solidity developer specializing in EVM smart contract architecture, gas optimization, upgradeable proxy patterns, DeFi protocol development, and security-first contract design across Ethereum and L2 chains. |
| Solution Engineer | `codex/agents/solution-engineer.toml` | Hands-on GIS prototype builder who takes strategy from Technical Consultant and turns it into working demos, proof-of-concepts, and technical validations across the full Esri and open-source stack. |
|        Sovereign Health Systems Agent | `codex/agents/sovereign-health-systems-agent.toml` | Government health mandate engagement framework for AI agents |
| Spatial Data Engineer | `codex/agents/spatial-data-engineer.toml` | ETL specialist who transforms messy geospatial data from any source into clean, standardized, production-ready datasets — format conversion, CRS reprojection, attribute normalization, and automated pipelines. |
| Spatial Data Scientist | `codex/agents/spatial-data-scientist.toml` | Advanced spatial analytics specialist who applies statistical modeling, spatial econometrics, clustering, and predictive analytics to geospatial data — finding patterns that aren't visible on a map. |
| Sprint Prioritizer | `codex/agents/sprint-prioritizer.toml` | Expert product manager specializing in agile sprint planning, feature prioritization, and resource allocation. Focused on maximizing team velocity and business value delivery through data-driven prioritization frameworks. |
| SRE (Site Reliability Engineer) | `codex/agents/sre-site-reliability-engineer.toml` | Expert site reliability engineer specializing in SLOs, error budgets, observability, chaos engineering, and toil reduction for production systems at scale. |
| Statistician | `codex/agents/statistician.toml` | Expert in quantitative research methodology, experimental design, and statistical inference — pressure-tests claims, designs sound studies, and separates real signal from noise, chance, and bias |
| Strategy Duel Agent | `codex/agents/strategy-duel-agent.toml` | Conducts live strategy duels using game theory and the 36 Chinese stratagems |
| Studio Operations | `codex/agents/studio-operations.toml` | Expert operations manager specializing in day-to-day studio efficiency, process optimization, and resource coordination. Focused on ensuring smooth operations, maintaining productivity standards, and supporting all teams with the tools and processes needed for success. |
| Studio Producer | `codex/agents/studio-producer.toml` | Senior strategic leader specializing in high-level creative and technical project orchestration, resource allocation, and multi-project portfolio management. Focused on aligning creative vision with business objectives while managing complex cross-functional initiatives and ensuring optimal studio operations. |
| Study Abroad Advisor | `codex/agents/study-abroad-advisor.toml` | Full-spectrum study abroad planning expert covering the US, UK, Canada, Australia, Europe, Hong Kong, and Singapore — proficient in undergraduate, master's, and PhD application strategy, school selection, essay coaching, profile enhancement, standardized test planning, visa preparation, and overseas life adaptation, helping Chinese students craft personalized end-to-end study abroad plans. |
| Supply Chain Strategist | `codex/agents/supply-chain-strategist.toml` | Expert supply chain management and procurement strategy specialist — skilled in supplier development, strategic sourcing, quality control, and supply chain digitalization. Grounded in China's manufacturing ecosystem, helps companies build efficient, resilient, and sustainable supply chains. |
| Support Responder | `codex/agents/support-responder.toml` | Expert customer support specialist delivering exceptional customer service, issue resolution, and user experience optimization. Specializes in multi-channel support, proactive customer care, and turning support interactions into positive brand experiences. |
| Tax Strategist | `codex/agents/tax-strategist.toml` | Expert tax strategist specializing in tax optimization, multi-jurisdictional compliance, transfer pricing, and strategic tax planning. Navigates complex tax codes to minimize liability while ensuring full regulatory compliance across local, state, federal, and international tax regimes. |
| Technical Artist | `codex/agents/technical-artist.toml` | Art-to-engine pipeline specialist - Masters shaders, VFX systems, LOD pipelines, performance budgeting, and cross-engine asset optimization |
| Technical Consultant | `codex/agents/technical-consultant.toml` | Strategic GIS advisor who translates business problems into geospatial solutions — gap analysis, technology roadmaps, RFP responses, and digital transformation strategy across Esri and open-source ecosystems. |
| Technical Writer | `codex/agents/technical-writer.toml` | Expert technical writer specializing in developer documentation, API references, README files, and tutorials. Transforms complex engineering concepts into clear, accurate, and engaging docs that developers actually read and use. |
| Terminal Integration Specialist | `codex/agents/terminal-integration-specialist.toml` | Terminal emulation, text rendering optimization, and SwiftTerm integration for modern Swift applications |
| Test Automation Engineer | `codex/agents/test-automation-engineer.toml` | Expert end-to-end test automation engineer for Playwright and Cypress — resilient selectors, flake elimination, isolated test data, CI parallelization, and trace-driven failure debugging. |
| Test Results Analyzer | `codex/agents/test-results-analyzer.toml` | Expert test analysis specialist focused on comprehensive test result evaluation, quality metrics analysis, and actionable insight generation from testing activities |
| Threat Detection Engineer | `codex/agents/threat-detection-engineer.toml` | Expert detection engineer specializing in SIEM rule development, MITRE ATT&CK coverage mapping, threat hunting, alert tuning, and detection-as-code pipelines for security operations teams. |
| Threat Intelligence Analyst | `codex/agents/threat-intelligence-analyst.toml` | Cyber threat intelligence specialist who tracks adversary groups, maps attack campaigns to MITRE ATT&CK, produces actionable intelligence reports, and builds detection rules that catch real threats. |
| TikTok Strategist | `codex/agents/tiktok-strategist.toml` | Expert TikTok marketing specialist focused on viral content creation, algorithm optimization, and community building. Masters TikTok's unique culture and features for brand growth. |
| Tool Evaluator | `codex/agents/tool-evaluator.toml` | Expert technology assessment specialist focused on evaluating, testing, and recommending tools, software, and platforms for business use and productivity optimization |
| Tracking & Measurement Specialist | `codex/agents/tracking-measurement-specialist.toml` | Expert in conversion tracking architecture, tag management, and attribution modeling across Google Tag Manager, GA4, Google Ads, Meta CAPI, LinkedIn Insight Tag, and server-side implementations. Ensures every conversion is counted correctly and every dollar of ad spend is measurable. |
| Trend Researcher | `codex/agents/trend-researcher.toml` | Expert market intelligence analyst specializing in identifying emerging trends, competitive analysis, and opportunity assessment. Focused on providing actionable insights that drive product strategy and innovation decisions. |
| Twitter Engager | `codex/agents/twitter-engager.toml` | Expert Twitter marketing specialist focused on real-time engagement, thought leadership building, and community-driven growth. Builds brand authority through authentic conversation participation and viral thread creation. |
| UI Designer | `codex/agents/ui-designer.toml` | Expert UI designer specializing in visual design systems, component libraries, and pixel-perfect interface creation. Creates beautiful, consistent, accessible user interfaces that enhance UX and reflect brand identity |
| Unity Architect | `codex/agents/unity-architect.toml` | Data-driven modularity specialist - Masters ScriptableObjects, decoupled systems, and single-responsibility component design for scalable Unity projects |
| Unity Editor Tool Developer | `codex/agents/unity-editor-tool-developer.toml` | Unity editor automation specialist - Masters custom EditorWindows, PropertyDrawers, AssetPostprocessors, ScriptedImporters, and pipeline automation that saves teams hours per week |
| Unity Multiplayer Engineer | `codex/agents/unity-multiplayer-engineer.toml` | Networked gameplay specialist - Masters Netcode for GameObjects, Unity Gaming Services (Relay/Lobby), client-server authority, lag compensation, and state synchronization |
| Unity Shader Graph Artist | `codex/agents/unity-shader-graph-artist.toml` | Visual effects and material specialist - Masters Unity Shader Graph, HLSL, URP/HDRP rendering pipelines, and custom pass authoring for real-time visual effects |
| Unreal Multiplayer Architect | `codex/agents/unreal-multiplayer-architect.toml` | Unreal Engine networking specialist - Masters Actor replication, GameMode/GameState architecture, server-authoritative gameplay, network prediction, and dedicated server setup for UE5 |
| Unreal Systems Engineer | `codex/agents/unreal-systems-engineer.toml` | Performance and hybrid architecture specialist - Masters C++/Blueprint continuum, Nanite geometry, Lumen GI, and Gameplay Ability System for AAA-grade Unreal Engine projects |
| Unreal Technical Artist | `codex/agents/unreal-technical-artist.toml` | Unreal Engine visual pipeline specialist - Masters the Material Editor, Niagara VFX, Procedural Content Generation, and the art-to-engine pipeline for UE5 projects |
| Unreal World Builder | `codex/agents/unreal-world-builder.toml` | Open-world and environment specialist - Masters UE5 World Partition, Landscape, procedural foliage, HLOD, and large-scale level streaming for seamless open-world experiences |
| USWDS Developer | `codex/agents/uswds-developer.toml` | Expert U.S. Web Design System frontend developer specializing in USWDS components and design tokens, accessible-by-default patterns, responsive government UI, Sass settings/theming, the federal design language, integration into CMS platforms (Drupal/WordPress), and compliance with 21st Century IDEA and the Federal Website Standards |
| UX Architect | `codex/agents/ux-architect.toml` | Technical architecture and UX specialist who provides developers with solid foundations, CSS systems, and clear implementation guidance |
| UX Researcher | `codex/agents/ux-researcher.toml` | Expert user experience researcher specializing in user behavior analysis, usability testing, and data-driven design insights. Provides actionable research findings that improve product usability and user satisfaction |
| Video Optimization Specialist | `codex/agents/video-optimization-specialist.toml` | Video marketing strategist specializing in YouTube algorithm optimization, audience retention, chaptering, thumbnail concepts, and cross-platform video syndication. |
| Video Streaming Engineer | `codex/agents/video-streaming-engineer.toml` | Expert video streaming engineer for adaptive bitrate delivery — HLS/DASH packaging, ffmpeg transcode ladders, CMAF low-latency, DRM, CDN delivery, and QoE-driven player tuning. |
| visionOS Spatial Engineer | `codex/agents/visionos-spatial-engineer.toml` | Native visionOS spatial computing, SwiftUI volumetric interfaces, and Liquid Glass design implementation |
| Visual Storyteller | `codex/agents/visual-storyteller.toml` | Expert visual communication specialist focused on creating compelling visual narratives, multimedia content, and brand storytelling through design. Specializes in transforming complex information into engaging visual stories that connect with audiences and drive emotional engagement. |
| Voice AI Integration Engineer | `codex/agents/voice-ai-integration-engineer.toml` | Expert in building end-to-end speech transcription pipelines using Whisper-style models and cloud ASR services — from raw audio ingestion through preprocessing, transcript cleanup, subtitle generation, speaker diarization, and structured downstream integration into apps, APIs, and CMS platforms. |
| Web GIS Developer | `codex/agents/web-gis-developer.toml` | Full-stack web GIS engineer who builds interactive mapping applications — MapLibre GL JS, ArcGIS JS API, Leaflet, real-time dashboards, REST API integration, and geospatial web services. |
| WebAssembly Engineer | `codex/agents/webassembly-engineer.toml` | Expert WebAssembly engineer — compiling Rust/C++/Go to Wasm, JS interop and the boundary marshalling cost, WASI and server-side runtimes (Wasmtime/Wasmer), the component model, and near-native performance tuning. |
| WeChat Mini Program Developer | `codex/agents/wechat-mini-program-developer.toml` | Expert WeChat Mini Program developer specializing in 小程序 development with WXML/WXSS/WXS, WeChat API integration, payment systems, subscription messaging, and the full WeChat ecosystem. |
| WeChat Official Account Manager | `codex/agents/wechat-official-account-manager.toml` | Expert WeChat Official Account (OA) strategist specializing in content marketing, subscriber engagement, and conversion optimization. Masters multi-format content and builds loyal communities through consistent value delivery. |
| Weibo Strategist | `codex/agents/weibo-strategist.toml` | Full-spectrum operations expert for Sina Weibo, with deep expertise in trending topic mechanics, Super Topic community management, public sentiment monitoring, fan economy strategies, and Weibo advertising, helping brands achieve viral reach and sustained growth on China's leading public discourse platform. |
| Whimsy Injector | `codex/agents/whimsy-injector.toml` | Expert creative specialist focused on adding personality, delight, and playful elements to brand experiences. Creates memorable, joyful interactions that differentiate brands through unexpected moments of whimsy |
| WordPress Performance Engineer | `codex/agents/wordpress-performance-engineer.toml` | Expert WordPress performance engineer specializing in Core Web Vitals, object caching (Redis/Memcached), page caching, database and WP_Query optimization, the Transients API, asset minification/deferral/critical CSS, image optimization and lazy loading, CDN integration, plugin performance auditing, and PHP-FPM/opcache tuning for fast, audit-passing sites |
| WordPress Shopping Cart Engineer | `codex/agents/wordpress-shopping-cart-engineer.toml` | Expert WordPress e-commerce engineer specializing in WooCommerce for product catalog management, payment gateway integration, checkout customization, order management, tax and coupon configuration, and conversion-optimized storefront delivery on WordPress |
| Workflow Architect | `codex/agents/workflow-architect.toml` | Workflow design specialist who maps complete workflow trees for every system, user journey, and agent interaction — covering happy paths, all branch conditions, failure modes, recovery paths, handoff contracts, and observable states to produce build-ready specs that agents can implement against and QA can test against. |
| Workflow Optimizer | `codex/agents/workflow-optimizer.toml` | Expert process improvement specialist focused on analyzing, optimizing, and automating workflows across all business functions for maximum productivity and efficiency |
| X/Twitter Intelligence Analyst | `codex/agents/x-twitter-intelligence-analyst.toml` | Social intelligence specialist for X/Twitter research, trend detection, account monitoring, and evidence-backed audience insights using public signals and structured data workflows. |
| Xiaohongshu Specialist | `codex/agents/xiaohongshu-specialist.toml` | Expert Xiaohongshu marketing specialist focused on lifestyle content, trend-driven strategies, and authentic community engagement. Masters micro-content creation and drives viral growth through aesthetic storytelling. |
| XR Cockpit Interaction Specialist | `codex/agents/xr-cockpit-interaction-specialist.toml` | Specialist in designing and developing immersive cockpit-based control systems for XR environments |
| XR Immersive Developer | `codex/agents/xr-immersive-developer.toml` | Expert WebXR and immersive technology developer with specialization in browser-based AR/VR/XR applications |
| XR Interface Architect | `codex/agents/xr-interface-architect.toml` | Spatial interaction designer and interface strategist for immersive AR/VR/XR environments |
| Zhihu Strategist | `codex/agents/zhihu-strategist.toml` | Expert Zhihu marketing specialist focused on thought leadership, community credibility, and knowledge-driven engagement. Masters question-answering strategy and builds brand authority through authentic expertise sharing. |
| ZK Steward | `codex/agents/zk-steward.toml` | "Knowledge-base steward in the spirit of Niklas Luhmann's Zettelkasten. Default perspective: Luhmann; switches to domain experts (Feynman, Munger, Ogilvy, etc.) by task. Enforces atomic notes, connectivity, and validation loops. Use for knowledge-base building, note linking, complex task breakdown, and cross-domain decision support." |
