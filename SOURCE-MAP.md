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
| 理论 | `courseware/swebok/swebok-v4.pdf` | 第 2 章 p67–82；第 3 章 p83–98 | 架构视图、质量属性、设计原则、设计记录 |
| 理论 | `courseware/se-education/book/designFundamentals/print.html` | 全章 | 设计 fundamentals |
| 理论 | `courseware/se-education/book/architecture/print.html` | 全章 | 架构风格、质量属性、取舍 |
| 实践 | `courseware/cmu-17-313/pdfs/08-design-docs.pdf` | 全篇 | design doc 的结构与评审 |
| 经典 | `courseware/ousterhout/aposd2ndEdExtract.pdf` | 摘录 | 深模块、接口与实现的区分 |
| 经典 | Parnas, “On the Criteria To Be Used in Decomposing Systems into Modules”（1972） | 全文 | 信息隐藏 |

### 3. Construction（构造）

| 类型 | 本地来源 | 位置 | 用来讲什么 |
|---|---|---|---|
| 理论 | `courseware/swebok/swebok-v4.pdf` | 第 4 章 | 最小化复杂度、可验证性、复用、依赖管理 |
| 理论 | `courseware/mit-6.031/classes/06-specifications/index.html` | 全篇 | 规格、前置/后置条件 |
| 理论 | `courseware/mit-6.031/classes/10-abstract-data-types/index.html` | 全篇 | ADT、表示独立性 |
| 理论 | `courseware/mit-6.031/classes/11-abstraction-functions-rep-invariants/index.html` | 全篇 | rep invariant、abstraction function |
| 实践 | `courseware/se-education/book/codeQuality/print.html` | 全章 | 代码质量、静态检查、命名 |
| 实践 | `courseware/se-education/book/errorHandling/print.html` | 全章 | 错误处理与异常设计 |

### 4. Testing & Quality（测试与质量）

| 类型 | 本地来源 | 位置 | 用来讲什么 |
|---|---|---|---|
| 理论 | `courseware/swebok/swebok-v4.pdf` | 第 5 章 | 测试级别、技术、度量、过程 |
| 理论 | `courseware/mit-6.031/classes/03-testing/index.html` | 全篇 | 划分、边界值、覆盖率、回归测试、stub |
| 理论 | `courseware/se-education/book/testCaseDesign/print.html` | 全章 | 测试用例设计 |
| 实践 | `courseware/cmu-17-313/pdfs/09-testing.pdf` | 全篇 | 测试的工程实践 |
| 实践 | `courseware/cmu-17-313/pdfs/11-oracles.pdf` | 全篇 | oracle 从哪来 |
| 进阶 | `courseware/cmu-17-313/pdfs/10-input-generation.pdf`、`12-pbt1.pdf`、`13-pbt2.pdf` | 全篇 | fuzz / property-based testing |
| 实践 | `courseware/se-education/book/qualityAssurance/print.html` | 全章 | 质量保证与评审 |

### 5. Maintenance & Evolution（维护与演进）

| 类型 | 本地来源 | 位置 | 用来讲什么 |
|---|---|---|---|
| 理论 | `courseware/swebok/swebok-v4.pdf` | 第 7 章 | 维护类型、遗留系统、再工程 |
| 理论 | `courseware/se-education/book/refactoring/print.html` | 全章 | 重构与代码坏味道 |
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
| 理论 | `courseware/swebok/swebok-v4.pdf` | 第 6 章、第 8 章 | 运维、配置管理、发布 |
| 实践 | `courseware/google-sre/postmortem-culture/index.html` | 全篇 | 事故复盘 |
| 实践 | `courseware/google-sre/managing-incidents/index.html` | 全篇 | 事故管理 |
| 实践 | `courseware/google-sre/monitoring-distributed-systems/index.html` | 全篇 | 监控与告警 |
| 实践 | `courseware/google-sre/release-engineering/index.html` | 全篇 | 发布工程 |
| 实践 | `courseware/12factor/codebase.html` 等 12 章 | 全篇 | 配置、构建、发布、运行 |
| 实践 | Missing Semester 2026（在线，中文版） | 代码质量一讲 | 格式化、lint、CI |

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

- 具体行业标准（如受监管行业的需求规格标准）没有本地全文；写到相关课时，只能说明「依行业而定」，不编具体条款。
- 团队心理学、组织行为学的本地材料只有 CMU 的 Teams 讲义和 SE-EDU 的 Teamwork 一章，深度有限；团队内容不扩成主线。
- 架构评估方法（ATAM 等）没有本地材料；第 17 课只讲质量属性与取舍，不展开完整评估方法。

> AI生成
