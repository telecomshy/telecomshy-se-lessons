# 软件工程与 AI 辅助开发 Resources

课程的知识来源。原则：优先一手材料；每条都写清「用来干什么」；不确定的链接不放进来。

> 本地离线副本：`courseware/`，清单见 `courseware/README.md`（2026-10-20 下载，约 59 MB）。
> 理论来源按活动索引见 `SOURCE-MAP.md`；写课时先查它，不要凭记忆。
> 课号以 `reference/course-map.html` v3 为准。骨架在 2026-10-20 从 28 节调整为 34 节（M0 拆为 3 节，后续课号整体后移一位）；本文少数「第 N 课」是写作时的旧编号，引用前先核对地图。

> 调研时间：2026-10-20。下面标「已验证」的链接，都是当天在本机实际抓取到内容的；标「不可达」的只记录线索，不作为教学依据。

## 一、公开课程与课件（课程骨架的主要来源）

- **[MIT 6.005 Software Construction](https://ocw.mit.edu/courses/6-005-software-construction-spring-2016/)**（已验证）
  [课程 readings 目录](https://ocw.mit.edu/courses/6-005-software-construction-spring-2016/pages/readings/) 完整公开，含 Testing、Code Review、Specifications、Abstract Data Types、Debugging、Version Control、GUI 分层。用 Java 讲，例子需要翻译成 Python。
  用于：模块 1 的「规格」、模块 4 的测试与 ADT、模块 5 的 code review 与调试。测试那一讲的「划分输入空间 + 边界值 + 回归测试」是第 19–21 课的主干。

- **[CMU 17-313: Foundations of Software Engineering](https://cmu-313.github.io/)**（已验证，2026 秋季）
  整套讲义公开：Project Planning、Metrics、Software Specifications、Design Docs、Unit Testing I、Testing Oracles、Property-based Testing I/II、Microservices/Architecture，以及两讲 AI 相关的内容（Intro + Pitch about AI usage、Responsible AI use in SE）。课程项目直接用 OpenCode（Project 1: Hello, opencode!），和本课程环境一致。没有指定教材，推荐 SE at Google 作为补充阅读。
  用于：模块 2 的计划与规格、模块 4 的测试（尤其是 oracle 与 property-based testing）、模块 6 的 AI 使用规范。取用具体讲义时以课程首页的 schedule 为准，PDF 链接会随学期更新。

- **[Berkeley CS 169: Software Engineering](https://www2.eecs.berkeley.edu/Courses/CS169/)**（已验证，经代理）
  课程目录页公开列出主题：过程、敏捷 / XP、需求、规格、UML、设计模式、版本控制、测试、调试、安全、重构、复用；学生以团队完成一个完整项目。实际课堂主页与讲义在 inst.eecs，目录页上有入口。
  用于：模块 1–2 的需求与过程、模块 5 的维护与重构。
  注意：这是课程目录，不是完整课件；具体讲义要看当学期的 class homepage。

- **[The Missing Semester of Your CS Education 2026](https://missing.csail.mit.edu/)**（已验证）· **[简体中文版](https://missing-semester-cn.github.io/)**（已验证）
  2026 版把 AI 工具折进了每一讲，包含 [智能体编程](https://missing-semester-cn.github.io/2026/agentic-coding/)、[代码质量](https://missing-semester-cn.github.io/2026/code-quality/)、[版本控制](https://missing-semester-cn.github.io/2026/version-control/)、[调试与性能分析](https://missing-semester-cn.github.io/2026/debugging-profiling/)。
  用于：模块 0 的工作台、模块 4 的代码质量与 CI、模块 6 的上下文管理。它的「智能体编程」一讲对上下文窗口、清空、压缩、子智能体的讲法，和技能包的 phase boundaries 是同一套东西，可以互相对照。

- **[Software Engineering at Google](https://abseil.io/resources/swe-book)**（已验证，全文免费）
  [目录](https://abseil.io/resources/swe-book/html/toc.html) 已验证。重点章节：第 1 章（软件工程与编程的区别：时间、规模、权衡）、第 9 章（Code Review）、第 11–14 章（Testing Overview / Unit Testing / Test Doubles / Larger Testing）、第 23–24 章（CI / CD）。
  用于：模块 5 的主教材；第 13 章讲 seam 与 fake，正好补模块 4 的测试替身课。注意许可是 CC BY-NC-ND，不能改写后分发。

- **[Google Engineering Practices — Code Review](https://google.github.io/eng-practices/)**（已验证）
  分「审查者指南」和「提交者指南」两套。讲小 CL、变更描述、礼貌与具体、哪些问题值得提。
  用于：第 25 课。和技能包的 `code-review` 双轴（Standards / Spec）配合：Google 讲「怎么审」，技能包讲「按哪两个轴审」。

- **[Software Engineering: A Modern Approach](https://softengbook.org/)**（已验证，Marco Tulio Valente）
  10 章、350 页、120 道练习、900 多张幻灯片，全部网页公开。第 1 章导论、第 2 章过程、第 3 章需求、第 4 章建模、第 5 章设计原则（信息隐藏、内聚、耦合、SOLID）、第 6 章模式、第 7 章架构、第 8 章测试、第 9 章重构、第 10 章 DevOps。
  用于：整门课的「原理」骨架。第 3 章支撑模块 1–2，第 5 章支撑第 14 课，第 8 章支撑第 19–22 课，第 9 章支撑第 28 课。
  注意：作者声明仅限个人使用，禁止再分发或修改。只链接、只转述，不复制原文。

- **[Software Design by Example](https://third-bit.com/sdxpy/)**（已验证，Greg Wilson）
  Python 写的 26 个小工具：测试运行器、数据库、构建管理器、调试器、解释器……开源许可。第 6 章 [Running Tests](https://third-bit.com/sdxpy/test/) 用几十行代码实现一个 pytest 式的测试运行器，特别适合测试从零开始的人。
  用于：模块 4 的 Python 示例与沙盒灵感；也可以作为「读代码学设计」的选读。

- **[Refactoring.Guru](https://refactoring.guru/)**（已验证）· **[中文版](https://refactoringguru.cn/)**（已验证）
  重构目录、代码坏味道、技术债、设计模式，带 [Python 示例](https://refactoring.guru/design-patterns/python)。中文版的设计模式部分已翻译，重构部分标注「未翻译」。
  用于：第 28 课（架构改良）与第 14 课（设计词汇）的补充读物。不要把它变成一门设计模式课，只按需查。

- **[The Architecture of Open Source Applications](https://aosabook.org/en/)**（已验证）
  Git、nginx、SQLAlchemy、matplotlib、ZeroMQ 等真实项目的架构复盘，开源许可。
  用于：模块 3、5 的选读。目的不是背架构，是建立「架构是一串取舍」的直觉。

- **[CMU 17-445/645: Machine Learning in Production](https://ckaestne.github.io/seai/)**（已验证）
  需求、架构、质量保证、部署、运维，全套幻灯片公开。
  用于：可选加餐。讲「AI 产品的工程约束」时用，不占主线课时。

## 二、经典理论与一手文献

- Frederick P. Brooks Jr., _The Mythical Man-Month_（1975，1995 纪念版）
  本质复杂度与偶然复杂度、沟通成本、为什么加人不能加速。用于：第 1 课。
- Frederick P. Brooks Jr., "No Silver Bullet — Essence and Accident in Software Engineering"（1986）
  为什么工具进步不能消除全部困难。用于：第 1 课结尾，讨论 AI 能替代什么、不能替代什么。
- David L. Parnas, "On the Criteria To Be Used in Decomposing Systems into Modules"（1972）
  信息隐藏。深模块与接缝的思想祖先。用于：第 13、14 课。
- John Ousterhout, _A Philosophy of Software Design_（2018）
  深模块、接口与实现的区分、复杂度的度量。用于：第 13 课的主教材。
- Kent Beck, _Test-Driven Development: By Example_（2002）
  红绿重构的原始表述。用于：第 16 课。
- Michael Feathers, _Working Effectively with Legacy Code_（2004）
  seam 一词的出处、特征测试。用于：第 14、22 课。
- Eric Evans, _Domain-Driven Design_（2003）
  Ubiquitous Language、bounded context。用于：第 4 课。
- Martin Fowler, _Refactoring: Improving the Design of Existing Code_（2nd ed., 2018）
  小步重构与代码坏味道。用于：第 24 课。
- Steve Freeman & Nat Pryce, _Growing Object-Oriented Software, Guided by Tests_（2009）
  由外向内、walking skeleton。用于：第 9、19 课。
- Andrew Hunt & David Thomas, _The Pragmatic Programmer_（1999，20 周年版 2019）
  tracer bullet 一词的出处。用于：第 9 课。
- Nicole Forsgren, Jez Humble & Gene Kim, _Accelerate_（2018）
  这些实践与交付绩效的相关证据。用于：回答「为什么要这么麻烦」，第 1、28 课。
- Titus Winters, Tom Manshreck & Hyrum Wright, _Software Engineering at Google_（2020）
  见上面免费网页版。用于：模块 4。

## 三、技能包本体（最权威，流程细节以此为准）

- 本地目录 `C:\Users\admin\.agents\skills\`
  每个技能的 `SKILL.md` 就是该流程的定义。不另造同义词、不简化步骤。
- `ask-matt/SKILL.md` 与 `ask-matt/PHASE-BOUNDARIES.md`
  技能包全景：主线、支线、术语层；阶段边界的五选一决策树。用于：第 3、32 课。
- `grilling/SKILL.md`、`grill-with-docs/SKILL.md`、`grill-me/SKILL.md`
  逼问的机制：轮次、frontier、事实与决策的分工。用于：第 5 课。
- `domain-modeling/SKILL.md`、`GLOSSARY-FORMAT.md`、`ADR-FORMAT.md`
  领域语言、`GLOSSARY.md` 与 ADR 的格式。用于：第 4、7 课。（2026-10 起上游把 `CONTEXT.md` 改名为 `GLOSSARY.md`；旧版仍用旧名。）
- `to-spec/SKILL.md`、`to-tickets/SKILL.md`
  spec 与工单的形状、阻塞边。用于：模块 2。
- `codebase-design/SKILL.md`、`DEEPENING.md`、`DESIGN-IT-TWICE.md`
  深模块词汇：module、interface、depth、seam、adapter、leverage、locality。用于：模块 3。
- `tdd/SKILL.md`、`tests.md`、`mocking.md`
  红绿重构、好测试的形状、测试替身的边界。用于：第 20–22 课。
- `implement/SKILL.md`、`code-review/SKILL.md`
  工单执行与双轴审查。用于：第 23、25 课。
- `diagnosing-bugs/SKILL.md`、`improve-codebase-architecture/SKILL.md`
  紧反馈回路、回归测试、架构改良。用于：模块 5。
- `prototype/SKILL.md`、`LOGIC.md`、`UI.md`
  可丢弃代码回答一个设计问题；逻辑与界面两条分支。用于：第 30 课。
- `research/SKILL.md`、`triage/SKILL.md`、`wayfinder/SKILL.md`、`handoff/SKILL.md`、`retro/SKILL.md`
  支线技能。用于：模块 2、6 与第 34 课。

## 四、工具与语言

- pytest 官方文档 `https://docs.pytest.org/`
  Python 测试的事实标准。用于：第 16–18 课的操作细节。
- Python 官方文档 `https://docs.python.org/3/`
  标准库与类型标注。用于：沙盒实现。
- Ruff `https://docs.astral.sh/ruff/`
  格式化与 lint，Python 生态里启动成本最低的一套。用于：模块 0 的工作台、模块 4 的代码质量。
- OpenCode 文档（本机技能 `opencode` 可查）
  agent、权限、上下文管理的实际行为。用于：所有操作示例。

## 五、Wisdom（社区）

- AI Hero（Matt Pocock）`https://www.aihero.dev/`
  Matt 本人的文章与 AI coding dictionary。用于：smart zone 等术语的原始定义。本地已存词条页：`courseware/aihero-smart-zone/index.html`。
- r/ExperiencedDevs `https://www.reddit.com/r/ExperiencedDevs/`
  有工作经验的开发者讨论设计取舍。用于：验证「这个做法在真实团队里成立吗」。
- Software Engineering Stack Exchange `https://softwareengineering.stackexchange.com/`
  偏概念与取舍的问答，质量高于一般论坛。用于：术语与设计争议。
- Lobsters `https://lobste.rs/`
  高信噪比的工程社区。用于：追踪架构与测试话题的长期讨论。
- OSSU Discord（Missing Semester 也在用）`https://ossu.dev/#community`
  自学者聚集地，适合问「这课该怎么学」。用于：卡住时求助。
- 本地：把课程练习拿到自己团队做一次 code review
  比任何在线社区都真实的反馈。用于：模块 4 之后。

## 六、Gaps

- **SWEBOK 已补到 v4 PDF**（本地 `courseware/swebok/`）。课程仍不声称覆盖全部 KA，只取主线所需的子集。
- **Berkeley CS 169 只有课程目录**：sp24 站点需要 CalNet 登录；SaaS 教材全文没有本地副本，只有主页与 teaching 页。
- **`martinfowler.com` 与 SE Radio 未下载**：前者是文章站、后者是播客，不属于课件；需要时再按篇抓。
- **中文系统课程未验证**：中国大学 MOOC 等平台的软件工程课程多数需要登录，无法确认内容与许可，暂不列入。
- **没有找到中文一手材料讲这套 AI 辅助工程流程**；课程里的中文表述由我翻译，术语保留英文。
- **未找到高质量中文社区**讨论这套流程；暂时用上面的英文社区替代。
- **已更正（2026-10-20）**：CMU 17-313 的正确地址是 <https://cmu-313.github.io/>。此前记录的 404 与超时是试错地址导致的误判，现已移入「已验证」列表。

## 七、离线课件与剩余缺口（2026-10-20 更新）

已通过 Clash 代理（`curl -x http://127.0.0.1:7890`）下载到 `courseware/`，清单见 `courseware/README.md`。合计约 59 MB：

| 目录 | 内容 |
|---|---|
| `mit-6.031/` | 30 讲 readings + general 页（42 个文件） |
| `cmu-17-313/` | 13 份 lecture PDF + syllabus |
| `swebok/` | SWEBOK v4 PDF |
| `se-education/` | SE-EDU 教材 28 章 |
| `google-sre/` | SRE Book 49 个章节页 |
| `12factor/` | 12 章 + epub |
| `ousterhout/` | 书页 + 第二版摘录 PDF |
| `saas-book/` | 课程主页 + teaching 页 |
| `berkeley-cs169/` | 课程目录页 |
| `brooks/` | “No Silver Bullet” PDF |
| `aihero-smart-zone/` | smart zone 词条页 |
| `teachyourselfcs/` | 自学课程表 |

仍未拿到：

- **Rutgers（Marsic）教材**：`https://ece.rutgers.edu/~marsic/books/SE/` 301 后 404，原书可能已迁移或下线。
- **Berkeley CS 169 的 sp24 站点**：`https://inst.eecs.berkeley.edu/~cs169/sp24/` 需要 CalNet 登录；本地只有课程目录页。
- **SaaS 教材全文**：商业书；只有主页与 teaching 页，视频在 YouTube。
- **SE Radio、Dijkstra archive、martinfowler 文章**：不是课件，未下载。

**代理已恢复（2026-10-20 10:31）**：结束后台旧 CLI 并重启后，新 CLI（PID 23480）继承了 `HTTP_PROXY` / `HTTPS_PROXY`。`webfetch` 已实测可访问 MIT 6.031、Berkeley CS 169、SaaS Book、Google SRE；SWEBOK 根域仍不通，但 v4 PDF 已从 IEEE CS 下载。下载课件时用的 `curl -x` 是当时的临时办法，现在可以直接用 `webfetch`。
