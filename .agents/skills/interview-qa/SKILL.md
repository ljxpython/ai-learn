---
name: interview-qa
description: 处理 AI 应用开发工程师面试题。收到原始题目（单题或批量文章）后，自动分类去重、生成结构化答案文档，输出口语化面试表述、练习思路与记忆技巧，并调度 gpt-image-gen 生成配套信息图。
---

# AI 面试题处理技能 (Interview Q&A)

## 一、 技能定位

本技能是整个 ai-learn 项目的**核心引擎**，负责将原始、碎片化的面试题资料转化为：
1. **结构化知识文档**（存入 `01-interview-qa/`）
2. **可直接开口说的面试表述**（口语化答案）
3. **图文并茂的知识信息图**（调度 `gpt-image-gen`）
4. **记忆技巧 & 练习路径**

---

## 二、 核心工作流

### 情景 A：单题处理（用户提一道题）

```
收到题目
  → Step 1：判断知识领域（见分类体系）
  → Step 2：检索 01-interview-qa/ 下是否已有同类题（去重）
  → Step 3：生成结构化答案文档
  → Step 4：产出口语化回答 + 记忆技巧
  → Step 5：判断是否需要配图（涉及架构/流程必须出图）
  → Step 6：判断是否与 ai-agent-platform 项目相关（调用 project-linker）
```

### 情景 B：批量文章处理（用户粘贴原始资料）

```
收到原始文章
  → Step 1：提取所有独立题目
  → Step 2：去重（与已有题库对比 + 本批次内部去重）
  → Step 3：按分类体系归类
  → Step 4：批量生成题目文档（每题一个 .md 文件）
  → Step 5：更新分类索引文件
```

---

## 三、 AI 应用开发工程师考点分类体系

```
01-interview-qa/
├── 01-llm-basics/           # LLM 基础原理
│   ├── transformer/         # Transformer 架构、注意力机制
│   ├── training/            # 预训练、微调、RLHF
│   └── inference/           # 推理优化、量化、KV Cache
│
├── 02-rag/                  # RAG（检索增强生成）
│   ├── basic/               # RAG 基础流程
│   ├── advanced/            # HyDE、多路召回、重排序
│   └── evaluation/          # RAG 评估指标
│
├── 03-agent/                # Agent & 多智能体
│   ├── frameworks/          # ReAct、CoT、Plan-and-Execute
│   ├── tools/               # Tool Calling、Function Calling
│   └── multi-agent/         # 多 Agent 协作架构
│
├── 04-frameworks/           # 工程框架
│   ├── langchain/           # LangChain 原理与实践
│   ├── llamaindex/          # LlamaIndex 使用
│   └── other/               # AutoGen、Dify、FastGPT 等
│
├── 05-prompt-engineering/   # Prompt 工程
│   ├── basics/              # Few-shot、CoT、Instruction
│   └── advanced/            # Prompt 注入防御、结构化输出
│
├── 06-engineering/          # 工程实践
│   ├── deployment/          # 模型部署、vLLM、Triton
│   ├── evaluation/          # 效果评估、LLM-as-Judge
│   ├── cost-opt/            # 成本优化、缓存策略
│   └── monitoring/          # 可观测性、日志、Trace
│
├── 07-system-design/        # 系统设计题
│   └── scenarios/           # 各类场景设计
│
└── 08-project-showcase/     # 项目相关问答（结合 ai-agent-platform）
```

---

## 四、 面试题文档标准模板

每道题生成一个独立 `.md` 文件，命名格式：`[序号]-[简短英文标题].md`

