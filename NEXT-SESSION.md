# 下一会话交接

> 用途：把课程状态从当前会话交接到一个新会话，避免重读整段对话。**课程已全部写完（34/34），老课审计也已全部完成，没有下一课**；本文件现在记的是收尾状态、练习留档约定与审计记录索引。
> **OpenCode 会自动读取根目录的 `AGENTS.md`；它已经要求新会话先读本文件、`COURSE-STANDARD.md` 和 `SOURCE-MAP.md`。**

## 先读这些（按顺序）

1. `AGENTS.md`：会话规则（OpenCode 自动加载，不用手动提醒）。
2. `NEXT-SESSION.md`：本文件，完结状态与审计记录索引。
3. `COURSE-STANDARD.md`：五段结构与审计流程；以后新增课或大改仍按它出提示词。
4. `SOURCE-MAP.md`：引用依据；核对引文先查它。
5. `MISSION.md`、`NOTES.md`、`reference/course-map.html`（34 节全部带链接）、`CURRICULUM-REVIEW.md`。

## 当前状态

- 课程骨架 34 节 / 7 模块全部写完并逐课按审计流程收尾：M0（1–3）、M1（4–8）、M2（9–13）、M3（14–18）、M4（19–24）、M5（25–29）、M6（30–34）。最后一课第 34 课「综合演练 + 迁移到真实项目」于 2026-11-06 写完。
- **老课审计已全部完成（2026-11-17）**：第 1–34 课全部审完。最后一批第 15 课于 2026-11-17 审完，首轮报「必须改 15、建议改 28、可不改 5」，15 条必须改与 28 条建议改全部落实；复查又报「必须改 5」，全部修完（默认练习的 id 假设、无第 14 课路径、`__main__.py` 与第 22 课相反、uuid4 与第 19 课示例冲突、待定错误模式的检查单）；终查无必须改，判完全掌握。沙盒 `master` 补两个提交（`f7fd50a`、`49f4388`）。此前：第 10 课报「必须改 8、建议改 23、可不改 5」；第 11 课首轮「必须改 12、建议改 21」、复查「必须改 2」；第 12 课首轮「必须改 14、建议改 14」、复查「必须改 2」；第 13 课首轮「必须改 10、建议改 18」、复查「必须改 4」、终查无必须改；第 14 课首轮「必须改 11、建议改 30、可不改 6」，复查两轮报「必须改 8」「必须改 4」，跨文件残留修完后判完全掌握。**没有待审计课**。审计记录见 `NOTES.md` 第七十次调整。
- **技能入口写法已统一（2026-11-17）**：全课程改用 `@skill-id`，共 135 处，只保留 `/clear`、`/compact`、`/new` 等 OpenCode 真命令的斜杠写法。第 32 课那张「技能文档的写法 vs OpenCode 里的动作」对照表是唯一例外，中间栏保留斜杠并写明理由。详见 `NOTES.md` 第七十一次调整。以后新增课按 `@` 写。
- **本地课件已补齐（2026-11-17）**：`courseware/fowler/mocks-arent-stubs.html` 与 `courseware/meszaros/` 六页到位（xunitpatterns.com 经 web.archive.org 的 `id_` 快照），课程地图里那处死链消失。`courseware/` 不进 git，换机器要重抓，抓法与来源记在两个目录的 `README.md`。详见 `NOTES.md`「补下载记录（2026-11-17）」。
- **课程站点已上线（2026-11-17）**：`https://telecomshy.github.io/telecomshy-se-lessons/`。入口是仓库根目录的 `index.html`（封面与目录），样式在 `assets/landing.css`；Pages 源是 `main` 根目录，带 `.nojekyll`。课件里的本地课件链接（`courseware/`）线上会 404，属已知限制。
- **沙盒（2026-11-17 建，2026-11-18 两次改口）**：私有仓库 `telecomshy/se-course-sandbox` 是作者自己两台机器同步用的实例，主干 `master`；课件里的沙盒指学员自己在第 3 课建的仓库，与本课程仓库同级（叙述写 `se-course-sandbox`，需要具体路径的命令写 `<工作区>\se-course-sandbox`）。**代码口径已改为学员自建（2026-11-18）**：第 13 课新增「开工前：把练习对象叫起来」一节，学员照一段短 brief 用 `@implement` 立 `kb/` 骨架、提交并打标签 `lesson-14-start`，再进 triage 练习；第 14、15 课在分支上做，第 15 课把迁移合回主干。第 14、15 课原来「`master` 是第 15 课完成态、可对照答案」的说法已删，第 19 课的「迁移已经做完」改成前提条件。核对清单（`kb search` 只打印 id 和标题、条目恰好四个键、id 非空唯一稳定、`add` / `search` 无调用先后要求、错误模式留给第 23 课）已写进第 13 课的 brief 与验收表。作者实例里的两版代码（`5544243` / `fa76ccd`）只作参考，不再是教材默认。
- **路径随机器而变（2026-11-07 与用户确认，重要）**：开发在两台机器上进行，文档不写死机器专属路径。技能包在当前用户主目录的 `.agents\skills\`，课件与参考卡统一写 `%USERPROFILE%\.agents\skills\`（44 个文件已批量替换）；课程地图页脚工作区写「本仓库」。两台机器现状：admin 机 `C:\Users\admin\.agents\skills\`（51 个目录）；18907 机 `C:\Users\18907\.agents\skills\`（40 个目录）、工作区 `E:\code\my_projects\telecomshy-se-lessons`。**派审计子代理时由主代理现场解析成当次机器的具体路径，不写 %USERPROFILE% 字面量。**沙盒路径不写死盘符（2026-11-18 改口径）：课件、参考卡与 `README.md` 叙述一律写「沙盒仓库 `se-course-sandbox`（与本课程仓库同级）」，需要具体路径的命令写 `<工作区>\se-course-sandbox`；两台机器 clone 同一私有仓库 `telecomshy/se-course-sandbox`，放在各自工作区。
- 写作原则：软件工程理论是主线，AI + 技能包是实践；课件是文章不是 PPT；文字没有 AI 味；修改课件先通读整篇（细则见 `COURSE-STANDARD.md`）。
- 结构定型：正文性小节（如「三个常见误区」）排在练习之前；recap 在练习与反馈回路之后；`div.source`、`div.next` 收尾。
- 自查分工（2026-11-03 定）：派审计前主代理只做机械自查（术语首见、引文照抄、文件互链、回指名）；掌握度、表达、逻辑、事实四类实质判断只归审计子代理。
- 去 AI 味的分工（2026-11-11 与用户议定，替代 07 版）：表达层判断仍归审计子代理，方法＝shuorenhua「只标问题」（annotation mode）＋「文字没有 AI 味」十条并列判据——shuorenhua 管通用自然度，十条管它默认不标的模式（夸赞式形容、「不是 A，而是 B」密度与对偶口号、连环破折号、术语括号注释）。shuorenhua 默认交付是改写稿，提示词必须显式指定「只标问题、不改写」；标注不产出改写稿，审计子代理直接套用，不必单派。审计报告指出的问题句仍由主代理点修。整篇 shuorenhua 改写工序（`.rewrite.html` 先 diff 那套）**已删除**——第 29 课试验结论边际改动小，深层改写由「修改课件」的「重写受影响的一节」兜底。shuorenhua 装在 OpenCode 全局技能目录 `.config\opencode\skills\shuorenhua\`（不在 `.agents\skills\`；18907 机未确认装没装），提示词里由主代理现场解析，未装则只用十条清单。

## 第 1 课已审计（2026-11-07）

- 必须改 1 条：「把本质复杂度提前解决掉」自相矛盾 → 「先让问题有答案，再让 AI 动手」。建议改 12 条全落实，最要紧三条：参考卡第二问补「、依赖它」+「多个团队」档（旧卡会把练习 4 的单人维护、12 服务依赖的库判成编程问题）；主读物补 *Scale and Efficiency*（与第 2 课「读三节」对齐）；练习加第 7 题「你手上的项目」，兑现目标栏承诺。
- 改动文件：`lessons/0001-what-is-software-engineering.html`、`reference/0001-three-questions.html`、`reference/course-map.html`（页脚两条本机路径）。

## 第 2 课已审计（2026-11-11）

- 派审计前机械自查发现两处术语首见问题并先行修掉：`SWEBOK` 首见（主读物行）无中文、`agent` 首见无中文（参考卡同句一并补）；文件互链、回指名全过。首次按新表达判断流程实跑：审计子代理内一次完成四问，表达判断＝shuorenhua「只标问题」＋十条清单并列——shuorenhua 对正文零命中，十条补出句式密度，分工如设计生效。
- 审计结果：报「必须改 2、建议改 7、可不改 6」；**事实层全干净**——SWEBOK 断言两条核过（十五个知识领域 + 计算/数学/工程基础单列；第 1 章 = PDF p43–66，子代理按页读 PDF）、SE-EDU print.html 在且相称、abseil ch01 三节名授权抓取核对、技能工作流五步与五个 SKILL.md 一致、八活动与模块名对照一致（两处地图同步项见建议改）。
- 必须改两条：① 「每节课都会问两个问题」与第 3 课同一排他句式宣布两对不同的两问（本课那对后续课也没按课兑现）→ 本课改「从这一课起拉回两句 + 动手后加一对」，第 3 课 216 行最小同步「除了问第 2 课的两问，还会再加上两个问题」；② 「不是 A，而是 B」7 处超「一两处为限」→ 留 lede 与 recap 首尾定义呼应，其余五处改平铺直叙。
- 建议改七条全落实：主读物指到小节级（Introduction「What Is Software Engineering?」PDF p38–42 + 第 1 章 §1 PDF p44–48，其余到模块 1 再读）；练习答案 2/5 去前向术语（「接缝/深模块」「写进词条」，答案 5 标签改「需求」并指回第 4 课）；「下一课」预告去重；「学习顺序 ≠ 项目流程」第 4 节改一句话回指；「模块收尾提醒回环/收账」承诺软化（grep 全 lessons 查无落实）；模块 0 名称统一为「地图与工作台」（改课程地图 h3）；课程地图模块 0 读物行补 SWEBOK。另顺手落实掌握度一条：第 4 节末补「参考卡是两张表的合订版」，让「产出」闭环。可不改 6 条维持现状。
- 改动文件：`lessons/0002-what-software-engineering-covers.html`（11 处）、`lessons/0003-ai-practice-and-workbench.html`（1 处）、`reference/0002-se-landscape.html`（1 处）、`reference/course-map.html`（2 处）。改后通读验收：遮小标题因果链成立、quiz 答案全部对得上八活动表、recap 与正文口径一致。

## 第 3 课已审计（2026-11-12）

- 派审计前机械自查修 10 处术语首见（正文 agent、UI、agent-ready 三处，参考卡 spec、seam、frontier、agent-ready、Local markdown、single-context 六处）；两条 README 引文由主代理在线预核（"not vibe coding" 属实；「装两个 agent」一条把现行原文交给审计员判断）。**交接文档挂起项销账**：本机 `.agents\skills\` 78 个目录 = Matt 技能恰 38 个（与三层表逐一相符）+ 非 Matt 40 个，课件 L306 注释已覆盖混入情况。
- 审计结果：报「必须改 3、建议改 12、可不改 8」；38 个技能调用类型（frontmatter）与三层表全对、成员无遗漏无混入，setup 产物与沙盒实况相符，练习四情境有 SKILL.md 支撑。必须改三条：① 「红-绿-重构」→「红-绿循环（重构留给收尾审查）」（`tdd/SKILL.md`「Refactoring is not part of the loop」，与 19/20/23 课同口径）；② README「装两个 agent」引述失真 → 照原文改述（同一 agent 上插件与复制文件两种方式并存才重复）；③ 第二层导语「要开 PR」→「要给提交加自动检查」（pr 在第一层）。建议改落实 11 条、否决 1 条（L54「四个 agent 各有各的安装命令」忠实于 README，系给审计员的摘录裁剪导致误报）。
- 改动文件：`lessons/0003-ai-practice-and-workbench.html`（23 处）、`reference/0003-skill-map.html`（6 处）；课程地图无需改。要点见 `NOTES.md` 第五十九次调整。

## 第 4 课已审计（2026-11-12）

- 派审计前机械自查修 11 处：术语首见（`SWEBOK`、`agent`、`DDD` 全称挪回首见、`spec`）、活动名回指（课件与参考卡的 Testing/Maintenance 短名改回第 2 课规范全名、练习 2「Design 阶段」改「Design & Architecture 阶段」）、参考卡（agent 首见、ADR 英文全称）。Evans 引文由主代理在线核对逐字属实（DDD 无本地全文，经典转引）。
- 审计结果：报「必须改 5、建议改 6、可不改 7」，总体判断「修掉必须改即达完全掌握」。技能事实底账干净：`grill-with-docs` 调用描述、词条四规则、懒创建、GLOSSARY-MAP、CONTEXT.md 旧版注逐条与技能包原文吻合；SWEBOK p48–61 覆盖五类需求活动、SE-EDU《Requirements》三条断言均核实成立。参考卡无必须改项。
- 必须改五条：贯穿例子时序矛盾（两次删除后 `kb list` 不可能还列着，症状挪到第一次删除之后）；Evans 中译中段不通+尾句漏译（重译补全）；recap「观点」→「取舍」；产出栏「位置卡」→「参考卡」；「开工读词表」从 domain-modeling 自动化清单移出（SKILL.md 第 8 行明说不算这个技能，出处是 setup 的 `domain.md`，回指第 3 课）。
- 建议改六条全落实：SE-EDU「elicitation」0 命中改「gather、analyze、specify、manage + prioritization 一节」；Entry 进词表与沙盒「不进」补一句和解；手写词条与「平时 agent 写」点破；`/domain-modeling` 手动入口口风统一；「不是 A，而是 B」12 处削到 2 处（留 lede 与表内对照）；「把这件事叫做」指代修正。主代理另按「同类一次改完」追加 3 处同款句式（L37、L55、译文开头）。
- 改动文件：`lessons/0004-domain-language-and-context.html`（30 处编辑）、`reference/0004-glossary-card.html`（2 处）；课程地图无需改。要点见 `NOTES.md` 第六十次调整。

## 第 5 课已审计（2026-11-13）

- 派审计前机械自查修 17 处：引文与出处 4（头脑风暴改引 SE-EDU 原话、SE-EDU「新需求的最大来源」加码归还课程口吻、CMU 引文页码 p5→PDF p6 并改英文原句+译文、回指第 4 课追问句对齐原课原句）；术语首见 6（agent、SWEBOK、UI、spec、seed、Implementation Decisions 对照第 8 课定名「实现决定」）；跨课回指 3（第 4 课两处「到底要不要做」→「到底做什么」，与第 5、6 课口径对齐；「后面几类留给第 6 课」→「中间三类」并把 management 去向交代清）；参考卡 4（Requirements/agent/spec/seed 首见、「derive 前需清晰理解」翻译腔）；杂项（嵌套引号改『』、弯引号、「明确结论」对齐「明确决定」）。
- 审计结果：报「必须改 5、建议改 16、可不改 9」，总体判断「修掉必须改即达完全掌握」。事实层大面积干净：grilling 的 design tree / rounds / frontier、每问附推荐答案、yes 措辞、事实派子代理不阻塞、frontier 空收尾、确认一致前不动手，与 SKILL.md 逐条对上；SWEBOK 五类 p48–61、SE-EDU 六方法与头脑风暴/原型两处原句、CMU 第 6 页引文全核实。
- 必须改五条全落实：① grilling 调用类型「用户调用」→「模型调用」（frontmatter 无 `disable-model-invocation`、第 3 课地图归「模型」；真入口是 `grill-me` 与 `grill-with-docs`，课件与参考卡两处同改）；② elicitation 定义「写成能被检验的形式」越界到 specification（SWEBOK 原句 surface candidate requirements，与第 6 课分工冲突）→「取出来、摆上桌面」+ 写成形推给第 6 课，lede「才配得上需求称号」同步改；③ 练习 3 题面补说话人（agent 问用户）；④ 练习 2 判词定「树没画全」（原答案两个判词打架；与第 6 课 quiz 4「还不是需求」口径对齐并预告）；⑤ 步骤 3 病句「某个『为什么不问』的你最想定的事」改写。
- 建议改 16 条全落实：要点：「grilling 不产文件」在步骤 5 补存档方式（导出成文件或复制保存，参考卡同步，第 6 课不再像补丁）；步骤 2「答完一轮才问下一轮」对齐 SKILL.md；「不是 A，而是 B」5 处削到 1 处；三处表演性开场删；product survey「和观察同源」无出处删；五种方法补来源层级说明；CMU 原文误拼 specifations 照抄加注；参考卡「一轮一个推荐答案」歧义改「每个问题都附一个推荐答案」。
- 改动文件：`lessons/0005-grilling.html`（30 处编辑）、`reference/0005-grilling-card.html`（9 处）、`lessons/0004-domain-language-and-context.html`（2 处最小同步）；课程地图无需改。要点见 `NOTES.md` 第六十一次调整。

## 第 7 课已审计（2026-11-13）

- 派审计前机械自查修 11 处：正文 ADR 首见（lede 补全称，删 position 节重复展开）、`spec（规格说明）`、`derived entry（派生条目）` 语序、`Considered Options`、`changelog`、`slug` 说明；参考卡 ADR 首见、Considered Options、changelog、「难难不难回滚」笔误。
- 审计结果：报「必须改 8、建议改 16、可不改 8」，总体判断「修掉必须改即达完全掌握」。事实层两条硬伤：`domain-modeling` 被写成「倾向多记」（`SKILL.md` 是 Offer ADRs sparingly、三条缺一就跳过）；「决定和理由先落盘、再谈开工」被归给 `domain-modeling`（该技能无此条，`grilling` 才有确认一致前不动手）。SWEBOK 页码更正：change control p59、footprint p61、p57 rationale 属性；「被否方案」补第 3 章 §4.6（p93，rejected decisions 与理由、条件变化可重看），设计记录归属改 ch.2 p73 + ch.3 p93。
- 必须改八条全落实，要点：① 贯穿例子与第 6 课相反（第 6 课写「本轮只打印、不存条目」进范围外，本课例子却说第 6 课定了「存成条目」）→ 例子改成「改口径」，被否方案①改「维持第 6 课口径」，第 8 课 L45 最小同步；② 练习「至少两个被否方案」与「非显而易见才记」打架 → 「有几个写几个，没有就说明为什么没有」；③ 两处技能事实错（见上）；④ 模板统一为「整篇 1–3 句；四字段是内容检查项，不是标题」；⑤ 「回第 6 课」改「回第 5 课」，接口细节标注属第 8、14 课；⑥ 位置冲突（第 4 课判 ADR 属 Design & Architecture）补和解句，management 收窄并把完整变更流程指向第 13 课；⑦ 出处错误与缺源；⑧ Nygard 命名（记录不叫 Architecture Decision）。
- 建议改十六条全落实：Status 补 `deprecated` 与 frontmatter；编号补「扫最大编号加一」；需求清单是起点不是唯一来源；`proposed` 与「还没拍板」和解；「建索引」例子换成锁定型选择；「为什么这样定」；「为开工做准备」；management 补敏捷对照；反馈提示补需求清单路径；「一字不差」改「一一对应」；Nygard 措辞；参考卡活动名补中文；「只看总结」开关同步；练习措辞；检查单第 4/6 条；表达清单 E1–E12（`不是 A 而是 B` 削到两处、`最值钱/唯一`、翻译腔、指代等）；`SOURCE-MAP.md` 补第 7 课来源条目。
- 改动文件：`lessons/0007-adr.html`（约 50 处）、`reference/0007-adr-card.html`（约 20 处）、`lessons/0008-spec.html`（1 处最小同步）、`SOURCE-MAP.md`（1 行）；课程地图第 7 课行无需改。终稿通读：遮小标题因果链成立、例子与第 6/8 课同一事实、标签配平通过。要点见 `NOTES.md` 第六十二次调整。

## 第 8 课已审计（2026-11-13）

- 派审计前机械自查修 5 类：`前置` 改「第 4–7 课」；`seam（接缝）` 首见与重复括号；CMU 07-specs 页码按第 5 课口径改 PDF p6，并同步第 13 课与两张参考卡；SWEBOK 三处页码由 p50 改 p52 / p53 / p54；来源块与参考卡同步。
- 审计结果报「必须改 13 条（去重 11 项）、建议改 29、可不改 5」，总体判断「修掉必须改即不会学错，加上操作性建议才达完全掌握」。事实层核过 to-spec 三步与模板七节、seam 三规则、`ready-for-agent` 含义、本地 tracker 路径与 Status 写法、setup 前置；CMU PDF p6、SWEBOK p52–54 逐页核过。
- 必须改全落实：① 贯穿例子明写「第 7 课随后改口径」，练习以 ADR 为准，补「只看总结」去向；② 补第 6 课产物到 spec 各节的映射（功能/非功能 → User Stories，验收标准 → Testing Decisions，接口细节与 ADR 约束 → Implementation Decisions，不做 → Out of Scope）；③ 检查单加 Testing Decisions，结论改「缺在哪一节」；④ 「只靠自己开工」改「spec + 仓库已有词表和 ADR」；⑤ 练习第 2 步把需求清单路径交给 to-spec；⑥ Out of Scope 三个示例标明「现在拍板」；⑦ 六节改六个核心小节 + Further Notes（课件、卡、地图同步）；⑧ 「不访谈」改「不做需求访谈，只确认接缝草图」；⑨ seam 通俗说法加「第 15 课会修正」；⑩ 「差别只在最后两节」改为差别不止两节；⑪ 「拆工单留给下一课」拆成第 9 / 第 10 课；⑫ SWEBOK 恢复 `might be` 与 `this KA` 范围；⑬ 入口由 `/to-spec` 改 `@to-spec`。
- 建议改落实要点：seam 高度判据、Status 放文件顶部、Testing Decisions 允许写「无」、`ready-for-agent` 引完整定义、to-spec「一次成稿」、契约降为「达成一致的基础」、删无源概括、Out of Scope 受众拆分、接缝问题与需求缺口分开归因、第 7 课别的 ADR 替换说明、第 4 课词表补正、参考卡补完整技能路径、课程地图术语家谱补 spec 行、表达层清理（口号/最高级/口语/术语首见）。
- 否决：来源块 p43–66「把第 2 章算进来」不成立（p66 仍是 printed 1-24）；整份 spec 样例不另加，用映射段落回应；SE-EDU 只在来源块挂名维持。
- 改动文件：`lessons/0008-spec.html`、`reference/0008-spec-card.html`、`reference/course-map.html`（术语家谱 1 行）、`lessons/0013-triage.html` 与 `reference/0013-triage-card.html`（CMU 页码同步）。终稿标签配平通过，与第 6、7、9、10 课例子同一事实。

## 第 9 课已审计（2026-11-13）

- 派审计前机械自查修 9 处：目标栏 `预测式（predictive）` 改 `predictive（预测式）`；`开发周期（SDLC）` 补全称；`waterfall（瀑布式，顺序式 sequential）` 拆开；`每一圈都走完` 改 `可以走完`；Scrum 按 SE-EDU 补计划会与「一周到一个月」；连续谱引文页码 p9-9 改 p9-8；五步链路第一步 `grilling` 改 `grill-with-docs`；next 的 `tracer-bullet` 补中文；参考卡术语语序与 `product backlog` 首见中文同步。
- 审计结果：报「必须改 5、建议改 28、可不改 5」，总体判断「修掉必须改能读懂并做出表，完全掌握还需建议改里的判据与事实层修正」。事实层核过五步链路与第 3 课及五个 `SKILL.md`、SWEBOK ch.9 p9-8 / ch.10 p10-2、p10-5~6、p10-8、p10-10、SE-EDU 三模型机制；CMU 03-project-planning 全文无 risk，原「计划与风险」错。
- 必须改全落实：① 四个变量在正文、练习、检查单、recap 四处统一，并补四条判据；② 删「靠下一张工单补需求」的假机制，改「回 grilling / to-spec 补再重拆」；③ 练习明写五列表头；④ `不是 A，而是 B` 削到 1 处；⑤ SWEBOK 引文去自造「一串点」，删「大多落在中间」。
- 建议改 28 条全落实：练习反例拆成需求 / 反馈两个变量；迭代补适用判据与贯穿例子、敏捷补 sprint backlog；明写「选型由人拍板、agent 只证前后一致」；参考卡补过程模型定义、检查单与正文同步；表达层删预告、夸赞、生造词与同义反复。事实层补第 3 课例外、`一个人 + 一套 agent 编排`、瀑布可重叠的限定、敏捷归类、12207 / 33000 范围、CMU 延伸、ch.10 p10-8 adaptation 出处。逻辑层修正位置节设问、SE-EDU 说法、「回上一节」、next 的「拆多深」承诺。
- 复查（同一审计会话）又报「必须改 3、建议改 13」，必须改全修：正文与 next 的「拆多深」口径统一、删「反馈落回下一张工单」的跨工单机制、参考卡迭代位置与正文统一；建议改 13 条全落实（偏迭代标签、风险落到三选一、「备注」列名与五条验收、12207/33000 分页、第 5 课回指拆分、第一圈引用口径、PDF 页码表、卡片补提交、沙盒第 10 课与练习选型的关系）。
- 改动文件：`lessons/0009-process-models.html`（整篇重写）、`reference/0009-process-card.html`（整篇重写）、`SOURCE-MAP.md`（模块 6 的 SWEBOK 行补核实页）；课程地图无需改。要点见 `NOTES.md` 第六十四次调整。

## 第 10 课已审计（2026-11-16）

- 派审计前机械自查修 20 处：术语首见（`spec`、`agent`、`SWEBOK`、`schema`、`API`、`UI`、`ADR`、`prefactor`、`issue tracker`、`expand-contract`、`tracer bullet`/`walking skeleton` 目标栏）、`layer` 改「层」、`gate 它` 统一改「挡住它」；SE-EDU 里程碑那句原为「」里夹中文改写，改为忠实转述；`/setup-matt-pocock-skills` 改 `@`；`这里 front 的`、`人还拍板`、`一张一卡/块文件` 三处笔误；参考卡同步 WBS 全称、术语首见与措辞。
- 审计结果：报「必须改 8、建议改 23、可不改 5」，总体判断「修掉必须改能读懂核心概念并按步骤产出工单；完全掌握还需建议改里的 WBS 工时、经典转引、验收标准归属与沙盒检查单四类」。事实层核过：`to-tickets` 五步、quiz 三问、本地模板四字段、依赖序发布、`ready-for-agent` 标签与无原生关系回退、expand-contract 的分支、slug `prefactor`/ADR/GLOSSARY 行为；第 8–11 课贯穿例子主体同一事实。
- 必须改八条全落实：① 核心场景首句补谓语；② blocking edge 方向说反（「它做完之前那些才可能开工」）改「那些工单做完之前，这张不能开工」，参考卡同步；③ quiz 四问改三问（粒度 / 阻塞边 / 合并拆分），wide refactor 只留在人拍板四件；④ 「第一张就是 tracer bullet」与 prefactor 先行冲突 → 01 可能是 prefactor，第一张「能演示」的切片才是曳光弹，标尺与练习同改；⑤ 依赖图在第 9 课 next、课程地图、第 11 课四处承诺却零处产出 → 练习加第 6 步，按 `Blocked by` 画图存 `.scratch/<feature>/dependency.md`，元信息与地图同步；⑥ 贯穿例子回到第 9 课「第一圈不带引用」口径，第一张切片去掉引用、后续切片补引用，并把「超时」改「500 毫秒内返回」；⑦ 层清单三处不一致 → 统一为「条目格式、摘要逻辑、存储、命令、测试」，技能原文的通用词单独说明；⑧ 工单字段补 `What to build`、`Blocked by: None (can start immediately)`、`Status`、可勾验收标准，并写明验收标准来自 spec 的 User Stories / Testing Decisions。
- 建议改 23 条全落实，要点：expand-contract 由「标准做法」改「to-tickets 给的做法」并补共享集成分支退路；WBS 补工时列与 SWEBOK ch.9 §1.2（printed 9-6~9-7）；经典出处标「本地无全文、经典转引」；「Make the change easy」改「技能引用的一句话」、删「WBS 时代」推断；五步流程编号对回 SKILL.md；「机械劳动」拆成自动化与待核对；检查单给出技能路径与课程仓库 `courseware/` 路径；练习输入补 spec 路径与 `@to-tickets`；「回 tracer 那段再拆」补「从一条 user story 写出每层、删到能演示」三步；里程碑从「算出来 / 低阻塞」改「判断 / 从 frontier 挑」；真实 tracker 补标签与 `Blocked by` 回退；规则来源区分本课两条与技能新增两条；frontier 双义提醒从三次降到两次；卡片的「阻塞解除」改「不再挡着下游」；表达层削「不是 A，而是 B」到 2 处、删表演性开场与夸赞形容、修「图 / 可点 / 扩出爆炸半径 / 尺子量你」等搭配；tracer bullet 中文名统一为「曳光弹」（第 3、9、10、20、34 课与两张参考卡、`SOURCE-MAP.md` 同步）；卡片补 GOOS 全称、blast radius/prefactor 中文，课程地图「带走」与术语家谱补第 10 课两行。
- 跨课最小同步：第 9 课「超时」改「500 毫秒内返回」；第 11 课 tracer bullet 例去掉「带引用」、改「摘要截断的位置」、练习改「第一张能演示的切片」。
- 整改稿交同一审计会话复查，报「必须改 1、建议改 13」：必须改是第 11 课 L50 / L82 仍把「引用定位」列为第一张的假设，与第一张不带引用矛盾（已改「摘要截断的位置」）；建议改全落实——WBS 四样口径统一、依赖图改存 `.scratch/<feature>/dependency.md`（与 `issues/` 并列，不占工单编号）、练习卡住时指回「练习最后一段」、recap 统一为「四件拍板 + 验收标准/阻塞边两样核对」、L95 补「能演示的」、SWEBOK 改「可能形成」、规则标「译自 `SKILL.md`」、验收标准来源移出括号、依赖图用途改「第 11 课 PERT / 关键路径」、第 4 步补「没它真的会坏吗」、卡片 first-occurrence 补 prefactor 中文、三处小词、课程地图 frontier 补第 12 课第三种用法。复查总体判断：修掉这条必须改即达完全掌握。
- 改动文件：`lessons/0010-vertical-slice.html`（约 50 处）、`reference/0010-tickets-card.html`（约 20 处）、`reference/course-map.html`（第 10 课行 + 术语家谱 4 行）、`lessons/0009-process-models.html`（3 处）、`lessons/0011-estimation.html`（5 处）、`lessons/0020-tdd-red-green.html`、`reference/0020-tdd-card.html`、`lessons/0034-capstone-migration.html`（4 处）、`reference/0034-capstone-card.html`、`SOURCE-MAP.md`。终稿标签配平通过；遮小标题因果链成立；与第 8、9、11 课例子同一事实。

## 第 11 课已审计（2026-11-16）

- 派审计前机械自查修 16 处：术语首见（`spec`、`frontier`、`buffer`、`SWEBOK`、`agent`、`WBS`、`tracer bullet`、`PERT chart`/`GQM` 全称、`backlog`、`UI`、`issue tracker`、`ticket`），目标栏与 lede 的重复注释去重，参考卡同步；主代理本地预核 SWEBOK p9-9 / p15-7 / p15-15 / p9-15~17、SE-EDU WBS/Buffers/PERT、CMU 的 Hofstadter / conformity / 拆小再估 / Kaner & Bond / GQM / Goodhart / McNamara。
- 首轮报「必须改 12、建议改 21、可不改 8」，总体判断「修掉必须改能不做错并做出结构完整的估算；完全掌握还要产物闭环组」。必须改的硬伤：两幅 xkcd 凭记忆改写（实际是 1658 翻倍法、612 十五分钟/六天/三十秒）；anchoring 写成幸存者偏差；「三股力都往小拉」与 Goodhart 写大自保矛盾；`actual/estimate` 分母未定义；进度公式比例加天数；练习第 5 步「做完第一张」与不写代码、第 23 课冲突；「前 3 张才是第一个能演示版本」与第 10 课冲突；「拆解不为排序只为估」与第 10 课主问题冲突；01 号可能是 prefactor；总区间/buffer 无算法；wayfinder 的 task 例外被写成全称判断。
- 复查报「必须改 2」：① 「不取中」与「比值用中点」打架 → 明确「中点只用于台账比值，不对外报」；② 建行时要求填完成日期与第 23 课回填冲突 → 建行只填工单号/估算日期/类型/区间/假设，完成日期与实际值留空。两条已修，并同步落实建议改 13 条（三股力计数、conformity 说明、WBS/PERT/GQM 代价、Q1 问法、卡片 P/I/O/V、课头产出、`SOURCE-MAP` decomposition 四步、Scrum 框架、删「比临时建模快」、人拍板补台账核对、next 补 research 例外与「把问题说尖」、关键路径统一用悲观值）。
- 跨课最小同步：第 12 课 lede 补 `ticket（决策单）`，与第 11 课 next 的别名接上。
- 改动文件：`lessons/0011-estimation.html`（约 40 处）、`reference/0011-estimation-card.html`（约 20 处）、`reference/course-map.html`（第 11 课行 + 术语家谱 1 行）、`SOURCE-MAP.md`（第 6 节 1 行）、`lessons/0012-wayfinder.html`（1 处）。要点见 `NOTES.md` 第六十六次调整。

## 第 12 课已审计（2026-11-17）

- 派审计前机械自查修 20 余处：术语首见（`spec`、`agent`、`issue tracker`、`triage`、`SWEBOK`、`API`、`UI`、`resolution`、`assign`、`effort`、`wayfinder`）、括号顺序（`index/store`、`gist`、`chart the map`）、`fog of war` 统一「战争迷雾」、`Out of scope` 统一「范围外」、`session`→「会话」；笔误（「才棋局」「区清楚」「把网页转 PDF 转换做出来」）；第 9 课对照表原名回指；CMU 03「风险」在第 11、12 课与 `SOURCE-MAP` 三处一起改；转述第 11 课的「总体 + 逐迭代」改回「里程碑级粗估 + 单张细估」。
- 首轮报「必须改 14、建议改 14、可不改 6」，总体判断「概念讲清了，产物没落地」。事实层核过 `wayfinder` 用户调用、建图/走图、四类型 HITL/AFK、index 非 store、frontier、一次会话一张、assign 先于工作、无雾则停、out of scope 永不毕业；第 11 课 next、第 13 课 position 一致；沙盒 tracker 有 Wayfinding operations。硬伤四处：练习把能说尖的问题放进雾、五段地图只产出两段、纸面练与真建图口径打架、贯穿例子先说「做什么没定」后说「目的地明确」。另有 SWEBOK 描述句被称「标准」、SE-EDU 引文漏原因、「交给 to-spec 开工」错、第 5 课 frontier 释义漏「前置已定」、70% 与「两条主流的路」无来源、tracker 物理形态与 sandbox 不符、无雾去向两个答案。
- 必须改 14 条全落实，做法是**整篇重写课件与参考卡**：练习改五栏、雾例重换、能说清的另立 ticket、补划范围与记账、检查单 8 条；纸面稿与真建图分开；SWEBOK 改「主流、描述性（typically；Foreword PDF p26）」；SE-EDU 按第 10 课补原因；to-spec→to-tickets；第 5 课 frontier 同步第 10 课两处与卡；越界关闭不进 Decisions so far；删 70%、两条路标经验判断、spike 改 prototype；补本地 markdown tracker 的 map.md/issues/Type/Status/Blocked by 与三类 ticket 落点；无雾去向改为「小改动按第 3 课例外直接 implement / 拆单走 spec → to-tickets」。
- 建议改 14 条全落实：CMU 引 p63 里程碑句、决策图与估算关系、人拍板四件、走图补点名与失效 ticket、无雾问用户、task 无技能、Notes/Decisions 正文、前置第 5、8、10、11 课、课程地图第 12 课行与术语家谱、`SOURCE-MAP` 的 p9-9/Foreword/CMU。表达层「不是 A 而是 B」清零，删生造词（可作业、摸前沿、毕业新雾、低清图、读外、那个槽、工单图）。
- **复查报「必须改 2」并已修**：走图改成「先定解哪张（点名优先，否则 frontier 第一张）再 assign」；纸面稿改存 `.scratch/multi-source/paper-draft.md`，并说明真建另建 `map.md` 与子 ticket，参考卡同步；另删 L115 半句。复查确认 14 条教学要求全部落地。
- 改动文件：`lessons/0012-wayfinder.html`、`reference/0012-wayfinder-card.html`、`lessons/0010-vertical-slice.html`（frontier 2 处）、`lessons/0011-estimation.html`（CMU 延伸 + 错字）、`reference/course-map.html`、`SOURCE-MAP.md`。要点见 `NOTES.md` 第六十七次调整。

## 第 13 课已审计（2026-11-17）

- 派审计前机械自查约 20 处：术语首见（`SRE`、`on-call`、`spec`、`issue tracker`、`triage notes`、`PR`、`CLI`、`GUI`、`adapter`、`ADR`、`diff`）、`escalate` 与 brief 四原则的括号顺序、`agent brief` 统一、拆嵌套括号；课程地图术语家谱补 category/state role 与 triage notes、读物栏补《Being On-Call》；`SOURCE-MAP` 模块 6 补 SWEBOK ch.1 与两条 Google SRE 来源。
- 首轮报「必须改 10、建议改 18、可不改 6」，总体判断「修掉必须改不会学错，完全掌握还要建议改里的操作闭环」。十处硬伤：第 13 课位置与第 3 课技能表 Maintenance / Requirements 冲突；SWEBOK validation 被写成「进入规格之前」并把 §3.1/§7.3 属性混进 §5；change control 丢了计划驱动限定与完整流程；把 SWEBOK 写成「要求/态度很硬」；「CLI 代码还没写」与沙盒、第 14 课、课文场景三处矛盾；「入库只吃本地 Markdown 文件」与 `kb add` 不符；外部 PR 被写成无条件进 triage；快速通道漏「问要不要写 brief」；练习没给 category 落点、文件名、标题；「比较急」写成不能当优先级。
- 必须改全落实：SWEBOK 改「五类活动 p48–61；validation §5 PDF p57–58（审可审的形式）；change control §6.2 PDF p59（计划驱动项目、影响分析可选、接受/拒绝/延后、通知、跟踪到关闭；敏捷 implicit 进 backlog）；Foreword PDF p26 非规范」，同步四份文件；沙盒事实改为 `kb search` 只打印 id/标题、`kb add` 只有标题+正文、`.out-of-scope/` 还没建；PR 改条件句；快速通道补 brief；练习补文件名、标题、`Category:` 本课约定；「比较急」拆成严重度与排期。
- 建议改 18 条基本全落实：CMU 引文回第 8 课译文；SRE 删「谁去止血/谁去查因」「不吃修得快」「情绪驱动」；AI 声明覆盖评论与 issue；补 `@triage` 入口与手工/技能分工；报告者只提供现象、维护者拍产品决定；指到两份模板；spec 可当 brief；wontfix 与地图 Out of scope 分产物；反馈分三类；`GLOSSARY` 条件读取；自动化清单改「取证和整理」；补需求/变更候选映射；执行在第 23 课；HTTP adapter 未做；`SkillConfig` 示例；GitHub/GitLab 经验判断；三桶入口。
- 复查报「必须改 4」并已修：严重度/排期落进 notes「已确认」；notes/brief 落 `## Comments` 下并用 `###`；学员自己登记的两条 issue 也带 AI 声明；删重复问「哪条查询」。
- 终查无必须改，G1–G3 同步：`Category:` 与 `@triage` 改写「角色名」并说明沙盒无标签；参考卡补 PR 状态读数、`来源可查`、validation 口径；验证结论与两个检查结论固定落到 notes 第一行和 `## Comments` 下的 `### Scope Checks`；表达层清旧词。
- 改动文件：`lessons/0013-triage.html`（约 60 处）、`reference/0013-triage-card.html`（约 25 处）、`reference/course-map.html`（第 13 课术语家谱）、`SOURCE-MAP.md`（模块 6 新增 3 行）。终稿标签配平与互链通过；与第 8、12、14 课同一事实。要点见 `NOTES.md` 第六十八次调整。

