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

## 第二十次调整（2026-10-22）

- 第 8 课「Spec：从共识到可执行」已完成：`lessons/0008-spec.html`、`reference/0008-spec-card.html`。标题与地图一致（未改名）。
- 按五段结构写：位置（Requirements 的 specification 收口——第 4 词表 → 第 5 逼问 → 第 6 需求 → 第 7 ADR → 第 8 合写成 spec；下一课进模块 2 过程）→ 问题与概念（散落的共识 vs 一份 spec：可执行、可评审、不是又一份需求文档；CMU 07-specs「spec 是客户和工程师达成一致的基础」p5；SWEBOK「specification 是最有争议的一块、面向受众」p50）→ 行业做法（六节结构 Problem/Solution/User Stories/Implementation Decisions/Testing Decisions/Out of Scope，逐节回答什么问题；为什么 Out of Scope 防返工）→ AI + Matt 落地（`to-spec` 用户调用、`disable-model-invocation`；探索仓库用 GLOSSARY + 尊重 ADR、画 seam 先给草图确认、写模板发布 tracker 打 `ready-for-agent`；不访谈用户；人拍板三件事）→ 练习与反馈（沙盒把总结功能的词表/需求/ADR 合成 spec 落 `.scratch/<feature>/spec.md`，用「能不能开工」检查单验）。
- 理论来源：SWEBOK v4 第 1 章 p43–66（requirements specification p50、结构化自然语言 / user story p1-12、ISO/IEC/IEEE 29148 模板）；CMU 17-313《07-specs》p5（spec 是契约与估算基础，回指第 6 课已用）；SE-EDU《Specifying Requirements》（回指第 6 课）。实践工具 `to-spec` 只作落地方式。
- 写作沿用定型：术语首次 `English（中文）`（spec 规格说明、seam 接缝——首次出现给中文并注明第 15 课正式展开）；recap 在练习后；练习用「能不能开工」检查单反馈；结尾指向第 9 课。
- seam 首次出现在第 8 课（to-spec 的动作），故课程地图术语家谱 seam 行由「15」改为「8, 15」，出处补 Matt Pocock `to-spec`。
- 参考卡 `reference/0008-spec-card.html` 总结 spec 定义、六节结构、Out of Scope 理由、to-spec 三件拍板事、验收 prompt、三坑。
- 课程地图：第 8 课补链接；next 段更新为「下一步写第 9 课」；第 7 课 next 段原本就指第 8 课、标题一致，无需改。
- 第 9 课大纲已在 `NEXT-SESSION.md` 备好（过程模型），只差写正文。

## 第二十一次调整（2026-10-22）

- 第 9 课「过程模型：瀑布、迭代、敏捷，以及这套流程的位置」已完成：`lessons/0009-process-models.html`、`reference/0009-process-card.html`。标题与地图一致（未改名）。
- 按五段结构写：位置（Process & Management，模块 2 导读式首课——第 8 课 spec 就绪后回答「用什么过程把它排出来」，给第 10 课 to-tickets、第 11 课估算定位）→ 问题与概念（过程模型在回答「怎么把工作排开」，本质是「需求何时敢提前写死」；SWEBOK 用 predictive → adaptive 连续谱）→ 行业做法（瀑布式=顺序式、迭代式=广度/深度优先、敏捷=Scrum/XP，各自是什么/怎么做/何时用/代价，标标准/主流/取舍）→ AI + Matt 落地（本课无独立技能，把第 3 课五步链路当作一整套过程，在谱上定位：偏预测式的「先 spec」+ 偏自适应式的「小步可验收」，因为是单人+agent 的中间路）→ 练习与反馈（就沙盒总结功能造项目画像、选过程、写理由、标谱系位置、做「明天要演示」反例，用检查单验）。
- 理论来源：SWEBOK v4 第 10 章 p10-2（「没有任何理想过程存在，只能挑选和适配」）+ 第 9 章 p9-8~9-9（过程计划、SDLC 从 predictive 到 adaptive 的连续谱、瀑布/增量/螺旋/敏捷）；SE-EDU《Process Models》（全章）；延伸 CMU 17-313《03-project-planning》。实践工具：本课无独立技能，回指第 3 课五步链路。
- 写作沿用定型：术语首次 `English（中文）`（process model 过程模型、predictive 预测式、adaptive 自适应式、waterfall 瀑布式、sequential 顺序式、iterative 迭代式、agile 敏捷、Sprint 冲刺、product backlog 产品待办）；recap 在练习后；练习用「选型站得住吗」检查单反馈；结尾指向第 10 课。
- 参考卡 `reference/0009-process-card.html` 总结谱系、三种过程取舍、四选型变量、本课流程定位、三坑、验证 prompt。
- 课程地图：第 9 课补链接、术语家谱加「过程模型 / 预测式 / 自适应式」（第 9 课）；next 段更新为「下一步写第 10 课」；第 8 课 next 段标题已同步（原本就指第 9 课、标题一致）。
- 第 10 课大纲已在 `NEXT-SESSION.md` 备好（to-tickets 拆工单、tracer bullet + 阻塞边），只差写正文。

## 第二十二次调整（2026-10-22）

- 第 10 课「纵向切片与阻塞边：先做哪个」已完成：`lessons/0010-vertical-slice.html`、`reference/0010-tickets-card.html`。标题与地图一致（未改名）。
- 按五段结构写：位置（Process & Management，模块 2 第二站——第 9 课定了过程取向 → 本课把 spec 拆成带阻塞边的工单 → 第 11 课估算）→ 问题与概念（横向切片让每张都不能跑、风险堆到最后；vertical slice 穿透 schema/API/UI/测试、可独立验收；tracer bullet / walking skeleton 两经典；blocking edge 取 frontier）→ 行业做法（SE-EDU WBS 工作分解结构拆小+可验收+前置任务、Milestones 里程碑按依赖与优先级交付；tracer vs walking skeleton 侧重不同；wide refactor 用 expand-contract 而非硬塞纵向切片；无统一标准，标尺是「完成时有没有一件能跑能演示能验收的东西」）→ AI + Matt（`to-tickets` 用户调用、前置是 setup；流程为读 spec → 探索库用 GLOSSARY + 尊重 ADR + 找 prefactor → 起草 vertical-slice-rules（穿透所有层、可独立演示、塞进一个上下文窗口）→ 四个确认问题 → 按阻塞顺序发布 tracker；自动化拆解/验收/阻塞边/排序/发布；人拍板四件：粒度、阻塞边真实否、合并拆分、wide refactor 是否 expand-contract）→ 练习与反馈（沙盒总结功能：to-tickets 拆 `.scratch/<feature>/issues/NN-slug.md`，用「工单拆得对吗」检查单验「先做哪张」）。
- 理论来源：SE-EDU《Project Planning》WBS / Milestones 两节；SWEBOK v4 第 9 章（回指第 9 课 ch.9 p9-8~9-9）。实践工具 `to-tickets`（用户调用）只作落地方式。行业经典 Hunt & Thomas《The Pragmatic Programmer》(1999) tracer bullet、Freeman & Pryce《GOOS》(2009) walking skeleton。
- 写作沿用定型：术语首次 `English（中文）`（vertical slice 纵向切片、horizontal slice 横向切片、blocking edge 阻塞边、tracer bullet 追踪弹、walking skeleton 行走骨架、WBS 工作分解结构、milestone 里程碑、wide refactor 宽重构、expand-contract 先扩后缩）；recap 在练习后；练习用「工单拆得对吗」检查单反馈；结尾指向第 11 课。
- frontier 一词在第 5 课已用（grilling 的设计树前沿），本课明确写出两义区分：第 5 课是「还没问清的决定」，本课是「所有前置已完成的工单集」，不混。
- 参考卡 `reference/0010-tickets-card.html` 总结横向 vs 纵向、两经典、阻塞边与 frontier、行业做法、wide refactor、to-tickets 落地与四拍板、三坑、验证 prompt。
- 课程地图：第 10 课补链接（术语家谱 tracer bullet / walking skeleton 两行已预置第 10 课，无需改）；next 段更新为「下一步写第 11 课」；第 9 课 next 段原本就指第 10 课、标题一致无需改。
- 第 11 课大纲已在 `NEXT-SESSION.md` 备好（估算与度量：为什么工时估计总不准、区间 + 假设、不骗人的度量），只差写正文。

## 第二十三次调整（2026-10-22）

