# 理论来源地图

> 课程以软件工程理论为主线。每节课至少要有一条来自本文件的理论来源，写明文件与章节/页码；不能凭记忆。
> 技能包的 `SKILL.md` 只作为实践来源，不作为理论来源。
> 本文件只管「引用依据」（活动 → 文件 + 章节/页码）；课程结构、每模块主读物和术语家谱见 `reference/course-map.html`。两者分工不同，改动来源时需同步维护。

## 怎么用

1. 写课前，先在表中找到本课对应的活动（第 2 课的八个活动）。
2. 选一条核心理论来源，再选一条行业做法来源；优先用本地 `courseware/`。
3. 在课文中至少引用一次具体章节/页码；在课末的「理论来源」区块列出完整路径。
4. 找不到来源时，写「这是我的经验判断」，不要伪装成理论。
5. 理论只取回答本课问题所需的部分，不做教材摘要；理论、行业做法、AI 实践大约各占三分之一。

## 八个活动的来源

### 1. Requirements（需求）

| 类型 | 本地来源 | 位置 | 用来讲什么 |
|---|---|---|---|
| 理论 | `courseware/swebok/swebok-v4.pdf` | 第 1 章，p43–66 | 需求分类、elicitation、analysis、specification、validation、management |
| 理论 | `courseware/se-education/book/requirements/print.html` | 全章 | 功能 / 非功能需求、需求优先级、验收 |
| 实践 | `courseware/se-education/book/gatheringRequirements/print.html` | 全章 | 需求来源与 elicitation 的具体做法 |
| 实践 | `courseware/se-education/book/specifyingRequirements/print.html` | 全章 | 需求规格的写法 |
| 讲义 | `courseware/cmu-17-313/pdfs/07-specs.pdf` | 全篇 | 规格的边界、验收标准 |
| 经典 | Evans, *Domain-Driven Design*（2003）第 2 章 | 第 2 章 | Ubiquitous Language、bounded context |

### 2. Design & Architecture（设计与架构）

| 类型 | 本地来源 | 位置 | 用来讲什么 |
|---|---|---|---|
| 理论 | `courseware/swebok/swebok-v4.pdf` | 第 2 章 p67–82（printed 2-1~2-16）；第 3 章 p83–98 | 架构视图、质量属性、设计原则、设计记录。第 17 课已核实：ch.2 §1.2 关注点与干系人（printed 2-3）、§2 与 §2.1 架构描述 / 视图与视点 / multiple views problem（printed 2-4~2-6）、§2.2 风格与模式（2-6~2-7）、§2.4 架构即重大决定（质量属性取舍是设计决定依据、architecture rationale、架构技术债，2-7）、§3.2.1 ASR 定义（2-9）、§4.1 「好的架构」与 ATAM 概述（2-10~2-11）；ch.3 §6.2 Quality Attributes 与 §6.3 Quality Analysis and Evaluation Techniques（PDF p95–96 = printed 3-13~3-14，质量属性运行时/非运行时分类、scenario-based techniques） |
| 理论 | `courseware/se-education/book/designFundamentals/print.html` | 全章 | 设计 fundamentals |
| 理论 | `courseware/se-education/book/designApproaches/print.html` | 全章 | multi-level design、top-down/bottom-up、agile design 与 full upfront design 的取舍 |
| 理论 | `courseware/se-education/book/architecture/print.html` | 全章 | 架构风格、质量属性、取舍 |
| 实践 | `courseware/cmu-17-313/pdfs/08-design-docs.pdf` | 全篇 | design doc 的结构与评审 |
| 经典 | `courseware/ousterhout/aposd2ndEdExtract.pdf` | 摘录 | 深模块、接口与实现的区分 |
| 经典 | Parnas, “On the Criteria To Be Used in Decomposing Systems into Modules”（1972） | 全文 | 信息隐藏 |
| 经典 | Cockburn, “Hexagonal Architecture”（2005） | 全文 | ports & adapters、六边形架构（线上，无本地全文，经典转引） |

### 3. Construction（构造）

