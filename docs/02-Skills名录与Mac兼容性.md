# Skills 名录与 Mac 兼容性

实查两处个人目录，共 **196 个 SKILL.md、170 个顶级包**。这张表是迁移名录，未修改原 Skill。原始路径、原显示名、SHA-256、依赖及 Windows 线索行号见 `inventories/skills-inventory.json`。表内简介沿用原文件；原来缺字段时如实标注。

## 兼容状态如何看

| 标记 | 数量 | 解释 |
| --- | ---: | --- |
| A | 148 | 主要是文字或素材，可复制；可能仍依赖宿主工具、账号或外部服务，不代表零环境要求。 |
| B | 28 | 有脚本/依赖，需在 Mac 准备对应 Python、Node、CLI 或软件。 |
| C | 20 | 存在 Windows 调用线索，逐项检查 Mac 分支；不能据此判断整个 Skill 不可用。 |

优先恢复 `i-have-adhd`、`caveman`、规划/实施/验证相关 Skill；设计和媒体 Skill 按实际任务检查。Astra advisor、Ponytail 是插件，名录在下一份文件。Skills 标准并不会把脚本依赖和外部服务自动安装到新电脑。

## 需要明确适配的例子

- `cinema-dna-21x9x3` 的 `scripts/compose-nine-shot-storyboard.ps1` 使用 System.Drawing；Mac 选择等效拼版路径。
- `window-scenery` 的 `scripts/overlay_badge.py` 包含 Windows 字体目录；Mac 要选可显示中文的字体。
- `impeccable` 内 Windows x64 exe 已从迁移包排除，CMD 入口仍作为原始代码保留；使用前确认 Mac 版本或无需 CLI 的指令路径。
- `officecli` 有 macOS 安装入口，`img2threejs` 有 python3 路径；命中 PowerShell 不意味着不能用。
- `anysearch/runtime.conf` 是本机环境文件，已排除；Mac 按包内说明重新生成。`img2threejs` 两份 env 示例的键为素材/工作目录，未命中本次检测的真实密钥模式，保留为示例但路径需改；`shuorenhua/runtime-files.json` 是文件清单，不能当新机运行时已安装。

保留原 Skill 内容可回溯本地定制。若要修脚本，这是迁移后的独立适配工作；先明确具体文件、行为和验收。`lieflat-less-ai-tone` 原来缺少 `agents/openai.yaml`；恢复后按用户规则列出拟补内容请求确认，不自行改简介。

## 个人 Skills 完整名录

目录列 `codex/...` 对应包内 `skills/codex/...`，`agents/...` 对应 `skills/agents/...`。

