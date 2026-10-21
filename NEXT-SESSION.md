# 下一会话交接

> 用途：把课程状态从当前会话交接到一个新会话，避免重读整段对话。只记状态和下一课，不复制课程内容。
> **OpenCode 会自动读取根目录的 `AGENTS.md`；它已经要求新会话先读本文件、`COURSE-STANDARD.md` 和 `SOURCE-MAP.md`。**

## 先读这些（按顺序）

1. `AGENTS.md`：会话规则（OpenCode 自动加载，不用手动提醒）。
2. `NEXT-SESSION.md`：本文件，当前进度与下一课。
3. `COURSE-STANDARD.md`：五段结构、标准/主流/取舍、理论来源硬约束。
4. `SOURCE-MAP.md`：八个活动对应哪些本地课件、章节/页码；写课前必须查。
5. `MISSION.md`：课程目标、成功标准、约束、范围。
6. `NOTES.md`：用户偏好、多次调整、环境说明。
7. `reference/course-map.html`：34 节 / 7 模块的当前地图（v3）。
8. `CURRICULUM-REVIEW.md`：为什么这样排；文末「十、二次调整」是结构变更记录。
9. `lessons/0001-*.html` 到 `0004-*.html`：写法样例；第 3 课已按「为什么 → 安装 → 五步 → 全表」重写，第 4 课按五段结构写。
10. `reference/0001-three-questions.html`、`0002-se-landscape.html`、`0003-skill-map.html`、`0004-glossary-card.html`：参考卡。
11. `courseware/README.md`：本地课件的目录和来源。

## 当前状态

- 课程骨架：34 节 / 7 模块。M0 三节已完成：为什么学、包含什么、怎么练。
- `AGENTS.md` 已创建，OpenCode 会自动读取；新会话不需要用户手动要求读规范。
- `SOURCE-MAP.md` 已创建：八个活动都有对应的本地理论来源、行业做法来源、章节/页码和缺口。
- 技能包已装最新版（2026-10-20）：全局 `C:\Users\admin\.agents\skills\`，共 51 个技能目录，其中 Matt 仓库 38 个（engineering 20、productivity 7、misc 4、in-progress 7）；新增 `pr`、`chief-of-staff`。`domain-modeling` 已从 `CONTEXT.md` 改为 `GLOSSARY.md` / `GLOSSARY-MAP.md`，格式文件为 `GLOSSARY-FORMAT.md`。旧技能目录备份在 `C:\Users\admin\AppData\Local\Temp\opencode\skills-backup-20261020`。
- M1 第 4 课已按 `COURSE-STANDARD.md` 重写：标题「领域语言：需求的前置条件」，先定位 Requirements，再讲概念、行业做法、AI + Matt，最后练习；理论来源写到 SWEBOK ch1 p48–61、Evans ch2、SE-EDU Requirements。全文文件名已同步为 `GLOSSARY.md`；参考卡改名为 `reference/0004-glossary-card.html`。
- M1 第 5 课已完成：`lessons/0005-grilling.html`、`reference/0005-grilling-card.html`。标题「逼问：把模糊想法问成决定」，按五段结构写；理论来源 SWEBOK ch1 p48–61（elicitation）、SE-EDU《Gathering Requirements》（访谈 / 观察 / 问卷 / 焦点小组 / 头脑风暴 / 原型）、CMU 17-313《07-specs》；实践技能 `grilling`（design tree / rounds / frontier，事实归 agent、决策归人）。课程地图第 5 课已加链接与术语家谱；第 4 课 next 段标题已同步。
- M1 第 6 课已完成：`lessons/0006-requirements.html`、`reference/0006-requirements-card.html`。标题「需求工程：来源、验收标准与非功能需求」，按五段结构写；理论来源 SWEBOK v4 第 1 章 p43–66（需求定义、functional / non-functional 分类、perfect technology filter、需求品格、BDD 验收标准）、SE-EDU《Specifying Requirements》（conditions of satisfaction、user story 加非功能需求）、CMU 17-313《07-specs》（spec 是契约）；本课无独立技能，回指 `grilling` 产物当输入、`domain-modeling` 的 `GLOSSARY.md` 校验术语。课程地图第 6 课已加链接；第 5 课 next 段标题已同步。
- M1 第 7 课已完成：`lessons/0007-adr.html`、`reference/0007-adr-card.html`。标题「ADR：什么决定值得记下来」，按五段结构写；理论来源 SWEBOK 第 1 章 p57–62（requirements management / change control，为「需求会变」立据）、Michael Nygard《Documenting Architecture Decisions》（2011，线上无本地全文）；实践技能 `domain-modeling` 的 `ADR-FORMAT.md`（三判据 + 极简模板 + `docs/adr/` 目录约定），贯穿例子是「总结产物存不存、怎么进索引」，含两个被否方案。课程地图第 7 课已加链接、术语家谱加 ADR 一行；第 6 课 next 段标题已同步。
- 第 3 课结构调整（2026-10-21，第十七次，用户提出）：现为「为什么学软件工程要装技能包（呼应第 1 课判断成本、第 2 课八个活动）→ 动手安装与初始化（删掉「两层」讲解表）→ 场景与五步合并一节（先直写的病，再五步的药，七问当场落地）→ 它不替你做什么 → 38 技能三层全表」。安装命令、产物表、四种调用方式、练习均未动。安装段参考 `https://github.com/mattpocock/skills` 的 README，给出 `npx skills@latest add mattpocock/skills -a opencode -g -s "*"` 和对话式安装两种方式；生成文件只讲用途，理论留到第 4、7、8、13 课。
- 写作原则：软件工程理论是主线，AI + 技能包是实践；课件是一篇通俗、具体、有逻辑顺序的文章，先场景后概念，场景优先软件领域的实际工作场景（可以是构造的，但要像真的会发生），不滥用生活比喻，找不到合适场景就直接讲问题；段落之间有过渡，标题是叙事节拍；表格只做对照，不能替代推理；遮住小标题仍能读出前后因果。修改课件时先通读本课全文、前后相关课和参考卡，不要只改被指出的局部。
- 沙盒：`D:\code\my_projects\se-course-sandbox`，迷你知识库 CLI + 薄 HTTP adapter。已存在 `AGENTS.md`、`docs/agents/domain.md`、`docs/agents/issue-tracker.md`；仍缺 `docs/agents/triage-labels.md`（标签写进了 `issue-tracker.md`）。第 7 课练习会懒创建 `docs/adr/`（第一条 ADR）；`GLOSSARY.md`、`.scratch/` 仍留到各自课时懒创建。第 13 课（triage）之前补 `triage-labels.md`，或改第 3 课产物清单。