| 类型 | 本地来源 | 位置 | 用来讲什么 |
|---|---|---|---|
| 理论 | `courseware/swebok/swebok-v4.pdf` | 第 4 章 | 最小化复杂度、可验证性、复用、依赖管理；第 20 课已核实 §4.16 Test-First Programming（PDF p112 = printed 4-14）；第 23 课已核实 §3.4 Construction Testing（PDF p105 = printed 4-7，「reduce the gap between when faults are inserted into the code and when those faults are detected」、构造测试是写代码者自做的单元与集成测试）、§3.6 Construction Quality（PDF p106–107 = printed 4-8~4-9，质量手段七项清单与「depend on the software constructed and on the skill set of the engineers」）、§4.17 Feedback Loop for Construction（PDF p112 = printed 4-14，「Early and continuous feedback…」）、§3.7 Integration 的 CI 句（printed 4-9，「automated by a pipeline that builds and tests each integration」，第 24 课已用并核实） |
| 理论 | `courseware/mit-6.031/classes/06-specifications/index.html` | 全篇 | 规格、前置/后置条件；第 21 课已核实 “Behavioral equivalence”“Testing and specifications”“Testing units”（测试是规格的客户端、玻璃盒测试也守规格、find 越界断言例子） |
| 理论 | `courseware/mit-6.031/classes/10-abstract-data-types/index.html` | 全篇 | ADT、表示独立性 |
| 理论 | `courseware/mit-6.031/classes/11-abstraction-functions-rep-invariants/index.html` | 全篇 | rep invariant、abstraction function |
| 实践 | `courseware/se-education/book/codeQuality/print.html` | 全章 | 代码质量、静态检查、命名；第 21 课用 “Maximize Readability”“Name Well”“Comment minimally but sufficiently”（Explain WHAT and WHY, not HOW） |
| 实践 | `courseware/se-education/book/errorHandling/print.html` | 全章 | 错误处理与异常设计 |

### 4. Testing & Quality（测试与质量）

