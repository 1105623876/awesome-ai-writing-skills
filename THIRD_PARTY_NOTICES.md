# 第三方来源与许可

`references/paper-translate/`、`references/paper-well-know/` 和 `references/concept-well-know/` 由本仓库 PR #2 的贡献改写，各自的 MIT [翻译许可](references/paper-translate/LICENSE)、[阅读许可](references/paper-well-know/LICENSE)和[概念许可](references/concept-well-know/LICENSE)原样保留（Copyright (c) 2026 ai-writing contributors）。它们不捆绑论文或标准正文；使用时访问的论文、网页、字体和外部工具仍按各自许可处理。

`references/` 保存以下参考 skill 的来源材料。来源、版本和整合方式见 [SOURCES.md](SOURCES.md)，各项目原有的版权声明与许可证随文件保留。本项目的 MIT 许可证适用于本项目编写的入口和说明，不替代参考材料各自的许可。

## MIT 项目

| 项目 | 原版权声明 | 许可证依据 |
|---|---|---|
| [asd-ste100-skill](https://github.com/danyuchn/asd-ste100-skill) | Copyright (c) 2026 Dustin Yuchen Teng | [LICENSE](references/asd-ste100/LICENSE) |
| [Humanizer-zh](https://github.com/op7418/Humanizer-zh) | Copyright (c) 2026 歸藏 | [LICENSE](references/humanizer-zh/LICENSE) |
| [qu-ai-wei](https://github.com/hzblacksmith/qu-ai-wei) | Copyright (c) 2026 Frank Li | [LICENSE](references/qu-ai-wei/LICENSE) |
| [CCFA-Skills](https://github.com/mikubaka88/CCFA-Skills)（收录其 `ccf-paper-writer` skill，置于 `references/ccf-writing-skills/`） | Copyright (c) 2026 Chaoyue Li | [LICENSE](references/ccf-writing-skills/LICENSE) |
| [answer-me-with-html](https://github.com/QingYunA/answer-me-with-html)（参考与捆绑渲染器） | Copyright (c) 2026 Answer me with HTML contributors | [LICENSE](references/answer-me-with-html/LICENSE) |
| [humanizer](https://github.com/blader/humanizer) | Copyright (c) 2025 Siqi Chen | [LICENSE](https://github.com/blader/humanizer/blob/main/LICENSE)；中文参考声明的上游 |
| [stop-slop](https://github.com/hardikpandya/stop-slop) | Copyright (c) 2025 Hardik Pandya | [LICENSE](https://github.com/hardikpandya/stop-slop/blob/main/LICENSE)；Humanizer-zh 声明的参考 |

上述各版权声明分别与下列 MIT 许可文本一起保留：

```text
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 其他材料

HTML 渲染脚本捆绑了 `@dagrejs/dagre` 3.1.1、`@dagrejs/graphlib` 4.0.5 和 `marked` 18.0.14。各依赖的完整署名与 MIT 许可保存在[渲染器许可清单](references/answer-me-with-html/scripts/THIRD_PARTY_NOTICES.md)中；marked 的 LICENSE 另含 John Gruber 的 Markdown 版权与 BSD 风格条款，dagre 的附加打包声明也一并保留。本项目的 MIT 许可不替代这些条款。

Humanizer-zh 声明其内容基于维基百科社区的 [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) 页面。该页面的文本采用 [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) 许可，另有条款可能适用；页面保留[贡献者历史](https://en.wikipedia.org/w/index.php?title=Wikipedia:Signs_of_AI_writing&action=history)。此处记录上游声明和页面许可，不对具体内容的衍生关系或许可兼容性作额外判断，本项目的 MIT 许可也不替代该页面的许可。

CCF 参考自带的 3 篇论文 PDF（`references/ccf-writing-skills/paper_ref/`）**未包含在本仓库中**（已由 `.gitignore` 排除）；其版权归论文作者或出版方，上游仓库的 MIT 许可不当然延伸至这些论文。ASD-STE100 标准正文和官方词典不在本项目中，参考 skill 的 MIT 许可不延伸至该标准。
