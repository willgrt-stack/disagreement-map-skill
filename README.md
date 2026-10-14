# 分歧地图

面对两种相反的说法，先弄清楚各自在说什么，再看依据，最后用好懂的话给出判断。

它会考虑观点的语境、前提和潜台词，检查营销包装与关键证据。默认先给结论，再解释理由和重要例外，不把整套分析术语铺给读者。

## 使用

仓库地址：<https://github.com/willgrt-stack/disagreement-map-skill>。

在支持安装 GitHub Skill 的 Codex 中，可以直接说：

```text
从 https://github.com/willgrt-stack/disagreement-map-skill
安装 skills/disagreement-map 目录里的分歧地图 Skill。
```

把 `skills/disagreement-map/` 整个文件夹放入所用 Agent 的技能目录。在 Codex 中，默认目录为 `~/.codex/skills/`；使用自定义配置目录时，放入对应的 `skills/`。

例如：

```text
用 $disagreement-map 分析：
有人说“环境再差也有人赚钱，别只顾着抱怨”，
另一个人说“环境不好，赚钱就难”。
先用好懂的话解释他们各自在说什么，再查关键依据。
```

也可以要求“只根据给定材料分析”“把关键研究展开给我看”或“导出能导入分歧地图项目的 JSON”。

需要支持读取 `SKILL.md` 的 Agent。研究环节使用宿主已有的检索工具；没有检索工具时会说明材料限制。无需单独的 DeepSeek/Kimi 账号或 API Key。本 Skill 不自动上传材料或发布内容。

## 更新

通过复制文件安装的版本不会自动更新。需要更新时，把仓库链接发给 Agent，要求先比较仓库版本与本地版本、保留自己的修改，再更新 `disagreement-map` 目录。

安装或更新后，可以用“用分歧地图分析：……”检查当前 Agent 是否识别到该 Skill。

## 有什么不同

- 先理解意思：原文明示的条件与根据语境推测的潜台词分开。
- 去营销：把包装还原成能核实的主张；商业资助与权威身份都不能直接决定真伪。
- 查依据：按问题选择研究方法，寻找反证，说明证据适用于谁。
- 说人话：结论在前，关键理由随后，例外说清；需要时才展开完整地图。
- 保持判断：有些观点在回答不同问题，有些确实互相矛盾，不强求“双方都对”。

## 文件

- [Skill 入口](skills/disagreement-map/SKILL.md)
- [研究规则](skills/disagreement-map/references/research.md)
- [表达示例](skills/disagreement-map/references/writing-examples.md)
- [可选地图导出](skills/disagreement-map/references/map-export.md)

## 验证范围

发布前检查技能结构、引用文件、地图 Schema 兼容性，并用具体请求检查表达和判断。行为检验只能证明观察到的样例表现，不能保证每次输出质量；真实检索是否可用取决于宿主工具。

版本：0.1.0。
