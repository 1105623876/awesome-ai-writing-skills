# 参考来源与整合记录

## 单一入口与按需参考

根目录 [SKILL.md](SKILL.md) 是唯一 skill 执行入口。长期回复偏好可放在 Agent 的指令文件中；入口按场景或点名请求读取 `references/` 的相关方法，不注册多个入口，不继承来源的私人偏好与强制工作流。

本项目的目的贯穿回答、讲解、文章和论文：内容具体，读者跟得上，句子自然，事实与条件准确。根入口维护通用的交付、路径、来源与清理规则；[plain-language-examples.md](references/plain-language-examples.md) 是本项目编写的自拟示例，不属于八份来源参考。

参考可以保留原文，也可以按本项目精神改写。输出语言、文体、深度、文件与工具使用由当前用户和根入口决定。来源中“必须”“不可省略”的门检、报告、固定轮次、自动触发、安装和配套调用不自动执行，也不在后台执行。

## 原有四份参考

Humanizer-zh、qu-ai-wei 和 CCF 来自维护者本地保存的副本，ASD-STE100 下载自其 GitHub 仓库。早期整合调整了入口文件名、用途说明、存档说明和本地链接，具体见下文；0.4.2 又改写了 CCF 入口和部分配套说明，其余三份保留原正文。

| 参考 | 版本 | 项目内入口 | 原始来源 |
|---|---|---|---|
| Humanizer-zh | 副本未标版本 | [source.md](references/humanizer-zh/source.md) | [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) |
| qu-ai-wei | 0.6.6 | [source.md](references/qu-ai-wei/source.md) | [hzblacksmith/qu-ai-wei](https://github.com/hzblacksmith/qu-ai-wei) |
| ASD-STE100 | 0.4.0 | [source.md](references/asd-ste100/source.md) | [danyuchn/asd-ste100-skill](https://github.com/danyuchn/asd-ste100-skill)，2026-10-03 下载的 master 分支 |
| ccf-writing-skills | 本地副本未标版本 | [source.md](references/ccf-writing-skills/source.md) | [mikubaka88/CCFA-Skills](https://github.com/mikubaka88/CCFA-Skills) 的 `ccf-paper-writer` |

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

中文的语体与句法主要参考 qu-ai-wei，Humanizer-zh 补充诊断；英文回答和解释默认 STE-flavored，技术操作文本采用 Strict。这里的“八成 STE”是项目的写法简称，不是官方模式或合规比例。学术稿件的章节与证据组织可参考 CCF，原作者格式和范例不自动视为当前用户偏好。

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