## 第 14 课已审计（2026-11-17）

- 派审计前机械自查修 9 处：`spec`、`SWEBOK`、`adapter`、`CLI`、`docstring`、`KPI`、`pytest` 首见中文，`deletion test` 首见格式与 `秘密（secret）` 语序；SWEBOK 设计定义页码拆成 PDF p85（定义）/ p86（设计原则）。MIT 6.031 Reading 10/11 三条引文逐字核过。
- 首轮报「必须改 11、建议改 30、可不改 6」，总体判断「概念骨架立得住，但操作闭环断、核心概念会学反」。硬伤：沙盒 `master` 已是第 15 课完成态而课件讲第一版 `KnowledgeStore`；把 rep invariant 说成「接口的一部分」（MIT R11 原文相反）；「匹配规则」既当秘密又当契约；练习给「store 与 `kb.jsonl` 一致」当接口不变量（不在 R 上、无法公开断言、对内存 adapter 不成立）；草图的 `add -> id` 与代码不符；把「测试越接口」直接等同于 rep exposure；Parnas 文献号 [32] 串章（第 3 章是 [17]）；depth 与行数比三套说法打架；草图无落点；`domain-modeling` 的 ADR 描述失真；第 15 课仍假设旧沙盒。
- 整改做法是**整篇重写正文与参考卡**：不变量分两层（interface invariant 进草图、能用公开操作断言；rep invariant 写 rep 旁普通注释、由 `checkRep()` 检查；AF 只作文档）；「匹配算法 / 匹配语义」「id 的生成机制 / id 的语义」各拆一对；不变量定义分「MIT 的抽象状态定义」与「操作边界检查点」；练习第 1 步切到 `lesson-14-start`，草图落 `.scratch/storage-module/interface-sketch.md`，新设「待改的接口问题」下分「表示暴露」「接口缺口」，并加最小 `_check_rep()`；反馈意见分三类。
- 复查两轮报「必须改 8」「必须改 4」。第二轮硬伤：RI/AF 的沙盒例子不在 R 上、AF 被说成「由代码强制」；「任何时刻」与检查点两套定义并存；练习只写注释却要求「由代码守」；接口缺口无落点；第 15 课把后置条件叫接口不变量；id 规则跨课矛盾；depth 归属坐实到 Ousterhout。第三轮：接口不变量与行为契约在 14、15 混回；表示暴露与接口缺口混回；第 15 课参考卡未同步 id；`StorageError` 误指第 22 课。全部落实。
- 终查确认两个跨文件残留：沙盒 `master` 的 `Store` docstring 仍把 id 生成机制写成 port 契约、`_check_rep()` 在 14→15 断掉。已修：port 只承诺 id 语义（非空、唯一、稳定），生成机制写进两个 adapter 的 docstring，两个 adapter 补 `_check_rep()`（沙盒 commit `7f695a5`）；第 15 课第 2 步明确把 `_check_rep()` 搬进 adapter。跨课最小同步：第 19 课 port oracle 列表改「id 非空、唯一且稳定」并标明 `eNNNN` 是两个 adapter 的共同约定、不是 port 承诺；第 26、28 课与参考卡 0020/0026 的「id 规则」一并改口。
- 沙盒：标签 `lesson-14-start` 打在 `b2162ce`（第一版骨架）；`master` HEAD `49f4388`（第 15 课完成态 + 第 14 课修复 `7f695a5` + 第 15 课审计的 port docstring 澄清 `f7fd50a` / `49f4388`）；README 注明起点与完成态（`6f2b240`）。练习分支约定 `lesson14-practice` / `lesson15-practice`。
- 改动文件：`lessons/0014-deep-modules.html`（整篇重写）、`reference/0014-deep-modules-card.html`（整篇重写）、`lessons/0015-seams-adapters.html`（约 12 处）、`reference/0015-seams-adapters-card.html`（3 处）、`lessons/0019-pytest-test-design.html`（3 处）、`lessons/0026-tight-feedback-loop.html`（1 处）、`lessons/0028-architecture-improvement.html`（2 处）、`reference/0020-tdd-card.html`、`reference/0026-red-command-card.html`、`reference/course-map.html`（第 14 课产出、术语家谱、Ousterhout 版本）、`SOURCE-MAP.md`（模块 3 三条）、沙盒 `kb/storage.py` 与 `README.md`。终稿标签配平通过；遮小标题因果链成立；表达层「不是 A 而是 B」剩 1 处、破折号从 51 降到 20。

