# AI 笔记 · Map of Content

AI 领域个人知识库，使用 Obsidian 管理。涵盖核心概念、RAG、智能体框架、AI 编程、大模型、社区与机器学习、基础设施七大板块。

---

## 01. 核心概念

AI 基础概念、术语与本体。

- [[00. 思维导图]] — 知识体系思维导图
- [[00. 疑问点]] — 待解决的疑问
- [[05. 大模型/01. 基础理论/02. 大模型定义|大模型定义]] — LLM 定义
- [[05. 大模型/01. 基础理论/05. 术语|术语]] — AI 术语表
- [[什么是智能体]] — 智能体概念
- [[ReAct]] — ReAct 范式
- [[kimi]] — kimi 介绍
- [[SearXNG]] — SearXNG 搜索
- [[本体与AIP应用]] — Palantir AIP 产品体系
- [[多智能体]] — 多 Agent 协作
- [[skillhub]] — Skills 技能市场

## 02. RAG

检索增强生成（Retrieval-Augmented Generation）知识体系。

**基础篇**
- [[01. RAG核心概念]] — RAG 是什么、核心流程
- [[02. 向量检索与Embedding]] — 向量检索原理
- [[03. 分块策略]] — 文档分块方法
- [[04. 检索优化]] — 相似度检索与重排序

**进阶篇**
- [[05. Advanced-RAG与Agentic-RAG]] — Advanced RAG 范式
- [[06. RAG评估与生产优化]] — 评估体系
- [[07. Agentic-RAG架构与实现]] — Agentic RAG 架构
- [[08. Self-RAG详解]] — 自反思 RAG
- [[09. 多跳检索与推理]] — Multi-Hop
- [[10. Corrective-RAG与RAG变体]] — CRAG 与变体

**框架与生产**
- [[11. LangGraph实现Agentic-RAG]] — LangGraph 实战
- [[12. RAG生产级架构与工程实践]] — 生产架构
- [[13. 混合检索与知识图谱RAG]] — 混合检索

**知识图谱**
- [[14. 知识图谱核心概念]] — KG 基础
- [[15. Graph-RAG原理与实践]] — Graph RAG
- [[16. 知识图谱嵌入与GNN]] — KG Embedding
- [[17. 实体消歧与知识融合]] — 实体对齐
- [[18. 知识图谱与RAG面试汇总]] — 面试汇总

**RAG 工具链**
- [[01. 概念/rag流程图|RAG 流程图]]
- 向量数据库：[[03. 向量数据库/Milvus/01. 概念|Milvus]]、[[03. 向量数据库/Qdrant|Qdrant]]、[[03. 向量数据库/weaviate|Weaviate]]、[[03. 向量数据库/重排序|重排序]]
- 嵌入模型：[[04. 嵌入模型/01. 概念|嵌入模型概念]]
- 知识图谱：[[06. 知识图谱/01. 知识图谱|知识图谱]]、[[06. 知识图谱/02. neo4j|Neo4j]]、[[06. 知识图谱/03. 知识图谱的价值|价值]]
- RAG 框架：[[05. RAG 框架/启动|RagFlow]]

## 03. 智能体框架

主流智能体框架。

- [[01. LangChain/01. LangChain快速入门|LangChain]] — LangChain 系列
- [[02. LangChain4j/01. LangChain4j基础配置|LangChain4j]] — Java 版 LangChain
- [[03. Dify/Dify 安装与使用指南|Dify]] — 低代码 AI 应用平台
- [[04. MCP/mcp|MCP]] — Model Context Protocol
- [[05. Skill/01. 概念|Skill]] — Skills 概念
- [[06. Higress/01. 启动|Higress]] — AI 网关
- [[07. OpenClaw/openclaw|OpenClaw]] — OpenClaw
- [[08. Hermes/01. 源码启动|Hermes]] — Hermes 智能体
- [[09. MinerU/01. 启动|MinerU]] — 文档解析
- [[10. Spring AI/Spring AI|Spring AI]] — Spring AI
- [[11. one-api/one-api|one-api]] — LLM API 网关
- [[12. Open-WebUI/使用指南：从安装到上手|Open-WebUI]] — Web UI
- [[国产OpenClaw平替产品汇总]]
- [[99. 能力/01. Json Mode|Json Mode]] — LLM 结构化输出

