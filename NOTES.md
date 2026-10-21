# 教学笔记

## 用户偏好（2026-10-20 确认）

- 中文讲解，但**术语保留英文原词**（seam、deep module、tracer bullet…），并在术语表里给中文解释。用户明确说术语是过去最大的痛点，不要用中文同义词替换英文术语。
- 每节课要短，20–40 分钟能读完；「详尽」由**课的数量 + 参考卡**承担，不由单节长度承担。
- 偏好可打印的参考材料，方便回看。
- 讲解用完整句子，不要用短语堆砌；表格只用来对照，不用来替代推理。
- 理论是主线，实践是证据：每节课先讲清软件工程里的一个活动或取舍，再用 AI 和技能包在沙盒里验证。不要写成纯操作手册。
- 示例环境统一用 OpenCode；命令要能直接照抄。
- 教学语言 Python；测试从零教起（pytest），不要假设读者知道 fixture、mock。

## 工作方式

- 课程状态全部放在这个目录：`MISSION.md`、`RESOURCES.md`、`lessons/`、`reference/`、`learning-records/`、`assets/`。
- 每节课的结构固定：**一个问题 → 一个概念 → 一个动作 → 一个反馈回路 → 一张参考卡**。
- 每节课最多引入 3 个新术语；术语只有用户能正确使用后才进 `GLOSSARY.md`。
- 课程里的流程细节一律回到 `C:\Users\admin\.agents\skills\` 下的 `SKILL.md` 核对，不凭记忆写。
- 不主动新增仓库文件到 `knowledge-pet`。

## 已定

- 课程骨架：34 节 / 7 模块（见 `reference/course-map.html` v3 与 `CURRICULUM-REVIEW.md`）。
- 沙盒：`D:\code\my_projects\se-course-sandbox`，迷你知识库，先 CLI，后加薄 HTTP adapter。
- 单人开发者版：团队概念保留，活动改写为与 agent / 未来维护者的协作。
- 最后一课：迁移到 `knowledge-pet`，只写迁移计划，不改它的代码。
- 课程材料是否公开发布：暂不发布，先按「自己学 + 沉淀教材」处理。

## 骨架 v3（2026-10-20 二次调整）

- 用户反馈：第二课突然跳到技能包，SE 主线不成立；文字太碎，像 PPT。
- M0 拆为 3 节：第 1 课「为什么学」、第 2 课「软件工程包含什么」、第 3 课「怎么练：AI + 技能包 + 工作台」。
- 新增 10 节：SE 全貌、需求工程、过程模型、计划/估算/度量、架构、设计文档、pytest/测试设计、CI、运维/postmortem、安全/伦理/AI 责任。
- 合并 4 处：技能全景+工作台、领域语言+CONTEXT、纵向切片+阻塞边、双轴审查+读 diff。
- 从 28 节变为 34 节；约 52 小时，8–10 周，每周 3–4 节。
- 导读 6 次（模块 1–6），全部改用 `courseware/` 本地课件。
- 写作风格改为完整段落；技能包从「课程主角」降为「实践工具」。

## 课程开发规范（2026-10-20 三次调整）

- 用户反馈：第 4 课仍然从 Matt 技能开场，没有先讲领域语言属于哪个软件工程活动、业内怎么做；课程之间缺少前后逻辑。
- 新增 `COURSE-STANDARD.md`：从模块 1 起，每节课按五段写：位置 → 问题与概念 → 行业做法 → AI + Matt 怎么落地 → 练习与带走。
- 行业做法必须区分「标准 / 主流 / 取舍」，不要笼统说最佳实践。
- 第 4 课已按规范重写：标题改为「领域语言：需求的前置条件」；加了 Requirements 定位、四活动影响、行业做法表、技能包与 DDD 的差异；参考卡同步。
- 以后每一课先回指第 2 课的八个活动，再讲理论，再讲技能包。

## 第四次调整（2026-10-20）

- 用户反馈：英文术语没有中文；行业做法只有名字，不知道怎么做的；课件里有只有本会话才懂的指代；Matt 部分只解释技能是什么，没写清怎么被调用、开发者做什么。
- `COURSE-STANDARD.md` 新增四条：术语首次出现写 `English（中文）`；行业做法写清「是什么、怎么做、什么时候用、产物、代价」；课件必须自洽；Matt 部分写清技能名、调用类型、开发者动作、产物、怎么判断生效。
- `AGENTS.md` 同步四条硬规则，新会话自动生效。
- 第 4 课：行业做法改成五个「是什么 / 怎么做 / 例子 / 何时用 / 代价」小节；Matt 部分改成 `domain-modeling` 的调用类型 + 开发者四件事；术语补中文。
- 第 3 课：新增「技能是怎么被调用的」表（用户调用 / 模型调用 / 前置配置 / 路由器），并补术语中文。
- 第 1 课：`essential complexity` / `accidental complexity` 改为英文在前、中文在括号里。

## 第五次调整（2026-10-20）

- 用户反馈：第 4 课还在重复技能调用方式；技能包总介绍被拆成三块；没有讲为什么选这套技能包；课件太分块，不够像文章。
- 第 3 课重写为技能包唯一总介绍：为什么选它（完整链路、产物、为 agent 设计、CMU 实践样本）、由什么组成、从一句话到一次提交的走查、用户 / 模型 / 配置 / 路由四种调用方式、局限、后面各模块怎么用它。
- 第 3 课的走查改用「给用户管理加按姓名搜索」这个更直观的例子，并把「组件介绍」和「怎么用」合并成一条叙事线，删掉重复的主线讲解。
- 第 4 课删掉调用方式表，只保留一句回指第 3 课，重点放在 `domain-modeling` 的具体用法。
- `COURSE-STANDARD.md` 新增「文章体」和「介绍工具先讲为什么选它」；技能包总介绍只在第 3 课。
- `AGENTS.md` 同步；课程地图第 3 课标题/产出更新。

## 第六次调整（2026-10-20）

- 用户反馈三点：安装应放在「为什么选它」和「场景走查」之间，并补装技能包本身；开头场景和走查可以融合，五步就能从需求走到审查；最后补一张 Matt 全部技能的表，把与软件工程无关的标出来。
- 先装最新版技能包：全局 `C:\Users\admin\.agents\skills\`，Matt 仓库 38 个技能（engineering 20、productivity 7、misc 4、in-progress 7）；新增 `pr`、`chief-of-staff`；`domain-modeling` 改用 `GLOSSARY.md` / `GLOSSARY-MAP.md`。安装前备份在 `C:\Users\admin\AppData\Local\Temp\opencode\skills-backup-20261020`。
- 第 3 课重排为：熟悉的场景（只留七个问题）→ 为什么选它 → 两层安装（技能包装一次 / 仓库 setup 一次）→ 回到场景走五步 → 它不替你做什么 → 38 技能三层全表 → 模块对应 → 练习 → 带走。
- 安装段区分「装技能包」和「初始化仓库」，给出 `npx skills@latest add mattpocock/skills -a opencode -g -s "*"`、对话式安装、`ls -g` 验证、`update -g` 更新；生成文件只讲用途，理论留到第 4、7、8、13 课。
- 场景和走查做成书挡：开头七个问题，结尾一张表回收「每个问题落在 GLOSSARY / spec / 工单 / 测试 / ADR 的哪里」；五步写成 grill-with-docs → to-spec → to-tickets → implement（内部 TDD + 单张审查）→ code-review（整条分支复审）。
- 38 技能表按「直接对应软件工程活动 / 开发辅助 / 与软件工程无关」分三层，标出 7 个 in-progress 实验项；同时说明本机还有 `shy-*`、`skill-creator` 等非 Matt 技能，不要混进表里。
- 第 4 课与参考卡同步改名：`CONTEXT.md` → `GLOSSARY.md`，`CONTEXT-MAP.md` → `GLOSSARY-MAP.md`，`CONTEXT-FORMAT.md` → `GLOSSARY-FORMAT.md`；参考卡改为 `reference/0004-glossary-card.html`。`MISSION.md`、`RESOURCES.md`、`CURRICULUM-REVIEW.md`、课程地图同步。
- 用户明确：完整表优先于时长；旧内容可以调整，但精简的理由是重复啰嗦，不是省时间。

## 第七次调整（2026-10-20）

- 用户要求：课程要通俗易懂、尽量生动，有逻辑顺序，像文章，而不是 PPT 那样分块解释。
- `COURSE-STANDARD.md` 的「文章体」一节扩写：判断标准是“遮住所有小标题，仍能读出前后因果”；通俗是先场景后术语；生动来自具体的人和代价，不靠空词；逻辑顺序是先问题后概念、先具体后抽象、先主线后分支，段落之间要有过渡；标题是叙事节拍，不是主题清单；表格只做对照，不能替代推理。
- 检查清单新增四条：遮住标题读因果、语言通俗具体、表格前后有叙事引导、段落有过渡。
- `AGENTS.md` 同步一条硬规则，新会话自动生效。
- 第 3 课的 38 技能表是目录型内容，保留表格，但在每层表前补一句过渡，说明“为什么现在看这一层”，避免变成纯目录。

## 第八次调整（2026-10-20）

- 用户要求：修改课件时，不要只修改局部，要基于整篇课程的完整内容进行修改。
- `COURSE-STANDARD.md` 新增「修改课件：基于整篇，不做局部补丁」：先通读本课全文、前后相关课和参考卡；至少检查位置与承接、术语首次出现、贯穿例子、表格与图、练习与反馈、结尾指向下一课；涉及文件名/技能名/流程步骤/术语时全篇搜索旧说法，并同步参考卡、课程地图、术语表、`NEXT-SESSION.md` 和相邻课。
- 检查清单新增两条：修改时通读全文与相邻课；改完后前后课不重复、不矛盾，参考卡和课程地图已同步。
- `AGENTS.md` 同步一条硬规则；`NEXT-SESSION.md` 的写作原则补上「修改时通读全篇」。
- 判断标准：局部修改后如果读起来像补丁，就重写受影响的一节，不继续打补丁。

## 第九次调整（2026-10-20）

- 用户要求：熟悉场景尽量用软件领域的实际场景，不要滥用比喻；不合适就不加，不要硬编。
- `COURSE-STANDARD.md` 的「文章体」新增：场景优先取需求变更、线上故障、代码评审、部署失败、返工、交接等软件领域的实际工作场景（可以是构造的，但要像真的会发生）；比喻只在明显降低理解成本时使用，用后要说明映射什么、哪里不成立，并回到真实动作和产物；找不到合适场景就直接讲问题。
- 检查清单新增两条：场景优先真实软件场景、不硬套比喻；用了比喻要说清映射和边界。
- `AGENTS.md` 与 `NEXT-SESSION.md` 同步。

## 第十次调整（2026-10-21）

- 用户确认文件职责，不删除 `NEXT-SESSION.md` 与 `SOURCE-MAP.md`：前者是项目状态检查点（不依赖 handoff 技能，每课写完重写），后者是「引用依据」索引，与学习者用的课程地图分工不同。
- `AGENTS.md`：会话开始时新增「用 `lessons/` 目录核对进度」的防呆句；新增「文件职责（谁说了算）」一节。
- `SOURCE-MAP.md` 与 `reference/course-map.html` 补相互引用。

## 第 3 课校对（2026-10-21）

- 用户要求：第 3 课基本完成，按课程要求校对——只改语句通顺与重复，不动主题内容。
- 改动 10 处，均为句子级：删「跑一遍……走了一遍」的重复动词；换掉与开头重复的「把软件工程的活动落成……动作」；补字「三件事都有地方查」；「模型调用不等于你不能输入」改顺；`/to-spec` 的「画出准备测试的 seam」改为「标出准备用来测试的 seam」；压缩「模型调用四技能」一段的重复；`domain docs（领域文档）的布局` 补「的」；「主线只给你五个动作」改「主线只有五个命令」等。
- 结构、五步链路、38 技能三层表、练习与参考卡均未动。

## 第十一次调整（2026-10-21）

- 连贯性修复 2 处（用户确认）：① 第 1 课标题以课程地图为准，`<title>` 与 `<h1>` 改为「软件工程在管什么」，参考卡 0001 的回链同步；② 第 2 课「下一课」链接标题改为第 3 课实际标题「为什么用这套技能包，以及怎么用」。
- `NOTES.md` 骨架 v3 与 `CURRICULUM-REVIEW.md` 里的旧课名是历史记录，不改写；被推迟的改动记在 `NEXT-SESSION.md` 的待确认里。

## 第十二次调整（2026-10-21）

- 第 1 课标题反转回「软件工程不是把代码写出来」（用户拍板），`<title>`、`<h1>`、参考卡 0001 回链、课程地图四处同步。
- 理由：标题即本课论点（编程问题 vs 工程问题），符合「标题是叙事节拍，不是主题清单」；与第 2 课「软件工程到底包含什么」的「什么」式问句拉开差距；「在管什么」实为 v2 骨架的设计标签（`CURRICULUM-REVIEW.md` 第九节），写课时标题已进化，地图没跟上。
- `CURRICULUM-REVIEW.md` 里的「软件工程在管什么」是 v2 历史快照，保留不改。

## 第十三次调整（2026-10-21）

- 第 4 课合并重复引用（用户确认）：「位置」一节保留 SWEBOK 五类+页码的完整引用，「行业做法」一节改为一句回指「（「位置」一节引用过）」。
- 顺带补同一句里两个漏掉中文释义的术语：functional / non-functional（功能性 / 非功能性）、prioritization（优先级排序）——此前核查报告漏检这两处，本次一并修正。

## 第十四次调整（2026-10-21）

- 第 2 课打磨（用户确认）：八活动表 7 处裸英文补中文（spec、ADR、design doc、CI/CD、runbook、postmortem，review 记录改「评审记录」）；SWEBOK 首次出现补「（软件工程知识体系）」；主读物与来源块补 SWEBOK 第 1 章页码 p43–66。
- 第 1 课（用户确认）：「三个常见误判」从练习之后移到练习之前（正文内容不应排在练习后）；该节 TDD、vibe coding 补中文；练习第 3 题 hackathon 补「（编程马拉松）」；demo、README 按用户意见不补。
- 规范修订（用户提议，经讨论采纳）：`COURSE-STANDARD.md` 文章体的「不要用连续的项目符号代替段落」改为「真正并列、可扫读的条目可用项目符号，但条目须为完整句子、列表前后须有引导句和收束句、一节不能只有列表」；检查清单与 `AGENTS.md` 对应条目同步。
- 第 1 课误判节按新规则落为「引导句 + 列表 + 收束句」，三条各加小标签：把形式当工程 / 把整洁当标准 / 把工程当流程。
- 撤回两项（复核后不做）：第 2 课八活动表前后的叙事过渡（重看后已有引导与收束，够用）；表格活动名的中英双行形式（对照表的合理用法）。

## 第十五次调整（2026-10-21）

- recap（各课「今天带走的三句话」）位置定案：用户质疑其在练习后；经讨论维持现状。理由：recap 无新内容，跳过练习不损失信息（与误判类正文不同）；规范第五段「练习与带走」字面顺序 Do → Check → Carry 即练后带走；复习场景翻到页尾即得；与主读物、下一课同属收尾块（HTML 中 `div.recap` / `div.source` / `div.next`，非正文 section），四课架构统一。教科书「总结→习题」先例对应章末作业，本课练习是内嵌随堂自测，不适用。
- 第 4 课「三个常见误区」从练习之后移到「反馈回路」与「练习」之间（与第 1 课误判同类：教学正文排在练习后）；补引导句「词条收进词表只是开始……先认清，再去做下面的练习」，与 L1 误判节引导句句式一致；移后与「反馈回路」末句「这一轮只收三个」正好衔接（误区一即「一次写完一本词典」）。

## 第十六次调整（2026-10-21）

- 第 5 课「逼问：把模糊想法问成决定」已完成：`lessons/0005-grilling.html`、`reference/0005-grilling-card.html`。标题定为「把模糊想法问成决定」（非地图旧标题「把模糊问题问成决定」），与 lede「一个想法只有被一句句问清之后才配叫需求」一致；课程地图、第 4 课 next 段、`NEXT-SESSION.md` 四处标题已同步。
- 按五段结构写：位置（Requirements 的 elicitation，第 4 课给词 → 本课问做什么 → 第 6 课写完整）→ 问题与概念（design tree / rounds / frontier，事实归 agent、决策归人）→ 行业做法（访谈 / 观察 / 问卷 / 焦点小组 / 头脑风暴 / 原型，逐一写清，标标准/主流/取舍）→ AI + Matt（`grilling` 是用户调用，开发者三件事，自动化了什么 / 没自动化什么，适用边界）→ 练习与反馈。
- 理论来源：SWEBOK v4 第 1 章 p48–61（elicitation）；SE-EDU《Gathering Requirements》（全章）；CMU 17-313《07-specs》。实践工具 `C:\Users\admin\.agents\skills\grilling\SKILL.md`，只作落地方式。
- 写作沿用前几课定型：术语首次 `English（中文）`（design tree 设计树、frontier 前沿、rounds 轮次）；recap 在练习后；「三个常见误区」在反馈回路与练习之间；每个练习用「看判断」自测、结尾指向下一课。
- 参考卡 `reference/0005-grilling-card.html` 总结设计树/前沿/轮次/铁律/五法/三误区/验证 prompt。
- 课程地图：第 5 课补链接、术语家谱加 `elicitation / design tree / frontier`（第 5 课）；next 段更新为「下一步写第 6 课」。

## 第十七次调整（2026-10-21）

- 第 3 课结构重排（用户提出）：原「场景 → 为什么 → 两层安装 → 回到场景走五步」改为「为什么（呼应第 1、2 课）→ 安装 + 初始化 → 场景与五步合并一节 → 它不替你做什么 → 全景」。依据有三：① lede 本来承诺「先装工作台 → 走五步 → 摊开」的顺序，正文与 lede 脱节；② 场景被割裂在首尾两处，读者要挂着七个问题穿过两节；③ NEXT-SESSION 待确认第一条早记了疑虑「五步是否接得上开头的七个问题」。
- 动手段删「两层」讲解表与防范式开场（「很多人卡住……混成了一件」），只留一句先后与频次；「第一层/第二层」小标题改「先装技能包 / 再初始化仓库」；初始化过渡句按规范文章体自带的示例改写（「技能装好了，但它还不知道你的仓库长什么样」）。
- 开篇新增两段：技能包是什么（38 个 SKILL.md、每份写清何时用/问什么/产出什么/何时停）+ 为什么学软件工程要装它（第 1 课「写的成本降、判断成本升」、第 2 课「八个活动还是名词」→「翻成动词」）；第三条理由中重复的 SKILL.md 定义删去；「这套东西」两处统一为「这套技能包」。
- 合并节内：七问与五步相邻成对比（先直写的病、再五步的药）；七问落点表表头「开头的问题」改「场景里的问题」，表前补引导句「回头看看那七个问题……」；四种调用方式的表保留在五步之前。
- recap 前两条随结构改写（去「两层安装」术语、七问改「场景里」）；「它不替你做什么（含三种走错）」位置不动（内容服务刚学完的五步，全景随后展开）。
- 不动的部分：全景节 38 技能的「三层」（与安装的「两层」是两套概念）、参考卡 0003「工作台：两层安装」（卡片内自含定义，属速查非叙事）、课程地图、第 2/4 课的回指链接、练习与主读物。NEXT-SESSION 待确认第 1 条闭环。

## 第十八次调整（2026-10-21）

- 第 6 课「需求工程：来源、验收标准与非功能需求」已完成：`lessons/0006-requirements.html`、`reference/0006-requirements-card.html`。标题与地图一致（未改名）。
- 按五段结构写：位置（Requirements 的 analysis + specification + validation，第 4 课给词 → 第 5 课问做什么 → 第 6 课写完整 → 第 7 课挑 ADR 原料）→ 问题与概念（决定 vs 需求，SWEBOK 定义 software requirement 是 property that must be exhibited；对付 incompleteness 和 ambiguity）→ 行业做法（functional / non-functional 分类、perfect technology filter、验收标准 Given/When/Then、标准/主流/取舍）→ 非功能需求单独一节（最容易漏、最晚被发现）→ AI + Matt 落地（无独立技能，回指 grilling 产物 + domain-modeling 的 GLOSSARY，数字由人拍板）→ 练习与反馈。
- 理论来源：SWEBOK v4 第 1 章 p43–66（需求定义 p45、functional / non-functional + perfect technology filter p46–47、需求来源 p48、需求品格 p50、BDD 验收标准 p55）；SE-EDU《Specifying Requirements》（conditions of satisfaction、user story 加非功能需求）；CMU 17-313《07-specs》（spec 是契约）。本课无独立技能，实践工具回指 `grilling` / `domain-modeling`，只作落地方式。
- 写作沿用定型：术语首次 `English（中文）`（functional 功能性、non-functional 非功能性、acceptance criteria 验收标准、perfect technology filter 完美技术过滤器）；recap 在练习后；「三个常见误区」在反馈回路与练习之间；每个练习用「看答案」自测、结尾指向下一课。
- 参考卡 `reference/0006-requirements-card.html` 总结决定 vs 需求、完美技术过滤器、需求品格、Given/When/Then 写法、非功能单节、三误区、验证 prompt。
- 课程地图：第 6 课补链接、术语家谱复用既有「需求 / 验收标准 / 非功能需求」（第 6 课）行；next 段更新为「下一步写第 7 课」；第 5 课 next 段标题已同步。

## 第十九次调整（2026-10-21）

- 第 7 课「ADR：什么决定值得记下来」已完成：`lessons/0007-adr.html`、`reference/0007-adr-card.html`。标题与地图一致（未改名）。
- 按五段结构写：位置（Requirements 的 management——第 6 课做 elicitation+analysis+specification+validation，第 7 课做 management：需求会变，所以「为什么这么定」要留得住）→ 问题与概念（SWEBOK change control 立据 p57–62；ADR 记的是决定与 why 不是 what；三判据：难回滚 / 无上下文很怪异 / 有真实取舍）→ 行业做法（Nygard 2011，ADR 无统一标准是主流做法，Context / Decision / Consequences / Status）→ 被否掉的方案单独一节（贯穿例子「总结产物存不存、怎么进索引」，两个被否方案都带理由）→ AI + Matt 落地（`domain-modeling` 的 `ADR-FORMAT.md`：三判据与课文一字不差、极简模板、`docs/adr/` 目录约定、懒创建；模型调用；三条由人拍板）→ 练习与反馈。
- 理论来源：SWEBOK v4 第 1 章 p43–66（management / change control p57–62、stability / volatility、tracing footprint p60）；Michael Nygard《Documenting Architecture Decisions》（2011，线上无本地全文）。实践工具 `C:\Users\admin\.agents\skills\domain-modeling\ADR-FORMAT.md` 只作落地方式。
- 写作沿用定型：术语首次 `English（中文）`（ADR 首次给全称「架构决策记录」、rejected alternatives 被否掉的方案、Context/Decision/Consequences/Status）；recap 在练习后；「三个常见误区」在反馈回路与练习之间；每个练习用「看答案」自测、结尾指向下一课（第 8 课 to-spec）。
- 参考卡 `reference/0007-adr-card.html` 总结三判据、ADR 四字段、被否方案范例、domain-modeling 落地、三误区、验证 prompt。
- 课程地图：第 7 课补链接、术语家谱加「ADR（架构决策记录）→ Nygard 2011 + domain-modeling，第 7 课」；next 段更新为「下一步写第 8 课」；第 6 课 next 段标题已同步。

## 调研记录（2026-10-20）

- 第一版 `RESOURCES.md` 里的书单来自记忆，不算调研；用户指出后已补齐。
- 本机没有可用的网页搜索（`websearch` 全部报错），只能对已知来源逐个抓取验证。
- 已验证可访问：MIT 6.005（OCW）、CMU 17-313（2026 秋，含 OpenCode 项目）、Missing Semester 2026（含中文版）、Software Engineering at Google（全文）、Google Code Review 指南、Valente《Software Engineering: A Modern Approach》（全文网页版）、Software Design by Example（sdxpy）、Refactoring.Guru（含中文）、AOSA、CMU 17-445（ML in Production）。
- 后经代理补齐：SWEBOK v4 PDF、Berkeley CS 169 目录页、CMU 17-313、MIT 6.031、SaaS 主页、Google SRE 等已下载到 `courseware/`；Rutgers（Marsic）教材仍 404。清单见 `courseware/README.md`。
- 课程主读物策略：每个模块指定一份主读物，其余为选读；单节课只推一条，避免把「详尽」变成「书单轰炸」。
- 许可注意：Valente 仅限个人使用、禁止再分发；SE at Google 是 CC BY-NC-ND；MIT OCW 是 CC BY-NC-SA。课程只链接与转述，不复制原文。
- 第 1 课与三问卡已完成：`lessons/0001-what-is-software-engineering.html`、`reference/0001-three-questions.html`；六个模块导读已排进课程地图 v3。
- 第 2 课（SE 全貌）与第 3 课（AI 实践 + 工作台）已完成：`lessons/0002-what-software-engineering-covers.html`、`lessons/0003-ai-practice-and-workbench.html`；参考卡 `reference/0002-se-landscape.html`、`reference/0003-skill-map.html`。
- 第 4 课（领域语言）已完成：`lessons/0004-domain-language-and-context.html`、`reference/0004-glossary-card.html`。三个新术语：ubiquitous language、glossary / `GLOSSARY.md`、Avoid list。主来源：Evans 第 2 章、Fowler 的 bliki、本机 `domain-modeling/SKILL.md` + `GLOSSARY-FORMAT.md`。下一步第 5 课「逼问」。`GLOSSARY.md` 在 2026-10 之前叫 `CONTEXT.md`，旧版安装仍用旧名。
- 沙盒核验（2026-10-20，写第 4 课时）：`D:\code\my_projects\se-course-sandbox` 存在 `AGENTS.md`、`docs/agents/domain.md`、`docs/agents/issue-tracker.md`，**缺** `docs/agents/triage-labels.md`（标签本身写进了 `issue-tracker.md`）。第 13 课（triage）之前要么补文件，要么改第 3 课的产物清单。尚无 `GLOSSARY.md`、`docs/adr/`、`.scratch/`，符合懒创建。注意：`docs/agents/domain.md` 还是旧版 `CONTEXT.md` 写法；装完最新版后，重跑 `/setup-matt-pocock-skills` 或手动同步为 `GLOSSARY.md`。

## 环境与网络（2026-10-20 核查）

- 当前 OpenCode 桌面版 2.0.32，PID 20000，启动于 08:34:14，父进程是 `explorer.exe`（PID 8104），**不是** `wscript.exe`。开始菜单快捷方式 `OpenCode.lnk` 直接指向 `C:\Users\admin\AppData\Local\Programs\@opencode-aidesktop\OpenCode.exe`，无参数。结论：当前实例不是用 `D:\programs\launch-opencode.vbs` 启动的。
- VBS 本身是对的：设置 `HTTP_PROXY` / `HTTPS_PROXY` = `http://127.0.0.1:7890`，`NO_PROXY` = `127.0.0.1,localhost,::1`，再启动 exe。
- 当前 shell 环境只有 `NO_PROXY`，没有 `HTTP_PROXY` / `HTTPS_PROXY`。Clash for Windows 0.19.21 在跑（`clash-win64.exe` PID 17436），7890 端口可连。
- `curl` 实测 Berkeley CS 169：不走代理 25 秒超时（code 000），走 `127.0.0.1:7890` 返回 200（1.88 秒）。代理可用，但 `webfetch` 没走代理。
- 因此 `webfetch` 的部分超时是直连造成的。修法：用 VBS 启动，或设置用户级 `HTTP_PROXY` / `HTTPS_PROXY` 后重启 OpenCode。重启后应先在 shell 里确认 `$env:HTTP_PROXY` 有值，再测 `webfetch`。
- Berkeley CS 169 的正确地址：`https://www2.eecs.berkeley.edu/Courses/CS169/`（课程目录；讲义在当学期的 inst.eecs 主页）。
- 已修改启动方式（2026-10-20）：开始菜单 `OpenCode.lnk` 现在指向 `C:\Windows\System32\wscript.exe`，参数 `"D:\programs\launch-opencode.vbs"`；原快捷方式备份为 `OpenCode.lnk.bak-20261020`。另在桌面新建 `OpenCode (Proxy).lnk`，指向同一个 VBS，避免升级覆盖开始菜单快捷方式后失去代理。需完全退出并重启 OpenCode 后生效。
- 2026-10-20 10:31 最终状态：结束后台 CLI 并重启后，新 CLI PID 23480 继承了 `HTTP_PROXY` / `HTTPS_PROXY`（`http://127.0.0.1:7890`）。`webfetch` 已实测可访问 MIT 6.031、Berkeley CS 169、SaaS Book、Google SRE。SWEBOK 根域仍不通，但 v4 PDF 已从 IEEE CS 下载。快捷方式与桌面 `OpenCode (Proxy)` 保持现状。
- 离线课件已下载到 `courseware/`（约 59 MB），清单见 `courseware/README.md`。下载时用 `curl -x http://127.0.0.1:7890`，因为当时 `webfetch` 仍走直连；现在已不需要这个临时办法。

> AI生成
