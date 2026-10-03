# 第三方来源与许可

`references/` 保存以下参考技能的原文件。来源和版本见 [SOURCES.md](SOURCES.md)，各项目原有的版权声明与许可证随文件保留。本项目的 MIT 许可证适用于本项目编写的入口和说明，不替代参考材料各自的许可。

## MIT 项目

| 项目 | 原版权声明 | 许可证依据 |
|---|---|---|
| [asd-ste100-skill](https://github.com/danyuchn/asd-ste100-skill) | Copyright (c) 2026 Dustin Yuchen Teng | [LICENSE](references/asd-ste100/LICENSE) |
| [Humanizer-zh](https://github.com/op7418/Humanizer-zh) | Copyright (c) 2026 歸藏 | [LICENSE](references/humanizer-zh/LICENSE) |
| [qu-ai-wei](https://github.com/hzblacksmith/qu-ai-wei) | Copyright (c) 2026 Frank Li | [LICENSE](references/qu-ai-wei/LICENSE) |
| [CCFA-Skills](https://github.com/mikubaka88/CCFA-Skills)（收录其 `ccf-paper-writer` 技能，置于 `references/ccf-writing-skills/`） | Copyright (c) 2026 Chaoyue Li | [LICENSE](references/ccf-writing-skills/LICENSE) |
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

## 未声明许可证、因而未随仓库分发的材料

- **academic-writing 1.0.0**（作者 teamolab，来源 [ClawHub](https://clawhub.ai/teamolab/academic-writing)）：**该技能文件与其来源页面均未声明任何许可证**——文件 frontmatter 只有 `name`/`description`/`tags`/`version`/`author`/`source`，无 license 字段；来源页面无可用的许可字段；该平台亦无对外许可条款页。按默认视为保留所有权利。

因此**本仓库不包含该技能**（`references/academic-writing/` 已由 `.gitignore` 排除）。使用者如已自行取得该技能，可放入同名目录使用；本项目的 MIT 许可证不为它授权，也不代表已获授权再分发。

## 其他材料

CCF 参考自带的 3 篇论文 PDF（`references/ccf-writing-skills/paper_ref/`）**未包含在本仓库中**（已由 `.gitignore` 排除）；其版权归论文作者或出版方，上游仓库的 MIT 许可不当然延伸至这些论文。ASD-STE100 标准正文和官方词典不在本项目中，参考技能的 MIT 许可不延伸至该标准。
