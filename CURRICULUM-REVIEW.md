# 课程骨架复核

> **2026-10-20 已批准**：按 34 节 / 7 模块执行（同日二次调整，M0 拆为 3 节）；单人版；最后一课迁移到 `knowledge-pet`；沙盒为 CLI + 薄 HTTP adapter。课程地图已更新为 v3。原始分析保留 33 节的版本，差异见文末「十、二次调整」。

日期：2026-10-20
对照对象：`reference/course-map.html`（28 节）、`MISSION.md`、`courseware/` 下已下载的四套课件。

## 复核方法

不是凭印象说「少了什么」，而是拿课件的目录逐项对照：

- **SWEBOK v4**：18 个知识领域（Requirements、Architecture、Design、Construction、Testing、Operations、Maintenance、Configuration Management、Management、Process、Models and Methods、Quality、Security、Professional Practice、Economics，加三个基础领域）。
- **CMU 17-313**：13 份讲义（Intro、Responsible AI、Project Planning、737-MAX、Teams、Metrics、Specs、Design Docs、Testing、Fuzz/Input Generation、Oracles、PBT 1/2）。
- **MIT 6.031**：30 讲 readings（Static Checking、Testing、Code Review、Specifications、ADT、Rep Invariants、Debugging、Concurrency、Ethics 等）。
- **SE-EDU**：28 章（Requirements、Specifying Requirements、Architecture、Design、Test Case Design、Quality Assurance、Process Models、Project Planning、Teamwork、Documentation 等）。

## 一句话结论

当前地图的重心是「怎么用 Matt 的技能包走完一个功能」，这条线是清楚的、可执行的。但「对整个软件工程有全面认识」这个目标，目前只覆盖了大约一半：**需求、架构、测试设计、过程与度量、CI/运维、安全/伦理/AI 责任**这几块是空的或很薄。

不是推翻重来。建议在保留主线的前提下，补 9 节、合并 4 处，得到 **33 节 / 7 模块**，仍然落在 8–10 周内。

---

## 一、受众复核

| 课件默认 | 你的实际 | 调整 |
|---|---|---|
| 大学学期，12–16 周，12h/week | 8–10 周，5–8h/week | 只取概念，不跟项目周期；33 节 × 约 1.5h ≈ 50h，按 6h/week 约 8.5 周 |
| 3–5 人团队，有助教和同伴评审 | 单人，只有 agent | 团队概念保留，活动改写成「与未来维护者和 agent 的协作接口」；用设计文档、review、ADR 代替团队流程 |
| Java / TypeScript 示例 | Python | 只取概念，代码全部转写成 Python / pytest |
| 假设学生写过测试 | 测试零基础 | M4 先补「pytest + 测试设计」，再进 TDD；否则第 16 课会断层 |
| 绿地主项目 | 真实工作里更多是维护和演进 | 维护、遗留代码、deprecation 要有位置，不能只讲新功能 |
| AI 作为政策话题（CMU 两讲） | AI 是日常工作方式 | 单独一节课讲「验证、责任、什么时候不该用 AI」，并把验证写进每节课的反馈回路 |

**结论**：课程应明确写成「单人开发者版」。这不是降级，而是把大学课件里依赖团队的部分，翻译成一个人也能执行的动作。CMU 的 Project 1 叫「Hello, opencode!」，说明这套环境已经被用于教学，但它背后的项目周期和团队结构不能照搬。

---

## 二、覆盖复核

图例：**有** = 当前地图有对应课；**部分** = 提到但不成体系；**缺** = 没有。

