---
name: ai-writing
description: >-
  Use for 去 AI 味、中文润色、文章改写、技术说明和学术写作。
  按任务读取 Humanizer-zh、qu-ai-wei、ASD-STE100、academic-writing
  或 ccf-writing-skills 的完整规则与示例。
license: MIT
metadata:
  version: "0.1.0"
---

# AI Writing

按下面的任务说明选择参考，读取原文后再写。不要只读这里的介绍，也不要用几条通用写作原则代替原参考里的具体规则。

## 中文去 AI 味

简体中文文章、邮件、评论、社交文案和口播稿，读 [qu-ai-wei](references/qu-ai-wei/SKILL.md) 和 [Humanizer-zh](references/humanizer-zh/SKILL.md)。先判断语体，再按规则处理；学术、公文、特稿、品牌文案各有例外，不能都改成聊天口吻。

它的 51 类模式有完整的定义、例子和适用条件，见 [patterns.md](references/qu-ai-wei/references/patterns.md)。不要只看入口里的索引。品牌文案还需读 [brand-voice.md](references/qu-ai-wei/references/brand-voice.md)，完整改稿示例见 [examples.md](references/qu-ai-wei/references/examples.md)。

[Humanizer-zh](references/humanizer-zh/SKILL.md) 保留了另外 24 类常见模式和改写例子，包括意义拔高、宣传腔、同义词轮换、否定式排比、助手腔，以及句子节奏和作者个性。用户指定 Humanizer-zh 时以它为主；与 qu-ai-wei 一起使用时，中文语体的具体例外按 qu-ai-wei 处理。

qu-ai-wei 原版只支持简体中文。遇到繁体输入，按原版说明处理，不擅自转换，也不把简体规则宣称为繁体规则。

## 英文技术说明

工具说明、错误消息、操作步骤、agent 指令和英文 README，读 [ASD-STE100](references/asd-ste100/SKILL.md)，以及它的[规则说明](references/asd-ste100/references/writing-rules.md)和[改写示例](references/asd-ste100/examples/before-after.md)。

执行指令使用 Strict，README 等解释性文字使用 STE-flavored。两个模式分别规定了句长、主动语态、时态、名词连用和词义一致性的处理方式。英语规则用于英文，不能直接当成中文规范；原版也不用于创意写作和营销文案。

## 学术写作

面向计算机会议的论文，或需要规划章节、梳理论证、根据审稿意见修改时，读 [ccf-writing-skills](references/ccf-writing-skills/SKILL.md)，并继续读取它指定的章节、会议和示例文件。该参考的故事线、章节写法、引用与证据对应、评分改进和审稿修改流程均按原文使用；没有指定会议时，也保留它原有的自定义写作格式。

一般学术文章、综述、研究方法和学位论文：本机若另装有 academic-writing（作者 teamolab，来源 ClawHub），按其要求处理，包括它规定的 Markdown 与 `<ama-doc>` 输出格式。该技能未声明许可证，**不随本仓库分发**，本仓库没有 `references/academic-writing/`；没有这份参考时，按上方 ccf-writing-skills 与通用学术规范处理，不要自行发明格式约定。

中文论文同时需要去套话时，再读 qu-ai-wei 的学术语体规则。不要把技术术语、论证步骤和必要的限定词当作套话删掉。

## 使用参考时

用户明确要求的内容、语气和交付格式先于参考的默认设置。例如，用户要 LaTeX 就保留 LaTeX，用户只要成稿就只给成稿；没有这些要求时，按所选参考自身的流程和格式执行。

不要把几份参考的所有流程叠在每个任务上，也不要为了统一它们而删除原有的阈值、例子、例外或写作方法。要组合时，各自处理对应的问题。

参考中的例子用于理解改法；用户稿件中的人物、经历、数据和引语仍需来自材料，不能照着例子补编。文风判断不能当作作者身份的事实鉴定。

各来源入口中的 `references/`、`examples/`、`scripts/` 和 `paper_ref/` 都从该来源自己的文件夹解析。原版自带的工具和配套模块按其说明使用。
