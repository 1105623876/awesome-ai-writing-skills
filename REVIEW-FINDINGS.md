# ai-writing skill — 重构审阅与待办

- **审阅对象**：`awesome-ai-writing-skills`（重构后状态）
- **审阅日期**：2026-10-03
- **审阅方式**：逐文件阅读 + 路径可达性核对 + 体积统计 + 泄漏扫描（未运行任何写作案例）
- **本文用途**：交给后续执行者继续重构。**第 1 节是已核验通过的部分，不要回退；第 2 节有阻塞项，先决策再动手。**

---

## 0. 基线快照

架构已从「原创综合」改为「路由 + 上游原文」：入口只负责按任务选择参考，规则与示例一律读上游原文件。

| 动作 | 文件 |
|---|---|
| 新增 ~63 个 | `references/asd-ste100/`(7) `references/humanizer-zh/`(4) `references/qu-ai-wei/`(11) `references/academic-writing/`(1) `references/ccf-writing-skills/`(40) |
| 删除 3 个 | `references/chinese.md`、`references/technical.md`、`references/academic.md` |
| 删除 2 个 | `evals/cases.md`、`evals/RESULTS.md`（`evals/` 目录残留为空） |
| 重写 4 个 | `SKILL.md`(67→48 行)、`README.md`(82→88)、`SOURCES.md`(69→15)、`THIRD_PARTY_NOTICES.md`(48→48) |
| 未改动 | `LICENSE` |

体积：**68 files / 13.74 MB**

| 参考 | 文件数 | 体积 |
|---|---|---|
| ccf-writing-skills | 40 | **13.37 MB** |
| qu-ai-wei | 11 | 0.27 MB |
| asd-ste100 | 7 | 0.06 MB |
| humanizer-zh | 4 | 0.03 MB |
| academic-writing | 1 | 0.00 MB |

无 git 历史（审阅时）。泄漏扫描：未发现本地绝对路径、用户名、邮箱或 API 凭据。

---

## 1. 已核验通过（勿回退）

1. **四份文档同步**：`SKILL.md` / `README.md` / `SOURCES.md` / `THIRD_PARTY_NOTICES.md` 已一致反映新架构，不是半成品。
2. **`SKILL.md` 全部 10 个引用路径可达**（逐条核对）：
   `qu-ai-wei/SKILL.md`、`qu-ai-wei/references/patterns.md`、`qu-ai-wei/references/brand-voice.md`、`qu-ai-wei/references/examples.md`、`humanizer-zh/SKILL.md`、`asd-ste100/SKILL.md`、`asd-ste100/references/writing-rules.md`、`asd-ste100/examples/before-after.md`、`academic-writing/SKILL.md`、`ccf-writing-skills/SKILL.md`
3. **脱敏已做且已声明**：CCF 来源说明中的原作者个人目录改为技能名，记于 `SOURCES.md:13`。
4. **MIT 参考的 LICENSE 随文件保留**：`asd-ste100`、`humanizer-zh`、`qu-ai-wei` 各自带 LICENSE，`THIRD_PARTY_NOTICES.md:9-11` 指向包内文件而非外链。
5. **诚实声明保留**：`README.md:40` 仍写明「尚未在 Codex 和 Claude Code 中分别实测自动加载」。
6. **相对路径解析规则已写明**：`SKILL.md:48` 声明各来源入口的 `references/`、`examples/`、`scripts/`、`paper_ref/` 从该来源自己的文件夹解析。

---

## 2. 阻塞项（需先决策）

### B1. 许可：五份参考的许可状态（2026-10-03 核查后更新）

