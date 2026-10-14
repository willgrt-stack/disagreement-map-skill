# 导出到原分歧地图项目

仅在用户要求导入项目、保存地图 JSON 或需要兼容数据时阅读。本格式不决定日常回答的顺序和篇幅。

按 [project.schema.json](../assets/project.schema.json) 生成 UTF-8 JSON。使用唯一项目 ID、ISO 日期时间和 `schemaVersion: 1`。`input.views` 保留用户观点与来源边界；`result` 存放已完成的分析。正常回答放在正文，JSON 另存文件或作为用户要求的附件。

映射方式：

| 字段 | 内容 |
| --- | --- |
| normalizedViews | 忠实概括观点；在 assumptions 中写明“原文明示”或“解释性推测”，不要把推测归给原作者。 |
| commonGround | 真正相容的部分；没有就留空，不虚构共同认可。 |
| surfaceDivergences | 双方看起来冲突的说法。 |
| rootDivergences | 真正导致不同结论的问题、事实或取舍。 |
| inferenceBridges | 哪个依据支持哪个判断；只保存对结论有影响的连接和不足。 |
| causalChains | 有材料支持或明确标为待查的因果路径。 |
| missingInformation | 会改变判断的缺失信息与核实方法。 |
| evidenceStatus | 原始证据、限制与链接；不套医学 A-D 层级。 |
| provisionalJudgment | 清楚的结论、当前倾向和限制；语言仍然自然。 |
| falsifiablePredictions | 什么新观察会让当前判断改变。 |

无内容的数组可留空；不得为填满图形造分歧、反方或证据。`strong/medium/weak/unknown` 是论证质量标签，不是统计概率。`evidenceStatus.status` 只描述该证据对明确命题的方向。

可选 `result.meta` 如实注明当前宿主、模型（未知就写未知）、生成时间与未完成模块。使用当前会话生成的结果，不能标成 DeepSeek、Kimi 或其他未实际调用的服务。

`input.providerId` 是旧项目的界面选择字段，与实际生成来源无关；无需额外模型调用即可导入。导出时可保留原项目已有值；没有时使用兼容默认值 `deepseek-v4-flash`，并在 `result.meta.provider/model` 记录真实来源。

生成后验证 Schema，并检查观点 ID 引用、各处结论一致性、链接来源和材料边界。程序校验通过仅说明结构兼容；不能据此声称已在运行中的网页导入或视觉验收。
