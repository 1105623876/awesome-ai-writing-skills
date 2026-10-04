# answer-me-with-html：可选 HTML 解释页参考

> 根据 [QingYunA/answer-me-with-html](https://github.com/QingYunA/answer-me-with-html) 0.4.6 改写；捆绑渲染脚本保留上游版本。这里只提供内容组织与工具方法，唯一执行入口是根目录 [SKILL.md](../../SKILL.md)。不继承高频模式、固定面板数量、个人缓存目录或配置与更新流程。版本与许可见 [SOURCES.md](../../SOURCES.md)。

## 何时使用

用户明确要 HTML、可视化页面，或流程、关系、层级、时间线与比较用页面更容易理解时，可以使用。简单回答、已有图表足够的说明和用户要求纯文本的任务，直接按根入口交付。

不根据概念数量自动触发，也不因为做了评审或总结就每次附页面。内容与载体分别选择：可以只借用组织方法，用普通文字、Mermaid 或表格；只有决定交付 HTML 时才读取下面的渲染步骤。

## 捆绑渲染器

[scripts/am.mjs](scripts/am.mjs) 是上游打包的单文件 CLI，使用已有 Node.js 20+，不需要安装 npm 包。仅在环境已有可用 Node 时调用；用户要求的输出需要额外依赖时先说明，不自动安装或全局注册命令。

这里使用显式输出路径、临时状态目录、关闭自动打开与更新的方式调用。脚本本身仍包含上游配置、清理、更新和视频能力；这些命令不属于普通 HTML 任务，不运行 `config / clean / update`，也不读取或清理用户原有缓存。

将示例路径换为本参考的实际位置，输出路径按用户要求或当前项目选择。`am_state` 是本次新建的临时目录，渲染器的状态写在其中，不写入用户主目录：

````sh
reference_dir="/absolute/path/to/ai-writing/references/answer-me-with-html"
am_state=$(mktemp -d)
AM_HOME="$am_state" AM_NO_UPDATE_CHECK=1 \
  node "$reference_dir/scripts/am.mjs" render - \
  --no-open --style off -o ./explanation.html <<'AM_EOF'
---
title: 请求怎样得到响应
template: sheet
theme: blueprint
cols: 2
---
请求经过校验后交给处理器，响应再返回调用方。

## 流程
```flow LR
调用方 -> 校验
校验 -> 处理器: 通过
校验 -> 错误响应: 未通过
处理器 -> 调用方: 响应
错误响应 -> 调用方: 错误原因
```

## 关键条件
```callout info 校验失败时
返回具体错误，不进入处理器。
```
AM_EOF
````

每次 `render / patch / video` 调用都显式设置 `AM_HOME`、`AM_NO_UPDATE_CHECK=1` 和 `--no-open`，不依赖客户端是否提供 `CLAUDE_SKILL_DIR` 或用户全局配置。`--style off` 关闭脚本自带检查，文字仍按根入口写；上游中文字符阈值不作为本项目规则。只在用户要该检查时选择 `80 / strict`，不能把它描述为官方 STE 认证。

验证结束后可清理本次新建的临时状态目录，成品保存在指定输出位置。不要把 HTML 成品放在随后清理的目录。生成前检查目标重名，避免覆盖任务外文件。

## 内容稿与布局

渲染器接受扩展 Markdown。`sheet` 用面板展示总览；`doc` 适合连续阅读。面板数量和页面长度由内容决定，不为达到 3–8 个面板拆句或添加内容。

````markdown
---
template: sheet
theme: blueprint
title: 标题
subtitle: 一句话说明
cols: 3
lang: zh
source: 实际来源
---
导语给核心结论，后面的面板解释证据或关系。

## A 关系 {span=2 meta="范围说明"}
普通 Markdown：段落、列表、表格、引用。

```flow LR
输入 -> 处理 -> 输出
```

## B 元信息 {bare}
```kv cols=2
主题: 当前主题
来源: 已读取的材料
```
````

- `theme` 可选 `blueprint / shadcn`；`mode` 可选 `auto / light / dark`。主题是工具选项，不是用户偏好。
- `##` 标题形成面板或章节，字母 ID 可省略；`span / rows` 控制跨列跨行，`meta` 放辅助信息，`bare` 隐藏标题栏。
- 表格中的 `ok / no / warn` 可渲染为状态徽章；普通文字仍可使用，不强制所有判断改成状态词。
- 稿件语言、简繁和术语服从用户。`lang` 支持 `zh / en / ja`，其他语言的界面能力以实际渲染为准。
- `html / svg` 围栏可原样嵌入。需要自定义页面时也可采用其他工具，不继承上游“不要手写 HTML / CSS / SVG”的禁令。

一个面板回答一个清楚的问题，信息密集的面板可加宽。数字只有真实来源或明确标为示意时才使用；没有数值就不用进度或限额组件。

## 组件速查

| 信息 | 组件 | 最小语法 |
|---|---|---|
| 流程、架构、决策分支 | `flow [LR]` | `A -> B: 标签`；`A --> C` 虚线；`A -> B & C` 扇出 |
| 多方按时间发送消息 | `sequence [num]` | `A -> B: 请求`；`B --> A: 响应`；`note A, B: 说明`；`== 阶段 ==` |
| 层级、目录、分类 | `tree [list]` | 缩进表达层级；`标签 \| 说明`；反引号包裹编号 |
| 时间演进 | `timeline [v]` | `时间 \| 标题 \| 说明`；`*` 高亮 |
| 数值与上限 | `limits` | `标签 \| 13 / 20 \| 单位`；`标签 \| max 20` |
| 逐段或逐词点评 | `annot` | `# 小标题 \| 右注`；`[片段]{注释}`；`[错词]{!注释}`；`> 底注` |
| 元信息 | `kv [cols=2]` | `键: 值`；`* 宽格: 值` |
| 结论或提示 | `callout <info\|ok\|warn\|err> 标题` | 正文 Markdown |
| 多维比较 | Markdown 表格 | 每列一个有意义的维度，解释放在表格附近 |

flow 节点还可用 `{判断?}`、`(开始)`、`[(数据库)]`；`*重点` 高亮节点；`group 名: A, B` 分组。语法需要细节时，运行 `node "$reference_dir/scripts/am.mjs" help format`、`help flow` 等，或 `list` 查看组件。`help / list` 不需要渲染页面。

## 修改已有页面与验证

上游渲染的 HTML 内含 `#am-source` 源稿，后续可以恢复并修改对应章节。局部修改可用 `patch --panel`：

````sh
AM_HOME="$am_state" AM_NO_UPDATE_CHECK=1 \
  node "$reference_dir/scripts/am.mjs" patch ./explanation.html \
  --panel "关键条件" --no-open --style off <<'AM_EOF'
## 关键条件
校验失败时返回具体原因，调用方按错误类型处理。
AM_EOF
````

`--panel` 匹配标题、字母 ID 或 `ID 标题`。目标不匹配、页面没有源稿时停止修改并检查，不凭猜测覆盖。补丁会写回目标页面，任务需包含该修改。

运行成功后实际打开页面，检查文字、图形、路径与窄屏布局；源稿能恢复不代表布局一定正确。组件报错根据错误行与正确语法修复，不把未成功生成的路径作为成品。回复保留用户需要的答案与可点击文件链接，不固定为只有两三行。

## 视频能力（仅用户明确需要时）

脚本还支持 `video`。内容稿与 HTML 相近，`##` 是场景，`>` 行是旁白；组件的源码行决定逐步出现顺序，`[名字]` 可指向同名节点并高亮。场景与旁白长度随讲解需要，不固定数量或模仿某种艺术风格。

可先查看 `help video`。调用仍使用上述状态与更新控制、`--no-open --style off`，并指定 `-o`。无配音需求时显式 `--voice off`；需要配音时按用户要求选择可用的本地或已获授权的服务，不因环境中存在 API Key 就自动调用远程服务。

`--mp4` 另需 Chrome、ffmpeg 和 Node.js 22+；只有明确要视频文件时检查这些能力。缺少依赖时说明影响，播放页不能冒称 MP4。不因解释复杂或 HTML 已生成就追加视频。
