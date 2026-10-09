---
title: "第2讲 音视频制作"
nav_order: 2
permalink: /02-audio-video/
date: 2026-09-08
layout: default
---

## 2.1 音视频自动化剪辑


### 2.1.1 从第1个案例开始

【任务概述】

用Ai交互制作一个关于历史人物的讲解视频，包含剧本、配图、视频、字幕、旁白、转场特效，整合为剪映草稿，导出视频，最终将全部流程生成一个技能包，随机或指定一个历史人物名字即可自动生成相应的视频，名字：李白。

* 【Prompt】：我现在要制作一个关于历史人物讲解的视频。要先做剧本，我的第一个任务就是要做一个标题，现在我给你一个历史人物名字。你帮我返回一个标题，比如秦始皇统一天下的一生，或者成吉思汗征战的一生。名字：李白。
* 【工具】
  * Ai Agent：豆包Work/TareWork/WorkBuddy（限免）、DeepSeek Harness、CodeX/Claude Code
  * Ai Models ID/API\_Key：火山方舟、DeepSeek、Hy3、SeeDream/SeeDance、MIniMax……
  * 音视频剪辑：剪映

【注意事项】

* 视频生成慢、Token成本大（豆包、商汤日日新、MIniMax…）用已生成的视频举例
* 剪映的API说明书生成草稿加密问题，见《==剪映API接口说明文档.md==》和《==剪映草稿生成指南.md==》
* 视频分辨率：==480p==、720p与1080p

| **称呼**   | **分辨率**           | **总像素** | **适用场景**  |
| -------- | ----------------- | ------- | --------- |
| 标清 SD    | 480P (720×480)    | 约35万    | 老式电视、低带宽  |
| 高清 HD    | 720P (1280×720)   | 约92万    | 普通网络视频    |
| 全高清 FHD  | 1080P (1920×1080) | 约207万   | 主流视频标准    |
| 2K / QHD | 2560×1440         | 约369万   | 中高端显示器/手机 |
| 4K / UHD | 3840×2160         | 约829万   | 高端电视、电影制作 |
| 8K       | 7680×4320         | 约3318万  | 顶级设备、未来标准 |

