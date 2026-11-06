# 下一会话交接

> 用途：把课程状态从当前会话交接到一个新会话，避免重读整段对话。**课程已全部写完（34/34），没有下一课**；本文件现在记的是收尾状态、练习留档约定与剩余的审计工作。
> **OpenCode 会自动读取根目录的 `AGENTS.md`；它已经要求新会话先读本文件、`COURSE-STANDARD.md` 和 `SOURCE-MAP.md`。**

## 先读这些（按顺序）

1. `AGENTS.md`：会话规则（OpenCode 自动加载，不用手动提醒）。
2. `NEXT-SESSION.md`：本文件，完结状态与剩余工作。
3. `COURSE-STANDARD.md`：五段结构、审计流程——老课审计仍按它出提示词。
4. `SOURCE-MAP.md`：引用依据；核对引文先查它。
5. `MISSION.md`、`NOTES.md`、`reference/course-map.html`（34 节全部带链接）、`CURRICULUM-REVIEW.md`。

## 当前状态

- **课程骨架 34 节 / 7 模块全部写完并逐课按审计流程收尾**：M0（1–3）、M1（4–8）、M2（9–13）、M3（14–18）、M4（19–24）、M5（25–29）、M6（30–34）。最后一课第 34 课「综合演练 + 迁移到真实项目」于 2026-11-06 写完：`lessons/0034-capstone-migration.html`、`reference/0034-capstone-card.html`（标题以地图为准）。
- **剩余工作只有老课审计**：已审计第 6、16–34 课（34 于 2026-11-06）；**待审计老课 14 课：第 1–5、7–15 课**。排法与提示词要求见下方「审计排期」。
- 技能包已装最新版（2026-10-20）：全局 `C:\Users\admin\.agents\skills\`，共 51 个技能目录，其中 Matt 仓库 38 个（engineering 20、productivity 7、misc 4、in-progress 7）。旧技能目录备份在 `C:\Users\admin\AppData\Local\Temp\opencode\skills-backup-20261020`。
- **沙盒现状（2026-11-06 核）**：`D:\code\my_projects\se-course-sandbox`，主干 `master`，`git log` 只有 `335b4bf`（port 迁移）与 `b2162ce`（骨架），工作区干净；`kb/` 为 `Store` port（`typing.Protocol`，契约在 docstring）+ `JsonlStore` / `InMemoryStore`；无 `tests/`、无 CI、无 remote；`.scratch/` 为空，`GLOSSARY.md`、`docs/adr/` 懒创建；`.pytest_cache` / `.ruff_cache` 是审计遗留。**第 19–33 课练习由学习者做、目前均未做**——第 34 课演练的每站退路（参考卡分支）就是为这个设计的，后续照旧不要代做练习。
- **knowledge-pet 现状（2026-11-06 核，34 课迁移计划的迁移对象）**：`D:\code\my_projects\knowledge-pet`，真实项目（AI 知识问答桌宠，Tauri 壳 + Python sidecar），只有文档没有代码：`AGENTS.md`（tracker 是 GitHub 私有仓库 `telecomshy/knowledge-pet`，gh 命令约定，五个默认标签，single-context）、`CONTEXT.md`（**旧版命名，未迁 `GLOSSARY.md`**）、`docs/architecture.md`（技术栈、Phase 0/1 边界、Deep Module 划分，**Phase 0 = spec #11 / 工单 #12–#18**）、`docs/ipc-seam.md`、`docs/research/` 恰七份（animo-vs-cta-decision、mvp-scope、resolution-2-fastapi、resolution-4-ipc-protocol、resolution-5-lightrag-storage、resolution-6-model-strategy、resolution-7-everything）、`docs/agents/` 三件；分支 `main` + `prototype/ipc-shape`；`.gitignore` 已含 `.env`。**MISSION 边界：课程只写迁移计划不改它的代码**；之后的真实使用按第 34 课迁移计划走。
- 写作原则：软件工程理论是主线，AI + 技能包是实践；课件是文章不是 PPT；文字没有 AI 味；修改课件先通读整篇（细则见 `COURSE-STANDARD.md`）。
- 结构定型：正文性小节（如「三个常见误区」）排在练习之前；recap 在练习与反馈回路之后；`div.source`、`div.next` 收尾。
- 自查分工（2026-11-03 定）：派审计前主代理只做机械自查（术语首见、引文照抄、文件互链、回指名）；掌握度、表达、逻辑、事实四类实质判断只归审计子代理。

## 第 34 课已完成（2026-11-06）

- 写课前用户拍板三项：演练对象＝**薄 HTTP adapter**（第 15 课 Store port 的「将来的 HTTP adapter」兑现；第 33 课错误披露取舍的复查条件「加 HTTP adapter 时」触发；与 knowledge-pet 的 Sidecar seam 同构）；执行深度＝**全程真跑**（八站每站真调技能、真落产物，带退路）；迁移计划落点＝**沙盒 `.scratch/migration-3401/`**（引 knowledge-pet 真实路径但不改它任何文件）。
- 核心内容：位置（不占第九个活动，把八个活动串成一条线，全课收口）；drill（演练）沿用第 29 课一词，对象从事故换成流程；**adaptation（裁剪）**是主概念——SWEBOK ch.10 §2.8（printed 10-8）的裁剪四步（识别差异特征 / 挑标准与文档 / 选策略阶段过程 / 记录决定与理由）加许可句「The adaptation will not require keeping the names provided in Section 2, or including them all」，回指第 9 课引过的 §1.1「no ideal process…」（printed 10-2）；tracer bullet（追踪弹）从「所有层」换成「所有站」。行业做法三条（明说无统一标准）：第一张工单当流程的追踪弹（回指第 10 课，经典转引）；发布口径要可重复（SRE《Release Engineering》「Running reliable services requires reliable release processes.」「aren't 'unique snowflakes.'」「intentional, rather than accidental」+ SWEBOK ch.8 §6 release 定义 printed 8-13——内部发布也算发布）；复盘分两层（retro 管 agent 环境、postmortem 管事故，回指 24/29 课）。
- 八站对照表（站 / 对应活动 / 入口 / 拍板 / 产物 / 退路）：需求（/grill-with-docs，5 课）、规格（/to-spec，8 课，活动列含 Design & Architecture 接缝确认）、工单（/to-tickets，10 课）、实现（/implement，23 课）、测试盘点（19/21/22 判据自查）、CI（24 课链或本地三条）、审查（/code-review，25 课）、上线与复盘（/retro，24/29 课，活动列是 Configuration & Operations）。生效判据两条：演练八站产物齐全可查；迁移计划过第 32 课零上下文判据。
- 练习：第 0 步起点盘点（master、装 ruff/pytest、建 `.scratch/migration-3401/notes.md` 演练站志、33 课遗留处理、knowledge-pet 只读）→ 站 1 需求（六问推荐答案表：端点 POST /add + GET /search?q= 不做 delete、错误映射照 33 课取舍、只监听 127.0.0.1、匹配语义沿用 Store 契约、单线程、标准库 http.server 不引新依赖）→ 站 2 spec（`.scratch/http-adapter/spec.md`）→ 站 3 工单（示例两张：端到端最小链 / 错误映射与关联编号；提交词表+spec+工单记固定点，开 `feature/http-adapter` 分支）→ 站 4 实现（23 课流水线，测试打 HTTP 接口真实 socket + InMemoryStore 注入，500 路径用 22 课桩件）→ 站 5 测试盘点（缺的记 notes 不补课）→ 站 6 CI（本地三条命令兜底）→ 站 7 审查（固定点 + 双轴分档裁决）→ 站 8 上线（合回 master + README 发布说明含已知限制 + 可选 tag v0.1.0 + /retro）。第 2 部分迁移计划：先做沙盒 ↔ knowledge-pet 差异盘点七行（tracker / 词表旧命名 / 代码 / 测试与 CI / 密钥 / 两进程 / 已有工件），再写六节（现状与目标 / 范围与非目标 / 迁移顺序 / 交 agent 与人做与必须验 / 风险与回滚 / 验收与时间盒）。反馈回路：零上下文接手人五问（第一张工单 / 能做哪些 / 想翻案 / 验收含糊 / 越界），处置四类，记 `plan-review.md`。
- **审计已走完（2026-11-06）**：学习者子代理审计（SWEBOK 三处、SRE 四句逐字核全过；grill-with-docs/to-spec/to-tickets/implement/tdd/code-review/retro/handoff/wizard/ask-matt 逐一对原文；沙盒与 knowledge-pet 实地核对），报「必须改 2、建议改 14、可不改 7」，按惯例落实「必须改 + 全部建议改」。值得记的：① 站 1 产物原本没有提交出口（GLOSSARY.md 不在任何一步 `git add` 里，收尾 `git status` 必脏）→ 站 3 提交改为 `git add GLOSSARY.md .scratch/http-adapter`（落了 ADR 再加 `docs/adr`）；② 八站表活动列与第 2 课对不上（「Operations / Maintenance」两课里都不存在；设计与架构整表无落点）→ 站 2 活动列补 Design & Architecture 接缝确认、站 8 改 Configuration & Operations（发布）、收口句改「Requirements 与 Testing & Quality 各占两站」；③ 其余：站 5 判据统一 19/21/22；「19 课集成测试口径」改「19 课契约测试口径」；删「22 课造过缝的形状」（沙盒 cli.py 并无注入缝，缝在本课新代码里自建）；交代站 4 单张工单 review 与站 7 整分支正式审查的关系；「未决问题」补落点（第五节或计划末尾单列）；收尾挪到反馈回路之后并补 retro 改动的提交出口；「参考卡按课索引在课程地图」不实，改「从各课页脚进」；站 1 退路补卡 0004；CI 全称挪到首现处；长句拆分等表达修。可不改档维持现状（retro 七类缩成四类与 29 课口径一致、ch.8 §6 节名差一个 Software 等）。

## 第 34 课练习的留档约定

- 演练记录 `.scratch/migration-3401/notes.md`：每站一行卡点（哪一站、卡了什么、怎么解的），末节 retro 收尾。
- 演练产物：`.scratch/http-adapter/`（spec、issues、review-report.md）+ `feature/http-adapter` 分支实现合回 `master` + README 发布说明（含已知限制：只监听 127.0.0.1、无鉴权、错误只给通用消息加关联编号）+ 可选 `git tag v0.1.0`。
- 迁移计划 `.scratch/migration-3401/migration-plan.md`：差异盘点七行每行填「对流程的影响」+ 六节；引用路径不复制、决定带理由、写给零上下文读者。
- 反馈记录 `.scratch/migration-3401/plan-review.md`：两轮零上下文接手人反馈与处置。
- 收尾提交（反馈回路之后）：README+tag 一笔、`.scratch/` 记录一笔；`git status` 干净；主干 `master`。knowledge-pet 全程只读。

## 审计排期（backlog，暂不执行）

- 已审计：第 6、16、17、18、19、20、21、22、23、24、25、26、27、28、29、30、31、32、33、34 课。**待审计老课 14 课：第 1–5、7–15 课。**
- 默认排法（提案，可调）：按 1→15 顺序，每会话 2–3 课（审计＋修复耗上下文，一轮报告很长）；先审前面的课是因为概念依赖——前面讲错，后面跟着错。若想先堵「技能包行为写错会误导操作」的风险，可把技能事实密集的课提前：第 3（工作台/技能总览）、8（to-spec）、13（triage）、12（wayfinder）、10（to-tickets）。
- 每批的审计提示词按 `COURSE-STANDARD.md`「写完一课」的提示词要点写，**必须交代**：参考资料已本地化（`courseware/`，不联网）、技能包全目录可读（`C:\Users\admin\.agents\skills\`）。点名的技能按每课内容现选（地图技能栏 + 「AI + Matt」节落地的技能 + 正文点到的技能），不要照抄上一课的审计提示词；技能栏「—」的课明说无独立技能，正文点到的技能仍逐一对原文。
- 何时启动、每批几课由用户拍板；启动后逐批销账，在本节更新剩余清单。

## 待确认

- **两轴命名已定案（2026-11-03）**：规范轴（Standards）/ 工单轴（Spec），第 25 课定死用法，第 23 课两处措辞已同步。以后统一用这两个名字，不要再引入别名。
- **第 19 课留下的契约问题**：`Store` 的「关键词」是子串还是整词、空 query 返回什么，由学习者在练习里拍板并写进 docstring；课件给的是示例决定（子串 + 空列表），不是标准答案。id 到 10000 条之后（`e9999 → e10000`）的宽度没定；空白串 query、错误模式（现在不抛异常）也没定。第 34 课站 1 把这些列为「在这一站拍掉」的候选，学习者没做演练就仍未决。
- **第 20 课练习添的两组契约问题**：`delete` 删不到的返回值、返回值形状、id 复用（同样是示例决定，别把示例当契约），以及「删光后重开 id 从哪排」（计数痕迹被删除抹掉，三条出路见第 20 课循环四，课件只当契约空洞处理，未给答案）。
- **第 22 课练习添的一组契约问题**：`JsonlStore` 写文件失败（权限、磁盘满）的错误行为——抛什么、返回什么——契约没定，课件明写「先拍板写进契约再断言，拍不了记进未决问题」。**第 23 课练习正是把它拍板掉**：示例决定是三要素（失败抛 `StorageError` 带原异常 / 失败无返回值、成功路径仍返回副本 / 不留半截条目），学习者可照可改，拍完写进 `Store` docstring。第 34 课站 1 的错误映射推荐答案以它为前提；没做 23 课练习的人按 33 课参考卡样例拍。
- **各课练习的留档约定**（第 24–33 课）仍见 `NOTES.md` 对应条目与本文件历史版本要点：lint 豁免写理由（24）、裁决与实验分支纪律（25）、盲诊断与注入（26）、四份诊断记录与撤修复实验（27）、git status 白名单含 GLOSSARY/ADR（28）、演练目录可复用（29）、记录留主分支原型进分支（30）、研究笔记单文件四要素（31）、handoff 四条核对（32）、责任清单七列与脱敏占位（33）。这些约定不因课程完结失效；第 34 课演练遇到缺口时按对应退路走。
- 沙盒 `GLOSSARY.md`、`docs/adr/`、`.scratch/`、`.out-of-scope/` 仍懒创建，由各课练习带出，不要提前建。沙盒分支名是 `master`、无 remote。

> AI生成
