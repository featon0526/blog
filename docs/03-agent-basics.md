---
title: "第3讲 Agent 基础知识"
nav_order: 3
permalink: /03-agent-basics/
date: 2026-09-15
layout: default
---

## 3.1 Ai Models

**大模型通常指"大语言模型"（Large Language Model，简称 LLM）**——一类以海量文本数据训练、拥有超大规模参数量的深度学习模型，能够理解并生成自然语言，完成对话、写作、翻译、推理、编程等多种任务。

* 底层的大语言模型，如 GPT、Claude、Deepseek等。
* 它只做一件事：吃一段文本，吐一段文本。
* 它**被动**——你不问它不答；它**没有记忆**（每次对话独立）、**没有工具**（不能自己上网、读文件、调 API）。
* 它是"脑子"，但不是"手"。

### 3.1.1 常用大模型

* 火山方舟（豆包大模型）
* DeepSeek（深度求索）
* MIniMax
* xiaomi MiMo
* 商汤日日新（免费）
* QWen（千问）
* GLM（智谱）
* [模力方舟](https://moark.com/serverless-api/?utm_sources=site_nav)


### 3.1.2 如何调用大模型——API

DeepSeek API 使用与 OpenAI/Anthropic 兼容的 API 格式，通过修改配置，您可以使用 OpenAI/Anthropic SDK 来访问 DeepSeek API，或使用与 OpenAI/Anthropic API 兼容的软件。

| **PARAM**             | **VALUE**                                               |
| --------------------- | ------------------------------------------------------- |
| base\_url (OpenAI)    | `https://api.deepseek.com`                              |
| base\_url (Anthropic) | `https://api.deepseek.com/anthropic`                    |
| api\_key              | 申请一个 [API key](https://platform.deepseek.com/api_keys)​ |
| model                 | `deepseek-flash
deepseek-v4-pro`                        |

* 接口地址
  * base\_url(O)base\_url (OpenAI) : `https://api.deepseek.com`
  * base\_url (Anthropic) : `https://api.deepseek.com/anthropic`
* api\_key
  * 申请API\_Key : sk-\*\*\*
  * 将 DeepSeek API Key 设置为环境变量 ：==setx DEEPSEEK\_API\_KEY "\"==
* model\_id（模型名称）
  * deepseek-flash
  * deepseek-v4-pro


## 3.2 MCP

**MCP（Model Context Protocol，模型上下文协议）**Anthropic 提出的**开放标准协议**，本质是 AI 世界的"USB-C"，即插即用接口。它规定：

* AI 应用要怎么跟外部工具/数据源通信。
* MCP 解决的是"**怎么标准化连接**"，不关心具体业务逻辑。

### **3.2.2 为什么飞书、Google、Stripe在2026年同时发布CLI工具？**

**2026年CLI工具集体爆发的根本原因，是AI主导的操作方式与GUI图形界面之间出现了结构性摩擦。** 当AI成为工具的主要操作者，原本为人类眼睛和手指设计的界面，正在变成AI操作的障碍。

**安德烈·卡帕西（Andrej Karpathy）**在一篇记录用AI构建应用的文章中，提供了最直接的第一手观察。他描述自己大部分时间不是在写代码，而是在浏览器标签之间反复跳转——配API Key、改DNS、填环境变量。他的结论是：

=="你的服务应该有一个CLI工具。不要让开发者去访问、查看或点击。直接指示和赋能他们的AI。"==

这句话的核心逻辑在于：**GUI（Graphical User Interface，图形用户界面）是为视觉系统设计的，AI没有眼睛；CLI是纯文字的，AI天生生活在这个世界里。** 当工具提供方意识到自己的主要用户正在从"人类点击者"变为"AI调用者"，发布CLI工具成了顺理成章的选择。

### 3.2.3 CLI到底是什么？GUI和CLI的本质区别在哪里？

**CLI（Command Line Interface，命令行界面）的核心定义是：通过纯文本指令完成操作，而非通过图形界面点击按钮或菜单。** 这个定义看起来简单，却是理解CLI与AI适配关系的基础。

一个最直观的类比：

* **GUI**（图形界面）= 去餐厅，看菜单，指给服务员"我要这个"
* **CLI**（命令行）= 直接对厨房喊"宫保鸡丁，少油，多辣"

结果相同，但CLI更精确、更容易被自动化，也更容易被程序（或AI）操作。

### 3.2.4 为什么AI天生在CLI世界里运作，而不是GUI？

**AI大模型的底层机制是"token序列输入，token序列输出"——本质是纯文本交互。** GUI界面为人类视觉系统设计，需要额外的图像识别和元素定位层（即Computer Use类能力），成本高且不稳定。CLI是纯文本的，与AI的输入输出格式完全一致，不需要任何额外转换层。

以视频压缩为例：

* **GUI方式** ：打开Premiere，在界面中找导出按钮，选择格式，配置参数，点击渲染——AI需要逐步解析界面元素
* **CLI方式** ：直接执行 `ffmpeg -i input.mp4 -crf 28 output.mp4`，一行命令完成——AI原生支持

**ffmpeg**：开源[音视频处理](https://cloud.tencent.com/product/mps?from_column=20421&from=20421)工具，几乎是[视频处理](https://cloud.tencent.com/product/mps?from_column=20421&from=20421)的行业标准。通过 `brew install ffmpeg` 即可安装，AI训练数据中已有大量用法示例，无需额外说明书即可使用。

**核心结论：人类没有重新爱上命令行。是AI原本就生活在命令行里，大公司只是顺应了这个事实。**

### **3.2.5 AI的实际能力边界在哪里？工具与上下文如何共同决定AI能做什么？**

**AI的实际能力 = 它能调用的工具 + 它拿到的上下文（说明书）。** 这个公式是理解AI能力边界最简洁的框架。

很多人把AI想象成全知全能的系统。更准确的比喻是：**一个极其聪明的新员工，学习速度快，但需要两样东西才能真正干活——工具和使用说明书。**

* 装了ffmpeg，AI能处理视频
* 装了飞书CLI，AI能查日程、发消息
* 装了Google Workspace CLI，AI能管Gmail和云盘
* 没装？"不好意思，这个我做不了。"

### 3.2.6 为什么新工具必须提供显式的Skills说明书？

工具的历史长度直接决定AI的先验知识量：

| **工具**         | **发布年份**     | **AI是否需要显式说明书** | **原因**          |
| -------------- | ------------ | --------------- | --------------- |
| ffmpeg         | 2000年        | 不需要             | 训练数据中已有大量用法记录   |
| curl / jq      | 1997 / 1988年 | 不需要             | 同上，经典工具覆盖充分     |
| 飞书CLI          | 2026年        | 必须提供            | 发布时间晚于AI训练数据截止点 |
| ElevenLabs CLI | 2026年        | 必须提供            | 同上              |

飞书CLI是2026年新发布的工具，AI训练数据里完全没有相关内容。不提供说明书，AI不知道这个工具的存在，更无从调用。

**因此，新一代CLI工具普遍自带"Skills文件"——一种Markdown格式的使用说明书，告诉AI这个工具能做什么、命令格式是什么、典型场景有哪些。**

这里有一个重要推论：**工具的发布速度永远快于AI训练数据的更新速度。随着AI工具层的持续爆发，Skills文件的重要性只会越来越高。**

## 3.3 Skills

Skills 这个概念最早是由 Anthropic 公司于 2025 年 10 月提出来的。

### 3.3.1 技能是什么？

**指把某类任务的做法封装成可复用的模块**，让模型在需要时调用。它通常包含三部分：

* **说明（Description）**：何时该用这个技能，供模型判断触发时机
* **指令（Instructions）**：具体怎么做，分步骤的操作指南
* **资源（Resources）**：配套的脚本、模板或参考文件

一句话：**技能 = 给 AI 的一本"任务操作手册"**，让它在特定场景下按既定方法干活。

WorkBuddy 平台层的**能力封装**——把一套工作流 + 指令写在 `SKILL.md` 里，AI 加载进来就会多一项专业本事（如 `pdf`、`tencent-pptx`）。它解决的是"**具体怎么做**"。

### 3.3.2 核心价值

* **按需加载**：不用把大量指令全塞进上下文，节省 token、减少干扰。
* **可复用、可组合**：一次写好，多任务共享；多个技能可串联完成复杂工作流。
* **降低门槛**：把专家经验固化成模块，让普通用户也能获得专业级处理效果。

### 3.3.3 安装技能

* 三种技能
  * 内置技能：WorkBuddy内搜索
  * 外部技能：[https://github.com/anthropics/skills](https://github.com/anthropics/skills)
  * 开发技能：自己创建，历史人物讲解视频技能
* 安装技能
  * `~/.claude/skills/` → 全局可用（所有项目）
  * `项目目录/.claude/skills/` → 仅当前项目可用
  * 实践：
    * 搜索taste skill
    * 以WorkBuddy的Hyperframes和Remotion 为例
      * **电影感产品类：**[~https://github.com/Vincentwei1021/video-shotcraft~](https://github.com/Vincentwei1021/video-shotcraft)
        * **最直接的方式：把仓库链接丢给你的 agent。** 在 Claude Code / Codex 等 agent 里说：
        * prompt：帮我安装这个 skill：[https://github.com/Vincentwei1021/video-shotcraft](https://github.com/Vincentwei1021/video-shotcraft)
      * **口播类：**[~https://github.com/Vincentwei1021/video-talkcraft~](https://github.com/Vincentwei1021/video-talkcraft)
      * **科普类：**[~https://github.com/Vincentwei1021/anything2explainer~](https://github.com/Vincentwei1021/anything2explainer)
    * 下载技能安装

### 3.3.4 技能调用

/skills-name，prompt

## 3.4 Agent

![]({{ site.baseurl }}/assets/img/1.webp)

图 3.1 智能体与环境的基本交互循环

### 3.4.1 什么是智能体？

**Agent（智能体）指能自主**感知→规划→调工具→执行多步任务直到达成目标的系统。它的公式是：

> **Agent = 大模型（大脑）+ 规划/记忆 + 工具调用（MCP / Skill）**

你正在用的 WorkBuddy 助手本身，就是一个 Agent。

### 3.4.2 **与普通大模型问答的关键区别**

* **普通对话**：你问一句，它答一句，被动响应，不接触外部世界。
* **Agent**：你给一个目标，它**自主规划路径、循环执行、根据结果调整**，直到完成——是"过程自动化"而非"单次回答"。

举个直观对比：

* 问大模型"北京明天天气如何" → 它只能凭训练数据猜测，可能过时
* 交给 Agent → 它主动调用天气接口、拿到真实数据、整理后回复你

### 3.4.3 与Workflow的差异

简单来说，**Workflow 是让 AI 按部就班地执行指令，而 Agent 则是赋予 AI 自由度去自主达成目标。**

![]({{ site.baseurl }}/assets/img/2.webp)

### 3.4.4 常用智能体

* 豆包Work
* TraeWork
* WorkBuddy（限免）：如何连接大模型？如何安装技能？
  * 专家
  * 技能
    * find skill（发现skill）
    * skills scanner（检查skill）
    * human writing（去ai味）
    * agent reach（获取网上信息）
    * Markitdown
    * skill creator（skill生成）
    * ppt master/taste skill（美化UI）
  * 连接器
  * **微信数据连接（最新版本）**
* DeepSeek Harness
* **CodeX（如何安装？）**
* **Claude Code**

### 3.4.5 Agent核心概念

* context（上下文）
* memory（记忆）
* workspace（工作区）
* tool calling（工具调用）
* computer use（电脑操作）
* mcp（模型上下文协议）
* skill（技能）
* sandbox & approval（沙盒与权限确认）
* sub-agent（agent协作）

## 3.5 Github

**GitHub 是全球最大的代码托管与协作平台**，**基于 Git 版本控制**，让开发者托管代码、追踪修改、多人协作、开源分享。可以把它理解为"程序员的云端工作台 + 社交网络"。

### 3.5.1 **5 个核心概念**

| **概念**               | **含义**               |
| -------------------- | -------------------- |
| **Repository（仓库）**   | 一个项目，存放代码与文件，是最基本的单位 |
| **Commit（提交）**       | 一次修改的存档，带说明信息，可追溯与回退 |
| **Branch（分支）**       | 从主线分出的独立工作线，用于并行开发   |
| **Pull Request（PR）** | 请求把自己的修改合并进主分支，是协作核心 |
| **Fork（复刻）**         | 把别人的仓库复制到自己账号下，独立修改  |

### 3.5.2 **入门基本流程**

1. **注册账号**：访问官网注册，建议开启两步验证
   * Watt Toolkit/steam++，网络加速器
2. **创建仓库**：点 New repository，填名称、描述，选择公开或私有
3. **克隆到本地**：
   * git clone [https://github.com/用户名/仓库名.git](https://github.com/用户名/仓库名.git)
4. **修改并提交**：
   * git add .
   * git commit -m "说明这次改了什么"
   * git push
5. **查看与回退**：网站上可看提交历史，随时回溯版本

### 3.5.3 **协作的经典流程**

参与开源或团队项目的标准做法：

1. **Fork** 目标仓库到自己账号
2. **Clone** 到本地并新建分支开发
3. 完成后 **Push** 到自己的仓库
4. 发起 **Pull Request**，说明改动内容
5. 等待维护者 **Review**，通过后合并

### 3.5.4 **常用功能**

* **Issues**：提问题、报 Bug、讨论需求
* **Actions**：自动化流水线（自动测试、构建、部署）
* **Pages**：免费托管静态网站
* **Star / Watch**：收藏关注感兴趣的项目
* **Gist**：分享代码片段

### 3.5.5 学习资源

​[~https://docs.github.com/zh/get-started~](https://docs.github.com/zh/get-started)​

## 3.6 MarkDown & HTML

**Markdown 和 HTML 是 AI 世界的"通用文字载体"——Markdown 是 AI 最自然的输出语言，HTML 是它最终落地的呈现格式，两者构成了 AI 与人类、AI 与网页之间的"翻译层"。**

| **格式**       | **本质**    | **特点**               |
| ------------ | --------- | -------------------- |
| **Markdown** | 轻量级标记语言   | 语法极简，纯文本可读，专注于"内容结构" |
| **HTML**     | 网页超文本标记语言 | 描述完整网页结构与样式，能被浏览器渲染  |

### **3.6.1 Markdown 是 AI 的"母语"**

**Markdown 是 AI 最主流的输出格式。**

原因：

1. **训练数据多**：GitHub、文档、论坛大量使用 Markdown，模型天然熟悉。
2. **结构清晰**：标题、列表、表格、代码块都能用简单符号表达。
3. **易读易解析**：人看着舒服，程序也容易转成 HTML。
4. **token 效率高**：比 HTML 标签更省 token。

典型场景：

* ChatGPT / Claude / DeepSeek 默认用 Markdown 回复
* AI 写文档、README、笔记
* AI 生成结构化内容（表格、步骤、代码）

### 3.6.2 AI 与 HTML 的关系

**HTML 是 AI 内容的最终落地形态之一。**

关系体现在：

1. **AI 可以生成 HTML**：写网页、邮件模板、报告页面。
2. **AI 可以解析 HTML**：爬虫、网页理解、信息抽取。
3. **AI 输出常被转成 HTML**：Markdown 渲染器把 AI 回复转成 HTML 显示在网页上。
4. **AI 智能体操作 HTML**：浏览器自动化、点击按钮、填表单。

**AI ↔ HTML 是“生成 + 解析 + 操作”的双向关系。**

### **3.6.3 MarkitDown**

**MarkItDown 是微软开源的一款轻量级文档转换工具。**[**~https://github.com/microsoft/markitdown~**](https://github.com/microsoft/markitdown)​

* **它解决什么问题**

大模型最擅长处理 Markdown 这类结构化文本，但现实中的资料却是 PDF、Word、Excel、PPT、图片等各种格式，含大量排版噪声。MarkItDown 就是中间的**"翻译器"**：不管源文件多复杂，统一转成干净的 Markdown 再喂给模型。

* **支持的格式**
  * **办公文档**：Word、Excel、PowerPoint、PDF
  * **结构化数据**：HTML、CSV、JSON、XML
  * **多媒体**：图片（通过 OCR 识别文字）、音频（语音转录）
  * **其他**：EPub、ZIP 压缩包、YouTube 视频链接等

**MarkItDown = 文档界的格式翻译官**，把 PDF、Word、图片、音频等统统转成 Markdown，让大模型能轻松读懂、索引和处理各种资料。
