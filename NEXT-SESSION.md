# 下一会话交接

> 用途：把课程状态从当前会话交接到一个新会话，避免重读整段对话。只记状态和下一课，不复制课程内容。
> **OpenCode 会自动读取根目录的 `AGENTS.md`；它已经要求新会话先读本文件、`COURSE-STANDARD.md` 和 `SOURCE-MAP.md`。**

## 先读这些（按顺序）

1. `AGENTS.md`：会话规则（OpenCode 自动加载，不用手动提醒）。
2. `NEXT-SESSION.md`：本文件，当前进度与下一课。
3. `COURSE-STANDARD.md`：五段结构、标准/主流/取舍、理论来源硬约束、写完一课的审计流程、文字没有 AI 味。
4. `SOURCE-MAP.md`：八个活动对应哪些本地课件、章节/页码；写课前必须查。
5. `MISSION.md`：课程目标、成功标准、约束、范围。
6. `NOTES.md`：用户偏好、多次调整、环境说明。
7. `reference/course-map.html`：34 节 / 7 模块的当前地图（v3）。
8. `CURRICULUM-REVIEW.md`：为什么这样排；文末「十、二次调整」是结构变更记录。
9. `lessons/0018-design-doc.html`、`lessons/0019-pytest-test-design.html`：最近两课写法样例（五段结构、文章体）。
10. `reference/0018-design-doc-card.html`、`reference/0019-testing-card.html`：最近两张参考卡的格式样例。
11. `courseware/README.md`：本地课件的目录和来源。

## 当前状态

