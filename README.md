# AI Writing

给 Codex、Claude Code 等 AI 助手用的写作 skill。可以根据材料起草文章和邮件，也可以修改中英文稿件，删套话、理顺段落、压缩篇幅。修改时保留事实和作者的语气，不编造细节。

例如，这句通知：

> 在此温馨提醒各位同事，请大家务必注意：报销材料须在周五前提交。再次提醒，请勿错过提交时间。

去掉重复提醒后：

> 请各位同事在周五前提交报销材料。

这是一段自拟示例。删掉的是反复提醒，提交要求和时间仍然保留。原文若有“预计”“仅在测试环境中”等限制，也要留下。

## 先试一下

不安装也可以用：把这个文件夹交给助手，要求它读取其中的 `SKILL.md`，再按任务读取相应参考文件。例如，在当前项目中这样说：

```text
读取当前目录的 SKILL.md，按它的规则修改下面这段文字。
删掉套话和重复，保留我的语气，只给改稿：
……
```

这只是让助手读取文件；安装后，客户端才能按自己的机制发现这个 skill。

## 安装

在下表中选择一个位置，新建 `ai-writing` 文件夹，把本项目的内容完整复制进去。最终应能找到 `ai-writing/SKILL.md`，不能多嵌套一层项目目录。已有同名 skill 时，先比较内容再决定是否替换。

| Agent | 项目内安装目录 | 个人安装目录 |
|---|---|---|
| Codex | `.agents/skills/ai-writing/` | `~/.agents/skills/ai-writing/` |
| Claude Code | `.claude/skills/ai-writing/` | `~/.claude/skills/ai-writing/` |

安装目录沿用项目 2026-10-03 的核对记录，依据为 [OpenAI 官方文档](https://learn.chatgpt.com/docs/build-skills) 和 [Claude Code 官方文档](https://code.claude.com/docs/en/skills)。`~` 表示运行助手的用户主目录；Windows 也可填写对应的完整路径。

新建会话，确认客户端能发现 `ai-writing`，再要求“使用 ai-writing”。安装时请保留整个 `references/` 目录，助手会从中读取原规则和示例。

其他支持 [Agent Skills](https://agentskills.io/specification) 的助手，请按各自的说明安装。当前版本为 0.1.0，尚未在 Codex 和 Claude Code 中分别实测自动加载。

## 怎么提要求

安装后，可以直接说明要改什么：

```text
使用 ai-writing，润色下面这段中文。保留我的语气，只输出成稿：……
```

```text
使用 ai-writing，根据以下要点写一封正式邮件。缺失的事实不要乱补：……
```

```text
使用 ai-writing，把这份说明压缩到 300 字，保留限制条件：……
```

```text
Use ai-writing to clarify this tool description. Preserve every condition
and the difference between may, should, and must: ...
```

```text
使用 ai-writing 修改这段论文摘要，保留实验数字和 LaTeX 引用。
若论断超出证据，请单独指出，不替我补结果：……
```

如果有明确的读者、字数或语气要求，就一起告诉助手。想看改动对照、要两个版本，或者只想听意见，也可以直接说。

技术说明会检查条件、步骤和责任是否清楚；论文修改会检查结论是否超出现有证据。润色本身不等于事实核查，也不能补上缺失的实验。

这里的“去 AI 味”指修改套话、重复和不自然的表达，不保证检测器结果或论文录用~

## 包含哪些规则

助手理应按任务读取对应参考：

- [qu-ai-wei](references/qu-ai-wei/SKILL.md)：简体中文去 AI 味。保留 51 类模式、九种语体、行业用词、标点规则、主动打磨方法和完整示例。
- [Humanizer-zh](references/humanizer-zh/SKILL.md)：24 类常见写法的诊断与改写，包括套话、宣传腔、助手腔、句式节奏和作者个性。
- [ASD-STE100](references/asd-ste100/SKILL.md)：英文技术说明。保留 Strict 和 STE-flavored 两种模式、具体规则、示例及原版工具。
- [ccf-writing-skills](references/ccf-writing-skills/SKILL.md)：计算机会议论文写作，包含章节方法、论文示例、会议要求和审稿修改流程。来源为 [CCFA-Skills](https://github.com/mikubaka88/CCFA-Skills) 的 `ccf-paper-writer`（MIT）。

**未随本仓库分发的内容**：**academic-writing**（原技能未声明许可证，需要时自行从 [ClawHub](https://clawhub.ai/teamolab/academic-writing) 取得后放入 `references/academic-writing/`）；**CCF 的 3 篇论文 PDF**（版权归论文作者或出版方，需要时自行从上游取得后放入 `references/ccf-writing-skills/paper_ref/`）。

这些参考各有完整的规则和例子，放在 `references/` 下。总入口 [SKILL.md](SKILL.md) 负责按任务选择。你也可以在请求里指定其中一份，比如“按 Humanizer-zh 改，保留我的语气，只给成稿”。

原参考自带的打磨报告、评分或审稿流程也保留；是否展示，按你的要求和所选参考处理。

来源与版本见 [SOURCES.md](SOURCES.md)。本项目编写的入口和说明采用 [MIT 许可证](LICENSE)，参考文件的署名与许可见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。复制时请一并保留。