| 领域 | 课件证据 | 当前地图 | 判断 |
|---|---|---|---|
| 需求工程 | SWEBOK ch1；SE-EDU `gatheringRequirements` / `specifyingRequirements`；CMU `07-specs` | M1 逼问、M2 `to-spec` | **缺**：没有需求来源、验收标准、非功能需求、需求验证 |
| 架构 | SWEBOK ch2；SE-EDU `architecture`；Valente ch7 | M3 深模块、接缝 | **缺**：只有代码级模块设计，没有系统级质量属性、视图、架构取舍 |
| 设计文档 | CMU `08-design-docs`；SE-EDU `documentation` | ADR、spec | **缺**：没有 design doc 这个产物 |
| 测试设计 | MIT 6.031 `03-testing`；CMU `09-testing` / `11-oracles` / PBT；SE-EDU `testCaseDesign` | M3 TDD、好测试、替身 | **部分**：有 TDD，但没有划分、边界值、覆盖率、oracle |
| 过程模型 | SWEBOK ch10；SE-EDU `processModels`；CMU `03-project-planning` | M0 技能全景 | **缺**：没有瀑布 / 迭代 / 敏捷的定位，容易把 Matt 的流程当成唯一答案 |
| 计划、估算、度量 | SWEBOK ch9；CMU `06-metrics`；SE-EDU `projectPlanning` | 工单、阻塞边 | **部分**：会排序，但不会估算、度量、管风险 |
| CI / 运维 | SWEBOK ch6；SRE Book；12factor；Missing Semester `code-quality` | 无 | **缺**：没有质量门、部署、事故与 postmortem |
| 安全 / 伦理 / AI 责任 | SWEBOK ch13/14；CMU `02-responsible-AI-use` / `04-737MAX`；MIT `30-ethics` | 无 | **缺**：这是「AI 辅助开发」课程最不该缺的一块 |
| 维护 / 遗留 | SWEBOK ch7；Feathers；SE-EDU `refactoring` / `reuse` | 诊断、架构改良 | **部分**：没有 characterization test、deprecation、维护类型 |
| ADT / 不变量 | MIT 6.031 `10-adt` / `11-rep-invariants` | 深模块 | **部分**：可以并入深模块一课，补 rep invariant 与 abstraction function |
| 并发 / 错误处理 / 集成 | SWEBOK ch3/4；SE-EDU `errorHandling` / `integration` | 无 | **缺**，但建议列为选读，不进主线 |
| 配置管理 | SWEBOK ch8 | git 会用 | **部分**：没有分支策略、发布、变更管理 |

粗算：SWEBOK 的 15 个软件知识领域里，当前地图完整覆盖约 5 个，部分覆盖约 5 个，明显缺 5 个。

---

## 三、重复与可合并

| 合并 | 理由 | 省下 |
|---|---|---|
| L2 技能包全景 + L3 装工作台 | 看地图和装地图可以在一次坐下完成 | 1 节 |
| L4 领域语言 + L6 `GLOSSARY.md` | 词条和术语表是同一件事的两面 | 1 节 |
| L9 tracer bullet + L10 阻塞边 | 都是「怎么切、先做哪个」，合起来更完整 | 1 节 |
| L20 双轴审查 + L21 读 diff | 两轴是框架，读 diff 是动作，可以一节讲完 | 1 节 |

不建议合并的：L22/L23（反馈回路与根因是两步）、L25/L26（原型与研究回答不同问题）、L27 阶段边界（独立技能）。

---

## 四、建议骨架：33 节 / 7 模块

标 **NEW** 的是新增，标 **MERGE** 的是合并。

### 模块 0 · 地图与工作台（2 节）

| # | 课程 | 技能 |
|---|---|---|
| 1 | 软件工程在管什么 | — |
| 2 | 技能包全景 + 工作台 **MERGE** | `ask-matt` / `setup-matt-pocock-skills` |

### 模块 1 · 需求与语言（5 节）

| # | 课程 | 技能 |
|---|---|---|
| 3 | 术语与领域语言：`GLOSSARY.md` **MERGE** | `domain-modeling` |
| 4 | 逼问：把模糊问题问成决定 | `grilling` |
| 5 | **NEW** 需求工程：来源、验收标准与非功能需求 | — |
| 6 | ADR：什么决定值得记下来 | `domain-modeling` |
| 7 | Spec：从共识到可执行 | `to-spec` |

### 模块 2 · 计划与过程（5 节）

