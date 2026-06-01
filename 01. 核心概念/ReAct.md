# ReAct

**ReAct**（Reasoning + Acting）是一种让大模型交替进行**推理**和**行动**的范式。

## 核心思想

通过大模型的思考生成**推理轨迹**和**任务特定行动**，让两者协同：

- **推理轨迹** — 归纳、跟踪、更新行动计划；处理异常
- **行动** — 与外部资源（知识库/工具/环境）接口，收集信息

> 推理-行动-观察-再推理 循环

## 流程图

```
用户问题
   ↓
[1] Thought：分析问题、拆解步骤
   ↓
[2] Action：调用工具（搜索/计算/查询）
   ↓
[3] Observation：观察工具返回
   ↓
回到 [1]，直到得出最终答案
   ↓
Final Answer
```

## 提示词模板

```
Question: {input}
Thought: {reasoning}
Action: {tool_name}[{input}]
Observation: {tool_output}
... (循环 N 次)
Thought: 我现在知道最终答案了
Final Answer: {output}
```

## 与 CoT 的区别

| 维度 | CoT | ReAct |
|------|-----|-------|
| 推理 | 纯推理 | 推理 + 工具调用 |
| 知识来源 | 模型内部 | 模型 + 外部 |
| 适用 | 数学、逻辑 | 需实时信息、工具操作 |
| 幻觉 | 较高 | 较低（工具可校验） |

## 典型实现

- **LangChain Agent**（ReAct Agent、Structured Chat Agent）
- **LangGraph** — 状态图显式建模循环
- **Dify 工作流** — 拖拽实现 ReAct 循环
- **Claude Tool Use** — 配合工具调用

## 参考资料

- [ReAct 论文](https://arxiv.org/abs/2210.03629)
- [ReAct 项目主页](https://react-lm.github.io/)
- [[多智能体]] — 智能体中的工具调用