| 类型 | 本地来源 | 位置 | 用来讲什么 |
|---|---|---|---|
| 理论 | `courseware/swebok/swebok-v4.pdf` | 第 5 章 p117–136（printed 5-1~5-20） | 测试级别、技术、度量、过程；第 19 课已核实测试定义、oracle、EP、BVA、覆盖率、变异、彻底性度量；第 20 课已核实 §2.2.5 Regression Testing（PDF p124 = printed 5-8）与 §6.1.2 TDD / shift-left（printed 5-23~5-24）；第 22 课已核实 §2.1.2 Integration Testing（PDF p123 = printed 5-7，top-down / bottom-up / sandwich / big bang）；第 27 课再用 §2.2.5（可在每个测试级别做、selection / minimization / prioritization 与取舍；该节回归测试定义转引 [5] = ISO/IEC/IEEE 24765 词表，**不是 14764**——14764 对应 ch.7 的维护类别） |
| 理论 | `courseware/swebok/swebok-v4.pdf` | 第 12 章 §3.4.1 末尾与 §3.4.5 Technical Reviews and Audits（PDF p258–259 = printed 12-13~12-14） | 评审定义与依据；第 25 课已核实：「review and audit processes are considered static analysis activities… they examine software engineering artifacts … concerning standards established by the organization or project for those artifacts」出自 §3.4.1 末尾（预告 §3.4.5，printed 12-13）；§3.4.5 有 peer review 定义「the review of work products performed by peers during development of the work products to identify defects for removal」（ISO/IEC/IEEE 24765:2017 转引）、code review 的 pull request 形态、「Reviews are valuable because they can identify issues early … Fixing a defect in a component that has been coded is much more expensive than catching it beforehand」、ISO/IEC 20246:2017 五种评审类型（Ad hoc / Checklist-based / Scenario-based / Perspective-based / Role-based）、「Reviews should be part of the software engineering culture」 |
| 理论 | `courseware/mit-6.031/classes/03-testing/index.html` | 全篇 | 划分、边界值、覆盖率、回归测试、stub；第 20 课已核实 “Test-first programming” 与 “Iterative test-first programming”；第 22 课已核实 “Unit and integration testing” 的 stub / mock 段（「A stub for a class is often called a mock object」术语混用实证） |
| 理论 | `courseware/se-education/book/testing/print.html` | “Stubs”“Integration Testing”“Dependency Injection” | 第 22 课已核实：隔离论证、stub 定义（同接口、「so simple that it is unlikely to have any bugs」、硬编码答复）与 `StorageStub` 例子、「Mocks, Fakes, Dummies, Spies」一句、glue code 误解（Car/Engine/Wheel）、依赖注入与 `SalaryManagerStub` 例子 |
| 理论 | `courseware/se-education/book/testCaseDesign/print.html` | 全章 | 测试用例设计 |
| 经典 | `courseware/fowler/mocks-arent-stubs.html` | 全文（文内日期 2 January 2007） | 第 22 课核心：test double 统称与五种替身（转引 Meszaros）、only mocks insist upon behavior verification、状态验证 vs 行为验证、classical / mockist 两派取舍、cache 行为验证例外、绑实现与重构、「green but mask inherent errors」 |
| 经典 | `courseware/meszaros/`（xunitpatterns.com 经 web.archive.org 存档） | Mock Object、Test Stub 两页 | 第 22 课补充：Meszaros 一手定义（Mock Object＝Behavior Verification；Test Stub＝feeds the desired indirect inputs；均 Variation of: Test Double）。站点无法直连，其余四页（Test Double / Fake Object / Test Spy / Dummy Object）限速未取到 |
| 经典 | Beck, *Test-Driven Development: By Example*（2002） | 红绿重构三步、test list | 测试先行的循环与清单（线上，无本地全文，经典转引） |
| 实践 | `courseware/cmu-17-313/pdfs/09-testing.pdf` | 全篇（第 19 课用 p9、p11、p16、p18–20、p23、p25–33；第 20 课用 p21；第 21 课用 p9 Specification Testing） | 测试的工程实践 |
| 实践 | `courseware/cmu-17-313/pdfs/11-oracles.pdf` | 全篇（第 19 课用 p7、p18、p19；第 21 课用 p7、p19；第 26 课用 p10、p19） | oracle 从哪来；第 26 课用两处 flaky 引文：p10「non-determinism and environment coupling lead to flaky tests」、p19「Nondeterminism (timestamps, IDs, ordering) has to be scrubbed or the test becomes flaky」 |
| 实践 | `courseware/google-sre/testing-reliability/index.html` | 全篇 | 第 22 课用：mocks of complex dependencies、stateful database 换 lightweight mock、fake backend 版本 |
| 实践 | `courseware/se-education/book/qualityAssurance/print.html` | 全章 | 质量保证与评审；第 23 课用：「Quality Assurance = Validation + Verification」与「What is more important is that both are done」、“Code Reviews”（定义、三种形式、相对测试的三点优势与「manual process and therefore, error prone」）、“Static Analysis”（unused variables / unhandled exceptions / style errors、linters 是子集）、“Formal Verification”（「testing can only prove the presence of errors, not their absence」）；第 25 课另用 “Formal inspections” 四角色（author / moderator / secretary / inspector） |
| 实践 | Google Engineering Practices（本地全套 `courseware/google-eng-practices/`，2026-11-03 下载核实）：提交者指南 `review/developer/`（cl-descriptions / small-cls / handling-comments 三篇）、审查者指南 `review/reviewer/`（standard / looking-for / navigate / speed / comments / pushback 六篇） | 全篇 | 第 23、24 课用《Small CLs》（「one self-contained change」、「just one part of a feature」、「100 lines is usually a reasonable size… 1000 lines is usually too large」、「Tests are expected for all Google changes」、重构单独成 CL（小清理例外）、「Don't Break the Build」（小节标题，原文「make sure the whole system keeps working after each CL is submitted」）；第 24 课回指小步拆存量）；第 25 课用审查者指南（The Standard of Code Review、What to Look For、Navigating a CL、Speed、How to Write Comments、Handling Pushback）与提交者指南（Writing Good CL Descriptions、How to Handle Reviewer Comments）；第 27 课用《Writing Good CL Descriptions》（「A CL description is a public record of change」、what/why 两问、「Reading source code may reveal what the software is doing but it may not reveal why it exists.」） |
| 进阶 | `courseware/cmu-17-313/pdfs/10-input-generation.pdf`、`12-pbt1.pdf`、`13-pbt2.pdf` | 全篇 | fuzz / property-based testing |

### 5. Maintenance & Evolution（维护与演进）

