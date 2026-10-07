# 参考来源与整合记录

## 单一入口与按需参考

根目录 [SKILL.md](SKILL.md) 是唯一 skill 执行入口。长期回复偏好可放在 Agent 的指令文件中；入口按场景或点名请求读取 `references/` 的相关方法，不注册多个入口，不继承来源的私人偏好与强制工作流。

本项目的目的贯穿回答、讲解、文章和论文：内容具体，读者跟得上，句子自然，事实与条件准确。根入口维护通用的交付、路径、来源与清理规则；[plain-language-examples.md](references/plain-language-examples.md) 是本项目编写的自拟示例，不属于九份来源参考。

参考可以保留原文，也可以按本项目精神改写。输出语言、文体、深度、文件与工具使用由当前用户和根入口决定。来源中“必须”“不可省略”的门检、报告、固定轮次、自动触发、安装和配套调用不自动执行，也不在后台执行。

## 原有四份参考

Humanizer-zh、qu-ai-wei 和 CCF 来自维护者本地保存的副本，ASD-STE100 下载自其 GitHub 仓库。早期整合调整了入口文件名、用途说明、存档说明和本地链接，具体见下文；0.4.2 又改写了 CCF 入口和部分配套说明，其余三份保留原正文。

| 参考 | 版本 | 项目内入口 | 原始来源 |
|---|---|---|---|
| Humanizer-zh | 副本未标版本 | [source.md](references/humanizer-zh/source.md) | [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) |
| qu-ai-wei | 0.6.6 | [source.md](references/qu-ai-wei/source.md) | [hzblacksmith/qu-ai-wei](https://github.com/hzblacksmith/qu-ai-wei) |
| ASD-STE100 | 0.4.0 | [source.md](references/asd-ste100/source.md) | [danyuchn/asd-ste100-skill](https://github.com/danyuchn/asd-ste100-skill)，2026-10-03 下载的 master 分支 |
| ccf-writing-skills | 本地副本未标版本；0.5.0 起部分文件取自提交 `5969e6b`，见下文 | [source.md](references/ccf-writing-skills/source.md) | [mikubaka88/CCFA-Skills](https://github.com/mikubaka88/CCFA-Skills) 的 `ccf-paper-writer`、`ccf-humanization` |

这些原入口此前已改名为 `source.md`，前加用途说明；除下述 CCF 适配外，原正文保留。CCF 的 `agents/openai.yaml` 改存 `source-openai.yaml`，只作来源配置记录。来源 README / CHANGELOG 加了存档说明，本地入口链接改为 `source.md`；CCF 一处个人路径改为 skill 名称，其余配套规则、例子和脚本保留。

qu-ai-wei 的来源 README / CHANGELOG 提到的 `tests/` 不在维护者的本地副本中，属于上游开发记录，不是本项目可运行的测试。CCF 论文 PDF 仅本地使用，不随仓库分发。

## PR #2 的三份参考

来源为 [本仓库 PR #2](https://github.com/1105623876/awesome-ai-writing-skills/pull/2)，贡献者仓库为 [buaaeducn/awesome-ai-writing-skills](https://github.com/buaaeducn/awesome-ai-writing-skills)。原提交为 `e05d57350ed3deca4c3851a48b535778517873e0`；公开整合修正位于 `ca2bc398cfdf1927a04d07e9d7e0fd3c90b754bf`，合并提交为 `aca39f1373e54a27b8158e056f35a9ee08c6d9d5`。可在该版本的 `skills/` 下追溯重构前正文。

| 原 skill | 本地参考入口 | 改写范围 |
|---|---|---|
| paper-translate | [source.md](references/paper-translate/source.md) | 默认忠实自然译文；对照、术语、生词、图表按需；保留取源、续译、数字与 PDF 裁图方法 |
| paper-well-know | [source.md](references/paper-well-know/source.md) | 按问题选择读法与证据；报告模板改为可选，允许有依据的评价，不强制五段、流程图与推导 |
| concept-well-know | [source.md](references/concept-well-know/source.md) | 按读者与问题选择深度；可选提纲、核对和配图；保留概念关系、例子与数学错误目录 |

目录从 `skills/` 移到 `references/`，`SKILL.md` 改名为 `source.md`。三份入口与配套模板均按根入口改写，并非原文存档；各自 LICENSE 原样保留。去掉固定 `raw_papers / notes / translate / asserts` 目录、默认研究者与笔记软件、固定语言与色彩、强制配图、子代理与核对报告等私人习惯。

公式笔记不再被等同于一手来源，关键核对回到原材料；支撑成品的来源记录不在交付后自动删除。外部论文、凭证与本机配置不随参考分发。

## HTML 参考与渲染器

来源：[QingYunA/answer-me-with-html](https://github.com/QingYunA/answer-me-with-html)，2026-10-04 获取的版本 0.4.6，固定提交 `300b530c6f12f1db3463ff87c66e75c3f99ea573`。

- 原 `skills/answer-me-with-html/SKILL.md` 改写为 [source.md](references/answer-me-with-html/source.md)，保留内容稿、组件、局部修订与可选视频的使用方法，不继承固定触发阈值、高频模式、面板数量、中文字符限制、个人配置、清理与更新流程。
- [scripts/am.mjs](references/answer-me-with-html/scripts/am.mjs) 从同提交复制，未修改；没有导入整个应用或安装依赖。
- 本项目调用方法显式指定输出、独立临时 `AM_HOME`、`AM_NO_UPDATE_CHECK=1`、`--no-open` 和 `--style off`。脚本内部仍有上游能力，文档边界与调用参数用于控制此次任务的行为。
- 上游 MIT LICENSE 与打包依赖的许可证一并保留，依赖版本来自该提交的锁文件；许可全文取自对应 npm 发布包。见 [渲染器许可清单](references/answer-me-with-html/scripts/THIRD_PARTY_NOTICES.md)。

## 写作约定

中文的语体与句法主要参考 qu-ai-wei，Humanizer-zh 补充诊断；英文回答和解释默认 STE-flavored，技术操作文本采用 Strict。这里的“八成 STE”是项目的写法简称，不是官方模式或合规比例。学术稿件的逐句改写参考 CCF 的 humanization，章节与证据组织按当前问题选用 Nature 或 CCF 的对应方法；原作者格式和范例不自动视为当前用户偏好。

翻译、论文阅读、概念梳理和 HTML 都是按需方法，不是扩展出的四套默认流程。许可与署名见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。

0.4.1 的一致性审阅进一步区分了讲解与改稿意见、普通聊天与文件可视化，以及英文回答、技术操作文档和学术稿件的写法；删除新参考中重复的通用文件规则。英文回答的 STE-flavored 默认与原有数字阈值保留；这次审阅没有新增对原有四份来源参考目录的修改。


## 0.4.2：CCF 最小适配、本机发现验证与纠正后的交付

CCF 改为参考入口加按需方法文件的形式，仍通过根目录 `SKILL.md` 使用，不新增可发现的技能入口。重构前的本地完整版本可在本仓库提交 `91a2969a475124cc47971c1bbe47e2f23a5d27de` 的 `references/ccf-writing-skills/` 下追溯。

- `source.md` 改为使用边界、任务索引与交付说明，去掉来源的运行配置、默认私人格式、强制门检、固定报告和配套调用流程。
- 故事线、章节、清单、评分和模拟评审参考只调整默认触发、报告要求及循环终止条件；保留具体论证方法、证据检查、问题分类与模板。
- 自定义格式、范例索引及两份相关卡片明确为来源作者的可选方案，不把“未指定会议”当作启用条件。自定义格式的历史演示保留，但明确它不是本包的实测结果或真实研究证据。
- 三份卡片注明 `paper_ref/` 是可选本地 PDF 路径，PDF 不随包分发；原文链接保留。其他论文卡片、会议适配资料与许可证保留。
- 本机 Codex 0.160.0 的原生 `skills/list` 在仓库内外确认个人安装可被发现，未使用额外搜索目录；随后同一桌面会话的下一轮技能目录也列出了 `ai-writing`。模型隐式选用未单独实测；Claude Code 未安装，未实测。
- 根据实际使用反馈，在根入口补充用户纠正方向后的交付规则，并添加自拟示例：按最终要求组织内容，排除项落实为约束，不把已放弃的方案或会话纠正经过反复写进成稿；保留影响结果与结论范围的条件，以及用户要求的比较和变更记录。README 的长期偏好示例同步更新。

## 0.5.0：替换论文写作方法，加入 Nature 章节参考

起因是使用反馈：论文改稿套模板、空话多、越改越像 AI。此前几轮主要修正触发、授权和报告流程，论文正文方法仍沿用旧 CCF 的故事骨架。这一版替换方法本身，不叠加第三套规则。根入口新增规则：局部润色沿用原有组织，只有用户要求起草、重组或诊断结构时才借用章节方法；各类研究按实际贡献组织。

**CCF（[mikubaka88/CCFA-Skills](https://github.com/mikubaka88/CCFA-Skills)，固定提交 `5969e6b20a3bbcef9118fa00796d1417d48fcbf3`）**

- 新增 [humanization.md](references/ccf-writing-skills/references/humanization.md)，改写自 `ccf-humanization/references/humanization-policy.md`。保留逐句判断（先找出句子的科学信息，有就直说，没有就删）、中英改写表、不机械删除 `not`/`only`/`may` 的例外、负面结果与方法身份的处理。去掉全家族前置启用、破折号与句长配额、warning/checksum 流程和检查脚本要求；论断强度的改动按用户授权处理。
- [section-modules.md](references/ccf-writing-skills/references/section-modules.md) 按新版重写，只保留方法论文的引言、相关工作、方法、实验和图表部分，引用写法例子取自 `research-writing-patterns.md`。去掉引文数量与篇幅配额、未指定会议时以 NeurIPS 起草的默认、固定 booktabs 格式和配套 skill 调用。摘要、以发现为主的引言、结论与讨论改由 Nature 参考和 humanization 承担。
- 删除旧版 `storyline-blueprint.md`：它把论文统一组织成“任务—空白—根因—洞见—机制—证据—局限”的链条，是“套模板”的主要来源。其中的贡献类型与结构失效信号并入 [writing-checklists.md](references/ccf-writing-skills/references/writing-checklists.md)，旧文件可在提交 `15d8da5` 中追溯。
- 未引入新版的 `storyline-blueprint.md`、`prose-quality-guardrails.md`、`compression-rules.md`、`length-budget-policy.md` 和整套评分与评审流程：它们仍以固定故事链、句长节奏、引文与篇幅配额为默认，或与 humanization 的例外冲突。会议资料、论文卡片、清单、评分与模拟评审参考仍为旧版本地副本，只在用户要求时使用。
- 不把 [Adkid-Zephyr/anti-defensive-writing-Skill](https://github.com/Adkid-Zephyr/anti-defensive-writing-Skill)（MIT，Copyright (c) 2026 Adkid-Zephyr）作为参考文件收录。它要求只围绕优势组织、不写“性能下降”“未能超过”、删除可能引出争论的实验，与本项目保留负面结果、限定条件和论断分寸的原则冲突。根入口借用了其中三条思路，用自己的话重写，未复制原文：主要论断选证据最站得住的一面，不利结果照实报告；按最终成立的逻辑叙述，不写成工作汇报；负面判断也按证据定强度，不把局部弱点写成普遍缺陷，不替论文揽下没有声称的责任。

**Nature 章节参考（[Yuan1z0825/nature-skills](https://github.com/Yuan1z0825/nature-skills)，固定提交 `7d5f160ebfe8033375b4afef7c5911aa4203c983`）**

- 从 `skills/nature-shared/core/` 选取 `nature-abstract.md`、`nature-introduction.md`、`nature-results-discussion.md`、`discussion-argument-language.md` 和 `main-text-discipline.md`，放在 [references/nature-writing/](references/nature-writing/source.md)。保留章节分工、判断问题、例子与例外，尤其是 Results 与 Discussion 的分工、正文与补充材料的取舍和防止修改只加不减。
- 改写内容：审计表、结果分配表和压缩记录改为可选；固定的主张数、数字个数和“发现型”中心改为按贡献取舍；不因写作请求补跑统计分析；移动正文或补充材料限于授权范围，不把不利结果移出正文。每个文件开头注明来源与修改，Apache-2.0 [LICENSE](references/nature-writing/LICENSE) 原样保留。
- 未引入 `nature-writing`、`nature-polishing` 的路由、术语表、一致性审计、期刊格式与固定输出格式。Nature 参考是上游作者的语料归纳，不是期刊规定。

**针对“小节过多、过于老实、不利于讲故事”的复查**

- 根入口补充起草与重组的正面要求：先找出读者最该记住的发现或贡献，各章节围绕它展开；证据支持的论断按其强度直接写，范围说一次，局限写在改变结论的位置；按论证单元分小节，内容少的部分并入相邻部分。
- 自拟论文例子原来在句尾追加“仍需验证”，与 humanization 的“重复限定”冲突，改为只在句首交代一次测试范围。
- humanization 恢复上游“使用证据所能支持的最强措辞”，层叠限定的改法不再默认保留 `preliminary`。
- 评分循环删去残留的固定故事链；评分、模拟评审与会议适配写明：审稿视角用于找出缺少的证据，修订稿用论文自己的口吻写，安抚审稿人的话放进回复信。范例分析与清单中面向审稿人的措辞改为面向读者。
