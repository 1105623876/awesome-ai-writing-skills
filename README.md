# Awesome AI Writing Skills

给 Codex、Claude Code 等 AI 助手使用的中文写作与论文阅读 skills。仓库根目录仍是可独立安装的 `ai-writing`；`skills/` 目录收录三个可分别安装的专项 skill。

| Skill | 目录 | 用途 |
|---|---|---|
| `ai-writing` | 仓库根目录 | 回答、解释、起草、润色、压缩与结构调整 |
| `paper-translate` | [`skills/paper-translate/`](skills/paper-translate/) | CV / CS / LLM 英文论文的严格英中对照翻译 |
| `paper-well-know` | [`skills/paper-well-know/`](skills/paper-well-know/) | 单篇论文精读与图文中文梳理报告 |
| `concept-well-know` | [`skills/concept-well-know/`](skills/concept-well-know/) | 计算机概念、公式、发展脉络与横向对比文档 |

下面先介绍根目录的 `ai-writing`。

例如，这句通知：

> 在此温馨提醒各位同事，请大家务必注意：报销材料须在周五前提交。再次提醒，请勿错过提交时间。

去掉重复提醒后：

> 请各位同事在周五前提交报销材料。

这是一段自拟示例。删掉的是反复提醒，提交要求和时间仍然保留。原稿若有“预计”“仅在测试环境中”等限制，也要留下。

## 先试一下

不安装也可以用：把这个文件夹交给助手，要求它读取其中的 `SKILL.md`，再按任务读取相应参考文件。例如，在当前项目中这样说：

```text
读取当前目录的 SKILL.md，按它的规则修改下面这段文字。
删掉套话和重复，保留我的语气，只给改稿：
……
```

## 安装 `ai-writing`

在下表中选择一个位置，新建 `ai-writing` 文件夹，把本项目的内容完整复制进去。最终应能找到 `ai-writing/SKILL.md`，不能多嵌套一层项目目录。已有同名 skill 时，先比较内容再决定是否替换。

| Agent | 项目内安装目录 | 个人安装目录 |
|---|---|---|
| Codex | `.agents/skills/ai-writing/` | `~/.agents/skills/ai-writing/` |
| Claude Code | `.claude/skills/ai-writing/` | `~/.claude/skills/ai-writing/` |