## 第 34 课练习的留档约定

- 演练记录 `.scratch/migration-3401/notes.md`：每站一行卡点（哪一站、卡了什么、怎么解的），末节 retro 收尾。
- 演练产物：`.scratch/http-adapter/`（spec、issues、review-report.md）+ `feature/http-adapter` 分支实现合回 `master` + README 发布说明（含已知限制：只监听 127.0.0.1、无鉴权、错误只给通用消息加关联编号）+ 可选 `git tag v0.1.0`。
- 迁移计划 `.scratch/migration-3401/migration-plan.md`：差异盘点七行每行填「对流程的影响」+ 六节；引用路径不复制、决定带理由、写给零上下文读者。
- 反馈记录 `.scratch/migration-3401/plan-review.md`：两轮零上下文接手人反馈与处置。
- 收尾提交（反馈回路之后）：README+tag 一笔、`.scratch/` 记录一笔；`git status` 干净；主干 `master`。knowledge-pet 全程只读。

## 审计排期（已完成）

- 已审计：**第 1–34 课全部审完，没有待审计课。** 最后一批第 15 课于 2026-11-17 审完，报告与整改见 `NOTES.md` 第七十次调整。
- 下面这条提示词要求保留作历史记录：以后再新增课，仍按 `COURSE-STANDARD.md`「写完一课」的流程重写排期，不要照搬这一批的提示词。
- 每批的审计提示词按 `COURSE-STANDARD.md`「写完一课」的提示词要点写，**必须交代**：① 参考资料已本地化（`courseware/`，不联网；本机已核实 brooks PDF 等在位）；② 技能包全目录可读——当前用户主目录的 `.agents\skills\`（两台机器用户名不同；提示词里写主代理现场解析后的具体路径）；③ 表达判断按规范用 shuorenhua「只标问题」＋十条清单并列（shuorenhua 在当前用户主目录的 `.config\opencode\skills\shuorenhua\`，主代理现场解析；未装则只用十条）。点名的技能按每课内容现选（地图技能栏 + 「AI + Matt」节落地的技能 + 正文点到的技能），不要照抄上一课的审计提示词；技能栏「—」的课明说无独立技能，正文点到的技能仍逐一对原文。

## 待确认

- **~~沙盒代码缺口~~（2026-11-18 销账）**：用户要求先把代码恢复到新沙盒再推送。做法：旧本地沙盒删除前打成 `_git-archive\se-course-sandbox-legacy-2026-11-18.bundle`（6 个提交 + 标签 `lesson-14-start`，9.8 KB），删目录后 `gh repo clone` 私有仓库，只把 `kb/` 代码搬上去——第一个提交 `5544243` 是 b2162ce 的骨架（`KnowledgeStore` 直出 `entries`、`kb add` / `kb search`、落 `kb.jsonl`，`.gitignore` 补回 `kb.jsonl`）并打 `lesson-14-start`；第二个提交 `fa76ccd` 是 49f4388 的完成态（`Store` port + `JsonlStore` / `InMemoryStore` + `_check_rep()` + 再导出）停在 `master`。核对清单逐条过：`kb search` 只打印 id 和标题、条目恰好四个键、id 非空唯一稳定、`add` / `search` 无调用先后要求、错误模式留给第 23 课。旧历史的 hash 不再当基线；备份 bundle 确认不需要后可删。
- **~~OpenCode 技能入口写法待全课程统一~~（2026-11-17 销账）**：已按 `@skill-id` 全课程统一，共改 135 处技能提及，涉及 12 个课件、11 张参考卡与课程地图；`/clear`、`/compact`、`/new` 这些 OpenCode 真命令保留斜杠。第 3 课表格的调用类型、第 3 课参考卡的「你做什么」、`COURSE-STANDARD.md` 的调用类型条目同步改口。**第 32 课是唯一例外**：那张对照表专门比较「技能文档的写法」（`/clear`、`/compact`、`/handoff`）与「OpenCode 里的对应动作」，中间一栏保持斜杠并写明了这是技能文档的记法。以后新增课按 `@` 写，不新增斜杠入口。
- **两轴命名已定案（2026-11-03）**：规范轴（Standards）/ 工单轴（Spec），第 25 课定死用法，第 23 课两处措辞已同步。以后统一用这两个名字，不要再引入别名。
- **第 19 课留下的契约问题**：`Store` 的「关键词」是子串还是整词、空 query 返回什么，由学习者在练习里拍板并写进 docstring；课件给的是示例决定（子串 + 空列表），不是标准答案。id 到 10000 条之后（`e9999 → e10000`）的宽度没定；空白串 query、错误模式（现在不抛异常）也没定。第 34 课站 1 把这些列为「在这一站拍掉」的候选，学习者没做演练就仍未决。
- **第 20 课练习添的两组契约问题**：`delete` 删不到的返回值、返回值形状、id 复用（同样是示例决定，别把示例当契约），以及「删光后重开 id 从哪排」（计数痕迹被删除抹掉，三条出路见第 20 课循环四，课件只当契约空洞处理，未给答案）。
- **第 22 课练习添的一组契约问题**：`JsonlStore` 写文件失败（权限、磁盘满）的错误行为——抛什么、返回什么——契约没定，课件明写「先拍板写进契约再断言，拍不了记进未决问题」。**第 23 课练习正是把它拍板掉**：示例决定是三要素（失败抛 `StorageError` 带原异常 / 失败无返回值、成功路径仍返回副本 / 不留半截条目），学习者可照可改，拍完写进 `Store` docstring。第 34 课站 1 的错误映射推荐答案以它为前提；没做 23 课练习的人按 33 课参考卡样例拍。
- **各课练习的留档约定**（第 24–33 课）仍见 `NOTES.md` 对应条目与本文件历史版本要点：lint 豁免写理由（24）、裁决与实验分支纪律（25）、盲诊断与注入（26）、四份诊断记录与撤修复实验（27）、git status 白名单含 GLOSSARY/ADR（28）、演练目录可复用（29）、记录留主分支原型进分支（30）、研究笔记单文件四要素（31）、handoff 四条核对（32）、责任清单七列与脱敏占位（33）。这些约定不因课程完结失效；第 34 课演练遇到缺口时按对应退路走。
- 沙盒 `GLOSSARY.md`、`docs/adr/`、`.scratch/`、`.out-of-scope/` 仍懒创建，由各课练习带出，不要提前建。沙盒分支名是 `master`，远端为私有仓库 `telecomshy/se-course-sandbox`（2026-11-17 建，用于两台机器同步；第 24 课的「加远端」练习已改成「确认远端」）。
- ~~技能包目录数两台机器不一致~~（已销账，2026-11-12 第 3 课审计核实）：本机 `.agents\skills\` 78 个目录 = Matt 技能恰 38 个（与三层表逐一相符）+ 非 Matt 40 个（26 个 arkcli-*、8 个 shy-*、find-skills、skill-creator、obsidian-markdown、playwriter、resolving-merge-conflicts、software-factory）；课件 L306 注释已覆盖混入情况，教学内容不改。目录总数随安装来源漂移，以后审计以「Matt 技能 = 三层表 38 个」为口径，不按目录总数。

> AI生成
