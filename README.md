# Awesome AI Writing Skills

给 Codex、Claude Code 等 AI 助手使用的一套写作、阅读与解释方法。整个仓库只安装为一个 `ai-writing` skill：根目录 `SKILL.md` 统一处理用户要求，`references/` 保存八份按需读取的方法、例子与工具。

长期回复习惯放在 `AGENTS.md` / `CLAUDE.md` 的 preference 中，具体任务通过 `ai-writing` 入口选择参考。不把每份参考注册成独立入口，也不让安装一个写作 skill 变成每次执行一整套报告流程。

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

其他支持 [Agent Skills](https://agentskills.io/specification) 的助手，请按各自的说明安装。当前版本为 0.4.0，尚未分别在 Codex 和 Claude Code 中实测自动加载。

原 `skills/` 下的三个专项入口已经移入 `references/`，入口名改为 `source.md`，并按本项目规则改写。安装时保留整个仓库，不再分别安装这三个目录。已有旧版独立安装的专项 skill 不会因更新本仓库自动移除；请在客户端确认实际加载的是哪个入口，避免旧规则同时生效。

HTML 参考附有单文件渲染脚本；只有决定生成页面且已有 Node.js 20+ 时才使用。普通写作不需要 Node，也不会因此自动安装依赖、打开浏览器或修改个人配置。

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

## 按场景选择参考

通用写作规则见 [SKILL.md](SKILL.md)。助手按当前问题或点名指令选择相关部分，允许组合方法，不一次加载所有资料。

| 场景或指令 | 参考 | 主要内容 |
|---|---|---|
| 中文语体、句法、套话与修辞 | [qu-ai-wei](references/qu-ai-wei/source.md) | 51 类模式、九种语体、例外与完整示例 |
| 点名 Humanizer-zh，或补充诊断 | [Humanizer-zh](references/humanizer-zh/source.md) | 24 类写法与作者语气的处理 |
| 英文回答和技术说明 | [ASD-STE100](references/asd-ste100/source.md) | STE-flavored / Strict、规则、例子与可选检查脚本 |
| 论文章节与论证组织 | [ccf-writing-skills](references/ccf-writing-skills/source.md) | 问题、贡献、证据、会议适配与论文卡片 |
| 论文或技术材料翻译 | [paper-translate](references/paper-translate/source.md) | 忠实翻译、可选对照、长文接续与图表处理 |
| 理解或评价单篇论文 | [paper-well-know](references/paper-well-know/source.md) | 来源、方法与证据分析、可选笔记结构 |
| 解释概念、比较方法或梳理方向 | [concept-well-know](references/concept-well-know/source.md) | 概念关系、例子、可选数学核对与配图 |
| HTML 页面或适合可视化的复杂关系 | [answer-me-with-html](references/answer-me-with-html/source.md) | 内容组织、组件与可选渲染器 |

例如：

```text
使用 ai-writing，参考 paper-translate 翻译这段摘要，只要中文译文。
```

```text
使用 ai-writing，参考 paper-well-know 解释 Eq.3 的含义，说明原文与补充解释的区别。
```

```text
使用 ai-writing，参考 concept-well-know，用生活例子讲清楚动量，不用公式。
```

```text
使用 ai-writing，把这几个模块的关系讲清楚，保存成一页 HTML。
```

这些参考名称用于选择方法，不是需要另外安装的命令；已有客户端是否支持同名斜杠命令，由其实际配置决定。翻译不默认附生词表，概念解释不默认生成文件，论文笔记不固定五段，复杂回答不按数量自动生成 HTML。用户要对照、评分、系统报告或核对记录时，再按其要求展开。

原有四份参考保留具体方法、例子与例外；新引入的四份作了适配改写，原版可从记录的 Git 来源追溯。一般论文、综述和学位论文由总入口处理，CCF 方法按当前学科使用，不强加计算机会议模板。CCF 卡片已随仓库提供；三篇论文 PDF 由使用者本地提供，可放在 `references/ccf-writing-skills/paper_ref/`，卡片也附原文链接。

发现论断超出现有证据，或字数等要求与必须保留的内容冲突时，会指出具体问题，不擅自改动事实和论断强度。参考中的门检、强制报告、固定打分、自审轮次和配套调用不默认执行，也不在后台暗中执行。

来源、固定版本与改写范围见 [SOURCES.md](SOURCES.md)。本项目编写的入口和说明采用 [MIT 许可证](LICENSE)，参考文件与捆绑渲染器的署名、许可见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。复制时请一并保留。