* 免费TTS，Edge TTS与[模力方舟](https://moark.com/serverless-api/?utm_sources=site_nav)……
* 如何管理网址、注册用户、密码、Models\_ID、URL、API\_Key和Token（令牌），豆包Work/**~==应用生成个人凭据管理工作台==~**。


### 2.1.2 音视频自动化流水线

![]({{ site.baseurl }}/assets/img/1.webp)


### 2.1.3 三种方案

#### ChatCut：你的AI对话式剪辑师

ChatCut是一个**对话式AI视频剪辑工具**，核心是让用户通过自然语言指令来完成剪辑，就像跟一个剪辑师对话一样。

* **核心能力**：它能听懂你的指令，比如“剪掉所有口头禅并加字幕”、“把这段素材导入项目”。它的工作流是“文本化编辑”，先将视频转录成文本，你编辑文字，视频时间线就跟着变动，极大地简化了传统剪辑的复杂操作。
* **工作方式**：它通过MCP Server架构，将自己的编辑能力封装成AI Agent可以调用的接口。安装它的插件后，像Codex这样的智能体就可以直接指挥ChatCut进行粗剪、添加转场、生成配音等，最后产出一个**可继续编辑的真实时间线**，而非扁平视频。这使它既能快速出片，也能融入专业工作流（支持导出为Premiere Pro等软件的XML工程文件）

#### Remotion：React驱动的视频编程框架

Remotion是一个**用React代码来制作视频的开源框架**，核心理念是“代码即视频的唯一事实来源”。

* **核心能力**：开发者编写React组件来定义视频的画面、动画和逻辑，利用其强大的渲染引擎生成视频。它非常适合需要**数据驱动、批量生成和版本控制**的自动化视频场景，如个性化营销视频、数据报告视频等。
* **工作方式**：它提供了三种创作方式：让AI Agent写代码、在可视化Studio里拖拽编辑、纯编程开发，且这三种方式可以任意切换。它的生态更成熟，文档完善，但使用门槛相对较高，需要熟悉React和前端开发。**特别需要注意的是，Remotion对商业使用有特定许可要求，需要留意**。

#### HyperFrames：Agent友好的HTML视频渲染方案

HyperFrames是HeyGen开源的一个**视频渲染引擎**，它的理念是用最基础的**HTML文件来定义视频**。

* **核心能力**：你不需要学习React，只需要写一个包含`data-*`属性的HTML文件，配合CSS或GSAP等动画库，就可以定义出包含视频、音频、字幕、动画的复杂视频。它非常强调 **“确定性”** ，即同样的输入总能得到同样的输出，便于自动化测试和批量渲染。
* **工作方式**：它的特点在于 **“Agent友好”** ，因为AI Agent本身就很擅长生成和修改HTML代码。它被视为一个比Remotion更轻量的替代方案，对AI来说更“顺手”，尤其适合和AI Agent配合，根据模板批量生成风格统一的视频内容。

![]({{ site.baseurl }}/assets/img/2.webp)

#### 总结：如何选择？

你可以根据你的需求和角色来选择：

* **如果你是非技术背景的创作者**，想快速、高效地完成**口播视频、Vlog等的粗剪和包装**，希望像和人说话一样和AI沟通，那么**ChatCut**会更适合你。
* **如果你是开发者**，团队熟悉React生态，需要构建**复杂、定制化、且与数据或系统深度集成**的视频自动化流水线，可以选择**Remotion**。
* **如果你想和AI Agent（如Codex）紧密协作**，用**高度模板化、轻量级**的方式批量生成短视频（例如榜单、商品卡、白板动画），但又不想引入React的复杂性，那么**HyperFrames**的路线可能更合适。实际上，已经有开发者将HyperFrames用于生成“白板火柴人拆书短视频”等创意内容。

在你的工作流中，甚至可以组合它们：用ChatCut完成前期素材的智能粗剪，再导出到HyperFrames或Remotion进行更精细的动画包装和批量渲染。

#### 【作品展示】


**【作品1】**[~用Remotion制作纪录片风格的地图动画视频~](https://www.bilibili.com/video/BV1HFMi6tETK/?spm_id_from=333.1387.collection.video_card.click&vd_source=d714697529dc5478a80f00b51e6eb346)​


**【作品2】**[~用Remotion如何Vibe Coding出Vox风格动效视频~](https://www.bilibili.com/video/BV1sCMh6XEXR/?spm_id_from=333.1387.collection.video_card.click&vd_source=d714697529dc5478a80f00b51e6eb346)​


**【作品3】**[~世界杯数据可视化~](https://www.bilibili.com/video/BV1PeER65EVv/?spm_id_from=333.1387.collection.video_card.click&vd_source=d714697529dc5478a80f00b51e6eb346)​


**【作品4】**ChatCut、Remotion和HyperFrames口播视频的自动化剪辑

* HyperFrames：《剪映草稿生成完整指南》制作口播视频（==TraeWork==）
* Remotion：世界杯数据可视化（==WorkBuddy/WorldCup==）
* ChatCut：zzs的口播视频（==WorkBuddy/Video==）


#### 【作业1】

参照**【案例1】和【作品展示】**，制作一个关于_**==名著介绍==**_的讲解视频制作技能，包含剧本、语音、配图生成视频的Skills，随机或指定一本书名即可自动生成相应的视频，书名：《红楼梦》。


## 2.2 Skills是什么？

技能主要解决"AI 把一件事做得更专业"的问题。它本质是**一套可复用的专项能力包**，由精心设计的指令、示例、评判标准和操作流程组成，让AI在特定场景下按专业范式输出。

* 典型能力：行业报告撰写、数据分析、代码审查、特定格式的内容生产等；
* 本质：给AI增加"脑内方法论"，让它从"什么都会一点"变成"某件事很专业"。


## 2.3 Agent工具与大模型


### 2.3.1 Ai Agent工具安装与配置

* 豆包Work
* TraeWork
* WorkBuddy（限免）
* DeepSeek Harness
* CodeX
* Claude Code


### 2.3.2 Ai Models 

* API\_Key
* 火山方舟（豆包大模型）
* DeepSeek
* MIniMax
* xiaomi MiMo
* 商汤日日新（免费）
* QWen（千问）
* GLM（智谱）
* [模力方舟](https://moark.com/serverless-api/?utm_sources=site_nav)


### 2.3.2 Github使用

* Steam++（Watt Toolkit）
* 注册
* 仓库建立
* 网页发布
* 图床


##

​