| # | 课程 | 技能 |
|---|---|---|
| 8 | **NEW** 过程模型：瀑布、迭代、敏捷，以及这套流程的位置 | — |
| 9 | 纵向切片与阻塞边 **MERGE** | `to-tickets` |
| 10 | **NEW** 计划、估算与度量：为什么工时估算总是不准 | — |
| 11 | 模糊的大项目：wayfinder 与决策单 | `wayfinder` |
| 12 | 外部输入：triage 与 agent-ready | `triage` |

### 模块 3 · 设计与架构（5 节）

| # | 课程 | 技能 |
|---|---|---|
| 13 | 深模块、信息隐藏与不变量 | `codebase-design` |
| 14 | 接缝与适配器：测试的地基 | `codebase-design` |
| 15 | 设计两次：先造两个候选再选 | `codebase-design` |
| 16 | **NEW** 架构：质量属性、视图与取舍 | — |
| 17 | **NEW** 设计文档：让下一个人（或 agent）能接手 | — |

### 模块 4 · 实现与测试（6 节）

| # | 课程 | 技能 |
|---|---|---|
| 18 | **NEW** pytest 与测试设计：划分、边界、覆盖率 | — |
| 19 | TDD 红绿重构 | `tdd` |
| 20 | 好测试的形状：行为、边界、可读性 | `tdd` |
| 21 | 测试替身：fake、stub、mock 的边界 | `tdd` |
| 22 | `/implement`：把一个工单真正做完 | `implement` |
| 23 | **NEW** CI：让检查自动跑 | — |

### 模块 5 · 验收与维护（5 节）

| # | 课程 | 技能 |
|---|---|---|
| 24 | 双轴审查与读 diff **MERGE** | `code-review` |
| 25 | 紧反馈回路：先要一条会红的命令 | `diagnosing-bugs` |
| 26 | 回归测试与根因：修的是哪一层 | `diagnosing-bugs` |
| 27 | 架构改良与遗留代码 | `improve-codebase-architecture` |
| 28 | **NEW** 运维与事故：从 SRE 到 postmortem | — |

### 模块 6 · 专业实践与 AI（5 节）

| # | 课程 | 技能 |
|---|---|---|
| 29 | 原型：可丢弃代码回答一个设计问题 | `prototype` |
| 30 | 研究：把阅读外包，把引用留下 | `research` |
| 31 | 阶段边界：clear、compact、handoff、subagent | `handoff` |
| 32 | **NEW** 责任：安全、伦理与 AI 的边界 | — |
| 33 | 综合演练 + 迁移到真实项目 | 全部主线 |

---

## 五、时间与负荷

- 33 节 ×（25–40 分钟阅读 + 45–60 分钟练习）≈ **40–55 小时**。
- 按每周 6 小时：约 **8–9 周**；按每周 5 小时：约 **10 周**。仍落在原定的 8–10 周。
- 每周 3–4 节；如果某周只做 2 节，周期会拉到 11–12 周，需要相应改 `MISSION.md` 的约束。
- 新增的 9 节里，4 节是 P0（需求、架构、测试设计、责任），3 节是 P1（过程、计划度量、CI），2 节是 P2（设计文档、运维）。如果必须守 28 节，先砍 P2，再把 P1 降为选读。

---

## 六、读物与导读：改用本地课件

现在 `courseware/` 有离线副本，导读表应从「在线链接」改为「本地路径 + 原站链接」。建议对应关系：

