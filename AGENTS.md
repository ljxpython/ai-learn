# AI 应用开发工程师面试备战 - 项目总览

## 🎯 项目目标

本项目是一个系统性的 AI 面试准备与知识沉淀仓库，目标是帮助作者以最高效的方式通过 **AI 应用开发工程师** 岗位的面试，并构建可持续的个人技术影响力。

## 📌 核心战略

| 维度 | 内容 | 载体 |
|------|------|------|
| **学习** | 整理网络资料 + 抖音真实面试题 → 结构化知识体系 | `01-interview-qa/` |
| **实战** | 面试题与 [ai-agent-platform](../ai-agent-platform) 项目深度绑定，用真实生产代码/踩坑经验作答 | `02-my-project/` |
| **记忆** | **双视觉引擎**：`gpt-image-gen` (高质感封面/隐喻) + **Excalidraw** (白板手绘风思维导图/架构拓扑) | `assets/images/` & `assets/excalidraw/` |
| **笔记** | 体系化全量在线知识库，面试前速查与背书 | [knowledge-site](https://github.com/ljxpython/knowledge-site-template) (`04-knowledge-site/`) |
| **演示** | 面试现场高浓度战术汇报幻灯片，3分钟击穿面试官心智 | [knowledge-deck](https://github.com/ljxpython/knowledge-deck-template) (`04-knowledge-deck/`) |
| **输出** | 优质内容多端适配，打造个人技术影响力 | 掘金、小红书、CSDN、知乎 (`03-articles/`) |

## 🗂️ 目录结构

```
ai-learn/
├── AGENTS.md                   # 本文件：项目总览 & Agent 工作约定
├── README.md                   # 项目说明
│
├── .agents/skills/             # 专属 Skills
│   ├── gpt-image-gen/          # 图像生成能力（OpenAI-compatible / 概念图 / 封面）
│   ├── excalidraw-gen/         # Excalidraw 原生手绘思维导图生成与导出引擎（霞鹜文楷/双向绑定）
│   ├── interview-qa/           # 面试题处理核心技能（去重 / 分类 / 记忆技巧 / Excalidraw规范）
│   ├── project-linker/         # 关联 ai-agent-platform 真实实现
│   └── article-gen/            # 面试内容转多平台技术文章
│
├── 00-roadmap/                 # 学习路线 & 进度追踪
│   └── roadmap.md
│
├── 01-interview-qa/            # 面试题库（核心真实源 SSOT）
│   ├── 01-llm-basics/          # LLM 基础原理 (Transformer / 训练 / 推理优化)
│   ├── 02-rag/                 # RAG 检索增强生成 (基础流程 / 进阶召回重排 / 评估)
│   ├── 03-agent/               # Agent & 多智能体 (ReAct / 工具调用 / 协作拓扑)
│   ├── 04-frameworks/          # LangChain、LlamaIndex 等
│   ├── 05-prompt-engineering/  # Prompt 工程与防护
│   ├── 06-engineering/         # 工程实践 (vLLM部署 / 评测 / 监控 / 成本优化)
│   ├── 07-system-design/       # 系统设计题
│   └── 08-project-showcase/    # 项目专属大题精解
│
├── 02-my-project/              # 结合 ai-agent-platform 的实战方案与专项答卷
├── 03-articles/                # 写作草稿 & 发布追踪
│   ├── README.md               # 发布状态追踪表
│   ├── drafts/                 # 通用底稿
│   ├── juejin/                 # 掘金适配版
│   ├── zhihu/                  # 知乎适配版
│   ├── csdn/                   # CSDN 适配版
│   └── xiaohongshu/            # 小红书图文适配版
│
├── 04-knowledge-site/          # knowledge-site 内容整理（在线知识库映射）
├── 04-knowledge-deck/          # knowledge-deck 演示幻灯片（面试现场高光攻坚）
├── 05-resources/               # 原始资料存放区 (待处理)
│   ├── raw-articles/           # 网络技术文章
│   ├── douyin-qa/              # 抖音面试实战真题
│   └── other/                  # 其它散落资料
│
└── assets/                     # 统一静态资产库
    ├── images/                 # gpt-image-gen 生成的概念配图与海报
    └── excalidraw/             # Excalidraw 思维导图与手绘白板架构图 (.svg / .excalidraw)
```

## 🤖 Agent 工作约定

本项目由 Antigravity Agent（老王）辅助维护，贯彻 **KISS、DRY 与单一真实源 (SSOT)** 原则：

### 角色定位
- **学习伙伴**：深度剖析技术本质，坚决拒绝死记硬背
- **面试教练**：模拟严苛面试官步步紧逼，暴露逻辑漏洞
- **架构参谋**：把题目精准引流至 `ai-agent-platform`，用真实代码击溃八股文
- **视觉架构师**：调度 `gpt-image-gen` 与指导设计 `Excalidraw` 手绘脑图
- **宣发总监**：一鱼多吃，把一次性解题转化为多平台爆款文章与 Deck 演示胶片

### 核心工作流
1. **输入处理**：扫描 `05-resources/` 原始材料 ➔ 拆解题目 ➔ 分类归入 `01-interview-qa/` 且自动去重。
2. **结构化精解**：生成“一句话记忆锚点 + 标准规范解答 + 口语化应答 + 记忆技巧 + 延伸追问”。
3. **视觉与记忆赋能**：
   - 核心逻辑/流程链路/对比拓扑 ➔ 提供 **Excalidraw** 思维导图结构或图元（存入 `assets/excalidraw/`）。
   - 平台封面/概念隐喻 ➔ 调度 `gpt-image-gen` 产出高质量插图（存入 `assets/images/`）。
4. **项目联动**：调用 `project-linker` 检索 `ai-agent-platform`，生成真实实战段落。
5. **资产沉淀与分发**：
   - 笔记全景同步至 `knowledge-site`
   - 高光突破点精炼进 `knowledge-deck`
   - 优质专题调用 `article-gen` 转化为各平台文章。

---

## 📋 面试题文档模板

```markdown
# [题目标题]

> **来源**：[网络资料 / 抖音 / 真实面试]  
> **难度**：⭐⭐⭐（1-5 星）  
> **考点**：[对应分类路径，如 `02-rag/advanced`]  
> **与项目相关**：是 / 否  

---

## 🎯 一句话定义（记忆锚点）

> [用最凝练的一句话点破本质，如同肌肉记忆卡片]

---

## 📖 标准答案（技术规范表述）

[完整、严谨、层次分明的书面回答]

---

## 🗣️ 口语化面试表述

**开场破题（第一句话）**：
> 「...」

**核心展开（2~3 分钟版）**：
...

**30 秒极简版（应对打断）**：
...

---

## 🧠 记忆技巧 & Excalidraw 思维导图

- **口诀 / 生活隐喻**：...
- **核心逻辑链路**：
  `节点A ──(条件)──► 节点B ──(分支)──► 节点C`
- **Excalidraw 图解**：
  ![思维导图](../../assets/excalidraw/[文件名].svg)

---

## 🔗 结合项目的实战回答 (ai-agent-platform)

（如适用）
- **项目落地点**：...
- **具体实现方案**：...
- **踩坑与调优 (杀手锏)**：...
- **面试对谈台词**：
  > 「在我自己的项目中，这一块我们最初使用的是...，后来发现...，最终我们重构为...」

---

## 💡 延伸追问（面试官连环炮）

1. [追问1]
2. [追问2]
3. [追问3]

---

## 🎨 视觉概念海报 (可选)

![概念配图](../../assets/images/[文件名].png)
```

---

## 🔗 关联资源与在线交付

- **本地实战项目**：`/Users/lijiaxin/PyCharmMiscProject/ai-agent-platform`
- **核心知识库源码**：https://github.com/ljxpython/ai-learn (本仓库)
- **在线知识站 (Site)**：
  - 代码仓库：https://github.com/ljxpython/ai-knowledge-site
  - 线上访问：https://ljxpython.github.io/ai-knowledge-site/
- **现场演示胶片 (Deck)**：
  - 代码仓库：https://github.com/ljxpython/ai-knowledge-deck
  - 线上访问：https://ljxpython.github.io/ai-knowledge-deck/
- **全网分发矩阵**：掘金 / 小红书 / CSDN / 知乎