## 下一课：第 8 课「Spec：从共识到可执行」

- 模块：M1 需求与语言（对应第 2 课的 Requirements）。
- 位置：第 4、5、6、7 课攒下的词表（GLOSSARY）、需求清单、ADR 这份「共识」，是第 8 课的原料；第 8 课用 to-spec 把它合成一份 spec 发布到项目 tracker，给 agent 当开工依据。
- 目标：能把前几课的共识合成一份可发布的 spec，带 `ready-for-agent` 标签，落到 tracker。
- 理论来源（至少一条写进课文，带章节/页码）：SWEBOK v4 第 1 章（specification，p43–56 一带）；CMU 17-313《07-specs》（spec 是契约，本课可回指第 6 课已用）；SE-EDU《Specifying Requirements》（已在第 6 课用过，回指）。优先本地路径见 `SOURCE-MAP.md`。
- 实践来源：`to-spec`（用户调用，`disable-model-invocation`，需 tracker 已 setup——沙盒 `docs/agents/issue-tracker.md` 已存在）；写 spec 时先 sketch seams（测试的接缝）、用项目 GLOSSARY 词汇、遵守已落盘的 ADR。
- 五段结构：位置 → 问题与概念（spec 是「我们能开工的依据」：可执行、可评审、不是又一份需求文档）→ 行业做法（spec 结构：Problem/Solution/User Stories/Implementation Decisions/Testing Decisions/Out of Scope；为什么要 Out of Scope）→ AI + Matt 怎么落地（to-spec 流程、seam 判断、发布与 ready-for-agent 标签；哪步仍由人拍板）→ 练习与反馈（在沙盒发一篇 spec）。
- 风格：35–45 分钟；to-spec 模板字段较多，注意「表格/列表前后有引导与收束、不替代推理」。
- 产出：`lessons/0008-spec.html`、`reference/0008-spec-card.html`，并更新课程地图、`NEXT-SESSION.md`、`NOTES.md`。
- 不要写第 9 课。

## 待确认

- 2026-10-21 第 3 课结构反馈已处理（第十七次调整）：场景并入五步节、安装段去表，回答了本条前两问；全表密度若后续反馈仍偏密，再考虑拆到参考卡。
- 第 3 课的 38 技能清单按 2026-10 最新版整理；如果上游再改，以 `SKILL.md` 和 README 为准。
- 沙盒是否要现在补 `docs/agents/triage-labels.md`；如果不补，第 3 课的产物清单和第 13 课要注明标签写在 `issue-tracker.md`。
- 沙盒的 `docs/agents/domain.md` 仍是旧版写法（`CONTEXT.md` / `CONTEXT-MAP.md`）。下次进沙盒先重跑 `/setup-matt-pocock-skills`，或手动同步成 `GLOSSARY.md` / `GLOSSARY-MAP.md`，否则 agent 会按旧文件名找领域文档。
- `SOURCE-MAP.md` 的章节/页码是否够用；如果某课找不到合适来源，先补来源，不要凭记忆写。
- 2026-10-21 核查的两项打磨已全部处理：第 4 课重复引用已合并；第 2 课术语补中文与页码已完成；第 1 课「三个常见误判」已移到练习之前，并按修订后的列表规则补了引导句与收束句。「表前后补过渡」「活动名双行形式」两项经复核撤回。规范「项目符号」条已按用户提议修订，见 `NOTES.md` 第十四次调整。
- 2026-10-21 结构定案：各课 recap（「今天带走的三句话」）保持在练习之后——它与主读物、下一课同属收尾块，规范第五段「Do + Check + Carry」顺序即练后带走；第 4 课「三个常见误区」移到「反馈回路」与练习之间（与第 1 课误判同类问题，正文不排在练习后）。见 `NOTES.md` 第十五次调整。

> AI生成