| 类型 | 本地来源 | 位置 | 用来讲什么 |
|---|---|---|---|
| 理论 | `courseware/swebok/swebok-v4.pdf` | 第 7 章 | 维护类型、遗留系统、再工程；第 27 课已核实 §1.6 Categories of Software Maintenance（PDF p170 = printed 7-4，五类经 ISO/IEC/IEEE 14764 标准化；corrective「Reactive modification (or repairs)… to correct discovered problems」、preventive「…to correct latent faults… before they occur in the live system」，另定义 emergency maintenance）、§2.1.4 Maintainability（printed 7-7，技术债「often accumulates when the need to quickly address corrective, emergency, and additive maintenance tasks… leads to compromises」）、§2.3.1（printed 7-9，「technical debt should not be handled in isolation but through an examination of its root causes」）；第 28 课另核实 §1.5 Evolution of Software（PDF p169–170 = printed 7-3~7-4，Lehman 八律「Increasing Complexity — As software evolves, its complexity increases unless work is done to maintain or reduce that complexity.」）、§1.6 perfective maintenance 定义（printed 7-5，「…recoding to improve software performance, maintainability, or other software attributes」）、§2.1.1 Limited Understanding（printed 7-5，「Research suggests a significant portion of total maintenance effort is devoted to understanding the software to be modified.」）、§2.1.3 Impact Analysis（printed 7-6，「Impact analysis assesses the detailed effects of proposed changes on existing software.」与受影响面、资源估算、风险三句）、§4.2 Software Reengineering（PDF p179–180 = printed 7-13~7-14，「Refactoring is a reengineering technique that aims to reorganize a program without changing its behavior.」、reengineering「often undertaken not to improve maintainability but to replace aging legacy software.」、重构手法「before and after code changes」减债）、§4.3 Reverse Engineering（printed 7-14，被动分析、不改软件） |
| 理论 | `courseware/mit-6.031/classes/13-debugging/index.html` | 全篇 | 系统化调试（第 26 课主线，引文逐条核实）：复现优先「Start by finding a small, repeatable test case that produces the failure.」、「will pay off, because you'll have to run it over and over」、修完「keep the test case in your regression test suite」、Shakespeare 输入减半与「Binary search! Always a good technique.」、10 分钟规则与「move your debugging process out of your head… start taking notes」、Delta debugging（好/坏运行对照与版本二分「Using your version control system, you retrieve the most recent version that still passed the test…」）。第 27 课已用后半程：“Find the bug using the scientific method”（Study the data / Hypothesize / Experiment / Repeat 与记笔记四栏）、“2. Hypothesize”（「The point where the program actually failed… isn't necessarily where the bug is.」）、“Slicing”、“Prioritize Hypotheses”、“Fix the bug”（「Avoid the temptation to slap a patch on it and move on.」、coding error / design error 二分、「Look for related bugs, and newly-created ones.」、「Undo debugging probes.」、「Make a regression test.」）、“Regression testing” 题（候选含最小与原始用例，本地副本答案缺失）与「Systematic debugging helps build confidence that a bug is really fixed, and not just temporarily hidden.」 |
| 理论 | `courseware/swebok/swebok-v4.pdf` | ch.5 §1.3 Relationship of Testing to Other Activities（PDF p122 = printed 5-6）；ch.16 §4.6 Debugging（PDF p324 = printed 16-13） | 第 26 课已核实：testing 与 debugging「related to but different」与交叉引用句「Testing vs. Debugging: See Construction Testing … and Debugging Tools and Techniques in the Computing Foundations KA.」；调试对象三类错误 syntax / runtime / logical errors。另 ch.4 §3.6（printed 4-8~4-9）质量手段清单 debugging 第四位（第 25 课引过整张清单，第 26 课回指） |
| 理论 | `courseware/se-education/book/ides/print.html` | “Debugging” 节 | 第 26 课已核实：「Debugging is the process of discovering defects in the program.」与三途径评级（插临时 print 语句、肉眼通读 eye-balling 都标 Bad，后者理由「If you didn't spot the error while writing the code, you might not spot the error when reading the code either.」；debugger 标 Good、推荐途径） |
| 理论 | `courseware/se-education/book/refactoring/print.html` | 全章 | 重构与代码坏味道；第 25 课用 code smell 定义「A code smell is a surface indication that usually corresponds to a deeper problem in the system… smells don't always indicate a problem.」（转引 Fowler bliki）与坏味道例子；第 28 课用 “What”（refactoring 定义「restructuring code in small steps without modifying its external behavior」、「Refactoring is not rewriting」、「Refactoring is not bug fixing」、「each small refactoring should be followed by regression testing」、技术债比喻「The extra effort that it takes to add new features is the interest paid on the debt.」——Ward Cunningham 提出，经 Fowler bliki 转引）与 “When”（code smell 当路标） |
| 实践 | `courseware/google-sre/evolving-sre-engagement-model/index.html` | “Improvements and Refactoring”“Continuous Improvement” | 第 28 课用：「Improvements are prioritized based upon importance for service reliability. The priorities are discussed and negotiated with the development team, and a plan of execution is agreed upon.」（改良当项目做：排序、协商、排期）；“Continuous Improvement” 运行经验化作 suggestions and proposals |
| 实践 | `courseware/se-education/book/reuse/print.html` | 全章 | 复用与演进 |
| 实践 | `courseware/google-sre/postmortem-culture/index.html` | 全篇 | 无责复盘 |
| 经典 | Feathers, *Working Effectively with Legacy Code*（2004） | 相关章节 | seam、characterization test |