**已解决**：`references/ccf-writing-skills/` 的来源已定位为 [mikubaka88/CCFA-Skills](https://github.com/mikubaka88/CCFA-Skills) 中的 `ccf-paper-writer` 技能（逐条比对文件路径一致），该仓库为 **MIT（Copyright (c) 2026 Chaoyue Li）**。已补做两项合规动作：

1. 新增 `references/ccf-writing-skills/LICENSE`（上游 MIT 原文）。
2. `THIRD_PARTY_NOTICES.md` 的 MIT 表新增 CCFA-Skills 一行；`SOURCES.md` 记录上游与许可。

MIT 要求「在副本中包含版权声明与许可文本」，此前包里缺该文件，属合规缺口，现已补齐。

**仍阻塞**：`references/academic-writing/SKILL.md`（作者 teamolab，来源 ClawHub）**未声明任何许可证**——文件 frontmatter 只有 `name`/`description`/`tags`/`version`/`author`/`source`，无 license 字段；来源页面为 SPA 且无许可字段；该平台无 terms/legal/docs 页面，亦无公开 API。**按默认视为保留所有权利**。

- 本地使用无碍。**公开发布需要作者授权，或从公开副本中移除该文件**（1 个文件 / 0.00 MB；移除后需同步调整 `SKILL.md:34`、`README.md:81`、`SOURCES.md`、`THIRD_PARTY_NOTICES.md`）。
- 待决策见第 5 节 Q1。

### B1b. 3 篇论文 PDF 的版权归属（残留细节）

`references/ccf-writing-skills/paper_ref/` 的 3 篇 PDF 随 MIT 仓库 CCFA-Skills 一同分发，因此随包分发有上游先例；但论文本身版权属其作者或出版方，上游的 MIT 主张不当然覆盖它们。加上 agent 无法直接读取 PDF 正文，建议从仓库移除（可省 13.5 MB），改以已有的 `references/exemplars/cards/*.md` 承载示例。

### B2. 13.5 MB 论文 PDF 的实际效用未确认

| 文件 | 体积 |
|---|---|
| `references/ccf-writing-skills/paper_ref/LLaVA-4D.pdf` | 11,542 KB |
| `references/ccf-writing-skills/paper_ref/VGGT_ Visual Geometry Grounded Transformer.pdf` | 1,880 KB |
| `references/ccf-writing-skills/paper_ref/best-papers/aaai-2025-every-bit-helps.pdf` | 151 KB |

- agent 无法直接读取 PDF 正文（除非客户端具备文本提取）。若 CCF 的规则文件不实际引用这些 PDF，它们就是纯负重 + 许可风险。
- **已决定并执行**：移出仓库（`.gitignore` 排除，本地保留）。如需重新取得，可从上游 [CCFA-Skills](https://github.com/mikubaka88/CCFA-Skills) 的 `ccf-paper-writer/paper_ref/` 取回。
- **剩余待办**：核查 `references/ccf-writing-skills/` 内是否有文件引用 `paper_ref/`；若有，需在文档中注明该目录为可选的本地补充，否则会出现指向不存在文件的引用。

> 仓库状态：已建库并推送至 `https://github.com/1105623876/awesome-ai-writing-skills`（public，67 个跟踪文件），`academic-writing` 与 `paper_ref/` 均未上传。

### B3. 6 个 SKILL.md 的发现冲突（未实测）

```
SKILL.md                                     ← 本项目入口
references/academic-writing/SKILL.md
references/asd-ste100/SKILL.md
references/ccf-writing-skills/SKILL.md
references/humanizer-zh/SKILL.md
references/qu-ai-wei/SKILL.md
```

- 多数 Agent Skills 客户端**递归扫描 `SKILL.md` 来发现技能**。若客户端如此，安装本 skill 会注册成 6 个；且触发词重叠（「去 AI 味」同时命中 `ai-writing`、`qu-ai-wei`、`humanizer-zh`）→ 路由不确定。
- 另有 `references/ccf-writing-skills/agents/openai.yaml` 构成额外发现面。
- **待办**：在 Codex 与 Claude Code 各实测一次（装一个是否注册成多个、实际被触发的是哪个）；据结果决定是否重命名（如 `_upstream/asd-ste100.md`）或移出目录。

---

## 3. 功能缺陷

### C1. 上下文成本大幅上升（量化）

- `references/qu-ai-wei/SKILL.md` **93 KB** + `references/qu-ai-wei/references/patterns.md` **74 KB**。
- `SKILL.md:18-20` 要求中文去 AI 味时读取 qu-ai-wei 的 SKILL.md、patterns.md、brand-voice.md、examples.md。
- 中文 UTF-8 按 3 字节/字符计，仅前两份 ≈ 5.5 万字符，**约 3–5 万 token**，每次「润色一下」都要先付这个成本。
- **建议**：改成分层读取——先读入口索引，按任务命中的模式类别再读 `patterns.md` 的对应条目，而不是整篇加载。

### C2. 版本号未动

- `SKILL.md:9` 仍为 `version: "0.1.0"`。这是破坏性重构（架构、文件布局、引用路径全变），应升版。

### C3. evals 被删且无替代

- 删除 `evals/cases.md`（15 个回归案例）与 `evals/RESULTS.md`（含诚实的能力边界声明）。
- 新 `README.md` 已无任何测试段落，`evals/` 目录残留为空。
- **待办**：为新架构重建回归案例，重点测**路由正确性**（是否加载了正确参考、是否误加载、是否用通用原则替代了原文规则）——这正是重构要解决的问题。案例须标明「未运行不得写成已通过」。

### C4. description 退化

- 旧版 description 含排除句：`Not an AI-authorship detector or a substitute for research and experiments.`
- 新版 `SKILL.md:3-6` 无此排除句，仅 `SKILL.md:46` 保留弱化表述（「文风判断不能当作作者身份的事实鉴定」）。
- **影响**：description 是客户端的路由依据，缺排除句会增加误触发（被当作 AI 检测/研究替代）。

---

## 4. 能力回退（设计取舍，需明确确认是否接受）

| # | 丢失项 | 位置（旧版） | 后果 |
|---|---|---|---|
| D1 | **跨源冲突仲裁表**（8 行裁决） | 旧 `SOURCES.md` | 5 份来源互相矛盾时**运行时不再仲裁**。新 `SKILL.md:44` 明确「不要为了统一它们而删除原有的阈值、例子、例外或写作方法」。同一任务的行为将取决于模型如何理解来源冲突 |
| D2 | 操作边界表（5 行：润色/结构/摘要/起草/翻译各自的允许改动与保留边界） | 旧 `SKILL.md` | 各参考对「能改多少」的默认不同，缺少统一约束 |
| D3 | 「不应机械处理的情况」列 | 旧 `references/chinese.md` 诊断表 | 反过拟合设计丢失（哪些情况下不要套用该条规则） |
| D4 | 7 条明确拒绝及理由（禁词表、人味配额、自审表演、把抽象擅自具体化等） | 旧 `SOURCES.md` | 约束模型的负向清单消失 |
| D5 | 来源副本 SHA-256（4 条） | 旧 `SOURCES.md` | 无法确定所收录的是哪个修订版；`Humanizer-zh`、`ccf` 仍标「副本未标版本」 |
| D6 | 非编造规则段（9 条） | 旧 `SKILL.md` | 现仅 `SKILL.md:46` 残留两条（例子不可照抄补编、文风≠身份鉴定） |

**判断**：本次重构的方向是合理的——旧设计让模型「综合归纳」，本身就在邀请它自作主张；新设计改为「读原文规则、不得用通用原则替代」。但代价是从「有主张的编辑」退化为「路由器」，而 D1 的仲裁层是旧版唯一别人没有的东西。建议至少恢复 D1、D2、D4 的精简版。

---

## 5. 待决策清单（需用户先回答）

| # | 问题 | 选项 |
|---|---|---|
| **Q1** | ~~academic-writing 如何推？~~ | **已决定并执行：保持 public，剔除该文件。** `references/academic-writing/` 已写入 `.gitignore`（本地保留、仓库不含），四份文档已同步改为「本地自备」。 |
| **Q1b** | ~~CCF 的 3 篇论文 PDF 如何处理？~~ | **已决定并执行：移出仓库。** `references/ccf-writing-skills/paper_ref/` 已写入 `.gitignore`（本地保留、仓库不含）。 |
| **Q2** | 被删的 5 个文件（`references/chinese.md`、`technical.md`、`academic.md`、`evals/cases.md`、`evals/RESULTS.md`）是否恢复？ | 从原始来源恢复 ／ 从审阅方上下文逐字重建 ／ 接受删除 |
| **Q2** | 被删的 5 个文件（`references/chinese.md`、`technical.md`、`academic.md`、`evals/cases.md`、`evals/RESULTS.md`）是否恢复？ | 从原始来源恢复 ／ 从审阅方上下文逐字重建 ／ 接受删除 |
| **Q3** | D1–D6 是否恢复？ | 全部恢复 ／ 仅恢复 D1+D2+D4 精简版 ／ 全部放弃（纯路由） |
| **Q4** | `REVIEW-FINDINGS.md`（本文件）是否随仓库发布？ | 保留在仓库 ／ 加入 .gitignore ／ 发布前删除 |

---

## 6. 建议执行顺序

1. 回答 Q1 → 处理 B1 的分发范围（**在首次 push 之前**）
2. 实测 B3（Codex + Claude Code 的发现与触发行为），按结果决定嵌套 `SKILL.md` 的去留
3. 处理 B2（核查 `paper_ref/` 被引用情况 → 移出或 .gitignore）
4. 修 C1（分层读取）、C2（升版）、C4（description 补回排除句）
5. 依 Q3 决定恢复哪些回退项；恢复 D1 时需重写为新路径下的 `references/arbitration.md`
6. 重建 evals（C3），优先覆盖路由正确性
7. 更新 `README.md` / `SOURCES.md` / `THIRD_PARTY_NOTICES.md` 使之与新状态一致（尤其 Q1 选了 B 时的分发说明）
8. 补 `SOURCES.md` 的版本锚点（E2/D5）

**修订后仍需保持**：第 1 节的 6 项不得回退；`THIRD_PARTY_NOTICES.md` 关于无许可材料的自述不得删除或弱化。

---

## 7. 审阅方未能验证的事项

1. 未在 Codex / Claude Code 实测安装、自动加载与触发（B3 因此仍是推测）。
2. 未运行任何写作案例，**本次审阅不构成对写作效果的评价**。
3. 未逐一比对收录文件与上游原版是否逐字一致；仅核对了路径存在与体积。
4. 未核查五份上游 skill 内部相对链接在移动后是否仍然可达（例如 `qu-ai-wei/SKILL.md` → 其 `references/*.md`、`ccf-writing-skills/SKILL.md` → 其 `references/*.md`、`exemplars/index.md`）。**建议补做**：抽取各入口的 markdown 链接并逐个 Test-Path。
5. 未核查 `.pdf` 之外的二进制或压缩内容中是否含个人路径（文本扫描已覆盖）。
6. `references/ccf-writing-skills/agents/openai.yaml` 的作用与是否应随包分发未评估。