- 第 11 课「计划、估算与度量：为什么工时估算总是不准」已完成：`lessons/0011-estimation.html`、`reference/0011-estimation-card.html`。标题与地图一致（未改名）。
- 按五段结构写：位置（Process & Management，模块 2 第三站——第 9 课定过程取向 → 第 10 课拆出带阻塞边的工单 → 本课给工单估时并配度量 → 第 12 课处理拆不出工单的模糊大项目；SWEBOK ch.9 p9-9 估算迭代协商；第 9 课谱系决定估算粒度，预测式排任务起止、自适应式总体估算）→ 问题与概念（tracer bullet 估「半天」的场景；SE-EDU「估算出了名地难」；CMU xkcd 与 Hofstadter's Law；偏乐观三股力：顺利路径、anchoring 锚定、conformity bias 顺从偏差；核心概念＝估算不是数，是「区间 + 假设 + 依据」三段，SWEBOK ch.15 p15-7「用区间」；假设是塌方警报）→ 行业做法（能估的地基：WBS well-defined + 人日两列、拆解是为了好估、decomposition 分解估算；类比估算类比与分解两估法；Buffers 显式优于灌水 hidden buffer、理由是留下「估错了」的证据；PERT 箭头＝第 10 课 blocking edge、critical path＝最长阻塞链、buffer 砸关键路径；度量：定义与动机、杀「完成 90%」假度量、诚实进度与燃尽图、GQM 与 P/I/O/V、可抄的 actual/estimate 台账、Goodhart 红线与 McNamara fallacy；争议一节 Is Estimation Evil / Ron Jeffries 与本课立场经验判断）→ AI + Matt（无独立技能是分工：agent 无项目史、to-tickets 也不估工时但造好可估单元；agent 三件事：列假设、记台账、看趋势；独立一票为经验判断；人拍板三件：区间宽窄、buffer 大小、何时把区间交出去）→ 练习与反馈（沙盒 tracer bullet 写三段式 + 里程碑显式 buffer + 回填台账，用「写得像话吗」检查单验；新增 agent 陷阱：直接吐单点数）。
- 理论来源：SWEBOK v4 ch.9 p9-9、p9-15~9-17；ch.15 p15-7、p15-15；SE-EDU《Project Planning》WBS / Buffers / PERT charts；CMU 17-313《06-Metrics》（Time estimation / GQM 等）。实践：无独立技能，回指第 10 课工单当估算输入。
- 写作沿用定型：术语首次 `English（中文）`（man day 人日、well-defined、anchoring、conformity bias、Hofstadter's Law、buffer、decomposition、estimation by analogy、PERT、critical path、Gantt chart、burndown chart 燃尽图、GQM、Goodhart's Law、McNamara fallacy、wisdom of the crowd、#NoEstimates）；recap 在练习后；结尾指向第 12 课。
- 参考卡 `reference/0011-estimation-card.html` 总结三股力、三段式与 buffer 规则、两估法、PERT 与关键路径、不骗人的度量（含 GQM 模板与 Goodhart 红线）、AI 分工、三坑、验证 prompt。
- 课程地图：第 11 课补链接；术语家谱加「估算区间 / buffer / GQM / Goodhart's Law」（第 11 课）；next 段更新为「下一步写第 12 课」；第 10 课 next 段原本就指第 11 课、标题一致无需改。
- 第 12 课大纲已在 `NEXT-SESSION.md` 备好（wayfinder：决策地图、fog of war、何时不该用；练习已定：用户拍板不要实操对象，纸面练习 + 课文内构造贯穿例子，不真实创建项目 / issue），只差写正文。
- 本次同时修复了一处编辑事故：第二十二次调整首两条目曾被误拼为一行，已恢复换行。

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

## 第二十四次调整（2026-10-22）

- 第 12 课「模糊的大项目：wayfinder 与决策单」已完成：`lessons/0012-wayfinder.html`、`reference/0012-wayfinder-card.html`。标题与地图一致（未改名）。
- 按五段结构写：位置（Process & Management，模块 2 第四站/倒数第二站——第 10 课拆工单、第 11 课估时都假定「能开工」，本课处理「大到、模糊到连工单都拆不出来」的项目，把雾变成决策地图；第 13 课 triage 处理「别人递进来的外部问题」）→ 问题与概念（fog of war 战争迷雾：判据「现在能不能把问题说尖」不是「能不能回答」；决策地图=tracker 上打 `wayfinder:map` 的单一 issue、是 index 不是 store；destination 目的地；Plan, don't do 只产决定不产交付物；out of scope 被目的地排除、永不毕业）→ 行业做法（SWEBOK ch.9 p9-9 自适应式「需求不稳不宜一次排满」；SE-EDU Milestones「高层计划+近几个里程碑详设」；探索类主流两条路 roadmap+阶段化 vs spike/prototype，标主流/取舍）→ AI + Matt（`wayfinder` 用户调用、`disable-model-invocation`；建图五步+走图流程；四种 ticket 类型 research AFK / prototype HITL / grilling HITL 默认 / task 为决策扫障；人拍板三件：目的地、某张是不是雾、何时不用 wayfinder）→ 练习（纸面走查，参照第 9 课对照表模式）。
- 贯穿例子：课文内构造的「把迷你知识库升级为多来源知识库（网页/PDF/笔记混杂）」，与第 5–10 课「总结功能」同性质，不真实建项目、不真实建 issue（用户 2026-10-22 拍板，写课前提问已闭环）。
- 概念衔接：frontier 第三次出现（第 5 课 grilling 设计树前沿 / 第 10 课可开工工单集 / 第 12 课地图上未阻塞未认领的决策），三义不混；grilling 在 ticket 类型里复用（回指第 5 课）；「何时不该用 wayfinder」独立小节（无雾则停）。
- 参考卡 `reference/0012-wayfinder-card.html` 总结雾/判据、地图结构与 index 非 store、Plan don't do、四类型、frontier 三义、两种调用、判据表、三坑、验证 prompt。
- 课程地图：第 12 课补链接、术语家谱加「fog of war / 决策地图 / Plan don't do / HITL」（第 12 课）；next 段更新为「下一步写第 13 课」；第 11 课 next 段原本就指第 12 课、标题一致无需改。
- 第 13 课大纲已在 `NEXT-SESSION.md` 备好（triage 外部输入、沙盒缺 `triage-labels.md` 的待确认仍保留），只差写正文。

## 第二十五次调整（2026-10-26）

- 第 13 课「外部输入：triage 与 agent-ready」已完成：`lessons/0013-triage.html`、`reference/0013-triage-card.html`。标题与地图一致（未改名）。模块 2 至此五课写满：第 9 过程 → 第 10 拆单 → 第 11 估算 → 第 12 模糊大项目 → 第 13 外部输入。
- 按五段结构写：位置（Process & Management 收尾站——前四站处理「自己的工作」，本课处理「别人递进来的输入」；与第 12 课 wayfinder 同属「先理清再动手」的两头；接第 8 课 spec 家族：spec → ticket → brief 都是契约）→ 问题与概念（复合原始输入场景：混两件事 + 复现信息不足 + 情绪当优先级；triage 分诊＝先分类定级再深入；两套角色 category bug/enhancement + state 五态，「恰好一个」与流转规则；agent brief＝契约不是描述）→ 行业做法（明说 issue triage 无统一标准；SWEBOK ch.1 validation p43–66 与 change control p57–62 立「受控入口」据；主流一 GitHub/GitLab 标签状态流及其代价「状态腐烂」；主流二 SRE triage 谱系《Being On-Call》triage+escalate、《Effective Troubleshooting》Triage 一节「先止血留证据」与 Triage/Examine/Diagnose 易败；取舍：验证先行、拒了留档 institutional memory + dedup、wontfix 三种理由分开）→ AI + Matt（`triage` 用户调用、`disable-model-invocation`；前置三份配置 issue-tracker / triage-labels / domain；五步流程 gather context（redundancy + prior rejection）→ recommend 等点头 → verify the claim（三态，insufficient detail 是强 needs-info 信号）→ grill if needed（grilling + domain-modeling）→ apply outcome（五种产物表）；AGENT-BRIEF.md 四原则（耐久/行为/验收标准/范围边界）+ AI 声明硬纪律；人拍板三件：状态归属、拒不拒、验收标准够不够硬；差异说明：verify 与 brief 契约化是为 AFK agent 补的）→ 练习（沙盒实操：复合输入拆两条 issue，bug 条筛到 needs-info 出 triage notes、enhancement 条筛到 ready-for-agent 出 brief，补 AI 声明，顺带走一次 wontfix 写 `.out-of-scope/desktop-gui.md`）。
- 贯穿例子：课内构造「试用同事提的复合 issue（贴 URL 入库 + 引用行号对不上 + 急）」，接第 12 课「多来源知识库」的雾——外部输入正好撞上同一批未定问题。
- 理论来源：SWEBOK v4 第 1 章 p43–66（validation）、p57–62（change control，第 7 课已引、本课换角度）；Google SRE《Being On-Call》《Effective Troubleshooting》Triage 一节（本地已核实原文）；CMU 17-313《07-specs》p5（spec 是契约，回指第 6、8 课）。实践：`triage/SKILL.md` + `AGENT-BRIEF.md` + `OUT-OF-SCOPE.md`，只作实践方式。
- 写作沿用定型：术语首次 `English（中文）`（triage 分诊、category role 类别角色、state role 状态角色、escalate 升级、agent brief 智能体任务简报、verify the claim 验证声明、redundancy check 冗余检查、prior rejection 既往拒绝、institutional memory 机构记忆、dedup 去重、change control 变更控制、durable 耐久、disclaimer 声明）；recap 在练习后；练习用「够开工吗」检查单反馈；结尾指向第 14 课（模块 3 开篇）。
- 参考卡 `reference/0013-triage-card.html` 总结位置、两套角色与状态产物表、五步流程、brief 四原则、wontfix 三理由、AI 分工、三坑、验证 prompt。
- 课程地图：第 13 课补链接；术语家谱加「triage / agent brief / institutional memory」（第 13 课）；next 段更新为「下一步写第 14 课」；第 12 课 next 段原本就指第 13 课、标题一致无需改。
- 沙盒按用户指示补齐（2026-10-26）：新建 `docs/agents/triage-labels.md`（setup 模板 + 「本地用 Status: 行记录」一句），`docs/agents/domain.md` 从旧版 `CONTEXT.md` 写法同步为 `GLOSSARY.md` / `GLOSSARY-MAP.md` 新版，`AGENTS.md` 的 `## Agent skills` 块补 `### Triage labels` 子块，`docs/agents/issue-tracker.md` 的状态行改为引用 `triage-labels.md`（与模板一致）。第 3 课产物清单本来就把 `triage-labels.md` 列为「装了 triage 就生成」，无需改课件。沙盒仍无代码（仓库无提交），`GLOSSARY.md`、`docs/adr/`、`.scratch/`、`.out-of-scope/` 继续懒创建。
- 新发现（2026-10-26）：沙盒仓库目前只有 `AGENTS.md` 与 `docs/`，无任何代码、无 git 提交；模块 3（第 14 课起）需要代码对象，届时先立迷你知识库 CLI 最小骨架。
- 第 14 课大纲已在 `NEXT-SESSION.md` 备好（深模块、信息隐藏与不变量），只差写正文。