| 模块 | 本地主读物 | 原站 |
|---|---|---|
| 0 | `courseware/brooks/no-silver-bullet.pdf`；Missing Semester 2026 | 原站 |
| 1 | `courseware/se-education/book/gatheringRequirements/print.html`、`specifyingRequirements/print.html`；`courseware/cmu-17-313/pdfs/07-specs.pdf`；SWEBOK ch1 | 原站 |
| 2 | `courseware/se-education/book/processModels/print.html`、`projectPlanning/print.html`；`courseware/cmu-17-313/pdfs/03-project-planning.pdf`、`06-Metrics.pdf` | 原站 |
| 3 | `courseware/se-education/book/architecture/print.html`、`design/print.html`；SWEBOK ch2；`courseware/cmu-17-313/pdfs/08-design-docs.pdf` | 原站 |
| 4 | `courseware/mit-6.031/classes/03-testing/index.html`；`courseware/cmu-17-313/pdfs/09-testing.pdf`、`11-oracles.pdf`；`courseware/se-education/book/testCaseDesign/print.html` | 原站 |
| 5 | `courseware/google-sre/.../postmortem-culture/`；SWEBOK ch7；`courseware/se-education/book/refactoring/print.html` | 原站 |
| 6 | `courseware/cmu-17-313/pdfs/02-responsible-AI-use.pdf`、`04-737MAX.pdf`；Missing Semester 智能体编程；SWEBOK ch13/14 | 原站 |

导读次数也从 5 次变成 6 次（模块 1–6 各一次），每次仍然 10 分钟。

---

## 七、沙盒调整

当前沙盒是「迷你知识库 CLI」。它足够支撑模块 1–4，但对模块 3 的架构、模块 4 的 CI、模块 5 的运维偏弱。

建议保留领域和 CLI，但加一个**薄 HTTP adapter**：

- 它本身就是「接缝与适配器」那一课的真实产物；
- 让架构课有组件边界和质量属性可谈（延迟、可靠性、可观测性）；
- 让 CI 和运维课有一个可启动、可打日志、可制造故障的对象；
- 不需要云，不需要数据库，本地进程即可。

这样同一套代码从「CLI」长到「CLI + HTTP」，正好演示架构演进和维护。

---

## 八、拍板结果（2026-10-20）

- 节数：33 节 / 7 模块。
- 团队内容：单人改写。
- 迁移课：最后一课「综合演练 + 迁移到真实项目」。
- 沙盒：迷你知识库 CLI + 薄 HTTP adapter。
- 已同步：`reference/course-map.html` v2、`MISSION.md`、`NOTES.md`。

## 九、第 1 课复核（2026-10-20）

地图 v2 的 M0 L1 是「软件工程在管什么」，带走一张三问卡。逐项对照：

| 检查项 | 结果 |
|---|---|
| 位置与产出 | 符合：模块 0 第 1 课，产出三问卡 |
| 核心概念 | 符合：时间 / 规模 / 代价，加 Brooks 的本质 / 偶然复杂度 |
| 主读物 | 符合：SE at Google 第 1 章 + 本地 Brooks PDF |
| 练习 | 符合：六个场景分类，仍能检验三问 |
| 与后续课衔接 | 符合：下一课为「技能包全景 + 工作台」 |
| 文案一致性 | 已改：模块名、32 节、33 节、下一课名称、本地 Brooks 链接 |
| 链接 | 全部本地链接通过 |

**结论：不需要重写。** 第 1 课仍是有效的「地图课」；它不承担新增的需求、架构、测试设计内容，那些从模块 1 开始。

## 十、二次调整（2026-10-20）

用户反馈第二课突然跳到技能包，软件工程主线不成立；文字也太碎，像 PPT。调整如下：

- M0 从 2 节拆为 3 节：第 1 课「为什么学」、第 2 课「软件工程包含什么」、第 3 课「怎么练：AI + 技能包 + 工作台」。
- 总课数从 33 变为 34；后续课号整体后移一位。
- 第 2 课改为 SE 全貌与课程路线；原第 2 课的技能包内容移入第 3 课，并改写为完整段落。
- 课程地图更新为 v3；`MISSION.md`、`NOTES.md`、参考卡同步。
- 写作原则新增「讲解用完整句子」；「实践与原理各半」改为「理论是主线，实践是证据」。
- 第三次调整：新增 `COURSE-STANDARD.md`；从 M1 起每课按「位置 → 问题与概念 → 行业做法 → AI + Matt → 练习」五段写；第 4 课按此重写为「领域语言：需求的前置条件」。