## 04. AI编程

AI 辅助编程工具与实践。

- [[01. Claude-Code]] — Claude Code
- [[01. 概念/01. Spec Coding|Spec Coding]] — 规范驱动开发
- [[02. 工具/01. ClaudeCode|ClaudeCode]] — Claude Code 工具
- [[02. 工具/02. 架构|架构]] — AI 编程架构

## 05. 大模型

大语言模型理论、接口、微调、部署。

**基础理论**
- [[01. 基础理论/01. 原理|原理]] — LLM 原理
- [[01. 基础理论/02. 大模型定义|大模型定义]]
- [[01. 基础理论/03. 架构|架构]]
- [[01. 基础理论/04. 量化|量化]]
- [[01. 基础理论/05. 术语|术语]]
- [[01. 基础理论/06. 数据集|数据集]]
- [[01. 基础理论/07. 性能|性能]]

**接口与使用**
- [[02. 接口与使用/01. 大模型接口|大模型接口]]
- [[02. 接口与使用/02. 接口文档|接口文档]]
- [[02. 接口与使用/03. GPT使用|GPT 使用]]
- [[02. 接口与使用/04. Llama3|Llama3]]
- [[02. 接口与使用/05. 大模型表格|大模型表格]]
- [[02. 接口与使用/06. 模型提供商|模型提供商]]

**微调**
- [[03. 微调/01. 概念|微调概念]]
- [[03. 微调/02. LoRA|LoRA]]
- [[03. 微调/03. LLaMA Factory|LLaMA Factory]]
- [[03. 微调/04. 微调总览|微调总览]]

**推理与部署**
- [[04. 推理与部署/01. Ollama/01. 安装教程|Ollama]]
- [[04. 推理与部署/02. 语音转文字|语音转文字]]
- [[04. 推理与部署/03. 推理模型|推理模型]]

**DeepSeek**
- [[05. DeepSeek/01. 应用|DeepSeek 应用]]
- [[05. DeepSeek/02. 从热潮到应用-邓亚峰|从热潮到应用]]
- [[05. DeepSeek/03. token|token]]
- [[05. DeepSeek/04. 本地化部署|本地化部署]]
- [[05. DeepSeek/05. 参数|参数]]
- [[05. DeepSeek/06. 硅基流动|硅基流动]]
- [[05. DeepSeek/07. 一些知识点|一些知识点]]
- [[05. DeepSeek/08. 优化点|优化点]]

**能力**
- [[06. 能力/01. Json Mode|Json Mode]]
- [[06. 能力/02. OCR|OCR]]

**待整理**
- [[99. 待整理]]

## 06. 社区与机器学习

AI 社区平台与机器学习基础。

**社区平台**
- [[01. 社区平台/HuggingFace/HuggingFace|HuggingFace]]
- [[01. 社区平台/HuggingFace/01. 概念|HF 概念]]
- [[01. 社区平台/HuggingFace/02. token|HF token]]
- [[01. 社区平台/HuggingFace/03. 代码|HF 代码]]
- [[01. 社区平台/HuggingFace/04. 模型存储环境变量|模型存储]]
- [[01. 社区平台/HuggingFace/05. 文本测试集评估|测试集评估]]
- [[01. 社区平台/ModelScope/01. 下载模型|ModelScope]]

**机器学习**
- [[02. 机器学习基础/01. 西瓜书|西瓜书]]
- [[02. 机器学习基础/02. 千峰课程/01. 课程介绍|千峰课程]]
- [[02. 机器学习基础/02. 千峰课程/02. KNN最近邻算法|KNN]]
- [[02. 机器学习基础/99. 未整理|未整理]]

**通用 AI 文章**
- [[03. 通用AI文章/文章]]

## 07. 基础设施

硬件与 API 密钥。

- [[01. 硬件/01. 显卡|显卡]]
- [[02. API 密钥/01. NVIDIA API Key|NVIDIA API Key]]