## 第二十六次调整（2026-10-26）

- 写第 14 课前按交接文档问用户「现在立骨架还是先纸面」，用户拍板**先立最小骨架**。沙盒 `D:\code\my_projects\se-course-sandbox` 新增 `kb/` 包：`python -m kb add "标题" "正文"` / `python -m kb search "关键词"` 两个命令（`cli.py` + `__main__.py`），存储模块 `KnowledgeStore`（`storage.py`，JSONL 文件 `kb.jsonl`，`add` / `search` 两方法），另有 `README.md`、`.gitignore`（忽略 `__pycache__/` 与 `kb.jsonl`；`.scratch/` 是练习产物不忽略）。根提交 `b2162ce`（仓库此前无提交），`__pycache__` 误入后已 amend 修掉。刻意无测试、无 CI，不抢模块 4 的活。骨架带「第一版」味道：`add()`/`search()` 返回内部 dict（rep exposure）、接口无契约文档——留给第 14 课练习当对照物。
- 第 14 课「深模块、信息隐藏与不变量」已完成：`lessons/0014-deep-modules.html`、`reference/0014-deep-modules-card.html`。标题与地图一致（未改名）。模块 3 开篇：从「怎么想」（M0–M2：需求/过程/计划）转入「怎么造」。
- 按五段结构写：位置（Design & Architecture 第一站——模块形状；第 15 接缝、16 设计两次、17 架构、18 设计文档；给第 15 课留接口草图当原料）→ 问题与概念（反面教材：JSONL 读写散在每个命令里；module = interface + implementation，interface 是「调用者必须知道的一切」；deep module 判据是 leverage，Ousterhout ch.21 p172；通用 vs 特化的编辑器例子 ch.6 p41–43；information hiding 按「什么会变」拆模块，Parnas 1972 + MIT 6.031 定义；obscurity 反警告 ch.6 p44；invariant「任何时刻都为真」、ADT invariants replace preconditions、rep invariant / AF、representation exposure）→ 行业做法（明说无统一标准；主流四条：接口草图先行（CMU 08-design-docs）、deletion test、不变量单点强制、接口即测试面；取舍一条：general-purpose vs special-purpose，somewhat 是原词）→ AI + Matt（`codebase-design` 模型调用；三件工具：深浅三问 / 删除测试 / 接口即测试面 + 可测三形状；人拍板三件：什么算秘密、不变量选哪条、深到什么程度；差异明说：技能拒绝行数比度量深度、改用 depth-as-leverage，与书的判据重心不同标注「经验判断」；分工：domain-modeling 管词、codebase-design 管形状，先词后形）→ 三个常见误区（接口＝签名 / 藏太多＝obscurity / 不变量＝愿望）→ 练习（给 `kb/storage.py` 画接口草图 + 写一条不变量 + pytest 断言草图，断言伸手进 `store.entries` 就标「接口缺口」，顺手把不变量写进 rep 旁 docstring）→ 反馈回路（「这张草图够开工吗」检查单，意见分「草图漏了必须知道的事」vs「不变量守不住＝接口形状问题」两类）。
- 理论来源：MIT 6.031 Reading 10（“What abstraction means” 信息隐藏定义与 Parnas 出处、“Representation independence”）与 Reading 11（“Invariants”、RI : R → boolean / AF : R → A 写在 rep 旁、“ADT invariants replace preconditions”、representation exposure）；SWEBOK v4 第 3 章 p86（PDF 第 86 页＝printed 3-4：modularization、encapsulation = information hiding、separation of interface and implementation；章范围 p83–98）；Ousterhout 摘录 ch.6 p39–44、ch.21 p172；Parnas 1972 经 SWEBOK ch.3 文献 [32] 与 MIT 6.031 转引（本地无全文，照第 7 课 Nygard 办法标注）。实践：`codebase-design/SKILL.md`（含 DEEPENING.md、DESIGN-IT-TWICE.md），只作实践方式。
- **来源核实记录**：`courseware/ousterhout/aposd2ndEdExtract.pdf` 是 20 页扫描件（无文本层，用 pymupdf 渲染页图读页脚核实）：ch.6「General-Purpose Modules are Deeper」＝书内 p39–49（PDF 3–13），§6.1 p40、§6.2 编辑器例子 p41–43、p44 obscurity 警告、§6.6 p45；两段 Clean Code 对比 p76、p99–100；ch.21「Decide What Matters」p171–174（leverage 定义在 p172）。**ch.4「Modules Should Be Deep」不在摘录里**——以后别引它当本地来源。
- 写作沿用定型：术语首次 `English（中文）`（deep module 深模块、shallow module 浅模块、module 模块、interface 接口、implementation 实现、depth 深度、information hiding 信息隐藏、invariant 不变量、rep invariant 表示不变量、abstraction function 抽象函数、representation independence 表示独立、representation exposure 表示暴露、precondition 前置条件、leverage 杠杆、locality 局部性、deletion test 删除测试、interface sketch 接口草图、general-purpose 通用、special-purpose 特化、obscurity 晦涩、pass-through 转发层、abstract data type 抽象数据类型）；正文小节在练习前、recap 在练习后；练习用「够开工吗」检查单反馈；结尾指向第 15 课。
- 参考卡 `reference/0014-deep-modules-card.html` 总结三概念三面、信息隐藏的藏与露、不变量写法表、五个行业做法、codebase-design 落地与理论差异、三坑、验证 prompt。
- 课程地图：第 14 课补链接；术语家谱加「不变量 / rep invariant / abstraction function」（MIT 6.031 R11，第 14 课）与「leverage 杠杆 / 接口草图」（Ousterhout ch.21 + codebase-design，第 14 课）两行（原「深模块」「信息隐藏」两行已预置）；next 段更新为「下一步写第 15 课」，沙盒状态行改为「代码骨架已立」；第 13 课 next 段原本就指第 14 课、标题一致无需改。
- 第 15 课大纲已在 `NEXT-SESSION.md` 备好（接缝与适配器：port + 两个 adapter，拿第 14 课接口草图和「接口缺口」当原料），只差写正文。

## 第二十七次调整（2026-10-26）