`~` 表示运行助手的用户主目录，Windows 也可填写对应的完整路径。目录说明见 [OpenAI 官方文档](https://learn.chatgpt.com/docs/build-skills) 和 [Claude Code 官方文档](https://code.claude.com/docs/en/skills)。

也可以用 Git 安装到 Codex 的个人目录。目标目录不存在时，在 Bash 中运行：

```sh
git clone https://github.com/1105623876/awesome-ai-writing-skills.git ~/.agents/skills/ai-writing
```

Windows PowerShell 对应命令：

```powershell
git clone https://github.com/1105623876/awesome-ai-writing-skills.git "$env:USERPROFILE/.agents/skills/ai-writing"
```

Claude Code 把目标目录换成上表中的 `.claude/skills/ai-writing/`。两种安装方法都把目录命名为 `ai-writing`，与 `SKILL.md` 的 `name` 一致。

新建会话，确认客户端能发现 `ai-writing`，再要求“使用 ai-writing”。安装时请保留整个 `references/` 目录，助手会从中读取具体规则和示例。包内只有根目录的 `SKILL.md` 是 skill 入口，各参考原来的入口都改存为普通文档 `source.md`。

其他支持 [Agent Skills](https://agentskills.io/specification) 的助手，请按各自的说明安装。当前版本为 0.3.0，尚未分别在 Codex 和 Claude Code 中实测自动加载。

## 安装专项 skills

`skills/` 下的三个目录都是独立 skill，安装时要把选中的整个目录复制到代理的 skills 目录，不能只复制 `SKILL.md`，也不能把 `skills/` 本身当成一个 skill。包含 `references/` 的目录必须完整保留。

先克隆仓库：

```sh
git clone https://github.com/1105623876/awesome-ai-writing-skills.git
cd awesome-ai-writing-skills
```

例如，为 Codex 安装 `paper-translate`：

```sh
cp -a skills/paper-translate ~/.agents/skills/paper-translate
```

为 Claude Code 安装时，把目标目录换为 `~/.claude/skills/paper-translate`。另外两个 skill 同理替换目录名。已有同名目录时先比较内容，不要直接覆盖。

这些专项 skill 会在需要时调用 PDF、图片或联网检索工具。它们会先检查当前环境中实际可用的命令；仓库不绑定某个用户名、Conda 环境或模型版本，也不会自动安装依赖。

## 让助手平时回复也说人话

安装 skill 不等于每次回复都会加载它。想长期使用这套回复习惯，可以把下面这段放入 Codex 的 `AGENTS.md` 或 Claude Code 的 `CLAUDE.md`：

```text
回复我时使用 ai-writing 的回答和解释规则：先给答案，再补必要的理由、例子和条件。
不复述问题，不写空泛铺垫，不加客套结尾。回答长短跟着问题走，术语保持一致。
英文回答默认用 STE-flavored（八成 STE）：操作句不超过 20 词，说明句不超过 25 词，
名词连用不超过 3 词，一段不超过 6 句；多用主动表达和简单时态，不锁定词典词义。
中文只借短句、一句一事、主动表达和术语一致等原则，不套英文词数。
准确表达优先，不能为缩短句子删掉条件或不确定性。用户指定的文体和格式优先。
需要完整规则和例子时，读取已安装的 ai-writing/SKILL.md 及对应参考。
```

只想作用于当前项目，就放在项目的指令文件里。想跨项目使用，Codex 放在其用户配置目录的 `AGENTS.md`（默认 `~/.codex/AGENTS.md`，设置了 `CODEX_HOME` 时用对应目录）；Claude Code 放在 `~/.claude/CLAUDE.md`。具体加载规则见 [Codex 指令文档](https://learn.chatgpt.com/docs/agent-configuration/agents-md)和 [Claude Code 指令文档](https://code.claude.com/docs/en/memory)。

“八成 STE”是这里对 STE-flavored 的简称，不是 ASD-STE100 的官方模式或合规百分比。普通英文文章、邮件仍按文体写，不默认套技术说明的句长限制。

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

```text
Use ai-writing. Explain how X works, about 80% of the way to ASD-STE100.
```

```text
使用 ai-writing，看看这段论文引言的论证哪里不清楚。
先给修改意见和局部示范，不要整段代写：……
```

如果有明确的读者、字数或语气要求，就一起告诉助手。想看改动对照、要两个版本，或者只想听意见，也可以直接说。

技术说明会检查条件、步骤和责任是否清楚；论文修改会检查结论是否超出现有证据。润色本身不等于事实核查，也不能补上缺失的实验。

这里的“去 AI 味”指修改套话、重复和不自然的表达，不保证检测器结果或论文录用。

## 包含哪些规则

回答、解释、指导和改稿共用一套写作方法，见 [SKILL.md](SKILL.md)。遇到拿不准的写法、特殊语体或具体句式时，助手会按任务读取对应参考：

- [qu-ai-wei](references/qu-ai-wei/source.md)：简体中文去 AI 味。保留 51 类模式、九种语体、行业用词、标点规则、主动打磨方法和完整示例。
- [Humanizer-zh](references/humanizer-zh/source.md)：24 类常见写法的诊断与改写，包括套话、宣传腔、助手腔、句式节奏和作者个性。
- [ASD-STE100](references/asd-ste100/source.md)：英文技术说明和英文回答、解释。回答默认用 STE-flavored（八成 STE），技术操作指令用 Strict；保留具体规则、示例及附带的检查脚本。
- [ccf-writing-skills](references/ccf-writing-skills/source.md)：计算机会议论文写作，包含章节方法、论文示例、会议要求和审稿修改流程。来源为 [CCFA-Skills](https://github.com/mikubaka88/CCFA-Skills) 的 `ccf-paper-writer`（MIT）。

一般论文、综述和学位论文的写作由总入口处理，需要具体章节方法时读取 CCF 参考，并按学科和稿件要求使用。

CCF 的论文写作卡片已包含在仓库中。三篇论文 PDF 由使用者本地提供，可放在 `references/ccf-writing-skills/paper_ref/`；卡片也附有论文原文链接。

各参考保留了完整的方法和例子。你也可以指定要参考哪份，比如“按 Humanizer-zh 改，保留我的语气，只给成稿”。

本 skill 回答问题时直接回答，改稿时默认直接给成稿。qu-ai-wei 的真人／AI 门检，以及参考里的强制报告、评分和配套调用，都不默认执行；想看改动说明或对照，直接提出即可。发现论断超出现有证据，或字数等要求与必须保留的内容冲突时，会用一两句话指出问题，不擅自改动事实和论断强度。

来源与版本见 [SOURCES.md](SOURCES.md)。本项目编写的入口和说明采用 [MIT 许可证](LICENSE)，参考文件的署名与许可见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。复制时请一并保留。