```markdown
# [题目标题]

> **来源**：[网络资料 / 抖音 / 真实面试 / 用户整理]  
> **难度**：⭐⭐⭐（1-5 星）  
> **考点**：[对应分类路径，如 `02-rag/advanced`]  
> **与项目相关**：是 / 否  

---

## 🎯 一句话定义（记忆锚点）

> [用最简短的一句话说清楚这是什么，像背单词一样好记]

---

## 📖 标准答案（面试规范表述）

[完整、有层次的技术回答，适合书面理解]

---

## 🗣️ 口语化面试表述

> 面试官问这个问题，你开口说的第一句话是什么？

**开场句**：「[直接给出面试时的开口方式]」

**核心展开**（2-3 分钟版本）：
[口语化、有逻辑、能流畅说出来的版本，避免书面腔]

**30 秒极简版**：
[如果面试官打断你，只有 30 秒，你说什么]

---

## 🧠 记忆技巧 & Excalidraw 思维导图

- **口诀 / 比喻**：[用生活化比喻或口诀帮助记忆]
- **关键词串联**：[把核心要素串成一句话或首字母]
- **易混淆点**：[和哪些概念容易搞混，区别是什么]
- **Excalidraw 脑图设计**：
  - 核心链路描述（如：`输入 ➔ 分块 ➔ 稠密检索 + 稀疏检索 ➔ RRF融合 ➔ 重排序 ➔ LLM生成`）
  - 对应存储位置：`assets/excalidraw/[编号]-[英文简称].svg` 或 `.excalidraw`
  - 图引用：`![Excalidraw 架构脑图](../../assets/excalidraw/[文件名].svg)`

---

## 🔗 结合项目的实战回答

（仅当"与项目相关：是"时填写）

> 在 ai-agent-platform 中，这个问题的具体体现是...

[结合真实项目代码/设计说明如何回答]

---

## 💡 延伸追问（面试官可能继续问）

1. [追问1]
2. [追问2]
3. [追问3]

---

## 📊 视觉概念图 (gpt-image-gen)

（当涉及概念隐喻、平台封面或宏观视觉时，此处放置 gpt-image-gen 生成的信息图）

![视觉概念图](../../assets/images/[图片文件名].png)

---

## 六、 视觉资产生成规约 (Excalidraw vs gpt-image-gen)

严格执行“双视觉分工”：
- **Excalidraw 专精**：
  - 系统架构图、多 Agent 交互时序、数据流转、RAG 进阶召回链路、核心原理思维导图。
  - 特点：手绘风、0错字、无文字幻觉、支持 SVG 矢量缩放，适合高密度记忆与 Deck/Site 嵌入。
  - 文件命名：`assets/excalidraw/XX-[模块]-[简述].svg` (或配套保存同名 `.excalidraw` 方便二次编辑)。
- **gpt-image-gen 专精**：
  - 文章封面图（hero-metaphor）、小红书爆款图文、概念反差对比海报、高质感技术插画。
  - 特点：氛围感拉满、极强视觉冲击力、适合社交传播获客。
  - 文件命名：`assets/images/XX-[模块]-[描述].png`。
```

---

## 五、 大厂 vs 创业公司考查差异

| 维度 | 大厂（BAT、字节、美团等） | 中小厂 / 创业公司 |
|------|--------------------------|------------------|
| **原理深度** | 深挖 Transformer 细节、训练流程 | 了解即可，更看重能用 |
| **工程落地** | 高并发、稳定性、大规模部署 | 快速 MVP、产品 sense |
| **框架使用** | 框架原理、自研能力 | 熟练使用 LangChain/Dify 等 |
| **RAG 系统** | 评估指标、优化策略 | 能搭起来跑通 |
| **Agent** | 多 Agent 架构设计 | 会用 Tool Calling 就行 |
| **项目经验** | 百万级调用量、稳定性保障 | 从 0 到 1 搭建的经历 |

> **海投策略**：掌握「原理能说清 + 工程能落地 + 项目有实践」的三层结构，大厂创业公司通吃。

---

## 六、 信息图调度规则

以下类型题目**必须出图**（调用 `gpt-image-gen`）：
- 架构对比类（如：RAG vs Fine-tuning）
- 流程链路类（如：RAG 完整流程、Agent 执行流程）
- 核心概念类（如：注意力机制图解）

**优先使用模板**：
- 对比题 → `infographic-decision-poster`（双栏对比海报）
- 流程题 → `3d-staircase-evolution`（流程演化图）
- 架构题 → `exploded-diagram-tech`（系统架构爆炸图）