### 6. Process & Management（过程与管理）

| 类型 | 本地来源 | 位置 | 用来讲什么 |
|---|---|---|---|
| 理论 | `courseware/swebok/swebok-v4.pdf` | 第 9 章、第 10 章 | 计划、估算、风险、度量、过程模型 |
| 理论 | `courseware/se-education/book/processModels/print.html` | 全章 | 瀑布、迭代、敏捷 |
| 实践 | `courseware/se-education/book/projectPlanning/print.html` | 全章 | 项目计划与估算 |
| 实践 | `courseware/cmu-17-313/pdfs/03-project-planning.pdf` | 全篇 | 计划、里程碑、风险 |
| 实践 | `courseware/cmu-17-313/pdfs/06-Metrics.pdf` | 全篇 | 度量与指标 |
| 实践 | `courseware/cmu-17-313/pdfs/05-Teams-Communication.pdf` | 全篇 | 团队与沟通（单人版作参考） |

### 7. Configuration & Operations（配置与运维）

| 类型 | 本地来源 | 位置 | 用来讲什么 |
|---|---|---|---|
| 理论 | `courseware/swebok/swebok-v4.pdf` | 第 6 章、第 8 章 | 运维、配置管理、发布；第 24 课已核实 ch.8 §6.1 Software Building（PDF p197 = printed 8-13，CI 触发构建流水线段，注意原文 CIs 指 configuration item 配置项）与 ch.6 §1.4–1.5（PDF p155 = printed 6-5，「repetitive tasks are automated…」「manual testing is inefficient, error-prone and non-scalable」）；第 29 课已核实 ch.6 §1.1 定义（PDF p152 = printed 6-3，「the knowledge, skills, processes and tools…operates well during development, maintenance and in real conditions of operations」）、§3.4 Problem Resolution（PDF p160 = printed 6-11）、§4.1 Incident Management（printed 6-11，定义「recording, prioritizing and assessing the business impact, resolution, escalation and closure」与「proper analysis and/or post mortems must be conducted…」）、§4.3 Monitor / Measure / Track / Review（printed 6-11）、§5.1 Incident and Problem Prevention（PDF p161 = printed 6-12） |
| 实践 | `courseware/google-sre/postmortem-culture/index.html` | 全篇 | 事故复盘；第 29 课逐字核实：复盘定义、五条触发条件 + 兜底、blameless 定义与医疗/航空来源、指认与无责对照、「Review criteria might include」五条、「An unreviewed postmortem might as well never have existed.」、传播做法 |
| 实践 | `courseware/google-sre/managing-incidents/index.html` | 全篇 | 事故管理；第 29 课逐字核实：Unmanaged Incidents 三个坑（Sharp Focus / Poor Communication / Freelancing）、ICS 四角色、三条宣布判据、live incident document、交接话术、「Stop the bleeding, restore service, and preserve the evidence for root-causing.」 |
| 实践 | `courseware/google-sre/monitoring-distributed-systems/index.html` | 全篇 | 监控与告警；第 29 课用 four golden signals 与「Every page should be actionable.」、分页主要盯症状（原因只在非常确定、非常紧迫时报） |
| 实践 | `courseware/google-sre/release-engineering/index.html` | 全篇 | 发布工程 |
| 实践 | `courseware/google-sre/example-postmortem/index.html` | 全篇（Appendix D） | 复盘九个内容栏；第 29 课核实 action item 四列 Action / Type / Owner / Bug、mitigate / prevent / process / other 类型、「Where we got lucky」、时间线是 screenplay、脚注 165 条件反射式动作项 |
| 实践 | `courseware/google-sre/incident-document/index.html` | 全篇（Appendix C） | 活文档结构（摘要、状态、指挥链、退出条件、TODO 与已开 bug、倒序时间线） |
| 实践 | `courseware/google-sre/being-on-call/index.html` | 全篇 | 值班；第 29 课只取「单次事故平均 6 小时」 |
| 实践 | `courseware/12factor/codebase.html` 等 12 章 | 全篇 | 配置、构建、发布、运行 |
| 实践 | `courseware/missing-semester/code-quality-2026-en.md`（英文正源快照）、`code-quality-2026-zh.md`（中文版快照，2026-11-03 下载） | 代码质量一讲 | 格式化、lint、CI；第 24 课已核实：格式化统一风格与 Black/gofmt「limited or no configurability, to reduce bikeshedding」、pre-commit 钩子句、CI 三种触发「every time you push code (or on every pull request, or on a schedule)」、check-only 模式句、命令运行器 `just lint` |

