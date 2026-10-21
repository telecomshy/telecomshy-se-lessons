# 课程离线课件

下载时间：2026-10-20。下载方式：`curl -x http://127.0.0.1:7890`（本机 Clash）。

用途：个人学习与课程备课。各站许可不同，**以原站为准；本目录不再分发**。

## 目录

| 目录 | 内容 | 文件数 | 大小 | 来源 |
|---|---|---:|---:|---|
| `mit-6.031/` | 30 讲 readings、general 页、Starb 项目页 | 42 | 4.0 MB | [MIT 6.031](https://web.mit.edu/6.031/www/sp21/) |
| `cmu-17-313/` | 13 份 lecture PDF + syllabus | 15 | 26.8 MB | [CMU 17-313](https://cmu-313.github.io/) |
| `swebok/` | SWEBOK v4 PDF | 1 | 5.7 MB | [IEEE CS](https://ieeecs-media.computer.org/media/education/swebok/swebok-v4.pdf) |
| `se-education/` | SE-EDU 教材 28 章（print 版）+ 门户页 | 31 | 4.0 MB | [SE-EDU](https://se-education.org/se-book) |
| `google-sre/` | Google SRE Book 49 个章节页 | 50 | 3.2 MB | [SRE Book](https://sre.google/sre-book/) |
| `12factor/` | 12 章 + epub | 14 | 0.2 MB | [12factor.net](https://12factor.net/) |
| `ousterhout/` | 书页 + 第二版摘录 PDF | 2 | 13.3 MB | [Ousterhout](https://web.stanford.edu/~ouster/cgi-bin/book.php) |
| `saas-book/` | 课程主页 + teaching 页 | 2 | 0.5 MB | [SaaS Book](https://www.saasbook.info/) |
| `berkeley-cs169/` | 课程目录页 + sp24 跳转页 | 3 | 0.1 MB | [Berkeley CS 169](https://www2.eecs.berkeley.edu/Courses/CS169/) |
| `brooks/` | “No Silver Bullet” PDF | 1 | 0.8 MB | [UNC](https://www.cs.unc.edu/techreports/86-020.pdf) |
| `aihero-smart-zone/` | smart zone 词条页 | 1 | 0.2 MB | [AI Hero](https://www.aihero.dev/ai-coding-dictionary/smart-zone) |
| `teachyourselfcs/` | 自学课程表 | 1 | <0.1 MB | [teachyourselfcs](https://teachyourselfcs.com/) |

合计约 **59 MB**。

## 与课程的对应

- **模块 0–1（地图、想清楚）**：MIT 6.031 的 specifications、testing、code review；CMU 的 specs、design docs；SE-EDU 的 requirements、process。
- **模块 2（写成计划）**：CMU 的 project planning、metrics；SE-EDU 的 project planning、requirements。
- **模块 3（做出来）**：MIT 6.031 的 testing、ADT、debugging；CMU 的 unit testing、oracles、property-based testing；SE-EDU 的 design、testing、refactoring。
- **模块 4（验收与守护）**：CMU 的 metrics；SRE 的 postmortem、incident、monitoring；12factor 的运维约束。
- **模块 5（主线之外）**：AI Hero 的 smart zone；SRE；12factor。
- **原理底座**：SWEBOK、Ousterhout 摘录、Brooks 论文。

## 仍未拿到

- **Rutgers（Marsic）软件工程教材**：`https://ece.rutgers.edu/~marsic/books/SE/` 301 后仍 404，原书可能已迁移或下线。
- **Berkeley CS 169 的 sp24 站点**：`https://inst.eecs.berkeley.edu/~cs169/sp24/` 需要 CalNet 登录；本地只有课程目录页。
- **SaaS 教材全文**：商业书，只有主页与 teaching 页；视频在 YouTube 播放列表里。
- **SE Radio、Dijkstra archive、martinfowler 文章**：不是课件，未下载。

## 说明

- HTML 是离线快照，CSS 与图片可能缺失，正文可读。需要看排版时回到原站。
- 下载时用 `curl -x` 临时走 Clash；2026-10-20 10:31 重启后 `webfetch` 已恢复代理，后续可以直接抓取。
- 这个目录不进 git，也不对外分发。