| Skill 名称 | 原简介 | 分类 | 包内目录 |
| --- | --- | --- | --- |
| `agent-reach` | 小红书、X、Reddit、GitHub 等平台调研  \|  全网搜索与资料获取 | A：文档／素材 | `agents/agent-reach` |
| `andrej-karpathy-perspective` | AI工程、学习与技术判断  \|  Karpathy思维框架与工程现实主义 | A：文档／素材 | `agents/huashu-nuwa/examples/andrej-karpathy-perspective` |
| `anysearch` | 网页、新闻与公开资料查询  \|  实时搜索与页面内容提取 | C：Windows 线索待审 | `codex/anysearch` |
| `apple-design` | Apple 风格 Web 界面  \|  手势物理、流体动效、材质与排版原则 | A：文档／素材 | `codex/apple-design` |
| `ask-matt` | 开发任务规划  \|  技能选择与流程路由 | A：文档／素材 | `agents/ask-matt` |
| `brainstorming` | 编程、产品设计与内容创作前  \|  梳理需求、边界和方案 | C：Windows 线索待审 | `agents/brainstorming` |
| `brand` | 品牌语调、视觉识别与营销资产  \|  创建、审查并维护品牌一致性 | B：依赖待核对 | `agents/brand` |
| `brandkit` | 品牌规范、标志系统与视觉提案  \|  生成高端品牌视觉套件 | A：文档／素材 | `agents/brandkit` |
| `cangjie-skill` | 书籍与长内容蒸馏  \|  可执行方法论 Skill 工具包 | C：Windows 线索待审 | `codex/cangjie-skill` |
| `caveman` | 对话、技术说明与状态汇报  \|  保留准确性并压缩表达 | A：文档／素材 | `agents/caveman` |
| `character-casting-studio` | 梵想美学·写实角色选角  \|  建立差异化人物肖像与选角资产 | A：文档／素材 | `codex/character-casting-studio` |
| `chinese-style-poster-skill` | 梵想美学·当代中式海报  \|  生成东方视觉方向与排版方案 | A：文档／素材 | `codex/chinese-style-poster-skill` |
| `cinema-dna-21x9x3` | 梵想美学·电影三联画  \|  构建超宽银幕镜头叙事 | C：Windows 线索待审 | `codex/cinema-dna-21x9x3` |
| `cli-hub-meta-skill` | 创意、效率与 AI 软件的命令行操作  \|  查找代理友好的 CLI 工具 | A：文档／素材 | `codex/cli-hub-meta-skill` |
| `code-review` | 分支、PR 与工作区变更检查  \|  按规范和需求审查代码 | A：文档／素材 | `agents/code-review` |
| `codebase-design` | 模块接口、代码边界与可测试性设计  \|  改进代码库结构 | A：文档／素材 | `agents/codebase-design` |
| `create-pantone-photo-posters` | 梵想美学/摄影海报  \|  近似色号与主体穿框 | A：文档／素材 | `codex/create-pantone-photo-posters` |
| `culture-fragment-poster-engine` | 梵想美学·文化视觉转译  \|  提炼视觉基因并生成品牌主视觉 | A：文档／素材 | `codex/culture-fragment-poster-engine` |
| `dbs` | 商业分析、内容与个人决策任务  \|  导航 DBS 工具箱 | B：依赖待核对 | `codex/dbs` |
| `dbs-action` | 拖延、行动受阻与执行困难  \|  诊断心理原因和行动障碍 | A：文档／素材 | `codex/dbs-action` |
| `dbs-agent-migration` | Claude、Codex、Grok 与通用 Agents  \|  迁移并统一代理工作台 | A：文档／素材 | `codex/dbs-agent-migration` |
| `dbs-ai-check` | 文章、文案与社交媒体内容审查  \|  识别 AI 写作痕迹 | A：文档／素材 | `codex/dbs-ai-check` |
| `dbs-benchmark` | 商业定位、个人品牌与竞品研究  \|  筛选值得模仿的对标 | A：文档／素材 | `codex/dbs-benchmark` |
| `dbs-chatroom` | 复杂议题、观点碰撞与专家讨论  \|  组织多角色聊天室 | A：文档／素材 | `codex/dbs-chatroom` |
| `dbs-chatroom-austrian` | 奥派经济学、商业与政策讨论  \|  模拟哈耶克和米塞斯等观点 | A：文档／素材 | `codex/dbs-chatroom-austrian` |
| `dbs-content` | 文章、短视频与自媒体选题创作  \|  诊断内容方向和表达 | A：文档／素材 | `codex/dbs-content` |
| `dbs-content-system` | 文章、推文、案例与课程素材整理  \|  构建可复用内容资产库 | B：依赖待核对 | `codex/dbs-content-system` |
| `dbs-decision` | 业务、关系、健康、职业与投资决策  \|  建立长期决策系统 | A：文档／素材 | `codex/dbs-decision` |
| `dbs-deconstruct` | 商业术语、抽象概念与争议观点  \|  拆解概念和隐藏假设 | A：文档／素材 | `codex/dbs-deconstruct` |
| `dbs-diagnosis` | 业务问题、盈利逻辑与商业模式分析  \|  开展商业问诊和体检 | A：文档／素材 | `codex/dbs-diagnosis` |
| `dbs-goal` | 职业、业务、学习与个人成长规划  \|  把模糊目标变成可检查结果 | A：文档／素材 | `codex/dbs-goal` |
| `dbs-good-question` | 复杂问题、代理任务与自动化评估  \|  生成可推理的问题说明 | A：文档／素材 | `codex/dbs-good-question` |
| `dbs-hook` | 抖音、小红书与视频号短视频开头  \|  诊断并优化内容钩子 | A：文档／素材 | `codex/dbs-hook` |
| `dbs-knowledge` | 本地资料、项目文档与知识档案  \|  构建文件夹知识库 | A：文档／素材 | `codex/dbs-knowledge` |
| `dbs-learning` | 课程学习、技能训练与连续阅读  \|  生成自适应学习内容 | A：文档／素材 | `codex/dbs-learning` |
| `dbs-report` | 多轮商业诊断与咨询结果交付  \|  合并快照生成 Markdown 报告 | A：文档／素材 | `codex/dbs-report` |
| `dbs-resonate` | 文章、口播稿与短视频文案评审  \|  诊断传播共鸣和流失风险 | A：文档／素材 | `codex/dbs-resonate` |
| `dbs-restore` | 跨会话继续商业诊断任务  \|  恢复最近保存的状态 | A：文档／素材 | `codex/dbs-restore` |
| `dbs-save` | 商业诊断、咨询与分析任务存档  \|  保存当前关键状态 | A：文档／素材 | `codex/dbs-save` |
| `dbs-script-flow` | 短视频口播稿、逐字稿与脚本评审  \|  检查逻辑、密度和流畅度 | A：文档／素材 | `codex/dbs-script-flow` |
| `dbs-skill-cleaner` | Codex 与本地 Skills 整理  \|  发现重复、冲突和无效技能 | B：依赖待核对 | `codex/dbs-skill-cleaner` |
| `dbs-slowisfast` | 返工频繁、节奏失控与效率焦虑  \|  诊断过度求快的问题 | A：文档／素材 | `codex/dbs-slowisfast` |
| `dbs-spread` | 文章、短视频与社交媒体传播分析  \|  诊断扩散动力和传播阻力 | A：文档／素材 | `codex/dbs-spread` |
| `dbs-update` | 本地 DBS 技能库维护  \|  检查更新并保护自定义内容 | A：文档／素材 | `codex/dbs-update` |
| `dbs-wechat-html` | 微信公众号文章发布与排版  \|  生成可复制的精美 HTML | A：文档／素材 | `codex/dbs-wechat-html` |
| `dbs-xhs-title` | 小红书笔记、种草与品牌内容  \|  生成真实且有点击力的标题 | A：文档／素材 | `codex/dbs-xhs-title` |
| `de-AI-writing` | 中文写作、改写、润色与翻译  \|  保留原意并减少 AI 写作痕迹 | A：文档／素材 | `agents/de-ai-writing` |
| `design-system` | 设计令牌、组件规范与品牌演示  \|  构建设计系统并生成幻灯片 | B：依赖待核对 | `agents/design-system` |
| `design-taste-frontend` | 网站、Web 应用与落地页开发  \|  避免模板化的低质界面 | A：文档／素材 | `agents/design-taste-frontend` |
| `diagnosing-bugs` | 程序报错、测试失败与异常行为  \|  追踪调用链并定位根因 | B：依赖待核对 | `agents/diagnosing-bugs` |
| `dispatching-parallel-agents` | 多个互不依赖的调研或开发任务  \|  并行分派代理处理 | A：文档／素材 | `agents/dispatching-parallel-agents` |
| `domain-modeling` | 复杂业务系统、领域边界与对象关系  \|  建立可维护领域模型 | A：文档／素材 | `agents/domain-modeling` |
| `elon-musk-perspective` | 成本、工程与第一性原理决策  \|  马斯克思维模型与五步算法 | A：文档／素材 | `agents/huashu-nuwa/examples/elon-musk-perspective` |
| `executing-plans` | 已有规格和分步实施计划的开发任务  \|  按阶段执行并验证结果 | A：文档／素材 | `agents/executing-plans` |
| `fantasy-life-force-portrait-photography` | 梵想美学·生命感人像摄影  \|  将普通人像升级为鲜活氛围大片 | A：文档／素材 | `codex/fantasy-life-force-portrait-photography` |
| `fantasy-minimal-magazine` | 梵想美学·极简杂志海报  \|  将图片转译为留白编辑版面 | A：文档／素材 | `codex/fantasy-minimal-magazine` |
| `fantasy-movie-poster` | 梵想美学·电影海报设计  \|  生成原创竖版电影主视觉 | B：依赖待核对 | `codex/fantasy-movie-poster` |
| `fantasy-photography-simulation` | 梵想美学·摄影风格模拟  \|  生成相机质感摄影组图 | A：文档／素材 | `codex/fantasy-photography-simulation` |
| `fantasy-qiqiguaiguai` | 梵想美学·怪趣社交图文  \|  将生活碎片转为幽默编辑视觉 | A：文档／素材 | `codex/fantasy-qiqiguaiguai` |
| `feynman-perspective` | 学习、解释与科学验证  \|  费曼思维框架与反自欺检验 | A：文档／素材 | `agents/huashu-nuwa/examples/feynman-perspective` |
| `find-skills` | 编程、设计、办公与内容创作扩展  \|  搜索并评估合适的 Skills | A：文档／素材 | `codex/find-skills` |
| `finesse-ui` | 现有网站、应用与组件精修  \|  提升视觉和交互完成度 | B：依赖待核对 | `codex/finesse-ui` |
| `finishing-a-development-branch` | Git 功能分支完成与交付  \|  验证变更并选择合并方式 | A：文档／素材 | `agents/finishing-a-development-branch` |
| `frontend-design` | 网站、Web 应用与落地页开发  \|  设计高质量前端界面 | A：文档／素材 | `agents/frontend-design` |
| `gc-universal-field-study` | 梵想美学/照片艺术化  \|  极简 Field Study 插画 | A：文档／素材 | `codex/gc-universal-field-study` |
| `geo-sleuth` | 照片定位  \|  地理线索核验与机位推断 | C：Windows 线索待审 | `codex/geo-sleuth` |
| `good-writing` | 中文仿写、改写、精修与翻译  \|  复现指定作者风格并保持结构 | A：文档／素材 | `agents/good-writing` |
| `goutoujunshi` | 恋爱关系参谋  \|  情绪支持、聊天分析与可撤销记忆 | B：依赖待核对 | `codex/goutoujunshi` |
| `gpt-taste` | 界面、品牌与视觉作品评审  \|  应用高级审美和设计标准 | A：文档／素材 | `agents/gpt-taste` |
| `grill-with-docs` | 方案与设计讨论  \|  深度追问与文档沉淀 | A：文档／素材 | `agents/grill-with-docs` |
| `grilling` | 需求、方案与技术设计评审  \|  连续追问假设和失败条件 | A：文档／素材 | `agents/grilling` |
| `gsap-core` | GSAP 核心动画  \|  补间、缓动、交错与响应式动效 | A：文档／素材 | `codex/gsap-core` |
| `gsap-frameworks` | Vue、Nuxt 与 Svelte 动效  \|  生命周期、选择器作用域与卸载清理 | A：文档／素材 | `codex/gsap-frameworks` |
| `gsap-performance` | GSAP 动效性能  \|  减少布局抖动、批处理与流畅度优化 | A：文档／素材 | `codex/gsap-performance` |
| `gsap-plugins` | GSAP 插件生态  \|  插件注册、交互、SVG、文本与物理动效 | A：文档／素材 | `codex/gsap-plugins` |
| `gsap-react` | React 与 Next.js 动效  \|  useGSAP、作用域、SSR 与卸载清理 | A：文档／素材 | `codex/gsap-react` |
| `gsap-scrolltrigger` | GSAP 滚动动效  \|  ScrollTrigger 触发、固定与滚动联动 | A：文档／素材 | `codex/gsap-scrolltrigger` |
| `gsap-timeline` | GSAP 时间轴  \|  动画编排、标签、嵌套与播放控制 | A：文档／素材 | `codex/gsap-timeline` |
| `gsap-utils` | GSAP 工具函数  \|  数值映射、插值、随机、吸附与集合处理 | A：文档／素材 | `codex/gsap-utils` |
| `h3-prompt-writing` | MiniMax H3 视频生成  \|  多模态提示词编写 | A：文档／素材 | `codex/h3-prompt-writing` |
| `handoff` | 跨代理、跨会话与团队任务交接  \|  整理上下文、决策和待办 | A：文档／素材 | `agents/handoff` |
| `heytea-style` | 梵想美学/食品海报  \|  白底实物与童趣涂鸦双版 | B：依赖待核对 | `codex/heytea-style` |
| `high-end-visual-design` | 品牌视觉、营销页面与高端界面  \|  制定艺术方向并完成设计 | A：文档／素材 | `agents/high-end-visual-design` |
| `huashu-nuwa` | 人物思维框架与顾问视角  \|  深度调研并生成可运行的人物 Skill | B：依赖待核对 | `agents/huashu-nuwa` |
| `humanizer-zh` | 中文写作、编辑与审阅  \|  识别并去除 AI 生成痕迹 | A：文档／素材 | `agents/humanizer-zh` |
| `hypit` | Hypit 视频制作  \|  参考复刻与可编辑工作流 | B：依赖待核对 | `codex/hypit` |
| `i-have-adhd` | 专注友好回复  \|  行动优先、分步执行与进度重述 | A：文档／素材 | `codex/i-have-adhd` |
| `ilya-sutskever-perspective` | AI研究、安全与方向判断  \|  Ilya Sutskever思维框架 | A：文档／素材 | `agents/huashu-nuwa/examples/ilya-sutskever-perspective` |
| `image-to-code` | 网页截图、设计稿与产品界面还原  \|  生成布局、样式和组件代码 | A：文档／素材 | `agents/image-to-code` |
| `imagegen-frontend-web` | 网站、Web 应用与桌面端设计  \|  用图像生成探索界面方案 | A：文档／素材 | `agents/imagegen-frontend-web` |
| `img2threejs` | Three.js 图像转 3D  \|  程序化建模与质量门控 | C：Windows 线索待审 | `codex/img2threejs` |
| `impeccable` | 网站、应用与产品界面设计  \|  审查、重设计并精修 UI/UX | C：Windows 线索待审 | `agents/impeccable` |
| `implement` | 已有规格、设计和计划的开发任务  \|  完成最小必要代码实现 | A：文档／素材 | `agents/implement` |
| `improve-animations` | 界面动效审计  \|  发现问题并生成优先级修复计划 | A：文档／素材 | `codex/improve-animations` |
| `improve-codebase-architecture` | 大型项目、模块依赖与技术债治理  \|  小步改进代码库架构 | A：文档／素材 | `agents/improve-codebase-architecture` |
| `last30days` | 近30天趋势研究  \|  跨平台讨论聚合与证据摘要 | C：Windows 线索待审 | `codex/last30days` |
| `lieflat-less-ai-tone` | 未显式设置 | A：文档／素材 | `codex/writing-dna-skill/skills/lieflat-less-ai-tone` |
| `loop-me` | 可重复检查、生成和修正的任务  \|  循环执行直到满足完成条件 | A：文档／素材 | `agents/loop-me` |
| `make-photo-stamp-archive` | 梵想美学/照片档案  \|  直拼纸面与定制图章 | A：文档／素材 | `codex/make-photo-stamp-archive` |
| `minimal-logo-design` | 梵想美学·极简标志设计  \|  生成字标、几何标志与品牌纹样 | A：文档／素材 | `codex/minimal-logo-design` |
| `money-find` | AI 兼职与副业  \|  需求信号检索与反诈筛选 | B：依赖待核对 | `codex/money-find` |
| `money-init` | AI 副业初始化  \|  用户画像与状态建档 | B：依赖待核对 | `codex/money-init` |
| `money-plan` | 副业行动规划  \|  两周计划、收入验证与止损线 | B：依赖待核对 | `codex/money-plan` |
| `money-retro` | 副业执行复盘  \|  投入收入对账与经验沉淀 | B：依赖待核对 | `codex/money-retro` |
| `money-status` | 副业状态看板  \|  画像、机会与进度汇总 | B：依赖待核对 | `codex/money-status` |
| `money-verify` | 兼职与副业审查  \|  实时查证与反诈判定 | B：依赖待核对 | `codex/money-verify` |
| `mono-color` | 单色/双色编辑印刷  \|  网点图像、留白与排版 | B：依赖待核对 | `codex/mono-color` |
| `morph-ppt` | PowerPoint 连续动画与 Keynote 式转场  \|  制作平滑变形演示 | C：Windows 线索待审 | `agents/officecli/skills/morph-ppt` |
| `morph-ppt-3d` | PowerPoint 三维模型与镜头动画  \|  制作 3D 变形演示 | C：Windows 线索待审 | `agents/officecli/skills/morph-ppt-3d` |
| `mrbeast-perspective` | YouTube选题、包装与留存优化  \|  MrBeast内容增长方法 | B：依赖待核对 | `agents/huashu-nuwa/examples/mrbeast-perspective` |
| `munger-perspective` | 投资、决策与认知偏误检查  \|  芒格多元思维模型与逆向分析 | A：文档／素材 | `agents/huashu-nuwa/examples/munger-perspective` |
| `naval-perspective` | 财富、杠杆与人生选择  \|  Naval思维框架与特定知识分析 | A：文档／素材 | `agents/huashu-nuwa/examples/naval-perspective` |
| `no-negative-echo` | AI 交付文案  \|  会话残留清理与结果核验 | B：依赖待核对 | `codex/no-negative-echo` |
| `officecli` | Word、Excel 与 PowerPoint 文档处理  \|  使用 CLI 创建、检查和修改 | C：Windows 线索待审 | `agents/officecli` |
| `officecli-academic-paper` | 论文、期刊稿与学位论文章节  \|  制作规范引用的 Word 文档 | C：Windows 线索待审 | `agents/officecli/skills/officecli-academic-paper` |
| `officecli-data-dashboard` | Excel KPI、运营和管理看板  \|  生成指标卡、图表与条件格式 | C：Windows 线索待审 | `agents/officecli/skills/officecli-data-dashboard` |
| `officecli-docx` | Word 报告、信函、备忘录与模板  \|  创建、读取和编辑 DOCX | C：Windows 线索待审 | `agents/officecli/skills/officecli-docx` |
| `officecli-financial-model` | Excel 三表、DCF、LBO 与情景分析  \|  构建公式驱动财务模型 | C：Windows 线索待审 | `agents/officecli/skills/officecli-financial-model` |
| `officecli-pitch-deck` | PowerPoint 种子轮与各阶段融资路演  \|  制作投资人演示文稿 | C：Windows 线索待审 | `agents/officecli/skills/officecli-pitch-deck` |
| `officecli-pptx` | PowerPoint 汇报、路演与教学演示  \|  创建、编辑和检查 PPTX | C：Windows 线索待审 | `agents/officecli/skills/officecli-pptx` |
| `officecli-word-form` | Word 入职、调查与合规表单  \|  创建可填写且受保护的 DOCX | C：Windows 线索待审 | `agents/officecli/skills/officecli-word-form` |
| `officecli-xlsx` | Excel 表格、模型、看板与跟踪器  \|  创建、读取和编辑 XLSX | C：Windows 线索待审 | `agents/officecli/skills/officecli-xlsx` |
| `open-websearch` | 开放网页检索  \|  搜索、正文抓取与 GitHub README 获取 | A：文档／素材 | `agents/open-websearch` |
| `opencli-browser` | OpenCLI/Chrome/网页操作  \|  登录态浏览器读取、点击与表单交互 | A：文档／素材 | `codex/opencli-browser` |
| `opencli-usage` | OpenCLI/命令发现/使用参考  \|  查询站点适配器、参数与输出格式 | A：文档／素材 | `codex/opencli-usage` |
| `oriental-editorial-poster` | 梵想美学·东方编辑海报  \|  生成文化排版与极简主视觉 | A：文档／素材 | `codex/oriental-editorial-poster` |
| `paul-graham-perspective` | 创业、写作与产品判断  \|  Paul Graham思维框架 | A：文档／素材 | `agents/huashu-nuwa/examples/paul-graham-perspective` |
| `photo-revival` | 梵想美学·照片诗意焕新  \|  将随手拍重绘为留白手绘插画 | A：文档／素材 | `codex/photo-revival` |
| `photo-to-travel-sketch` | 梵想美学/旅行照片  \|  松弛干性马克笔速写 | A：文档／素材 | `codex/photo-to-travel-sketch` |
| `plan-vibecoding-project` | VibeCoding 项目规划  \|  分级生成需求、PRD、验收标准与轻量架构 | A：文档／素材 | `codex/plan-vibecoding-project` |
| `project-graveyard` | 本地项目复盘  \|  识别停滞项目并制定重启计划 | B：依赖待核对 | `codex/project-graveyard` |
| `prototype` | 产品状态、交互逻辑与界面方向验证  \|  构建一次性原型 | A：文档／素材 | `agents/prototype` |
| `reality-restaged` | 梵想美学/纪实照片  \|  超现实电影舞台重构 | A：文档／素材 | `codex/reality-restaged` |
| `receiving-code-review` | PR 与代码审查意见处理  \|  核实反馈后实施可靠修改 | A：文档／素材 | `agents/receiving-code-review` |
| `redesign-existing-projects` | 现有网站、应用与后台系统升级  \|  提升设计且保持功能完整 | A：文档／素材 | `agents/redesign-existing-projects` |
| `regional-culture-poster` | 梵想美学·地域文化海报  \|  将地方文化转译为当代大字视觉 | B：依赖待核对 | `codex/regional-culture-poster` |
| `remotion-best-practices` | Remotion 视频制作  \|  路由创建、动画、媒体与渲染实践 | B：依赖待核对 | `codex/remotion-best-practices` |
| `remotion-render` | Remotion 视频渲染  \|  MP4、静帧与透明视频输出 | A：文档／素材 | `codex/remotion-render` |
| `requesting-code-review` | 主要功能完成、合并或发布前  \|  发起代码审查并核验需求 | A：文档／素材 | `agents/requesting-code-review` |
| `research` | 技术文档、API 与专业主题调研  \|  查证一手来源并保存结论 | A：文档／素材 | `agents/research` |
| `resolving-merge-conflicts` | Git 合并与变基冲突处理  \|  安全解决冲突并验证结果 | A：文档／素材 | `agents/resolving-merge-conflicts` |
| `review-animations` | Web 动效代码审查  \|  检查时序、物理感、性能与无障碍 | A：文档／素材 | `codex/review-animations` |
| `setup-pre-commit` | Git、Husky 与 lint-staged 项目检查  \|  配置提交前自动验证 | A：文档／素材 | `agents/setup-pre-commit` |
| `ship-vibecoding-slice` | VibeCoding 开发交付  \|  按范围小步实现、验证、状态同步与故障止损 | A：文档／素材 | `codex/ship-vibecoding-slice` |
| `shuorenhua` | 中英文写作、改写与审稿  \|  清理 AI 套路并保留事实与语域 | B：依赖待核对 | `agents/shuorenhua` |
| `steve-jobs-perspective` | 产品、设计与战略决策  \|  乔布斯思维框架与聚焦判断 | A：文档／素材 | `agents/huashu-nuwa/examples/steve-jobs-perspective` |
| `street-photo-illustration` | 梵想美学·街拍人物插画  \|  保留实景并转换人物画风 | A：文档／素材 | `codex/street-photo-illustration` |
| `sun-yuchen-perspective` | 营销、注意力与危机公关  \|  孙宇晨叙事与传播策略分析 | A：文档／素材 | `agents/huashu-nuwa/examples/sun-yuchen-perspective` |
| `taleb-perspective` | 风险、决策与不确定性分析  \|  塔勒布反脆弱与尾部风险框架 | A：文档／素材 | `agents/huashu-nuwa/examples/taleb-perspective` |
| `tdd` | 功能开发、缺陷修复与代码重构  \|  执行测试驱动开发 | A：文档／素材 | `agents/tdd` |
| `teach` | 工作区内的编程、工具与概念学习  \|  提供结合项目的教学 | A：文档／素材 | `agents/teach` |
| `thinking-out-loud` | 口述需求梳理  \|  回显确认长篇思路与约束 | A：文档／素材 | `codex/thinking-out-loud` |
| `threejs-animation` | Three.js 动画  \|  关键帧、骨骼与混合控制 | A：文档／素材 | `codex/threejs-animation` |
| `threejs-fundamentals` | Three.js 基础开发  \|  场景、相机与渲染器搭建 | A：文档／素材 | `codex/threejs-fundamentals` |
| `threejs-geometry` | Three.js 几何建模  \|  几何体、BufferGeometry 与实例化 | A：文档／素材 | `codex/threejs-geometry` |
| `threejs-interaction` | Three.js 交互  \|  射线检测、控件与对象选择 | A：文档／素材 | `codex/threejs-interaction` |
| `threejs-lighting` | Three.js 灯光  \|  光照、阴影与环境照明 | A：文档／素材 | `codex/threejs-lighting` |
| `threejs-loaders` | Three.js 资产加载  \|  模型、纹理与异步加载 | A：文档／素材 | `codex/threejs-loaders` |
| `threejs-materials` | Three.js 材质  \|  PBR、基础材质与 ShaderMaterial | A：文档／素材 | `codex/threejs-materials` |
| `threejs-postprocessing` | Three.js 后期处理  \|  Bloom、景深与屏幕特效 | A：文档／素材 | `codex/threejs-postprocessing` |
| `threejs-shaders` | Three.js 着色器  \|  GLSL、Uniform 与自定义特效 | A：文档／素材 | `codex/threejs-shaders` |
| `threejs-textures` | Three.js 纹理  \|  UV、环境贴图与纹理优化 | A：文档／素材 | `codex/threejs-textures` |
| `to-spec` | 需求讨论、方案对话与产品决策  \|  整理规格并发布到问题跟踪器 | A：文档／素材 | `agents/to-spec` |
| `to-tickets` | 项目计划、规格与开发任务拆分  \|  生成带依赖关系的任务票 | A：文档／素材 | `agents/to-tickets` |
| `travel-memory-card-duo` | 梵想美学/旅行记忆  \|  卡片与透明底贴纸双图 | A：文档／素材 | `codex/travel-memory-card-duo` |
| `travel-memory-sticker-card` | 梵想美学/旅行记忆  \|  水粉剪纸贴纸卡 | A：文档／素材 | `codex/travel-memory-sticker-card` |
| `triage` | GitHub Issues 与外部 Pull Requests  \|  分类、核实并完善任务说明 | A：文档／素材 | `agents/triage` |
| `trump-perspective` | 谈判、权力与传播行为分析  \|  特朗普决策逻辑与行为预判 | A：文档／素材 | `agents/huashu-nuwa/examples/trump-perspective` |
| `ui-ux-pro-max` | Web、移动端与桌面端 UI/UX  \|  检索本地设计库并指导设计和审查 | B：依赖待核对 | `agents/ui-ux-pro-max` |
| `using-git-worktrees` | 并行功能开发与隔离实验  \|  创建独立 Git 工作树 | A：文档／素材 | `agents/using-git-worktrees` |
| `using-superpowers` | Codex 对话和任务开始阶段  \|  优先识别并调用合适 Skills | A：文档／素材 | `agents/using-superpowers` |
| `verification-before-completion` | 代码提交、合并与任务交付前  \|  运行检查并用结果证明完成 | A：文档／素材 | `agents/verification-before-completion` |
| `vinyl-image-generator` | 梵想美学/唱片视觉  \|  虚构黑胶发行套装 | A：文档／素材 | `codex/vinyl-image-generator` |
| `voxel-icon` | 体素图标  \|  等距静态图与四帧循环动画 | B：依赖待核对 | `codex/voxel-icon` |
| `wayfinder` | 跨会话、大型项目与长期计划  \|  建立可逐项解决的决策地图 | A：文档／素材 | `agents/wayfinder` |
| `webgpu-threejs-tsl` | Three.js WebGPU/TSL  \|  节点材质、计算着色与后期处理 | B：依赖待核对 | `codex/webgpu-threejs-tsl` |
| `wigolo` | 网页搜索、抓取、监控与版本对比  \|  提供可缓存的网络情报 | A：文档／素材 | `agents/wigolo` |
| `wigolo-agent` | 价格、产品与多网站结构化采集  \|  自主规划并执行数据搜集 | A：文档／素材 | `agents/wigolo-agent` |
| `wigolo-cache` | 已抓取网页、文档与历史资料查询  \|  搜索和维护本地缓存 | A：文档／素材 | `agents/wigolo-cache` |
| `wigolo-crawl` | 文档站、知识库与网站批量索引  \|  抓取多页内容并写入缓存 | A：文档／素材 | `agents/wigolo-crawl` |
| `wigolo-diff` | 网页更新、文档版本与文本变化检查  \|  比较内容并显示差异 | A：文档／素材 | `agents/wigolo-diff` |
| `wigolo-extract` | 价格表、参数表与网页结构化数据  \|  提取表格、键值和元数据 | A：文档／素材 | `agents/wigolo-extract` |
| `wigolo-fetch` | 指定网页、PDF 与动态页面读取  \|  提取干净内容并保存缓存 | A：文档／素材 | `agents/wigolo-fetch` |
| `wigolo-find-similar` | 相似文章、资料来源与竞品页面发现  \|  融合语义和关键词检索 | A：文档／素材 | `agents/wigolo-find-similar` |
| `wigolo-research` | 市场、技术与专业主题深度调研  \|  分解问题并生成研究简报 | A：文档／素材 | `agents/wigolo-research` |
| `wigolo-search` | 网页、新闻与限定站点搜索  \|  执行多查询并提供证据评分 | A：文档／素材 | `agents/wigolo-search` |
| `wigolo-watch` | 产品页、公告与文档更新监控  \|  建立任务并检查页面变化 | A：文档／素材 | `agents/wigolo-watch` |
| `window-scenery` | 梵想美学·车窗旅行摄影  \|  生成写实窗景与地点标识 | C：Windows 线索待审 | `codex/window-scenery` |
| `writing-beats` | 文章、演讲与叙事内容组织  \|  把素材编排为连续节拍 | A：文档／素材 | `agents/writing-beats` |
| `writing-dna-skill` | 作者/品牌风格分析  \|  写作 DNA 蒸馏 | A：文档／素材 | `codex/writing-dna-skill` |
| `writing-fragments` | 笔记、采访与原始素材探索  \|  挖掘有价值的写作片段 | A：文档／素材 | `agents/writing-fragments` |
| `writing-plans` | 规格、需求与多步骤开发任务  \|  编写可执行实施计划 | A：文档／素材 | `agents/writing-plans` |
| `writing-shape` | 文章、博客与长篇内容成稿  \|  按段落塑造完整结构 | A：文档／素材 | `agents/writing-shape` |
| `x-mastery-mentor` | X/Twitter内容与账号增长  \|  选题、写作和算法运营方法 | A：文档／素材 | `agents/huashu-nuwa/examples/x-mastery-mentor` |
| `zhang-yiming-perspective` | 产品、组织与全球化决策  \|  张一鸣思维框架与人才判断 | A：文档／素材 | `agents/huashu-nuwa/examples/zhang-yiming-perspective` |
| `zhangxuefeng-perspective` | 教育选择与职业规划  \|  张雪峰决策框架与现实约束分析 | A：文档／素材 | `agents/huashu-nuwa/examples/zhangxuefeng-perspective` |