- 课程骨架：34 节 / 7 模块。M0 三节已完成；M1（第 4–8 课）写满；M2（第 9–13 课）写满；M3（第 14–18 课）写满；**M4（第 19–24 课）开篇第 19 课已完成。下一步写第 20 课「TDD 红绿重构：先写失败测试买到了什么」。**
- 技能包已装最新版（2026-10-20）：全局 `C:\Users\admin\.agents\skills\\`，共 51 个技能目录，其中 Matt 仓库 38 个（engineering 20、productivity 7、misc 4、in-progress 7）；新增 `pr`、`chief-of-staff`。`domain-modeling` 已从 `CONTEXT.md` 改为 `GLOSSARY.md` / `GLOSSARY-MAP.md`，格式文件为 `GLOSSARY-FORMAT.md`。旧技能目录备份在 `C:\Users\admin\AppData\Local\Temp\opencode\skills-backup-20261020`。
- **沙盒代码骨架（2026-10-26 立，2026-10-28 迁移）**：`D:\code\my_projects\se-course-sandbox` 有 `kb/` 包：`python -m kb add "标题" "正文"` 与 `python -m kb search "关键词"` 两个命令。第 15 课练习（port + 两 adapter）已于 2026-10-28 补做（提交 `335b4bf`，接根提交 `b2162ce`）：`kb/storage.py` 是 `Store` port（Protocol，契约写在 docstring：条目四键 id/title/text/created_at、id 形如 `e0001` 递增、UTC ISO 8601、搜索大小写不敏感、返回副本）+ `JsonlStore`（唯一碰文件的实现）+ `InMemoryStore`（纯内存，禁文件逻辑）；`add`/`search` 返回副本，第 14 课练习标出的 rep exposure 缺口已补；装配单点在 `kb/cli.py`。**沙盒仍无测试、无 CI**——`tests/test_storage.py` 是第 19 课练习的产物，由学习者做，不要代做；第 24 课 CI 也不要提前抢。
- **知识库 CLI 的教学定位**：第 14 课练习的对照物（接口草图 + 不变量）；第 15 课练习的迁移对象（已完成）；第 16 课练习的设计对象；第 17 课练习的架构对象；第 18 课练习的交接对象（design doc 可引用 `kb/storage.py` 真实路径）；第 19 课起对着 `Store` port 写测试，`InMemoryStore` 现成当测试替身。
- **M4 第 19 课已完成（2026-10-28）**：`lessons/0019-pytest-test-design.html`、`reference/0019-testing-card.html`。标题「pytest 与测试设计：划分、边界、覆盖率」（与地图一致）。M4 开篇：把第 14 课的不变量、第 15 课的缝、第 18 课的 design doc 接成测试面。核心内容：测试是从无限输入里选出的有限样本；MIT 6.031 的 correct / thorough / small；等价类划分与边界值分析；组合用例不做笛卡尔积（pairwise 折中）；黑盒先写、白盒补漏；语句/分支/路径覆盖与「覆盖率不证明断言对」；pytest 的 fixture、parametrize、tmp_path；同一批契约测试跑两个 adapter；三次变异检查（只搜标题 / startswith / 返回内部 dict）；两处契约空洞由人拍板（关键词是子串还是整词、空 query 返回什么）。理论来源：SWEBOK v4 ch.5（5-1~5-20）、MIT 6.031《Testing》、SE-EDU《Test Case Design》；行业做法：CMU 17-313《09-testing》与《11-oracles》；实践：pytest / pytest-cov 官方文档，`tdd` 技能留给第 20 课。**注意：`pytest-cov` 的 `--cov-branch` 看不到同一行 `or` 的短路，课件已改成「用变异检查或 if/elif」，不要写回旧说法。**
- **第 19 课已按审计流程收尾（2026-10-28）**：学习者子代理两轮审计（引用、页码、沙盒代码、pytest 实际行为全部核实）。第一轮报「必须改 6、建议改 27、可不改 5」，必须改已全部落实：① 十一格表套不进单条目 `parametrize`，代码改成 `entries` 列表（空仓库/多条命中才写得出来）；② 分区表把输入划分、边界清单、输出不变量混在一起，拆成「输入划分」表 + 边界表 + 独立不变量说明；③ `--cov-branch` 不标 `or` 短路（实测 coverage 7.17），改成「变异检查或 if/elif」；④ 「四十个测试 small 占了」自相矛盾，改成「跑得快但重复，谈不上 small」；⑤ 整词语义下该改的是「Test」「P」，不是「入门」；⑥ 变异检查没有还原机制、会冲掉契约改动，补「先 git commit，改完 git diff，git checkout 还原，再 git diff」。第二轮复核又报 6 条新的必须改，已落实：① 参考卡分区表仍混着边界和不变量，已拆；② 正文「七种场景 + 单字符/整标题/空 query」少算「Test」，已补；③ 整词语义下第 3 条改空会失去「标题中间命中」代表，已改成「Py Test 入门」查「Test」并交代第 10 条的分词规则；④ 完成标准和参考卡写 `pytest -q` 与正文自己的 `python -m pytest` 警告矛盾，已统一；⑤ 反馈提示词的「第 2 步」悬空、未提交时 `git checkout` 会冲掉契约改动，已改成「先确认 git status 干净，未提交不要 checkout」；⑥ source 把 SWEBOK p5-16 写成「覆盖率度量」，实际是「测试过程度量 / ISO 29119」，已改。建议改也落实了大部分：步骤 5 改成「读红也读绿」、覆盖率命令改 `--cov=kb.storage` 并说明 `cli.py` 0%、补 `pip install`、补副本/重开测试代码、design doc 未定/已定分指「风险与未决问题」/「架构」、删 `knowledge-pet`、补 `python -m pytest` 与 `pytest` 的区别、`created_at` 口径统一（UTC + 微秒，不断言字符串写法）、oracle 的「另一个实现」补 CMU 11-oracles p18、CMU 可测性四原则改成「符合后两条」、「三个词/四个关键词」修正、「对狠小」统一成「正确彻底小」、删「拍四块板/小而狠」等生造短语、砍「不是 A 而是 B」密度、测试名改具体、下一课「最后重构」按 `tdd/SKILL.md` 改成「重构不在循环里」、场景动机改成「嫌结果太杂」、参考卡的示例决定与代价列同步、`.coverage`/`.pytest_cache` 提交提醒、变异改「一次只改一个 adapter」。未做的只有「可不改」档的风格偏好（如「解药」「认三个坑」等课程惯用说法）。
- **审计提示词规范（2026-10-27）**：每写完一课派「懂编程、没系统学过软件工程、用过技能包」身份的子代理审计，目标完全掌握，按必须改/建议改/可不改报告，修完必须改才算写完；提示词**必须交代**「参考资料已本地化在 `courseware/`，核引文不用联网」和「技能包全目录 `C:\Users\admin\.agents\skills\` 可读，技能描述逐一对原文」（`COURSE-STANDARD.md`「写完一课」一节）。落实范围由用户拍板，惯例是「必须改 + 措辞」，可按审计总体判断追加衔接类。
- 写作原则：软件工程理论是主线，AI + 技能包是实践；课件是一篇通俗、具体、有逻辑顺序的文章，先场景后概念，场景优先软件领域的实际工作场景；段落之间要有过渡，标题是叙事节拍；表格只做对照；遮住小标题仍能读出前后因果；文字没有 AI 味（电报式短语、表演性开场、生造名词、夸赞形容、同义反复、翻译腔都算，「不是 A，而是 B」和对偶口号一节课一两处为限）。修改课件时先通读本课全文、前后相关课和参考卡，不要只改被指出的局部。
- 结构定型（沿用 12–19 课）：正文性小节（如「三个常见误区」）排在练习之前；recap（「今天带走的三句话」）在练习与反馈回路之后；`div.source`、`div.next` 收尾。

## 下一课：第 20 课「TDD 红绿重构：先写失败测试买到了什么」

- 模块：M4「实现与测试」第二课。地图行：技能 `tdd`，产出「第一个完整的红绿重构循环」。
- 位置：第 19 课把「测什么」设计清楚（划分、边界、预期值、覆盖率缺口），这一课把用例表放进循环；第 21 课修测试形状（行为、公开接口、反同义反复），第 22 课测试替身，第 23 课 `/implement` 做完工单，第 24 课 CI。开头要回指第 19 课的 `tests/test_storage.py` 是回归网，结尾指向第 21 课。
- 理论来源：SWEBOK v4 第 4 章 §4.16 Test-First Programming（printed 4-14，写课前核对原文）＋第 5 章回归测试；MIT 6.031《Testing》的 “Test-first programming” 与 “Iterative test-first programming”；CMU 17-313《09-testing》p21 TDD（「Tests first!」「Never write code without a failing test」及其 claims）；经典 Beck《Test-Driven Development: By Example》（2002，本地可能无全文，按经典转引处理）。`tdd/SKILL.md`、`tests.md`、`mocking.md` 只作实践来源，不作理论来源。
- 实践来源：`C:\Users\admin\.agents\skills\tdd\SKILL.md`（红→绿循环、测试站在预定的 seam、好测试走公开接口、反 tautological、反 horizontal slicing、**Refactoring is not part of the loop**）、`tests.md`（好/坏测试与 tautological 例子）、`mocking.md`（第 22 课再展开）。写课前按 `SKILL.md` frontmatter 核对调用类型（当前没有 `disable-model-invocation`，可被模型拉起，也可用户手动调用；课件写清这一点）。
- 教学注意：MISSION 要求「测试从零教起」，第 19 课已把 pytest 基础打完；第 20 课不要再教 fixture/parametrize 语法，只教循环。**技能与课程标题有一处差异要写清**：课程地图叫「红绿重构」，但 `tdd/SKILL.md` 明确说 refactoring 不属于红绿循环，属于 review 阶段；课件要么按技能口径写成「红→绿；重构在 review」，要么明说这是课程借用的常见叫法、技能的分工不同。不要含糊过去。
- 练习对象：在沙盒里对 `Store` 加一个真实的小行为，做完整的一轮。候选：`delete(id)`（契约要定：删不存在的 id 返回什么；两个 adapter 都要实现；可自然带出共享的 entry 构造/查找逻辑重构）；`count()` 太浅，不推荐；改 `search` 多关键词会牵动第 19 课整套用例，风险大。写课前由用户拍板对象；如果用户没做第 19 课练习，先用第 19 课的最小套件或现补一条失败测试，不要代做。
- 产出：`lessons/0020-*.html`（文件名以实际标题为准）、`reference/0020-*.html`，并更新课程地图、`NEXT-SESSION.md`、`NOTES.md`。
- 不要写第 21 课。

## 审计排期（backlog，暂不执行）

- 已审计：第 6、16、17、18、19 课（19 于 2026-10-28）。**待审计 14 课：第 1–5、7–15 课。**
- 默认排法（提案，可调）：按 1→15 顺序，每会话 2–3 课（审计＋修复耗上下文，一轮报告很长）；先审前面的课是因为概念依赖——前面讲错，后面跟着错。若想先堵「技能包行为写错会误导操作」的风险，可把技能事实密集的课提前：第 3（工作台/技能总览）、8（to-spec）、13（triage）、12（wayfinder）、10（to-tickets）。
- 每批的审计提示词按 `COURSE-STANDARD.md`「写完一课」的提示词要点写，**必须交代**：参考资料已本地化（`courseware/`，不联网）、技能包全目录可读（`C:\Users\admin\.agents\skills\`）。点名的技能按每课内容现选（地图技能栏 + 「AI + Matt」节落地的技能 + 正文点到的技能），不要照抄上一课的清单；技能栏「—」的课明说无独立技能，正文点到的技能仍逐一对原文。
- 何时启动、每批几课由用户拍板；启动后逐批销账，在本节更新剩余清单。

## 待确认

- **第 19 课留下的契约问题**：`Store` 的「关键词」是子串还是整词、空 query 返回什么，由学习者在练习里拍板并写进 docstring；课件给的是示例决定（子串 + 空列表），不是标准答案。id 到 10000 条之后（`e9999 → e10000`）的宽度没定，已作为「边界从契约来」的例子记在课件里，未解决；空白串 query、错误模式（现在不抛异常）也没定。第 20 课若动 `Store`，先读这些决定，别把示例当契约。
- **第 20 课练习对象未拍板**：`delete(id)` 是候选，不是决定；写课前问用户。若用户想用别的行为，保持「一个真实小行为 + 一轮完整循环」即可。
- **假件/桩件/模拟对象的细分留给第 22 课**：MIT 6.031 只有 stub 的简短段落；第 22 课写课前要补来源（候选：Meszaros《xUnit Test Patterns》或 Fowler《Mocks Aren't Stubs》，均无本地全文，照经典转引处理或补下载）。
- Feathers《Working Effectively with Legacy Code》（2004）与 Cockburn《Hexagonal Architecture》（2005）本地无全文；第 15 课已按「经典转引 + 标注」处理。联网后可补一次原文核对（seam、enabling point 的英文原句）。
- Bass/Clements/Kazman《Software Architecture in Practice》本地无全文；第 17 课的 quality attribute scenario 六段写法按经典转引处理。ATAM / SAAM / QAW 无本地材料，任何课都不要展开完整评估方法。
- Ousterhout 摘录（`courseware/ousterhout/aposd2ndEdExtract.pdf`，扫描件 20 页）实测内容：ch.6「General-Purpose Modules are Deeper」书内 p39–49（PDF 3–13）、ch.21「Decide What Matters」p171–174、两段 Clean Code 对比（p76、p99–100）。**经典的 ch.4「Modules Should Be Deep」和「Design It Twice」章节都不在摘录里**；引用时注明「书不在本地」或用摘录章节 + MIT 6.031。
- 第 16–18 课审计的「建议改」未采纳项已存档在 `NOTES.md` 对应调整条目（第 16 课四条、第 17 课七组、第 18 课七条）；以后若大改这三课，从那里找。
- 沙盒 `GLOSSARY.md`、`docs/adr/`、`.scratch/`、`.out-of-scope/` 仍懒创建，由各课练习带出，不要提前建。
- 第 3 课的 38 技能清单按 2026-10 最新版整理；如果上游再改，以 `SKILL.md` 和 README 为准。

> AI生成
