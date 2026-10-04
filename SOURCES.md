# 参考来源

Humanizer-zh、qu-ai-wei 和 CCF 写作 skill 来自本项目维护者本地保存的副本，ASD-STE100 下载自其 GitHub 仓库。各参考的具体规则与示例保存在 `references/` 下。CCF 的三篇论文 PDF 仅在本地使用，不随仓库分发。

| 参考 | 版本 | 项目内文件 | 原始来源 |
|---|---|---|---|
| Humanizer-zh | 副本未标版本 | [source.md](references/humanizer-zh/source.md) | [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)，维护者本地副本 |
| qu-ai-wei | 0.6.6 | [source.md](references/qu-ai-wei/source.md) | [hzblacksmith/qu-ai-wei](https://github.com/hzblacksmith/qu-ai-wei)，维护者本地副本 |
| ASD-STE100 | 0.4.0 | [source.md](references/asd-ste100/source.md) | [danyuchn/asd-ste100-skill](https://github.com/danyuchn/asd-ste100-skill)，2026-10-03 下载的 master 分支 |
| ccf-writing-skills | 本地副本未标版本 | [source.md](references/ccf-writing-skills/source.md) | [mikubaka88/CCFA-Skills](https://github.com/mikubaka88/CCFA-Skills) 的 `ccf-paper-writer`，MIT（Copyright (c) 2026 Chaoyue Li） |

## 怎样整合

[SKILL.md](SKILL.md) 统一处理回答、解释、写作指导、起草、润色、压缩和结构调整。中文的语体、句法与修辞主要参考 qu-ai-wei，Humanizer-zh 补充常见套话与句式诊断；英文回答和解释默认采用 ASD-STE100 参考的 STE-flavored 模式，技术操作指令采用 Strict；论文章节和论证组织参考 CCF 写作 skill。一般学术写作由本入口处理，需要时读取适用的章节参考。

“八成 STE”是本项目对 STE-flavored 的简称，用于说明英文回答的默认写法，不代表官方标准中的模式或合规比例。CCF 默认格式和范例中的用户偏好保留为来源资料，不自动视为当前用户的要求。

保留参考里的定义、例子、阈值、例外和交叉引用。原 skill 判断稿子是不是真人写的门检、强制报告、评分合格线、自审轮次、安装和配套调用不继承；这也包括要求在内部执行但不输出的流程。输出格式统一由用户要求和本项目入口决定。参考中的“必须”“不可省略”等措辞只描述原 skill 的设计。

## 文件说明

各来源的 `SKILL.md` 改名为 `source.md`，前加用途说明，原正文保留。CCF 的 `agents/openai.yaml` 改为 `source-openai.yaml`，只保存原来的界面配置。包内只保留根目录一个 skill 入口。

来源 README 和 CHANGELOG 加了存档说明，其中指向本地 `SKILL.md` 的链接改为 `source.md`；安装命令和历史记录仍描述上游项目。CCF 来源说明中的一处原作者个人目录已改为 skill 名称。其余配套规则、示例和脚本保留，不要求在写作时执行安装或打包脚本。

qu-ai-wei 的原 README 和 CHANGELOG 提到了 `tests/`，维护者的本地副本未包含该目录。那些链接属于上游的开发记录，不是本项目可运行的测试。

版权与许可见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。