## C 类逐项线索

| Skill | 证据位置与类型（节选） |
| --- | --- |
| `anysearch` | README.md：PowerShell command（行 118,142,163）；README_zh.md：PowerShell command（行 118,142,163）；requirements.txt：PowerShell command（行 2） |
| `brainstorming` | visual-companion.md：PowerShell command（行 89）；visual-companion.md：Windows executable（行 89）；scripts\server.cjs：Windows executable（行 298） |
| `cangjie-skill` | scripts\cangjie.py：Windows batch or cmd（行 303,305,307） |
| `cinema-dna-21x9x3` | README.md：PowerShell command（行 174,176,178）；SKILL.md：PowerShell command（行 138）；scripts\compose-nine-shot-storyboard.ps1：PowerShell command（行 36） |
| `geo-sleuth` | scripts\baidu_pano.py：Windows batch or cmd（行 245,263,265）；scripts\board.py：Windows batch or cmd（行 865）；scripts\clues.py：Windows batch or cmd（行 577） |
| `img2threejs` | WINDOWS.md：PowerShell command（行 6,10,28）；WINDOWS.md：Windows executable（行 24）；scripts\run-windows.ps1：Windows executable（行 31） |
| `impeccable` | SKILL.md：Windows batch or cmd（行 17）；scripts\impeccable.cmd：Windows executable（行 3,31,37）；scripts\impeccable.cmd：Windows batch or cmd（行 78） |
| `last30days` | SKILL.md：Windows executable（行 460）；scripts\lib\setup_wizard.py：Windows batch or cmd（行 277） |
| `morph-ppt` | SKILL.md：PowerShell command（行 17） |
| `morph-ppt-3d` | SKILL.md：PowerShell command（行 18） |
| `officecli` | build.sh：Windows executable（行 5,67,68）；install.ps1：PowerShell command（行 4,87,155）；install.ps1：Windows executable（行 7,8） |
| `officecli-academic-paper` | SKILL.md：PowerShell command（行 17） |
| `officecli-data-dashboard` | SKILL.md：PowerShell command（行 15） |
| `officecli-docx` | SKILL.md：PowerShell command（行 13） |
| `officecli-financial-model` | SKILL.md：PowerShell command（行 17） |
| `officecli-pitch-deck` | SKILL.md：PowerShell command（行 17） |
| `officecli-pptx` | SKILL.md：PowerShell command（行 13） |
| `officecli-word-form` | SKILL.md：PowerShell command（行 22,24） |
| `officecli-xlsx` | SKILL.md：PowerShell command（行 13） |
| `window-scenery` | README.md：PowerShell command（行 156）；README.zh-CN.md：PowerShell command（行 129,141）；SKILL.md：PowerShell command（行 102） |
