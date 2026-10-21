# 软件工程 + AI 辅助编程（课程开发仓库）

一门给「写了很多年代码、但没系统学过软件工程」的开发者准备的课。主线是软件工程的生命周期，实践方式是用 [Matt Pocock 的技能包](https://github.com/mattpocock/skills) 加 AI 辅助编程，把每个活动在沙盒里真做一遍。

34 节、7 个模块，约 52 小时；每周 5–8 小时，8–10 周跑完。单人开发者版：团队概念保留，活动改写成与 agent、与未来维护者的协作。

## 课程结构

| 模块 | 主题 | 节数 |
|---|---|---|
| 0 | 地图与工作台 | 3 |
| 1 | 需求与语言 | 5 |
| 2 | 计划与过程 | 5 |
| 3 | 设计与架构 | 5 |
| 4 | 实现与测试 | 6 |
| 5 | 验收与维护 | 5 |
| 6 | 专业实践与 AI | 5 |

模块 1–6 开头各有一次十分钟的「模块导读」：一篇主读物、三个问题，不产出练习，不计入 34 节。

## 目录

| 路径 | 用途 |
|---|---|
| `lessons/` | 课件，每节一个独立 HTML，直接浏览器打开 |
| `reference/` | 参考卡；`course-map.html` 是 34 节的完整地图 |
| `learning-records/` | 学习记录 |
| `courseware/` | 理论来源课件的本机副本（PDF 不进仓库，清单见 `courseware/README.md`） |
| `MISSION.md` | 课程目标、成功标准、约束、范围 |
| `COURSE-STANDARD.md` | 写作规范：五段结构、来源要求、术语与叙事规则 |
| `SOURCE-MAP.md` | 八个软件工程活动各自对应的课件章节/页码 |
| `CURRICULUM-REVIEW.md` | 为什么这样排：复核过程与结构变更记录 |
| `AGENTS.md` | 给 AI 助手（OpenCode）的会话规则 |
| `NEXT-SESSION.md` | 当前进度与下一节写什么 |
| `NOTES.md` | 调整历史与偏好 |

## 怎么用

1. 先打开 `reference/course-map.html`，看清 34 节和七个模块的关系。
2. 从 `lessons/0001-what-is-software-engineering.html` 开始按序读；每节先读、再在沙盒 `D:\code\my_projects\se-course-sandbox` 里做练习。
3. 写新课或改课之前，读 `AGENTS.md`、`COURSE-STANDARD.md`、`SOURCE-MAP.md`，再读前后各一节。

## 来源与版权

课件 PDF（CMU 17-313、SWEBOK v4、*A Philosophy of Software Design*、Google SRE Workbook、MIT 6.031、SE-EDU 等）仅作本地理论来源，未随仓库分发；需要时按 `courseware/README.md` 的清单自行获取。课程正文引用处均标注文件名与章节/页码。