- 第 15 课「接缝与适配器：测试的地基」已完成：`lessons/0015-seams-adapters.html`、`reference/0015-seams-adapters-card.html`。标题与地图一致（未改名）。模块 3 第二站：从「接口长什么样」（第 14 课）到「接口放在哪、谁来实现」。
- 按五段结构写：位置（Design & Architecture 第二站——第 14 课定模块形状，本课定落点与可替换性；给第 19–22 课测试技术备地基；回指第 8 课 to-spec 的 seam 工作定义并修正「接缝为替换而生，测试只是第一个客户」）→ 问题与概念（场景：写第一个测试就撞上文件——跑两次就红、测试长出「文件摆位」仪式、想测坏行得手工造文件；根因＝行为与载体焊死，SWEBOK 要求的「使用与构造细节隔离」没发生；seam Feathers 定义＋enabling point；port＝缝上的接口（接口草图升级）、adapter＝缝上的具体物（角色非体量）；Protocol vs ABC 取舍；「一个 adapter＝假想缝、两个＝真缝」，测试用 in-memory 是合法第二个；顺手堵第 14 课缺口「返回条目副本」；replace, don't layer，MIT stub 论证打底）→ 行业做法（明说无统一标准；主流三条：ports & adapters / 六边形（Cockburn 2005）、依赖注入（收依赖不造依赖）、替身走缝＋contract test 防 fake 漂移；取舍两条：旧测试删不删（替换 vs 迁移期共存＋删除截止条件）、什么时候不开缝（先写实现后抽 vs 先抽接口））→ AI + Matt（`codebase-design` 模型调用，用 `DEEPENING.md` 的缝纪律：四类依赖表（in-process / local-substitutable / remote but owned / true external）＋「分类是启发式，会不会真的变才是判据」＋内部缝不提到 port＋replace don't layer；人拍板三件：缝开在哪层、port 契约认不认、第二个 adapter 真不真；差异明说「两个 adapter 才是真缝」是技能纪律不是行业标准）→ 三个常见误区（seam＝测试文件放哪 / 一个 adapter 也抽 port（含反向误用警告）/ fake 比真物聪明）→ 练习（沙盒实操：定 port → 迁 `JsonlStore` → 写 `InMemoryStore`（禁文件逻辑、照契约抄不许多做）→ 走缝验证（同一断言跑两遍）→ 单点装配；提示：两 adapter 的 id 规则对不上＝id 规则其实是契约，被两个实现逼现形）→ 反馈回路（「这条缝开得值吗」检查单，意见分「契约没说清」vs「缝开错了地方」两类）。
- 贯穿例子（沿用）：沙盒 `KnowledgeStore` 迁成「存储 port + `JsonlStore` + `InMemoryStore`」，处理第 14 课练习标出的「返回内部 dict」缺口；沙盒代码本次不动，迁移是练习步骤，由用户做。
- 理论来源：SWEBOK v4 第 3 章 p83–98（p86「separation of interface and implementation」原文已用 pymupdf 核实：「isolating the use of a component from the details of how that component is built」，同页含 coupling / cohesion）；MIT 6.031《Testing》「Unit and integration testing → Isolating a higher-level module」（本地已核实：不许在测 `extract` 时调 `load` 的隔离论证、stub「完全不碰文件系统」定义、类的 stub 常称 mock object）。经典：Feathers《Working Effectively with Legacy Code》（2004）seam / enabling point、Cockburn《Hexagonal Architecture》（2005）ports & adapters——**均无本地全文，按第 7 课 Nygard 办法经典转引 + 标注**；seam 定义与 `codebase-design` 词汇表逐字一致（本地实践来源可佐证）。实践：`codebase-design/SKILL.md` + `DEEPENING.md`（四类依赖、缝纪律、replace don't layer），只作实践方式。
- **来源核实记录**：本次会话网络不可用（websearch / webfetch 均失败），Feathers 与 Cockburn 原文未再核实，只用通行转引；若以后联网，可补一次原文核对。`SOURCE-MAP.md` 已补缺口行（Feathers / Cockburn 无本地全文；MIT 6.031 只有 stub 简短段落，fake/stub/mock 细分留给第 22 课）并在 Design & Architecture 表加 Cockburn 经典行。
- 写作沿用定型：术语首次 `English（中文）`（seam 接缝、enabling point 启用点、port 端口、adapter 适配器、indirection 间接层、test double 测试替身、fake 假件、stub 桩件、mock object 模拟对象、dependency injection 依赖注入、hexagonal architecture 六边形架构、ports & adapters 端口与适配器架构、contract test 契约测试、typing.Protocol 协议、ABC 抽象基类）；正文小节在练习前、recap 在练习后；练习用「这条缝开得值吗」检查单反馈；结尾指向第 16 课（设计两次）。
- 参考卡 `reference/0015-seams-adapters-card.html` 总结三词一条链、开缝判据、五个行业做法、四类依赖与人拍板三件、三坑、验证 prompt。
- 课程地图：第 15 课补链接；术语家谱「接缝 seam」行补 `codebase-design` 出处，新增「port 端口 / adapter 适配器 / enabling point 启用点」（Feathers + Cockburn + codebase-design，第 15 课）一行；next 段更新为「下一步写第 16 课」；第 14 课 next 段原本就指第 15 课、标题一致无需改。
- 第 16 课大纲已在 `NEXT-SESSION.md` 备好（设计两次：先造两个候选再选），只差写正文。