### 8. Professional Practice（专业实践）

| 类型 | 本地来源 | 位置 | 用来讲什么 |
|---|---|---|---|
| 理论 | `courseware/swebok/swebok-v4.pdf` | 第 13 章、第 14 章 | 安全、职业实践、伦理 |
| 实践 | `courseware/cmu-17-313/pdfs/02-responsible-AI-use.pdf` | 全篇 | 负责任地使用 AI |
| 案例 | `courseware/cmu-17-313/pdfs/04-737MAX.pdf` | 全篇 | 安全与组织失效 |
| 实践 | `courseware/cmu-17-313/pdfs/05-Teams-Communication.pdf` | 全篇 | 团队与沟通 |
| 理论 | `courseware/mit-6.031/classes/30-ethics/index.html` | 全篇 | 伦理 |
| 实践 | `courseware/se-education/book/teamwork/print.html` | 全章 | 团队协作 |
| 实践 | `courseware/se-education/book/documentation/print.html` | 全章 | 文档与交接 |

## 来源等级

| 等级 | 例子 | 用法 |
|---|---|---|
| 一手理论 | SWEBOK、SE-EDU、Evans、Parnas、Ousterhout、Brooks | 核心概念必须有这一层 |
| 课程讲义 | MIT 6.031、CMU 17-313 | 用来补具体做法和例子 |
| 行业实践 | SRE Book、12factor、Google Code Review 指南 | 用来说明「业内通常怎么做」 |
| 工具文档 | 技能包 `SKILL.md`、pytest、OpenCode | 只作为实践方式，不作为理论 |
| 经验判断 | 我自己的取舍 | 必须标明，不伪装成理论 |

## 引用格式

课文中至少出现一次具体引用，例如：

> SWEBOK 把需求活动拆成 elicitation、analysis、specification、validation、management 五类（SWEBOK v4, ch1, p48–61）。

课末的「理论来源」区块列出：

- 理论：`courseware/swebok/swebok-v4.pdf` 第 1 章，p48–61。
- 实践：`courseware/se-education/book/gatheringRequirements/print.html`。
- 工具：`C:\Users\admin\.agents\skills\grilling\SKILL.md`（只作实践方式）。

## 缺口

- 「一张工单做到什么程度算完」（agile 圈叫 Definition of Done）没有统一标准，Scrum 之类框架给的是做法名不是规范条文；第 23 课按「明说无标准、写主流做法和取舍」处理，立据靠 SWEBOK ch.4 §3.6 质量手段清单、SE-EDU《Quality Assurance》与 Google《Small CLs》三条。Google Engineering Practices 已补本地全套快照（2026-11-03，`courseware/google-eng-practices/` 共 13 页：总览、`review/`、审查者指南六章、提交者指南三章），引文可全部本地核实。