## 第二十八次调整（2026-10-27）
- 用户读第 6 课后反馈三点：① 「决定 vs 需求」易混（第 5 课逼问出来的到底是什么、算不算功能需求、非功能是不是缺的）；② NFR 缩写全课程没解释（mattpocock 技能包里也没有）；③ 技能包一路执行下来没有「把决定转成需求」的技能，非功能需求到底怎么补。
- 修改（先通读第 6 课全文与第 5、8 课和参考卡 0006，只选有用部分融入，保持正文顺畅）：第 6 课「行业做法」首次定义处补 NFR 缩写——non-functional requirements（非功能性需求，业界常缩写 NFR）；「AI + Matt 怎么落地」补两段——先说破空档（grilling 产出决定、to-spec 合成 spec，中间没有「写需求」命令，是把归类和数字这些业务判断留给人，不是遗漏），再给「三个挂点」把这一步接进流水线：上游（下次开 grilling 时就要求问出质量约束，NFR 进设计树成为待拍板的决定，推荐数字 agent 给、数字你拍，frontier 空前用完美技术过滤器自查）、中游（grilling 后、写 spec 前跑本课「动作」与「反馈回路」）、下游（NFR 写成带受益者的 user story 进第 8 课 to-spec 的 User Stories，明确不承诺的写进 Out of Scope）。参考卡 0006 术语表补 NFR、「AI + Matt」同步补三个挂点一段。
- 择优不融入的部分（用户明确要求以课件为准、不全搬讨论）：user story 写法的重复展开（第 6 课「非功能需求」一节已有 SE-EDU 受益者示范，只做回指）；写个人技能 to-requirements 的提议（未拍板，留待以后）；Out of Scope 的展开（第 8 课地盘，只给一词加括注）。
- 一致性核对：第 5 课 next 段、第 8 课 User Stories / Out of Scope 的说法与新内容一致；第 6 课「这一课只解决怎么把决定写成需求」的边界、五段结构、练习与反馈回路未动；标题与产出未变，课程地图无需改。
## 第二十九次调整（2026-10-27）
- 委派子代理以「懂编程、没系统学过软件工程、用过 mattpocock 技能包」的学习者身份通读第 6 课，结论：核心概念能掌握约八成，操作闭环有断点。用户拍板只落实「必须改 + 措辞」，跨课最小同步，补一个完整样例。已落实：
- 硬伤修复：① 五类需求活动的出处「第 5 课讲过」改回「第 4 课讲过」（第 5 课自己写的是「第 4 课说过」）；② validation 归属统一（本课做 analysis + specification + validation 自查，p57–62 的变更管理归第 7 课，「延伸」段重写）；③ 「动作」一节补完整样例清单（details 折叠：F1 + Given/When/Then、N1 带数字、X1 接口细节排除，并逐条对照开头那袋决定，含未拍板三条的去处：补 NFR 数字 / Out of Scope / 并进描述）；④ Given/When/Then 示范补判据（按句末标点计、每句不超 40 字），闭环开头「几句算几句」悬念，quiz 1 与 quiz 3 的判定差异在 quiz 3 答案里点破；⑤ 剧情对齐第 5 课：决定=当前打开的 Document、按引文逐条归纳、两到三句、先打出来；未拍板=中文/存条目/多快（正好喂给 NFR 与 Out of Scope）；⑥ 「上上一段」改指「问题与概念」一节，「三条再展开」改口（前两条进误区、第三条进检查单）；⑦ 检查单 prompt 改读逼问记录文件/会话记录 + 本地路径（SE-EDU《Requirements》品格清单、《Specifying Requirements》、SWEBOK PDF p50），删掉「SKILL.md 回看决定来源」的误导。
- 措辞修复约 20 处：可验收、可被检验→可检验；对面的电脑→那台完美电脑；一大坨→一大堆；自己那行→不属于自己的那一半；testable 的 scope→过不了 testable 这一关；很聪明的示范→好用的示范（并把「一千并发」收回为「高并发」，避免把发挥当 SE-EDU 引文）；只要不在…就停手→只要别在…那一刻就停手；不是某条命令替你做→没有哪条命令能替你做；逐条指→逐条指着查；好做得多→好做很多；「看起来合理」的数（「响应要快」）→貌似合理的空话；stakeholders（stakeholder，需求相关方）→stakeholder（干系人，与第 5、11 课一致）；它会指出→写不出验收标准这件事本身；功能的非功能→功能和非功能；改成了标题→换了个样子还是聊天记录；你签的字→签字的一定是你；derive 之前→动手实现之前；use case 补「（用例）」；testable / verifiable 注明同一件事；下一课预告「需求清单里那些大的取舍」改「逼问记录和需求清单里」（用不用模型、存哪按本课口径进不了清单）。
- 接口细节去向修正（第 6 课练习、quiz 4、第 5 课 quiz 同步）：「第 7 课以后」误导改为「第 8 课的 Implementation Decisions、第 14 课的接口草图」。
- grill-with-docs 说法收紧（上一轮新写段落的纠偏）：ADR 是 sparingly（难回滚/不解释会怪/有真实取舍三条齐才写，常常一条都不写），别指望它存完整逼问记录；补「换会话跑 to-spec 前先贴清单或让它先读（它只主动读 GLOSSARY.md 和 ADR）」；Given/When/Then 去向补明：挂在 user story 下当 conditions of satisfaction，Testing Decisions 落测试。
- 参考卡 0006 同步：降级→翻译、GWT 例句补判据、grill-with-docs 限定、分类三问去向、验证 prompt 改读逼问记录 + 出处改 SE-EDU《Requirements》。
- 择优不做（子代理建议改里未纳入）：需求清单路径定死并回填第 3 课约定表（仍用「比如」）；CMU 17-313 正文引用（保留在来源块）；第 7、8 课正文改动（validation 口径只需本课与第 7 课既有说法一致，已核对无需动）。
## 第三十次调整（2026-10-27）
- 用户拍板固化审计流程：每次新写完一课（或大改后），指派一个子代理审计课件，目标是**完全掌握**——与本次第 6 课的做法一致。
- `COURSE-STANDARD.md` 新增「写完一课：派学习者子代理审计，目标是完全掌握」一节：子代理身份固定为目标读者（懂编程、没系统学过软件工程、用过 mattpocock 技能包），不给作者视角、不提前透露意图；审计覆盖四问（掌握度与操作闭环 / 表达 / 逻辑与衔接 / 事实含 SKILL.md 行为核对）；要求逐条引用原句、按「必须改 / 建议改 / 可不改」三档报告并给总体判断；主代理先核实（事实类对照 SKILL.md 与原文）再落实，范围由用户拍板、跨课最小同步，「AI + Matt」事实纠错优先；结论未达完全掌握、必须改未修完，该课不算写完。检查清单新增一条。
- `AGENTS.md`「写课硬规则」同步一条硬规则（指到 `COURSE-STANDARD.md`「写完一课」一节）；`NEXT-SESSION.md` 写作原则补审计流程一行。
## 第三十一次调整（2026-10-27）
- 用户要求：文章风格的课程开发规则再检查一遍，强调「文字描述不要有 AI 味」。判断：「文章体」一节管住了结构和叙事，但第 6 两轮修订暴露的都是句子级毛病（步骤下面给、值得当面说破、三个挂点、很聪明的示范、derive 之前、它不是需求的终点……），既有检查清单拦不住，值得单开一节。
- `COURSE-STANDARD.md` 新增「文字没有 AI 味：句子像技术人写的，不像模型生成的」一节（排在「文章体」之后）：十条对号入座的模式各配正反例——电报式短语、表演性开场、生造名词、夸赞形容、同义反复、「不是 A，而是 B」句式套路化、指代不清的断言、翻译腔、混乱括号注释、连环破折号断言；判断标准一句话「一个写代码的朋友不会这么说话，就改」；口号例外（立得住的对偶收在概念转折处是加分的，问题只在密度）；与「写完一课」审计的「表达」一问挂钩。检查清单新增两条（别扭句自查、句式与口号限量）。
- `AGENTS.md`「写课硬规则」同步一条；`NEXT-SESSION.md` 写作原则补一行。
- 没动的部分：「文章体」一节既有条目（场景、比喻、表格、叙事线）经复核仍然成立，只字未改；口号不一刀切禁掉，保留「一节课一两处」的余地。
## 第三十二次调整（2026-10-27）
- 第 16 课「设计两次：先造两个候选再选」已完成：`lessons/0016-design-it-twice.html`、`reference/0016-design-it-twice-card.html`。标题与地图一致（未改名）。模块 3 第三站：第 14 课定模块形状、第 15 课定落点与可替换，本课给「造接口」补另一半——造之前先造两个
- 按五段结构写：位置（Design & Architecture 第三站——接口难收回所以值得多花设计功夫；给第 17 课比较动作练接口级版本；回指第 7 课 ADR rejected alternatives，本课产出那一栏的内容）→ 问题与概念（场景：试用同事要按标签筛、翻页；第一反应给 search 加参数＝第一个想法；Ousterhout「你的第一个想法不太可能是最好的」经典转引；换约束造候选的理论依据＝SWEBOK §5.9 约束缩小设计空间、force a few early decisions；走查两候选 A 仓库式加参数 vs B 查询对象式 Query/find；三笔账 depth/locality/seam placement 逐个算；选 A、为什么不选 B 一句话版本＋混合方案「窄方法＋共享过滤模块」；落选 B 进 ADR）→ 行业做法（明说无统一标准；主流两条：design doc 的 alternatives 一节（CMU 17-313 p7–8）、约束造候选；取舍两条：设计几次才停（SE-EDU agile vs full upfront，两次是下限，比不出去探原型第 30 课）、被否方案记不记（SWEBOK §4.6，落点 ADR））→ AI + Matt（`codebase-design` 的 `DESIGN-IT-TWICE.md`，模型调用；流程四步框问题/并行子代理各带一条设计约束（最小接口/最大灵活/最常见调用者/ports & adapters）/三轴散文对比/强判断与混合方案；每个子代理五件产出；人拍板三件：候选够不够不同、三轴权重、最终选谁；差异明说技能的「并行子代理＋三轴」是自动化不是行业标准）→ 三个常见误区（换皮候选/比功能多少不比复杂度从哪冒出来/选完不写落选理由含画三四轮停不下来）→ 练习（纸面设计两次六步：定问题空间→造 A→换约束造 B→三轴对比→取舍理由进 ADR 草稿→选中与落选候选各给两个 adapter 纸面实现试疼）→ 反馈回路（「这两套方案真的不同吗」检查单，意见分「候选不够不同」vs「理由没钉到判据」两类）
- 贯穿例子（沿用）：沙盒知识库存储接口，候选 A 起点＝第 15 课的存储 port（`add`/`search`），候选 B＝查询对象式（`Query`/`find`）；沙盒代码不动，纯纸面练习，第 15 课迁移做没做都能来（截至写完沙盒仍未迁，已记入交接）
- 理论来源：SWEBOK v4 ch.3 §4.6 Design Rationale（printed 3-11，pymupdf 核实：「alternatives considered, and trade-offs and criteria analyzed to select one approach and reject others」＋「记录被否掉的决定和否掉它们的理由」供假设变化时重新审视）、§5 导言（printed 3-11）、§5.9 Constraint-Based Design（printed 3-12，核实「limit the size of a design space…」「force a few early decisions」）；CMU 17-313《08-design-docs》p7–8（核实：「Propose key design decisions with an emphasis on their individual tradeoffs」、最好的设计文档「cover alternative designs, documenting the strengths and weaknesses of each」）；SE-EDU《Design Approaches》（核实：「Agile designs are emergent, they're not defined up front」vs full upfront design）。经典：Ousterhout《A Philosophy of Software Design》“Design It Twice”一章——**不在本地摘录里**（摘录只 ch.6/ch.21），经典转引＋标注，`SOURCE-MAP.md` 缺口已补该条。实践：`codebase-design/DESIGN-IT-TWICE.md` + `SKILL.md`，只作实践方式
- **审计流程走完（2026-10-27）**：学习者子代理（懂编程、没系统学过软件工程、用过技能包）审计结论「骨架和事实过硬，差距在交付细节」，必须改 4 项：①产物件数三种口径（三件套实列四件、两样 vs 三样）；②depth 分子分母段判词缺失、与前文打架；③「接口不动、调用者不动」违背第 14 课接口定义（Query 字段属接口）；④练习步骤 6（纸面实现落选候选）与检查单第 5 条（考选中候选）对不上，且「不是 A，是 B」句式 8+ 处超限。用户拍板「必须改 + 措辞」（同第 6 课口径），已全部落实：产物统一为「每个候选四件（接口/调用示例/缝后藏了什么/取舍），技能流程五件（多依赖策略与 adapter，纸面省）；产物两样加一处落盘（ADR）」；depth 段重写给按用例拆解的明确判词；第二笔账改「方法签名不动、老调用者一行不改＋Query 字段属接口、契约留第三笔」；步骤 6 改「先纸面实现选中候选、落选照做对照」；「不是 A，是 B」砍到 2 处（「会来的诉求不是拍板的需求」「功能多少是候选的介绍，不是判据」）；措辞约 12 处（操作成→落成、窄口→窄接口、目录懒创建→目录照旧懒创建第一次用到才建、最喜欢的地形→最容易钻的空子、生产→产出、还有一个去处更早→还有一个更早的去处、不然比的时候在翻译→不然对比的时候还得先互相翻译、来源栏 §5.1 归属改 §5 导言等）。参考卡同步（四件口径、卡片句式、产物 bullet）
- 择优不做（审计建议改 7 项未纳入，用户拍板范围外，存档在 `NEXT-SESSION.md` 待确认）：SWEBOK 约束推导补中间步＋「约束」三种用法辨析、打分表理由标注作者推断（注：「这个理由是我补的」一句属措辞已顺手加）、流程四步对齐文档三步、点破技能 3+ 候选与本课 2 套关系、练习换约束前提防照抄
- 课程地图：第 16 课补链接；术语家谱加「设计两次 Design It Twice / design rationale 设计理由 / rejected alternatives 被否掉的方案」（Ousterhout 经典转引 + SWEBOK ch.3 §4.6、§5.9 + codebase-design，第 7, 16 课）一行；进度段更新为第 1–16 课已写完、下一步写第 17 课；`SOURCE-MAP.md` 补 SE-EDU《Design Approaches》行与 Ousterhout 摘录缺口；第 15 课 next 段标题一致无需改
- 第 17 课大纲已备好（`NEXT-SESSION.md`：架构：质量属性、视图与取舍；SWEBOK ch.2 p67–82 + SE-EDU《Architecture》；ATAM 无本地材料不展开），只差写正文
## 第三十三次调整（2026-10-27）
- 用户对审计流程提三条建议，逐条评估均值得实施，已落实：
- ① 审计提示词未告知「参考资料已本地化」——16 课审计子代理是自己摸到 `courseware/` 核的引文，属运气；不写明可能白试联网（本环境 websearch 不可靠）或放弃核实。已补进 `COURSE-STANDARD.md`「写完一课」：提示词必须交代课件引用的参考资料已全部下载在本地 `courseware/`（清单见 `courseware/README.md`），核引文直接本地读取，不要联网搜索
- ② 审计只让读 `codebase-design`——课件涉及的技能不止一个（第 4/7 课 domain-modeling、第 8 课 to-spec、第 13 课 triage 等），只指一个会让审计面变窄。已补进同节：技能包完整目录 `C:\Users\admin\.agents\skills\` 全部可读，点明本课主技能（对照 `SKILL.md` 与配套文档），课件里出现的其它技能包行为描述也要逐一对原文；四问④同步改为「和 `SKILL.md` 及该技能的配套文档是否一致」；另补提示词要点一段（身份、目标、四问、要读文件清单、三档输出格式）
- ③ 未审计课排期——已审计第 6、16 课，待审计 13 课（第 1–5、7–15）。已在 `NEXT-SESSION.md` 新增「审计排期（backlog，暂不执行）」一节：默认提案按 1→15 顺序、每会话 2–3 课（审计＋修复耗上下文）；可选高风险优先（第 3、8、13、12、10 课技能事实密集）；每批提示词必须带上述两件环境事实；启动时机与批次由用户拍板，启动后逐批销账
- 未动：`AGENTS.md`（审计硬规则指向 `COURSE-STANDARD.md` 该节，无需重复）；课件与参考卡（本轮只改流程规范，不动课文）
## 第三十四次调整（2026-10-27）
- 第 17 课「架构：质量属性、视图与取舍」已完成：`lessons/0017-architecture-tradeoffs.html`、`reference/0017-architecture-tradeoffs-card.html`。标题与地图一致（未改名）。模块 3 第四站：第 14 课模块形状 → 15 缝与可替换 → 16 接口级比较取舍 → 本课把比较抬到系统级（组件、视图、质量属性）。
- 写课前拍板两项（问题已问）：练习产出**纯纸面**（同第 16 课，不动沙盒）；贯穿例子用**沙盒知识库升组件级**（CLI 入口 + 条目与检索核心 + 存储 port + 导入 web/笔记/PDF + 未来的薄 HTTP adapter，接第 12 课「多来源知识库」的雾）。
- 按五段结构写：位置（Design & Architecture 第四站，回指第 2 课八活动；给第 18 课设计文档供「取舍」原料；回指第 7 课 ADR 三判据与第 16 课「为什么不选另一个」）→ 问题与概念（「加 PDF 要动哪儿」问的是结构；SWEBOK 架构定义「推理系统所需的那些结构」+ Bass 等人「接口的公开面」；concern / view / viewpoint、logical/process/physical/development view、component-and-connector view、multiple views problem；quality attribute 分类（运行时可见/不可见/设计上可见）；ASR「任何影响架构的需求」是少数；取舍＝质量属性拉扯，§4.1 对撞例子；取舍说明四段式；architecture rationale + architectural technical debt）→ 行业做法（明说无标准——SE-EDU「架构图没有被普遍采用的标准记法」；主流三条：架构风格当第 16 课的「设计约束」造候选、质量属性写成可判场景句（scenario-based technique）、取舍落 ADR；取舍两条：画几个视图（一个问题一张图，经验判断）、决定写多细（组件图+取舍说明+ADR 中间地带，文档化跟着读者数量长））→ AI + Matt（无独立技能，技能栏「—」；agent 三件事：绘图员与追问者 / 组件级与模块级词汇双向翻译 / 按 ADR-FORMAT 落盘；人拍板三件：哪些是 ASR、取舍怎么称重、图给谁看；差异明说：技能包词汇只管到模块级，improve-codebase-architecture 反向禁 component/boundary 用词，ATAM 不展开）→ 三个常见误区（风格名字当答案 / 质量属性写成形容词 / 取舍只写选了谁含图越画越大）→ 练习（纸面五步：定组件清单含虚线规划件 → 画组件图标缝 → 三质量属性各一条取舍说明 → 至少一条 ADR 草稿 → 对图试疼「加 RSS 导入」「HTTP adapter 上线」两变化）→ 反馈回路（「这三个取舍站得住吗」检查单 7 条，意见分「取舍没场景化」vs「图没回答问题」两类）。
- 理论来源：SWEBOK v4 第 2 章 p67–82（printed 2-1~2-16）——§1.2（2-3）、§2 与 §2.1（2-4~2-6）、§2.2（2-6~2-7）、§2.4（2-7：质量属性取舍是设计决定依据、rationale、技术债）、§3.2.1（2-9：ASR）、§4.1（2-10~2-11）；第 3 章 §6.2–6.3（PDF p95–96 = printed 3-13~3-14：质量属性分类、scenario-based techniques）。行业做法 SE-EDU《Architecture》（架构定义、无标准记法、画图规矩、风格清单、「大多数应用混用多种风格」）。经典转引：Bass/Clements/Kazman《Software Architecture in Practice》quality attribute scenario 六段（本地无全文只借骨架）；ATAM/SAAM/QAW 不展开。实践：domain-modeling 的 ADR-FORMAT.md、codebase-design 词汇表、improve-codebase-architecture 词汇纪律。
- **审计流程走完（2026-10-27）**：学习者子代理审计（目标完全掌握）报「必须改 5 项」——①虚线组件与检查单「每个组件对应到代码」自相矛盾；②「沿用第 16 课那句式」指代错（三段式是本课新加）；③「三判据、四字段、rejected alternatives 必填」与 ADR-FORMAT.md 及第 7 课三方打架（实测模板极简：一句背景+决定加为什么，Status/Considered Options/Consequences 全可选）；④「检查单里有一条专门打它」承诺没兑现；⑤源块页码按课程 1-based 惯例应为第 2 章 p67–82、§6.2–6.3 p95–96（printed 页码引文全部核对无误）。用户拍板「必须改 + 措辞」，已全部落实：检查单区分已有/虚线组件并补第 7 条「框越画越多」；句式改成「四段式=三段+第 16 课那句」；ADR 描述按模板原文重写（AI 节、练习 step 4、行业做法三、参考卡四处同步）；页码修正（课件、参考卡、SOURCE-MAP 三处）。措辞约 12 处：「任务书」生造词改「沙盒的定位」（3 处）、「不是 A，是 B」从 5 处砍到 2 处、「没有双赢只有谁来扛」对偶改平实、「半节课」指代、「账单不值」搭配、「先立标尺」同句重复、「这是刻意的」重复、concern 译「疑问」改「关切」、「交给 ADR-FORMAT.md 落成」改「让 agent 按…落成」；另修三处出处/事实标注：两句架构定义同出 Bass 等人（SWEBOK 采纳并标注引自他们）、pipes-and-filters 解释非 SE-EDU 原文（标注为本课概述）、「ATAM 只提名字」改「有一句概述」。
- 择优不做（审计建议改里未纳入，存档在 NEXT-SESSION 待确认）：补一条写全的示例取舍说明、三条刺激「和谁拉扯」说清或放宽检查单第 4 条、存储画一框还是三框（port + 两 adapter 混写）、练习 step 5「动三个以上组件」判据武断、两套视图名单（四视图 vs C&C）未接上、质量属性三分类摘录补「等等」、n-tier 等术语补中文。
- 课程地图：第 17 课补链接；术语家谱加「ASR 架构级重要需求 / 架构风格 / architectural technical debt 架构技术债」（SWEBOK ch.2、SE-EDU Architecture，第 17 课）一行（原「质量属性 / 视图」行已预置）；进度段更新为第 1–17 课已写完、下一步写第 18 课；SOURCE-MAP Design & Architecture 行补第 17 课核实的章节/页码明细，缺口行补「quality attribute scenario 六段写法经典转引」。
- 第 18 课大纲已在 `NEXT-SESSION.md` 备好（设计文档），只差写正文。
## 第三十五次调整（2026-10-27）
- 用户指出：第 17 课审计提示词点名的三个技能文件（domain-modeling / codebase-design / improve-codebase-architecture）是架构设计系的，后面的课内容不同会对不上。核实：点名本来就是按当课内容现选的（第 17 课「AI + Matt」节落地的恰是这三个），但 `COURSE-STANDARD.md` 只说「点明本课主要涉及哪个技能」，没写清单从哪来，照抄旧提示词会错配。
- 修订两处：`COURSE-STANDARD.md`「写完一课」补明——点名技能**每课重选**，来源是三处合集（地图技能栏 + 「AI + Matt」节落地的技能 + 正文点到的技能）；技能栏「—」的课明说无独立技能，正文点到的技能照样逐一对原文。`NEXT-SESSION.md` 审计排期一节同步一句。
## 第三十六次调整（2026-10-27）
- 第 18 课「设计文档：让下一个人（或 agent）能接手」已完成：`lessons/0018-design-doc.html`、`reference/0018-design-doc-card.html`。标题与地图一致（未改名）。**模块 3（第 14–18 课）至此写满**：模块形状 → 缝与可替换 → 设计两次 → 架构取舍 → 设计文档。
- 写课前拍板三项（问题已问）：练习产出**落沙盒 `.scratch/<feature>/design.md`**（只落文档不动代码，给模块 4 留交接物）；第 15 课迁移**做没做都能来**（沿用 16、17 课口径）；「AI + Matt」**引 `handoff` 做对照**（design doc 作品级交接 vs handoff 会话级交接），技能栏保持「—」。
- 按五段结构写：位置（M3 收尾站，四站零件合成一份产物；划清与第 8 课 spec 的界线——spec 管做什么、design doc 管怎么组织为什么，两处重叠说破；给模块 4 当接手的起点）→ 问题与概念（接手的 agent 凭代码猜决定、删 `InMemoryStore`、PDF 疼打在核心；SWEBOK ch.2 §2 AD 是工作产物、有形表示、面向干系人、blueprint；ch.3 §4 设计记录捕获四样 + working specs vs final design products；CMU p8 最差文档嵌歧义 = 交接失败机制）→ 行业做法（明说无统一标准；主流三条：模板当骨架别当合同（CMU p11 十一项 + 六节版）、design review 当过滤器（CMU「Code review before there is code」+ SWEBOK §6.1）、RFC 状态流（CMU p13–15 判据与六标签，单人版留三态）；取舍一条：写多细——SE-EDU Document Minimally but Sufficiently + top-down，刻度「跟着读者数量长」）→ AI + Matt（技能栏「—」；agent 三件事：执笔者（引用不复制分三类：长产物指路径 / 结论短内容写死 / 结构性内容内嵌到能独立读懂，规矩出自 `handoff/SKILL.md`）/ 陌生读者试疼三问 / design doc 与 handoff 分工；人拍板三件：目标与非目标划在哪、取舍怎么裁、写给谁写多细；差异明说技能包无 design doc 自动化）→ 三个常见误区（流水账或代码说明书 / 模板当合同十一项全填 / 只写选了谁不写为什么）→ 练习（落 `.scratch/<feature>/design.md`，五步：收散件列引用清单 → 写六节草稿 → 逐节自查一问 → 给状态（草稿/已评审/已实现）→ 对文档试疼三问加一件事）→ 反馈回路（「这份文档能交接吗」检查单 7 条，意见分「接手者只能猜」vs「回答不了承诺的问题」两类）。
- 理论来源：SWEBOK v4 ch.2 §2（printed 2-4，pymupdf 核实：AD 工作产物、「有形的表示」对演化系统与进出人员、面向有关注点的干系人、blueprint 与依据）；ch.3 §4 Recording Software Designs（printed 3-7~3-8：捕获四样、沟通随受众、working specs vs final design products）、§4.6（printed 3-11：理由对后来者未必显然）、§6.1（printed 3-13：设计评审）。行业做法 CMU 17-313《08-design-docs》全篇 18 页逐页核过（p6 文档分类、p7、p8、p11、p13–15、p18）+ SE-EDU《Documentation》（developer-as-maintainer、Go Top-down、Document Minimally but Sufficiently）。实践：`handoff/SKILL.md`（「不重复已有产物、引用路径」引文逐字核对）、`to-spec/SKILL.md`（spec 模板对照）、`domain-modeling/ADR-FORMAT.md`。
- **审计流程走完（2026-10-27）**：学习者子代理审计（引文、页码、技能包事实全部核实无误），报「必须改 4、建议改 11、可不改 6」。用户拍板「必须改 + 衔接两条 + 措辞」，已全部落实：必须改①「引用不复制」与架构节内嵌组件图矛盾→改成分三类的精确规则（recap 与参考卡同步）；②spec/design doc 分工与六节重叠未解释→「位置」节说破（问题节是压缩版、非目标与 Out of Scope 同源摘要，结论性一两句允许重复）；③「下一节 agent」指错节；④CMU p11 映射过头（p11 无 Goals 项，goals 出自 p7 三件；「引用对着 Metadata 一族」是硬凑）→改成「各取所需」。衔接两条：⑤兑现第 17 课「备选设计展开」承诺（p8 最好文档一句 + alternatives 折进取舍节、与第 16 课「单开一节」的关系）；⑥试疼问题统一成正文三问（接下来做哪张工单 / 加 RSS 动哪儿 / 为什么不直接读 PDF），练习加「做一件事」，检查单第 7 条与「怎么判断生效」同步。措辞约 14 处：「不是 A，是 B」砍到 2 处、stakeholder（干系人）格式、RFC 全称 Request for Comments、RFC 用法判据补第五条（surface an idea, tension, or feedback）、「给底」「遮住标题」「没有没定的事」「换过会话的读者」「顺序」「解决法」、to-spec「可能很快过时」、练习 step 4「下一步」指代、行业做法标题补「状态当标牌」对齐四小节、参考卡术语表 rationale 去重。
- 择优不做（存档 `NEXT-SESSION.md` 待确认）：建议改第 7 条（「三件实打实的活」的第三件是概念区分）；可不改档剩余（「活不过一次会话的范围」引申、to-spec 原型例外未提、参考卡「待第 12 课雾散」措辞、「引用行号对不上」进 Problem 节）。
- 课程地图：第 18 课补链接；术语家谱加「design doc 设计文档 / architecture description 架构描述 / design review 设计评审」（SWEBOK ch.2 §2、ch.3 §4、§6.1；CMU 08-design-docs，第 18 课）一行；进度段更新为第 1–18 课已写完、模块 3 写满、下一步写第 19 课。
- 第 19 课大纲已在 `NEXT-SESSION.md` 备好（pytest 与测试设计：划分、边界、覆盖率，M4 开篇；MIT 6.031《Testing》为主读物候选；注意「测试从零教起」约束与 fake/stub/mock 留给第 22 课的缺口），只差写正文。
## 第三十七次调整（2026-10-28）
- 用户问「15 课的迁移是啥」并拍板**把这次迁移补上**。已在沙盒 `D:\code\my_projects\se-course-sandbox` 完成（提交 `335b4bf`）：`kb/storage.py` 从单个 `KnowledgeStore` 迁成 `Store` port（`typing.Protocol`，契约写在 docstring：条目恰好四键 id/title/text/created_at、id 形如 `e0001` 按加入顺序递增、created_at 为 UTC ISO 8601 精确到秒、search 大小写不敏感且顺序与加入顺序一致、所有返回 dict 是副本）+ `JsonlStore`（唯一碰文件的 adapter）+ `InMemoryStore`（纯内存，无文件逻辑）；`kb/cli.py` 单点装配（`store: Store = JsonlStore(STORE_PATH)`）；`__init__.py`、`README.md` 同步。顺手补掉第 14 课练习标出的 rep exposure 缺口（`add`/`search` 返回副本）。走缝验证（同一组断言在两 adapter 含重开仓库上都绿）以临时脚本跑过，**未落测试文件**（测试设计是第 19 课的活）。
- 迁移中验证脚本自己错了三轮（重开仓库 id 接着排、重开后 search 命中累积、hello 内容跨轮撞车），均是断言预期错、不是代码错——「走缝验证」这一步本来就该对契约抠细节，这三轮正是契约被逼现形的过程（第 15 课练习提示里「id 规则其实是契约」的现实版）。
- 后面几课练习核过**课件一行不用改**：第 15 课练习即此次迁移（教材起点仍是第一版骨架，不动）；第 16 课练习写明两个分支（「没做迁移就用现在 `KnowledgeStore` 的两个方法」），现在走迁移后分支；第 17 课组件清单本就按 `JsonlStore` / `InMemoryStore` 写；第 18 课「做没做都能来」，迁移后「引用清单」可直接指 `kb/storage.py` 真实路径，更强不用改。第 19 课（未写）「先补迁移还是直接测」的问题消失，直接对 `Store` port 写测试。
- `NEXT-SESSION.md` 沙盒状态、知识库教学定位、第 19 课教学注意、待确认四处已同步。
> AI生成

## 第三十八次调整（2026-10-28）

- 第 19 课「pytest 与测试设计：划分、边界、覆盖率」已完成：`lessons/0019-pytest-test-design.html`、`reference/0019-testing-card.html`。标题与地图一致（未改名）。M4「实现与测试」开篇：从 M3 的设计产物转到「拿证据检验」。
- 按五段结构写：位置（Testing & Quality，M4 开篇；测试站在第 15 课的 `Store` port 上，同一批契约测试跑两个 adapter；第 14 课不变量要能在测试里守住；给第 20 课 TDD 备用例表）→ 问题与概念（四十个绿测试的故事：标题前缀收窄后仍全绿，搜「入门」找不到「PyTest 入门」；SWEBOK 测试定义 dynamic/finite/selected/expected、Dijkstra、test case/suite/oracle；MIT correct/thorough/small 与 make it fail）→ 行业做法（EP、BVA、组合不做笛卡尔积、pairwise、黑盒先写白盒补漏、语句/分支/路径覆盖、覆盖率不证明断言对、pytest fixture/parametrize/tmp_path、单元测试与测试金字塔、记录测试策略）→ AI + Matt（技能栏「—」；agent 列候选/写骨架/做变异检查；人定四件：匹配语义、空 query、契约 vs 实现、覆盖率停在哪；CMU 11-oracles p19 的 golden master 警告；变异检查三次）→ 三个常见误区（覆盖率当目标 / 测实现细节 / 用例越多越好或只写两三个）→ 练习（写 `tests/test_storage.py`：策略注释、entries 参数化、两个 adapter、副本/四键/重开、覆盖率补漏、三次变异；契约决定落 design doc「风险与未决问题」）→ 反馈回路（分区缺口 / 断言越界 / 契约空洞三类）。
- 贯穿例子（沿用）：沙盒 `Store` 契约与 `JsonlStore` / `InMemoryStore`；第 15 课迁移已做，测试直接对 port 写。两处契约空洞由学习者拍板：关键词子串还是整词、空 query 返回什么；课件给示例决定（子串 + 空列表），不是标准答案。id 到 10000 条之后的宽度、空白串 query、错误模式未定，课件当作「边界从契约来」的例子/未决问题处理。
- 理论来源：SWEBOK v4 第 5 章 p117–136（printed 5-1~5-20）——测试定义（5-1~5-2）、oracle（5-4~5-5）、Dijkstra（5-5）、测试四级（5-6~5-7）、EP（5-10~5-11）、BVA（5-11）、结构测试与覆盖率（5-13）、覆盖率度量（5-16）、变异（5-14~5-15、5-18）、彻底性度量不充分（5-20）；MIT 6.031《Testing》（correct/thorough/small、make it fail、partitioning、boundaries、multiple partitions、black/glass box、coverage、documenting strategy、unit/integration、iterative test-first）；SE-EDU《Test Case Design》（EP、BVA、组合策略与两条启发式）。行业做法：CMU 17-313《09-testing》p9 基于规格的测试、p11 金字塔、p16 EP、p18–19 BVA、p20 pairwise、p23 可测性四原则、p25–33 七条原则；CMU《11-oracles》p7 基于例子的 oracle、p18 differential testing、p19 golden master 与 AI 生成测试的警告。测试设计无统一标准；ISO/IEC/IEEE 29119 只借 SWEBOK p5-16 一句概述。实践：pytest / pytest-cov 官方文档；`tdd` 技能留给第 20 课。
- **审计流程走完（2026-10-28）**：学习者子代理审计（引文、页码、沙盒代码、pytest 实际行为均核实），报「必须改 6、建议改 27、可不改 5」。必须改全部落实：① 十一格表单条目 `parametrize` 写不出空仓库/多条命中，代码改 `entries` 列表；② 分区表混入边界与输出不变量，拆成「输入划分」表 + 边界表 + 独立不变量说明；③ `--cov-branch` 实测不标同一行 `or` 的短路（coverage 7.17），改成「变异检查或 if/elif」；④ 「四十个测试 small 占了」与定义矛盾，改成「跑得快但重复，谈不上 small」；⑤ 整词语义下该改「Test」「P」而非「入门」；⑥ 变异检查补「先 commit、git diff、git checkout 还原、再 git diff」的机制。建议改落实：步骤 5 改「读红也读绿」、覆盖率命令改 `--cov=kb.storage` 并说明 `cli.py` 0%、补 `pip install`、补副本/重开测试代码、design doc 决定改指「风险与未决问题」、删 `knowledge-pet`、补 `python -m pytest` 与 `pytest` 的区别、`created_at` 口径统一（UTC + 微秒，不断言字符串写法）、oracle 的「另一个实现」补 CMU p18、CMU 可测性四原则改「符合后两条」、「三个词」改「四个关键词」并说明前三个、`对狠小` 改 `正确彻底小`、删「拍四块板/小而狠」、砍「不是 A 而是 B」密度、测试名改具体、下一课「最后重构」按 `tdd/SKILL.md` 改「重构不在循环里」、场景动机改「嫌结果太杂」、参考卡示例决定/代价列同步。未做仅「可不改」档风格偏好。
- **技术核实记录**：本机 Python 3.12 / pytest 8.3.2 / coverage 7.17 实测——课上的 `entries` 版测试 17 passed；`--cov=kb.storage --cov-branch` 显示 97%，唯一 partial 是 `JsonlStore.__init__` 的 `if line.strip()` 循环回边（43->42），不是 `search` 的 `or`；`python -m pytest` 可从沙盒根 import `kb`，直接 `pytest` 在部分环境会 `ModuleNotFoundError`。以后若有人建议「用分支覆盖看 `or` 两边」，先拿这个实测结果挡回去。
- 课程地图：第 19 课补链接；术语家谱「测试金字塔 / 覆盖率」改为「测试金字塔 / 覆盖率 / 等价类划分 / 边界值」，出处补 SWEBOK ch.5、SE-EDU Test Case Design；进度段更新为第 1–19 课已写完、M4 开篇、下一步第 20 课；沙盒状态行从 `KnowledgeStore` 更新为 `Store` port + 两 adapter（迁移提交 `335b4bf`），并注明测试文件由第 19 课练习创建。
- 沙盒仍未落测试文件（`tests/` 由学习者按第 19 课练习创建），无 CI；`GLOSSARY.md`、`docs/adr/`、`.scratch/`、`.out-of-scope/` 继续懒创建。
- 第 20 课大纲已备在 `NEXT-SESSION.md`（TDD 红绿重构：`tdd` 技能、SWEBOK ch.4 §4.16 + MIT/CMU 09-testing p21 + Beck 经典转引；练习对象候选 `delete(id)`，写课前拍板；注意 `tdd/SKILL.md` 说 refactoring 不属于循环，与课程标题「红绿重构」的差异要写清）。
## 第三十九次调整（2026-10-28）

- 第 19 课写完第一轮修订后，又派同一身份的学习者子代理做第二轮复核（读正文、参考卡、沙盒代码；实测 pytest / pytest-cov）。结论：第一轮六条必须改里，①③④已清零；②⑤⑥有残留，另发现 3 条新问题。第二轮必须改 6 条，已全部落实：
  1. 参考卡「划分」表仍混着「query 的边界」「返回值不变量」，与正文「这张表只放输入划分」冲突——已把这两行移出，边界并入边界表，不变量单独写一段。
  2. 正文说「示例七种场景，剩下单字符、整标题、空 query」少算「标题中间命中（Test）」——已补成七加四等于十一。
  3. 整词语义下第 3 条「Test」改成空后，全表失去「标题中间命中」代表；第 10 条含空格 query 的预期也没交代——已改成第 3 条标题「Py Test 入门」查「Test」，并写明第 10 条按分词规则定、本沙盒建议选子串（中文没有空格分词）。
  4. 完成标准和参考卡写 `pytest -q`，与正文「直接敲 pytest 会 ModuleNotFoundError」矛盾——已统一为 `python -m pytest -q`。
  5. 反馈提示词「开始前确认第 2 步的契约改动已提交」在独立提示词里悬空，未提交时 `git checkout` 会冲掉契约改动——已改成「确认 git status 干净；没有就先 commit；未提交时不要运行 git checkout」。
  6. source 把 SWEBOK p5-16 写成「覆盖率度量」，实际 p5-16 是 Test Process Measures / ISO 29119，覆盖口径在 p5-13 与 p5-20——正文与参考卡都已改。
- 第二轮建议改也落实：`git add -A` 会把 `.coverage` 带进去，改成 `git add tests kb/storage.py docs` + `git status` 提醒并建议把 `.coverage`/`.pytest_cache` 加进 `.gitignore`；design doc 未定的进「风险与未决问题」、已定的进「架构」；练习 step 2「选一个」改「两个问题各选一个答案」；「每个参与者」段把 search 的标题/正文与 add 的 title/text 说清；参考卡示例 docstring 与代码的空 query 行为注明「先改 adapter 再补第 11 条」；变异检查改成「一次只改一个 adapter 的一处，另一个保持正确」；手敲验证改成加一条含 PyTest 的条目再搜、再查空串；「少到随便不算小」改通；「100% 覆盖」改「100% 语句覆盖」；补 `add` 副本/四键与 `created_at` UTC+微秒的说明；`design doc` 首次给中文；`data participants` 给中文；CMU p11 改「单元多、端到端少，集成放中间是常见画法」；第 21 课说法改成「行为、边界、可读性；tdd 技能用公开接口、反同义反复说其中两条」；source「缺陷存在谬误」改「无缺陷谬误」；参考卡术语表补四个测试级别；参考卡补「样例只到七条」和整词分支说明。
- 实测复核：正文 `entries` 版 7 条 × 2 adapter = 14 passed；加副本/重开 = 17 passed；十一格全写当前子串实现 22 passed（空 query 第 11 条在改成返回空列表前会红）；`--cov=kb.storage --cov-branch` 97%，唯一 partial 是 `JsonlStore.__init__` 的 `if line.strip()` 回边（43->42）；`pytest -q` 在副本根目录确实报 `ModuleNotFoundError`，`python -m pytest -q` 正常。沙盒未被修改，仍在 `335b4bf`、无 `tests/`。