- 具体行业标准（如受监管行业的需求规格标准）没有本地全文；写到相关课时，只能说明「依行业而定」，不编具体条款。
- 团队心理学、组织行为学的本地材料只有 CMU 的 Teams 讲义和 SE-EDU 的 Teamwork 一章，深度有限；团队内容不扩成主线。
- 架构评估方法（ATAM 等）没有本地材料；第 17 课只讲质量属性与取舍，不展开完整评估方法。质量属性场景（quality attribute scenario）的六段写法出自 Bass/Clements/Kazman《Software Architecture in Practice》，本地无全文，第 17 课按经典转引只借骨架（SWEBOK ch.2 §4.1、ch.3 §6.3 只提及「scenario-based techniques」，够立据）。
- seam 的正源 Feathers《Working Effectively with Legacy Code》（2004）与 Cockburn 的《Hexagonal Architecture》（2005）本地均无全文；第 15 课按「经典转引 + 标注」处理（同第 7 课 Nygard 的办法）。fake / stub / mock 的细分已于第 22 课补来源：Fowler《Mocks Aren't Stubs》全文已下载本地（`courseware/fowler/mocks-arent-stubs.html`）；Meszaros《xUnit Test Patterns》（2007）本地无书，五种替身定义经 Fowler 转引，xunitpatterns.com 网页版经 web.archive.org 存档取回（`courseware/meszaros/`，站点无法直连）。
- Beck《Test-Driven Development: By Example》（2002）本地无全文；第 20 课的红绿重构三步与 test list 按经典转引 + 标注处理。另注意 `tdd` 技能把重构挪到 review，与 Beck / SWEBOK ch.4 §4.16（绿后可重构优化）口径不同，第 20 课已明说三口径，不要含糊。
- Fowler《Refactoring》（1999/2018）本地无全书；第 25 课的坏味道基线十二条出自 `code-review` 技能 SKILL.md（自标注 Fowler ch.3），按经典转引处理；SE-EDU《Refactoring》的 code smell 定义（转引 Fowler bliki）可当核对依据。
- 调试方法论的正源是 MIT 6.031 Reading 13: Debugging（自述受 Zeller《Why Programs Fail》启发，另引 Regehr《How to Debug》与 Agans《Debugging: The Nine Indispensable Rules》）；Zeller、Regehr、Agans 本地均无全文，第 26 课未直接引。`git bisect` 是 git 自带工具，本地无官方文档，第 26 课按工具用法加 MIT 的 delta debugging 段立据（已标经验判断）。偶发（flaky）问题怎么处置没有统一标准，第 26 课按「主流做法和取舍」处理，立据靠 CMU 11-oracles 两处引文与 `diagnosing-bugs` 技能。
- SWEBOK 没有 root cause / fault localization 专节：ch.5 §3.4 只在 ODC 语境提一句「reducing the time and effort of the root cause analysis」，ch.7 §2.3.1 提技术债要查 root causes，都不足以立「修根因不修症状」的据。第 27 课的「修的是哪一层」立据靠 MIT Reading 13 的 “2. Hypothesize”（症状点≠缺陷点）与 “Fix the bug”（coding error / design error 二分、「slap a patch」警告）；「修根因不修症状」与「回归测试先修还是先写」均按无统一标准的主流说法与取舍处理。
- 遗留系统替换策略（strangler fig 之类）本地无正源：SE-EDU《Reuse》零命中，SWEBOK ch.7 §4.2 只说 reengineering「often undertaken…to replace aging legacy software」。第 28 课只借这句划边界（替换是另一场仗，不展开），改良提案的验收立据靠 SWEBOK ch.7 §2.1.3 影响分析 + §4.2 重构定义 + SE-EDU《Refactoring》+ 第 14 课 deletion test 与第 21 课 characterization test（Feathers 经典转引）。「改良该做多少」按 SE-EDU「It is too much refactoring when the benefits no longer justify the cost.」当取舍处理，无统一标准。
- Ousterhout 摘录（`courseware/ousterhout/aposd2ndEdExtract.pdf`）只含 ch.6 与 ch.21，**“Design It Twice” 一章不在摘录里**；第 16 课的「你的第一个想法不太可能是最好的」按经典转引处理，出处以 `codebase-design/DESIGN-IT-TWICE.md` 的转述佐证，不作本地一手来源。

> AI生成
