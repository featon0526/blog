---
title: "第6讲 案例讲解"
nav_order: 6
permalink: /06-case-study/
date: 2026-09-29
layout: default
---



# 《新媒体交互设计》——第6讲 案例讲解

***

2026.9.29

***

# 一、Git & Github

## Git 和 GitHub 有什么区别

* Git↗ 是安装在电脑上的软件。本地查看差异、创建提交和恢复已记录文件，都可以在没有 GitHub 账号、没有网络的情况下完成。安装 Git 也不会自动把项目上传到云端。开发人员可以查看项目历史记录以找出：
  * 进行了哪些更改？
  * 谁进行了更改？
  * 何时进行了更改？
  * 为什么需要更改？
* [GitHub](https://github.com/) 是云端的代码托管与协作平台。你可以把本地仓库的提交推送到 GitHub；有读取权限的人可以克隆或拉取它，团队还可以围绕分支发起 Pull Request、审查改动。GitHub 上新建仓库也不会自动得到你电脑里的文件。

![](https://gitee.com/featon/picture/raw/master/20261009212749354.webp)

Git 本身也支持远程协作，GitHub 是常见的托管选择，并非唯一选择。只在本机 commit 后，同事不会自动收到更新；还要完成远程关联、认证和 push。

## 怎样安装 Git，确认它能用

我们可以直接在有本机操作能力的 AI Agent 对话框里说：

```
“帮我检查这台电脑有没有安装 Git。如果没有，按我的系统完成安装；安装完成后运行 git --version，把版本号告诉我。”
```

Agent 会在后台检查系统环境并完成配置。我们只需要核对它的回复中是否包含以 `git version` 开头的版本信息（例如 `git version 2.39.5`），这就说明当前环境已经能正常找到 Git。

## 基本 Git 命令

以下是使用 Git 的一些常用命令：

```
git init 初始化一个全新的 Git 存储库并开始跟踪现有目录。 它在现有目录中添加一个隐藏的子文件夹，该子文件夹包含版本控制所需的内部数据结构。
git clone 创建远程已存在的项目的本地副本。 克隆包括项目的所有文件、历史记录和分支。
git add 暂存更改。 Git 跟踪开发人员代码库的更改，但有必要暂存更改，并生成变更快照以将其包含在项目的历史记录中。 此命令执行暂存，即该两步过程的第一部分。 暂存的任何更改都将成为下一个快照的一部分，并成为项目历史记录的一部分。 通过单独暂存和提交，开发人员可以完全控制其项目的历史记录，而无需更改其编码和工作方式。
git commit 将快照保存到项目历史记录中并完成更改跟踪过程。 简而言之，提交就如同拍照。 任何使用 git add暂存的内容都将成为使用 git commit的快照的一部分。
git status 将更改的状态显示为未跟踪、已修改或已暂存。
git branch 显示正在本地处理的分支。
git merge 将开发线合并在一起。 此命令通常用于合并在两个不同分支上所做的更改。 例如，当开发人员想要将功能分支中的更改合并到主分支以进行部署时，他们会合并。
git pull 使用远程对应项的更新来更新本地开发线。 如果队友已向远程上的分支进行了提交，并且他们希望将这些更改反映到其本地环境中，则开发人员将使用此命令。
git push 使用本地对分支所做的任何提交来更新远程存储库。
```

## 创建 GitHub 帐户

### 第 1 步：创建存储库！

首先我们需要创建一个存储库。 存储库就好比包含相关项的文件夹，例如文件、图像、视频，甚至其他文件夹。 存储库通常会将属于同一“项目”或正在处理的事务的项组合在一起。

![](https://gitee.com/featon/picture/raw/master/20261009212754800.webp)

### 第 2 步：创建分支

通过分支，您可以同时拥有不同版本的存储库。

默认情况下，存储库有一个名为 `main` 的分支，它被视为最终分支。 可在存储库中从 `main` 创建其他分支。

![](https://gitee.com/featon/picture/raw/master/20261009212802487.webp)

### 第 3 步：进行和提交更改

### 第 4 步：打开一个拉取请求

![](https://gitee.com/featon/picture/raw/master/20261009212806692.webp)

### 第 5 步：合并拉取请求

## Pages

## 常用英文

### 📦 仓库与基础操作

* &#x200C;**repository (repo)**‌：仓库，项目代码存放的地方。
* ‌**clone**‌：克隆，把远程仓库完整复制到本地。
* &#x200C;**fork**&#x200C;：派生/复制，把别人仓库复制一份到你自己账户下，方便独立修改。
* &#x200C;**star**‌：星标，相当于点赞收藏，方便以后快速找到项目。
* &#x200C;**watch**‌：关注，接收这个仓库的更新通知，可以自己选通知级别。
* &#x200C;**README.md**‌：项目说明文件，通常介绍项目用途、安装和使用方法。
* ‌**LICENSE**‌：许可证，规定别人能怎么合法使用你的代码。
* &#x200C;**issue**&#x200C;：问题/任务，用来报告 bug 或记录待办事项。
* &#x200C;**release**&#x200C;：发布，正式发布的版本，会打上版本号。
* **deploy**：部署上线。

### 🌿 分支与版本管理

* &#x200C;**branch**‌：分支，独立的开发线，不影响主分支。
* &#x200C;**commit**‌：提交，把代码更改保存成一个版本记录。
* &#x200C;**push**‌：推送，把本地提交上传到远程仓库。
* &#x200C;**pull**&#x200C;：拉取，从远程仓库下载并合并更改。
* &#x200C;**merge**&#x200C;：合并，把不同分支的代码整合到一起。
* ‌**rebase**‌：变基，重新整理提交历史，让它变成一条线性记录。
* ‌**checkout**‌：检出，切换到另一个分支或某个历史版本。
* ‌**conflict**‌：冲突，不同分支改了同一处代码，需要手动解决。
* ‌**tag**‌：标签，给某次提交打上版本标记，比如 v1.0。

### 🤝 协作与代码审查

* &#x200C;**pull request (PR)**‌：拉取请求，提交代码合并请求，是团队协作的核心。
* &#x200C;**review**‌：代码审查，检查别人提交的代码并给意见。
* &#x200C;**approve**‌：批准，同意某次代码更改，可以合并了。
* ‌**collaborator**‌：合作者，有仓库写入权限的人。
* ‌**maintainer**‌：维护者，负责项目日常维护和决策的人。
* ‌**milestone**‌：里程碑，项目的阶段性目标。
* ‌**assignee**‌：受理人，某个 issue 或任务的具体负责人。

### ⚙️ 自动化与配置

* &#x200C;**workflow**&#x200C;：工作流，GitHub Actions 里的自动化流程。
* &#x200C;**action**‌：动作，工作流里自动执行的任务脚本。
* ‌**CI/CD**‌：持续集成/持续部署，自动化测试和发布流程。
* ‌**secret**‌：密钥，存在仓库里的隐藏配置变量，比如 API 密钥。
* ‌**webhook**‌：网络钩子，监听特定事件后自动触发外部操作。
* &#x200C;**.gitignore**‌：忽略文件列表，定义哪些文件不需要被 Git 追踪。

### 💬 常用缩写（看到不慌）

* &#x200C;**PR**&#x200C;：Pull Request，拉取请求。
* ‌**LGTM**‌：Looks Good To Me，代码审查通过，可以合并。
* ‌**WIP**‌：Work In Progress，还在开发中，别急着合并。
* ‌**PTAL**‌：Please Take A Look，请帮忙看一下。
* ‌**TBD**‌：To Be Done，还没搞定，待定。
* ‌**TL;DR**‌：Too Long; Didn't Read，太长不看，一般后面会跟简略版说明。

> 这几个缩写里 ‌**PR**‌、‌**WIP**‌、‌**LGTM**‌ 最常用，尤其提 PR 时标题加 `WIP` 是告诉维护者代码还没写完，可以先看看思路。‌‌

另外有两个小提醒：

* ‌**fork 和 clone 别搞混**‌：fork 是复制到‌**自己 GitHub 账户**‌下，clone 是复制到‌**本地电脑**‌。
* ‌**watch、star、fork 是仓库右上角三个核心按钮**‌：star 是收藏点赞，watch 是关注更新通知，fork 是复制到自己账户下做二次开发。‌‌

# 二、个人知识库

## 简易版Wiki

新建 Wiki 文件夹，用 Obsidian 打开，再添加到 Agent 的工作目录。发送Prompt：

```
你是我的「个人知识库管家」。我完全不懂AI，请全程用大白话，别用术语劝退我。
一、建两个文件夹：01_素材（原始资料）、02_知识卡（你读完之后的总结）。
二、建三个文件：档案目录.md、知识库工作规则.md、我的偏好.md。
三、以后我发文章或链接给你，都走：抓正文 → 去重比对 → 存原件 → 生成知识卡。
四、知识卡固定三块：核心结论 / 可复用方法 / 关键数据，每条都写清楚。
五、每次做完，提醒我哪些关注方向还没有素材，催我补料。
```

## LLM Wiki（Agent + Obsidian）

LLM Wiki 是一种由 Agent 持续整理和维护的本地知识库。原始资料被完整保存，重要信息会被提炼、关联，并写入可以持续更新的 Markdown 知识页。

使用 Agent + Obsidian，分别搭建三个独立知识库：

* 智能备忘录：整理想法、邮件、会议记录和 Apple Notes。
* 个人风格库：从历史文章和文案中提炼选题与表达习惯。
* 自动灵感库：定时读取 RSS，去重、归档并更新选题。

### 【核心】Karpathy 的 播客

```text
https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
```

为每个知识库创建一个独立文件夹，并添加为 Agent 工作目录。

一个基础 LLM Wiki 主要包含：

```
LLM Wiki/
├── raw/：保存邮件、笔记、文章等原始资料
├── wiki/：保存 Agent 提炼、关联和持续维护的知识
└── AGENTS.md：规定资料如何入库、整理、引用和检查
```

### 2.1 Vibe\_Note（智能备忘录）

新建 Vibe\_Note 文件夹，用 Obsidian 打开，再添加到 Agent 的工作目录。发送Prompt：

```
1.帮我在本地构建一个「智能备忘录」。
2.参考 Karpathy 的 LLM Wiki 方法论：
3.https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
4.核心目标是构建一个会自己整理、关联和更新的个人信息库。
5.我会不断把随手记录、邮件、会议记录、Apple Notes、网页、文件等重要信息放进来。我只负责记录和输入，不希望考虑分类、标签和应该存在哪里，这些交给 Agent 自动理解和维护。
6.整个系统以本地文件夹 + Markdown + Agent 为核心。保留原始信息，同时让 Agent 根据新进入的信息持续整理和更新已有知识，识别人物、项目、主题以及信息之间的关系，并尽量避免重复和信息孤岛。
7.保持实现简单、透明、可迁移。优先充分利用文件系统、Markdown 和 Agent 自身的搜索、理解与编辑能力，不要过度工程化，不要为了“智能”引入不必要的数据库、向量库、复杂 RAG 或其他基础设施。
8.请先理解 Karpathy 这套方法论，再结合这个目标自行规划并构建。
```

搭建完成后，可以把邮件截图、会议记录和 Apple Notes 笔记直接交给 Agent，如：

```
将这幅邮件截图入库
```

回到 Obsidian，检查原始资料是否保留、Wiki 页面是否更新，以及关系图谱中是否产生了有效链接。最后用一个真实问题验收：

```
帮我汇总这个项目相关的邮件、会议结论和历史笔记，
列出已经确定的事情、下一步，以及尚未解决的问题。
```

### 2.2 Style\_Lib（个人风格库）

新建工作目录，把过去积累的文章和文案放进去，然后发送：

```
帮我基于当前工作目录中的所有历史文案，构建一个「个人风格库」。
参考 Karpathy 的 LLM Wiki 方法论：
https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
核心目标是：从我长期创作的真实文案中，持续提炼、整理和更新我的个人写作风格，让 Agent 以后能够理解并尽可能复现“我是怎么写东西的”。
当前目录中的历史文案是原始资料和事实依据，请保留原文，不要为了整理而修改它们。在此基础上建立一个简单、可持续维护的 Markdown 风格知识库。
不要只做泛泛的“风格总结”，而要从真实文案中寻找反复出现的创作规律，例如：表达语气、内容结构、开场方式、观点推进、转折衔接、解释方式、案例使用、节奏、句式、用词习惯、口语化表达、结尾方式，以及我倾向使用和避免使用的表达。
注意区分稳定的个人风格与某一篇文章因为题材、产品或平台产生的偶然特征。重要判断尽量能够回溯到真实文案和具体例子，不要凭空定义我的风格。
随着以后更多文案进入工作目录，这套风格库应该可以继续被 Agent 阅读、修正、合并和更新，而不是每次重新分析一遍。
整个实现保持简单，以本地文件 + Markdown + Agent为核心，不要引入不必要的数据库、向量库或复杂系统。
最终希望这套知识库不仅能回答「我的文案有什么特点」，更重要的是能够直接作为 Agent 以后帮我**选题、构思、写稿、改稿和判断“这像不像我写的”**时的长期风格依据。
请先阅读和理解现有文案，再自行规划最合适的知识库结构并开始构建。
```

完成后，可以直接询问：

```
哪些观点我已经反复讲过，却还没有做成一期完整内容？
```

### 2.3 Ins\_Lib（ RSS 个人灵感库）

新建灵感库目录，准备一组长期关注的 RSS 信息源 放进工作目录。然后发送：

```
帮我在当前工作目录构建一个「个人灵感库」。
参考 Karpathy 的 LLM Wiki 方法论：
https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
我会提供一批 RSS 订阅源，之后每天都会有新的文章和信息进入这里。
这个知识库的目标不是做一个 RSS 收藏夹，而是让 Agent 随着信息不断进入，持续形成一个会自己整理、关联和更新的灵感 Wiki，帮助我发现值得关注的主题、观点、趋势、产品、案例，以及未来值得创作的内容方向。
RSS 获取到的原始内容作为 Raw Sources，尽量完整保留来源、标题、发布时间、原文链接等信息。在此基础上，由 Agent 持续维护整理后的知识库：识别不同信息之间的关联，把同一主题的新旧信息连接起来，更新已有认知，而不是每天产生一堆彼此孤立的摘要。
重点关注「这条信息为什么值得留下」以及「它和过去的信息有什么关系」。区分单纯新闻、持续趋势、重要观点、有价值案例和真正值得进一步创作的灵感，避免把所有内容都当成同等重要。
随着资料积累，这个库应该越来越能够回答：最近什么值得关注、某个主题发生了什么变化、有哪些反复出现的信号、哪些信息可以组合成新的选题，以及我过去围绕某个方向积累过哪些素材。
整个系统保持简单、透明、可维护，以本地文件、Markdown 和 Agent 为核心，不要引入不必要的数据库、向量库或复杂基础设施。
请根据这些目标自行规划合适的目录和 Wiki 结构，并为后续每日 RSS 自动入库设计清晰、简单的维护规则。
```

灵感库创建成功以后，设置定时任务，提示词：

```
读取个人灵感库中配置的 RSS 订阅源，获取自上次执行以来的新内容，并按照当前知识库的维护规则完成入库。
保留新内容的原始信息和来源，然后理解其中真正有价值的信息，并更新现有的主题、趋势、观点、案例和灵感等 Wiki 内容。
重点寻找新信息与已有知识之间的关系：能更新已有页面就优先更新，不要为每篇 RSS 文章都创建孤立的知识页面；发现新的重要主题时再创建新页面。
注意去重，避免重复处理已经入库的文章。所有重要判断和总结都应能够追溯到原始来源。
不要只是生成一份“今日 RSS 摘要”，目标是让整个个人灵感库随着每天的新信息持续生长和更新。
```

### 2.4 RSS 订阅源

RSS ：Really Simple Syndication，简易信息聚合是向订阅者提供网站上的新闻、博客和其他内容的一种方法。

RSS通过XML标准定义内容的包装和发布格式。对RSS内容提供者来说，RSS技术提供了一种实时、高效、安全、低成本的信息发布渠道；对RSS订阅用户来说，它提供了一种崭新的阅读体验。

```
教育部
最新文件
https://rsshub.dicomp.net/gov/moe/newest_file
政策解读
https://rsshub.dicomp.net/gov/moe/policy_anal
教育考试网
中小学教师资格
https://rsshub.dicomp.net/neea/local/ntce
PubScholar 公益学术平台
https://rsshub.dicomp.net/pubscholar/explore
联合早报
中港台
https://rsshub.dicomp.net/zaobao/realtime/china
中国新闻
https://rsshub.dicomp.net/zaobao/znews/china
央视新闻联播
https://rsshub.dicomp.net/cctv/tv/lm/xwlb
知乎热榜
https://rsshub.dicomp.net/zhihu/hot
知乎日报
https://rsshub.dicomp.net/zhihu/daily
第一财经新闻
https://rsshub.dicomp.net/yicai/news
哔哩哔哩排行榜
https://rsshub.dicomp.net/bilibili/ranking/all
36Kr热榜
https://rsshub.dicomp.net/36kr/hot-list
豆瓣实时热门书影音
https://rsshub.dicomp.net/douban/list/subject_real_time_hotest
豆瓣实时热门电影
https://rsshub.dicomp.net/douban/list/movie_real_time_hotest
豆瓣实时热门电视
https://rsshub.dicomp.net/douban/list/tv_real_time_hotest
豆瓣热门书籍
https://rsshub.dicomp.net/douban/book/rank/fiction
财联社头条
https://rsshub.dicomp.net/cls/depth/1000
格隆汇快讯
https://rsshub.dicomp.net/gelonghui/live
金十数据
https://rsshub.dicomp.net/jin10
虎嗅24小时新闻
https://rsshub.dicomp.net/huxiu/moment
虎嗅资讯
https://rsshub.dicomp.net/huxiu/article
华尔街实时新闻
https://rsshub.dicomp.net/wallstreetcn/live
同花顺财经
https://rsshub.dicomp.net/10jqka/realtimenews
OPENAI新闻
https://rsshub.dicomp.net/openai/news
每日AI资讯
https://rsshub.dicomp.net/ai-bot/daily-ai-news
AI新闻资讯
https://rsshub.dicomp.net/aibase/news
AI日报
https://rsshub.dicomp.net/aibase/daily
人民日报
时政新闻：http://www.people.com.cn/rss/politics.xml
社会新闻：http://www.people.com.cn/rss/society.xml
法治新闻：http://www.people.com.cn/rss/legal.xml
国际新闻：http://www.people.com.cn/rss/world.xml
台港澳新闻：http://www.people.com.cn/rss/haixia.xml
军事新闻：http://www.people.com.cn/rss/military.xml
全部新闻：http://www.people.com.cn/rss/ywkx.xml
虎嗅网
https://rss.huxiu.com/
数字尾巴
https://www.dgtle.com/rss/dgtle.xml
36氪
https://36kr.com/feed
爱范儿
https://www.ifanr.com/feed
威锋网
https://www.feng.com/rss.xml
少数派
https://sspai.com/feed
河北新闻网
http://www.hebei.com.cn/link/rss/rss.html
1905电影网
https://www.1905.com/rss.php?rssid=
国家统计局
最新发布   http://www.stats.gov.cn/tjsj/zxfb/rss.xml
数据解读   http://www.stats.gov.cn/tjsj/sjjd/rss.xml
中新网即时新闻
https://www.chinanews.com.cn/rss/scroll-news.xml
中国气象局
http://www.cma.gov.cn/2011qxfw/2011qxxdy/
和讯rss
http://news.hexun.com/rss/
中国金融信息网rss
http://app.xinhua08.com/rss.php
经济观察网
http://www.eeo.com.cn/sypd/rss/index.html
科学网
https://www.sciencenet.cn/RSS.aspx
国家国防科技工业局
http://www.sastind.gov.cn/n6182907/index.html
国家电力投资集团
http://www.spic.com.cn/hdjl2018/rss/
我的煤炭网
https://www.mycoal.cn/feed/
界面新闻
https://a.jiemian.com/index.php?m=article&a=rss
异次元软件
https://feed.iplaysoft.com/
cnBeta
https://www.cnbeta.com/backend.php
极客公园
https://www.geekpark.net/rss
异次元软件
https://feed.iplaysoft.com/
财新博客
https://blog.caixin.com/feed
钛媒体
https://www.tmtpost.com/feed
品玩
https://www.pingwest.com/feed/all
IT之家
https://www.ithome.com/rss/
知乎每日精选
https://www.zhihu.com/rss
煎蛋
http://jandan.net/feed
数英网
https://www.digitaling.com/rss
国务院新闻
http://www.gov.cn/govweb/jsonTag/tp/rss.xml 政策新闻
http://www.gov.cn/pushinfo/v150203/rss.xml  新闻时政
中新网
https://www.chinanews.com.cn/rss/
人力资源和社会保障部
http://www.mohrss.gov.cn/SYrlzyhshbzb/zxhd/RSS/
全国公共资源交易中心
http://subscribe.ggzy.gov.cn/subs/subscribe/rss.jsp
中国财经网
https://www.fecn.net/rss.php
C114通信网
http://www.c114.com.cn/rss/
中化集团
http://www.sinochem.com.cn/1240.html
产品经理
http://www.woshipm.com/feed
第一财经
https://www.yicai.com/feed
36Kr快讯
https://rsshub.dicomp.net/36kr/newsflashes
虎嗅资讯
https://rsshub.dicomp.net/huxiu/article
麦肯锡
https://rsshub.dicomp.net/mckinsey/cn
观察者网
https://rsshub.dicomp.net/guancha/gundong
参考消息第一关注
https://rsshub.dicomp.net/cankaoxiaoxi/column/diyi
参考消息中国
https://rsshub.dicomp.net/cankaoxiaoxi/column/zhongguo
环球网国内
https://rsshub.dicomp.net/huanqiu/news/china
环球网国际
https://rsshub.dicomp.net/huanqiu/news/world
爱范儿
https://rsshub.dicomp.net/ifanr/digest
律动
https://rsshub.dicomp.net/theblockbeats/newsflash
求是网
https://rsshub.dicomp.net/qstheory/toutiao
中国新闻周刊调查
https://rsshub.dicomp.net/inewsweek/survey
人民日报电子版
https://rsshub.dicomp.net/people/paper
凤凰网
https://rsshub.dicomp.net/ifeng/news
半月谈今日谈
https://rsshub.dicomp.net/banyuetan/jinritan
微信读书新书榜
https://rsshub.dicomp.net/qq/weread/newbook
微信读书Top200
https://rsshub.dicomp.net/qq/weread/all
中国互联网联合辟谣平台
https://rsshub.dicomp.net/piyao/jrpy
中文播客榜
https://rsshub.dicomp.net/xyzrank
中国国家博物馆资讯专题
https://rsshub.dicomp.net/chnmuseum/zx/xwzt
中国国家博物馆资讯要闻
https://rsshub.dicomp.net/chnmuseum/zx/xingnew
雪球热帖
https://rsshub.dicomp.net/xueqiu/hots
南方周末推荐
https://rsshub.dicomp.net/infzm/1
南方周末新闻
https://rsshub.dicomp.net/infzm/2
实时资讯
https://dicomp.net/hotnews/
国际实时新闻：【https://rsshub.app/zaobao/realtime/world】
```

### 2.5 Obsidian

### 2.6 Picgo

# 三、Audio Workbench（个人音频工作台）

面向 `qwen-audio-3.1-tts-next`的本地音频创作工作台。[~https://mp.weixin.qq.com/s/Lr53oCwxbtN-tPdRdefKZw~](https://mp.weixin.qq.com/s/Lr53oCwxbtN-tPdRdefKZw)​

![](https://gitee.com/featon/picture/raw/master/20261009212818641.webp)

![](https://gitee.com/featon/picture/raw/master/20261009212823800.webp)

![](https://gitee.com/featon/picture/raw/master/20261009212829143.webp)

【练习】：做一个自动化剪辑的视频工作台

# 四、自媒体工作台

## **定位与**选题（AI辅助决策）

**目标：找到“你能持续做 + 有流量 + 能变现”的交集。**

* **定位梳理**：把你想做的领域、目标人群、自身优势输入AI，让它帮你生成3-5个账号定位方向，并分析各自的天花板与变现路径。
* **选题挖掘**：
  * 用AI抓取/分析对标账号的爆款选题（输入“帮我分析XX领域近30天爆款选题规律”）
  * 让AI基于热点+你的定位，批量生成20-30个选题，你筛选出5个
  * 建立选题库：爆款复刻、痛点解决、热点借势、个人故事四类

**常用工具**：ChatGPT/Claude/DeepSeek、新榜、蝉妈妈、灰豚数据

## 内容生产（AI批量生成 + 人工精修）

* 图文类（公众号/小红书/头条）
  * **大纲**：AI生成3版大纲，你选一版调整
  * **初稿**：AI按大纲写全文，你补充个人案例、真实感受
  * **标题**：AI生成10个标题，你用“数字+痛点+情绪”标准筛选
  * **配图**：AI生图（Midjourney/即梦/可灵）或图库+AI改图
* 短视频类（抖音/视频号/B站）
  * **脚本**：AI写分镜脚本（画面+口播+时长）
  * **口播**：真人录制，或AI配音（剪映/ ElevenLabs）
  * **画面**：AI生图/生视频做素材，或实拍+AI剪辑
  * **剪辑**：剪映AI成片、自动字幕、智能卡点
  * **封面**：AI生成封面图+大字标题
* 直播类
  * **话术**：AI生成开场、留人、逼单、答谢话术模板
  * **选品**：AI分析历史数据给出选品建议
  * **复盘**：直播转录后丢给AI，分析停留、转化、互动问题

## 发布与运营（AI提效）

* **多平台分发**：一份内容用AI改写成不同平台版本（小红书短句+emoji、公众号长文、抖音口播稿）
* **发布时间**：AI分析你的粉丝活跃数据，推荐最佳发布时段
* **评论区运营**：
  * AI生成常见问题回复模板
  * 用AI分析评论情绪，找出用户真实需求，反哺选题
* **私域引流**：AI设计引流话术、自动回复SOP

## 数据分析与迭代（AI诊断）

* **数据复盘**：把播放/阅读、完播、互动、转化数据丢给AI，让它诊断问题（“完播低是前3秒问题还是节奏问题？”）
* **爆款拆解**：把爆款内容输入AI，反向拆解结构、钩子、情绪曲线，形成模板
* **A/B测试**：AI生成不同标题/封面/开头，小流量测试后放大
* **迭代方向**：AI根据数据给出下阶段内容调整建议

## 变现闭环（AI辅助）

* **广告**：AI写商单脚本、报价策略
* **知识付费**：AI帮你把内容整理成课程大纲、讲义
* **电商**：AI写产品卖点、详情页、直播话术
* **社群**：AI生成社群运营SOP、每日话题、答疑模板

## 推荐工具栈（按环节）

| **环节** | **工具**                            |
| ------ | --------------------------------- |
| 选题/文案  | ChatGPT、Claude、DeepSeek、Kimi      |
| 生图     | Midjourney、即梦、可灵、Stable Diffusion |
| 生视频    | 可灵、Runway、Pika、即梦                 |
| 配音     | ElevenLabs、剪映、魔音工坊                |
| 剪辑     | 剪映、CapCut、Descript                |
| 数据     | 新榜、蝉妈妈、灰豚、飞瓜                      |
| 自动化    | Coze、Dify、Make、Zapier             |

## 个人工作台

【炼化自己】跑通自己完整的Ai工作流。

* AI辅助定5个选题，写3篇初稿
* 精修+配图+做封面
* 录制/生成视频，剪辑3条
* 多平台分发+评论区互动
* AI复盘数据，调整下周方向
* 储备素材、拆解爆款

# 五、个人简历网页

[~https://featon0526.github.io/Resume/~](https://featon0526.github.io/Resume/)​

**【作业二**】：制作一个3D交互的个人主页，展示个人简历、自己的作品等内容，部署上线到Github。

## 团队介绍页面

使用时按下面顺序执行：

* 团队介绍页面：先投喂“基础提示词”，让豆包生成 React + TypeScript + Vite + Tailwind 的角色轮播页面。
* 团队成员素材：用“图像生成提示词”生成 3D 角色概念图，再用抠图得到 PNG。
* 团队页替换：用“替换人物提示词”把占位人物换成上传角色图，并让背景跟随人物衣着配色变化。

### 基础提示词

```
Build a single full-viewport hero section in React + TypeScript + Vite + Tailwind CSS, using `lucide-react` for icons. The component is a character-figurine carousel called "TOONHUB".
3. **Top-left brand label "TOONHUB"** (`absolute top-6 left-4 sm:left-8`, zIndex 60): `text-xs font-semibold uppercase`, white, opacity 0.9, letterSpacing `0.18em`.
4. **Carousel** (`absolute inset-0`, zIndex 3): map all 4 IMAGES; each item is `position:absolute`, `aspectRatio: '0.6 / 1'`, with role-based styles below. Inside, an `` `width:100%; height:100%; objectFit:contain; objectPosition:bottom center; draggable=false`.
Per-role style:
- **center**: `transform: translateX(-50%) scale(${isMobile?1.25:1.68})`, no blur, opacity 1, zIndex 20, `left:50%`, `height: isMobile?'60%':'92%'`, `bottom: isMobile?'22%':0`.
- **left**: `translateX(-50%) scale(1)`, blur 2px, opacity 0.85, zIndex 10, `left: isMobile?'20%':'30%'`, `height: isMobile?'16%':'28%'`, `bottom: isMobile?'32%':'12%'`.
- **right**: same as left but `left: isMobile?'80%':'70%'`.
- **back**: `translateX(-50%) scale(1)`, blur 4px, opacity 1, zIndex 5, `left:50%`, `height: isMobile?'13%':'22%'`, `bottom: isMobile?'32%':'12%'`.
Transition on each item: `transform 650ms cubic-bezier(0.4,0,0.2,1), filter 650ms ..., opacity 650ms ..., left 650ms ...`. `willChange: transform, filter, opacity`.
5. **Bottom-left text + nav buttons** (`absolute bottom-6 left-4 sm:bottom-20 sm:left-24`, zIndex 60, `maxWidth:320px`):
- `` "TOONHUB FIGURINES" — bold uppercase, tracking-widest, `mb-2 sm:mb-3 text-base sm:text-[22px]`, white, opacity 0.95, letterSpacing `0.02em`.
- `` (hidden on mobile, `hidden sm:block`): "The artwork is stunning, shipped fully prepared. The finish is a vision, the 3D craft is flawless. Many thanks! Wishing you the win. Order now." — `text-xs sm:text-sm`, white, opacity 0.85, lineHeight 1.6, `mb-4 sm:mb-5`.
- Two circular buttons (`w-12 h-12 sm:w-16 sm:h-16`, transparent bg, 2px white border, white icon): `ArrowLeft` and `ArrowRight` from lucide-react, size 26, strokeWidth 2.25. On hover: scale 1.08 + bg `rgba(255,255,255,0.12)`. Transition `transform 150ms, background-color 150ms`. Click triggers `navigate('prev')` / `navigate('next')`.
6. **Bottom-right link "DISCOVER IT"** (`absolute bottom-6 right-4 sm:bottom-20 sm:right-10`, zIndex 60): `` flex items-center, font Anton, `fontSize: clamp(20px, 4vw, 56px)`, weight 400, white, opacity 0.95→1 on hover (200ms), letterSpacing `-0.02em`, lineHeight 1, uppercase, no underline. Followed by `ArrowRight` (`w-5 h-5 sm:w-8 sm:h-8`, strokeWidth 2.25).
**Behavior summary:** clicking arrows rotates roles; background color, image positions, scales, blurs, and opacities all crossfade simultaneously over 650ms with `cubic-bezier(0.4,0,0.2,1)`. The character images sit at the bottom of the screen overlapping the giant "3D SHAPE" text behind them.
```

### 图像生成提示词

```
[Seedream 5.0 Pro]请根据我上传的人物参考图生成一张 3:4 竖版高质量 3D 游戏角色概念图。
保留参考人物的脸型、五官、发型、眼神、表情气质和年龄感，把人物转化为一个具有潮流感的 3D 游戏角色。不要复制参考图服装，服装重新设计，根据人物气质自由发挥。
角色全身出镜，动作要有表现力，不要僵硬站立。可以设计成一只手插兜、一只手扶帽檐、扶眼镜、做手势、身体微微侧转、一只脚自然前迈等姿势。整体动作自然、自信、有力量感，像游戏角色概念设定图中的展示姿态。
服装风格可以是街头潮牌、机能风、运动风、工装风、赛博街头风或轻战术风。服装颜色要鲜明、有冲击力，可以使用橙色、白色、米色、浅灰、蓝色、绿色、红色、黄色或拼色搭配。服装上加入喷漆、涂鸦、编号、贴布、标签、金属扣件、护具、功能性口袋、磨损和做旧细节，让角色像一套高级游戏皮肤。
高对比度纯色背景。可以是明亮色块、潮流摄影棚、游戏角色展示空间、几何图形墙、街头涂鸦墙或带灯带的概念场景。背景要和角色形成强烈对比，突出人物轮廓，画面有海报感和高级展示感。
整体风格：高质量 3D 渲染，虚幻引擎 5 视觉质感，AAA 游戏角色概念图，高精细节，摄影棚光效，电影级灯光，PBR 材质，Lumen 全局光照，柔和主光，边缘轮廓光，真实阴影，高级材质，清晰头发发束，真实布料纹理，精致建模，超清细节。
```

### 抠出主体（PNG）

### 重复生成（团队多人）

![](https://gitee.com/featon/picture/raw/master/20261009212843042.webp)

### 替换人物提示词

```
将页面中人物修改为上传的参考图人物
且背景按照参考图人物的衣着配色匹配
页面的加载图片太慢，压缩图片提高加载速度。
```

## 个人简历网站

使用时按下面顺序执行：

* 个人简历网站：投喂“基础提示词”，生成白底编辑部风格的 portfolio landing page。
* Hero 人物素材：依次生成正面近景、右侧半身、左侧全身、右侧半身动态图四张关键帧。
* Hero 视频：用“视频生成提示词”把四张关键帧合成 10 秒丝滑转场视频。
* 页面二次替换：把 Hero 视频上传给豆包，用“替换视频文件和文字的提示词”实现滚动驱动播放和 3 组文字动效

### 基础提示词

```
目前的页面是团队介绍页，选择工装男士点击 discover it 进入个人主页，下面我给出对应的提示词开始制作个人主页。
```

```
Build a premium creator portfolio landing page using React, TypeScript, Tailwind CSS, GSAP ScrollTrigger, Framer Motion, and Lucide React. The page is based on the original source portfolio prompt, but it must be redesigned around the provided futuristic creator video hero and a mostly white editorial layout. All visible UI copy must be rewritten around the persona "AI Archmage".
- Each character uses invisible placeholder + absolute positioned animated span.
- Adapt colors to the white theme.
Magnet:
- The original Magnet component is optional in this redesign.
- If used, apply it only to the ContactButton or a small accent element, not to the hero video.
- Settings must remain: padding 150, strength 3, activeTransition "transform 0.3s ease-out", inactiveTransition "transform 0.6s ease-in-out", willChange: 'transform'.
ViewCaseButton:
- Rounded-full ghost/outline pill button.
- Border-2 border-[#0C0C0C].
- Text color #0C0C0C.
- Font-medium, uppercase, tracking-widest.
- Sizes: px-8 py-3 sm:px-10 sm:py-3.5, text-sm sm:text-base.
- Hover: bg-[#0C0C0C]/10.
- Label: "View Case".
RESPONSIVE RULES
- Use Tailwind default breakpoints: sm 640px, md 768px, lg 1024px.
- Mobile-first approach.
- Heavy use of clamp() for fluid typography.
- No text may overflow or overlap incoherently at mobile or desktop widths.
- Preserve fixed-format dimensions with aspect-ratio for the hero media, marquee tiles, and project-card image grids.
- Do not scale font size directly with viewport width except where the original prompt already uses explicit vw heading sizes or clamp().
- Letter spacing should be 0 for large display headings; use tracking only for small uppercase labels.
IMPLEMENTATION NOTES
- Keep the application as a single-page landing page.
- Do not add a marketing intro page before the hero. The GSAP video hero is the first viewport.
- Do not add visible instructions explaining how to scroll or how the animation works.
- Keep the design clean, white, technical, and editorial.
- The first viewport must immediately show the futuristic white-background creator video/person as the main signal.
- The MarqueeSection and ProjectsSection must retain all original image URLs and movement/card-stacking behavior, only restyled for the white theme.
- The resume section should feel like a serious personal record, not a decorative services list.
```

### 图像生成提示词

![](https://gitee.com/featon/picture/raw/master/20261009212847594.webp)

### 图像生成提示词（正面近景头像特写）

```
以上传的人物照片作为唯一角色参考，生成同一个人物的正面近景头像特写。

严格保持参考图中的人物身份、脸型、五官、年龄感、肤色、发型、发色、护目镜、服装领口、材质、颜色和整体造型完全一致，不要重新设计人物，不要改变服装，不要增加或删除任何配饰。

画面构图要求：
横版 16:9，白色纯净摄影棚背景。人物为正面近景头像，位于画面中央，头部和护目镜居中，画面只展示头部、脖子和上胸区域。人物直视镜头，表情冷静、克制、未来感。双手不要入镜，不要扶眼镜，不要做手势。

姿势要求：
这是四视图中的第一张，主要用于展示脸部和护目镜，动作要简洁，不要模仿参考图中其他半身或全身动作。

风格要求：
高级 3D 游戏角色概念图，虚幻引擎 5 质感，真实材质，棚拍灯光，清晰锐利，高级时装大片质感。

不要生成文字、logo、水印，不要背景杂物。
```

### 图像生成提示词（右侧版式半身图）

```
以上传的人物照片作为唯一角色参考，生成同一个人物的右侧版式半身图。

严格保持参考图中的人物身份、脸型、五官、年龄感、肤色、发型、发色、白色未来感护目镜、紫色镜片、黑色科技感服装、护腕、腰带、配饰、材质、颜色和整体造型完全一致。只允许改变构图、朝向和动作，不要重新设计服装，不要改变人物。

画面构图要求：
横版 16:9，白色纯净摄影棚背景。人物必须明显靠画面右侧，不要居中。人物主体中心位置在画面横向 72% 到 78% 之间，人物右侧距离画面边缘保留少量安全边距。画面左侧必须保留 55% 以上的干净白色空白区域，用于后期添加文字。左侧空白区域不能有人物、不能有道具、不能有阴影杂物。

人物姿势要求：
人物为半身或中景构图，从头部到腰部或大腿上方入镜。身体略微侧转，呈右侧三分之二角度。人物一只手抬起，轻轻扶住或调整护目镜边缘；另一只手放在腰带附近、插兜或自然下垂。头部微微倾斜，姿势要比参考图更有变化，不要完全复制参考图的站姿和手臂角度。

动作关键词：
右手扶护目镜，手肘向外打开，肩膀有轻微倾斜，身体重心偏向一侧，姿态自然，有未来科技角色展示感。

风格要求：
高级 3D 游戏角色概念图，虚幻引擎 5 质感，真实材质，棚拍灯光，清晰锐利，高级时装大片质感。

不要把人物放在画面中央，不要填满整张图，不要占用左侧留白。不要生成文字、logo、水印。
```

### 图像生成提示词（左侧版式全身图）

```
以上传的人物照片作为唯一角色参考，生成同一个人物的左侧版式全身图。

严格保持参考图中的人物身份、脸型、五官、年龄感、肤色、发型、发色、白色未来感护目镜、紫色镜片、黑色科技感上衣、黑色下装、腰带、护腕、鞋子、所有配饰、材质、颜色和整体造型完全一致。只允许改变构图、朝向和动作，不要重新设计服装，不要改变人物。

画面构图要求：
横版 16:9，白色纯净摄影棚背景。人物必须明显靠画面左侧，不要居中。人物主体中心位置在画面横向 22% 到 30% 之间，人物左侧距离画面边缘保留少量安全边距。画面右侧必须保留 55% 以上的干净白色空白区域，用于后期添加文字。右侧空白区域不能有人物、不能有道具、不能有阴影杂物。

人物姿势要求：
人物全身完整出镜，从头到脚都要显示，不要裁切头发、脚、手臂或配饰。身体呈左侧三分之二角度，站姿要与参考图不同。可以让人物一只脚微微向前，形成自然重心变化；一只手插兜，另一只手自然下垂或轻扶腰带。头部可以微微转向镜头或转向画面右侧，整体像时装 Lookbook 的站姿。

动作关键词：
左侧全身，重心偏移，单脚前置，一手插兜，一手扶腰带或自然下垂，姿态松弛但有角色感，不要扶护目镜，不要做与第二张相同的动作。

风格要求：
高级 3D 游戏角色概念图，虚幻引擎 5 质感，真实材质，棚拍灯光，清晰锐利，高级时装大片质感。

不要把人物放在画面中央，不要填满整张图，不要占用右侧留白。不要生成文字、logo、水印。
```

### 图像生成提示词（右侧版式半身动态图2）

```
以上传的人物照片作为唯一角色参考，生成同一个人物的右侧版式半身动态图。

严格保持参考图中的人物身份、脸型、五官、年龄感、肤色、发型、发色、白色未来感护目镜、紫色镜片、黑色科技感服装、护腕、腰带、配饰、材质、颜色和整体造型完全一致。只允许改变构图、朝向和动作，不要重新设计服装，不要改变人物。

画面构图要求：
横版 16:9，白色纯净摄影棚背景。人物必须明显靠画面右侧，不要居中。人物主体中心位置在画面横向 72% 到 78% 之间，人物右侧距离画面边缘保留少量安全边距。画面左侧必须保留 55% 以上的干净白色空白区域，用于后期添加文字。左侧空白区域必须保持纯净，不要出现人物、手臂、道具、阴影杂物。

人物姿势要求：
人物为半身或中景构图，从头部到腰部或大腿上方入镜。身体呈右侧三分之二角度，姿势必须和第二张不同。不要扶护目镜。人物一只手向镜头前方或画面左侧轻微伸出，做一个自然、有表现力的科技感手势；另一只手可以放在胸前、腰带旁或自然下垂。头部略微转向镜头，表情冷静自信。

动作关键词：
右侧半身，手向前伸，手指自然张开或做轻微操作界面的手势，身体微微后仰或侧转，肩膀有动态变化。动作要明显区别于扶护目镜动作，也不要照抄参考图。

风格要求：
高级 3D 游戏角色概念图，虚幻引擎 5 质感，真实材质，棚拍灯光，清晰锐利，高级时装大片质感。

不要把人物放在画面中央，不要填满整张图，不要占用左侧留白。不要生成文字、logo、水印。
```

### 视频生成提示词

```
生成视频：0秒到2秒：
画面从图一开始。人物为正面近景头像，位于画面中央，直视镜头，保持轻微微笑。镜头非常轻微地向后拉开，人物有自然呼吸感，头部微微转动，墨镜和脸部细节清晰可见。动作克制，不要大幅移动。

2秒到4秒：
人物从图一自然过渡到图二。镜头继续缓慢后拉，并向右平滑平移，人物从居中位置移动到画面右侧，同时左侧逐渐形成大面积白色留白。人物上半身出现，身体转为右侧三分之二角度。人物抬起一只手，动作自然地扶住墨镜边缘，好像正在轻轻调整墨镜；另一只手自然插入口袋或放在腰侧。过渡必须丝滑，不能突然切换，不能瞬移。

4秒到6.5秒：
人物从图二过渡到图三。人物放下扶墨镜的手，身体开始向左转身，镜头同步进行平滑环绕和后拉，从半身视角逐渐变成全身视角。人物边转身边向画面左侧走出一步，最终形成图三的姿势：人物位于画面左侧，全身完整出镜，背部和侧身朝向镜头，头部回望镜头，右侧保留大面积白色留白。这个过渡要像一次连贯的转身走位，服装和裤腿随着动作有轻微自然摆动。

6.5秒到8秒：
画面保持图三的全身左侧站姿。人物站在画面左侧，右侧是干净白色留白。人物身体重心轻微变化，一只手自然放在裤袋附近，头部微微回望镜头，保持自信轻松的角色感。镜头轻微稳定推进，但不要改变人物位置，不要让人物回到画面中央。

8秒到10秒：
人物从图三过渡到图四。人物从左侧全身姿势转身面向镜头，迈步向画面右侧移动，镜头同步向右平移并逐渐推近，从全身变成半身中景。人物一只手从身体前方自然抬起并向镜头方向伸出，做出邀请、展示或科技感交互手势；另一只手抓住夹克边缘或自然放在身体前方。最终形成图四：人物位于画面右侧，左侧保留大面积白色留白，人物半身入镜，手掌向前伸出，动作有纵深感。过渡必须顺滑自然，不能硬切，不能跳帧。

镜头语言：
全程使用平滑推拉、平滑横移、轻微环绕镜头和动作匹配转场。每个姿势之间通过人物的抬手、转身、走位、回头、伸手动作自然衔接。人物位置必须准确：图二和图四人物靠画面右侧，左侧留白；图三人物靠画面左侧，右侧留白；图一人物居中近景。整体像一段高级角色介绍视频，动作流畅，节奏舒适，转场丝滑。，16:9
```

### 最后替换视频文件和文字的提示词

```
在现有首页 Hero 区域添加 GSAP ScrollTrigger 滚动驱动视频播放效果。

桌面端和移动端都要适配，移动端文字缩小并避开人物脸部和身体。
时间与内容：

最开始大标题：I AM TOUGE

第一组文字，靠左：

1:25 大标题进场
1:50 小字打字机进场
3:00 大标题和小字共同离场
大标题：VIBE CODING / AGENT

小字：I turn prompts into working worlds, pairing fast creative code with agentic workflows that iterate, test, and ship.

第二组文字，靠右：

3:50 大标题进场
4:20 小字打字机进场
6:00 大标题和小字共同离场
大标题：AIGC PLAYER

小字：I shape AI-generated visuals into polished stories, blending 3D character energy with brand-ready direction.

第三组文字，靠左：

6:30 大标题进场
6:50 小字打字机进场
9:20 大标题和小字共同离场
大标题：WELCOME

小字：Welcome to Touge, where code, AI, and 3D craft meet in one scroll-driven portfolio.

实现方式：

根据 video.currentTime 计算每组文字的 opacity、transform 和小字打字机进度。滚动时实时更新文字状态。保留现有页面结构、Hero 视频、pin、scrub、resize refresh、prefers-reduced-motion 逻辑。
```

# 六、手搓3D爆炸+视差滚动特效

视频、图像素材全部使用 [https://www.lovart.art](https://www.lovart.art) 制作。

## 视频链接

[~https://www.bilibili.com/video/BV1DNeu68EVv/?spm\_id\_from=333.1387.homepage.video\_card.click~](https://www.bilibili.com/video/BV1DNeu68EVv/?spm_id_from=333.1387.homepage.video_card.click)​

## 创建 “3D 拆解图”技能

```
下面的原封不动创建为 “3D 拆解图” 技能：

- 各张图之间保持统一的视角体系、构图边界、缩放逻辑和光照风格
- 输出图应适合网页进一步组装使用
- 背景必须透明
- 每个组件在拆分图中应尽量独立、清晰、边缘完整，便于后续在网页中单独使用或组合
- 如果某些曲面细节在尺寸图中无法完全确定，应参考官方产品外观做合理补足，但不能偏离原始产品气质

# 输出要求
固定输出 5 张透明背景图片：
1. 正面完整图
完整组装状态。
接近正交的正面视角，产品居中，用于准确表现整体宽度、比例和正面结构。

2. 背面完整图
完整组装状态。
与正面图严格相反的观察方向，并保持相同的产品尺度、中心位置和构图规范。

3. 侧面完整图
完整组装状态。
选择最能表现产品厚度、轮廓和结构层次的一侧，使用接近正交的侧面视角。

4. 上下方向组件拆分图
选择轻微 3/4 视角，略微侧转并轻微俯视，避免完全正面导致组件过于扁平，同时能看清各层厚度和装配关系。
各个关键组件只沿画面的 上、下方向 从原始安装位置拉开，形成垂直方向的组件拆分。
要求：
- 所有组件保持原本朝向
- 组件沿同一条垂直方向展开
- 不向左右或纵深方向随意散开
- 不翻转或单独旋转组件
- 保持原始中心和装配对应关系
- 从上到下能够清楚看出组件层级
- 将组件沿相反方向移动后，应能够自然重新组成完整产品

5. 左右方向组件拆分图
选择最适合表达结构关系的固定视角。
各个关键组件只沿画面的 **左、右方向** 从原始安装位置拉开，形成水平方向的组件拆分。

要求：
- 所有组件保持原本朝向
- 组件只向左或向右移动
- 不同时向上下方向散开
- 不翻转或改变组件观察角度
- 左右展开后仍然保持与原始安装位置的明确对应关系
- 将左右组件沿相反方向移动后，应能够自然重新组成完整产品

如果用户没有提供文档和产品名称，请提醒用户。
```

## Apple Watch 生成示例

![](https://gitee.com/featon/picture/raw/master/20261009212853909.webp)

## Apple Watch Ultra 3  官方结构文档

![](https://gitee.com/featon/picture/raw/master/20261009212858184.webp)

![](https://gitee.com/featon/picture/raw/master/20261009212905977.webp)

![](https://gitee.com/featon/picture/raw/master/20261009212901868.webp)

## 制作 3D 爆炸图视频

```
正面是视频唯一主体，Apple Watch Ultra 3 的造型、配色、材质全部以它为基准不得走样；侧面约束侧面轮廓、表冠与按键形态；左右拆解是左右横向拆解爆炸图，拆解与重组阶段的零件形态、分离顺序以它为依据。手表主体悬浮于纯黑背景，无表带、无人物、无文字。从正面转向侧面，侧面这里停留一会；然后慢动作沿左右方向拆解，按左右拆解顺序分离正面玻璃、显示屏、中框与传感器背盖，零件悬浮保持精确间距。 停留 2 秒后，把左右分离的组件合并成侧面（注意不用回到正面）。 16:9 横版视频
```

## 制作高级交互 HTML：视差滚动 + 悬停特效

````markdown
# 视差滚动与 3D 解构单 HTML 网页

你是一名顶级前端动效架构师与工业设计交互专家。

你的任务是根据用户提供的产品名称，以及该产品的拆解 / 爆炸动画视频，生成一个具备高质量视觉表现与沉浸式交互体验的单 HTML 全屏视差滚动网页（`index.html`）。

视频需要被转换或提取为 WebP 图片序列帧，并以这些序列帧作为产品主体动画素材。

页面无需依赖任何外部大型 3D 引擎（如 Three.js）或动画库（如 GSAP），全部采用原生 HTML5 Canvas、CSS 3D Transforms 与原生 JavaScript 动力学算法实现，并能够自包含运行。

## 一、执行前必须确认的输入

开始制作之前，必须确认用户已经提供以下两项内容：

1. 产品名称
2. 产品拆解、爆炸、组装或结构变化的视频素材

产品名称用于：

- 理解产品类型与使用场景
- 生成与产品匹配的页面标题、说明文字和 HUD 内容
- 判断哪些产品信息适合出现在界面中
- 决定文案、参数和信息模块的表达方式

视频用于：

- 分析产品动画过程
- 提取连续序列帧
- 驱动滚轮控制的正向与反向逐帧动画
- 判断产品主体在不同阶段的位置、比例与变化过程

如果用户没有提供产品名称，必须先询问产品名称。

如果用户没有提供视频，必须先要求用户上传或提供视频。

如果两者均未提供，应同时询问：

- 要展示的产品是什么？
- 请提供对应的产品拆解 / 爆炸 / 结构动画视频。

在缺少产品名称或视频素材时，不要自行假设产品，也不要开始生成最终网页。

## 二、核心任务目标与全局视觉标准

### 1. 画幅与视口控制

- 页面采用固定全屏画幅：`100vw × 100vh`。
- 设置 `overflow: hidden;`，禁止出现浏览器原生垂直滚动条。
- 统一由 JavaScript 全局监听滚轮事件，驱动 Virtual Scroll，实现精准、平滑的逐帧动画往复控制。
- 不使用长页面滚动，不允许原生滚动与虚拟滚动同时存在。

### 2. 页面视觉基调

- 采用深色背景，突出中央产品主体。
- 页面视觉重点始终集中在产品及其结构变化上。
- 四周可以根据产品属性设计轻量 HUD、参数卡片或辅助信息。
- UI 应保持克制、透气，不要过度装饰或抢夺产品主体视觉。
- 页面中的文案、参数、标签和信息内容，应根据用户提供的具体产品自动生成，而不是预先写死。

### 3. Retina 与高分屏适配

- 全屏 Canvas 必须适配 `window.devicePixelRatio`。
- Canvas 物理尺寸根据 DPR 缩放，CSS 显示尺寸保持 100%。
- 确保在 2K、4K、Retina 屏幕上产品边缘保持清晰。
- 产品图片采用 `contain` 逻辑居中等比缩放，禁止拉伸、裁切或比例失真。

参考实现：

​```javascript
const rect = canvas.getBoundingClientRect();
const dpr = window.devicePixelRatio || 1;

canvas.width = rect.width * dpr;
canvas.height = rect.height * dpr;

ctx.setTransform(dpr, 0, 0, dpr, 0, 0);
```

## 三、界面空间布局规范

页面以中央产品主舞台为核心，四周布局轻量辅助信息。

实际显示的文字、参数、模块名称和信息内容，必须根据具体产品动态生成，不要使用固定产品示例。

### 1. 顶部导航栏 Header / Nav

- 位于页面顶部，可采用居中悬浮或左右通栏布局。
- 包含产品名称或型号。
- 可以包含当前页面功能、状态或展示模式。
- 状态标签采用轻量磨砂玻璃胶囊样式。
- 导航视觉应轻量，不遮挡产品主体。

具体文案应结合产品类型生成。

### 2. 左上角主视觉文案区

根据用户输入的产品生成：

- 产品名称
- 简短主标题
- 产品特征说明
- 当前结构阶段相关说明

要求：

- 主标题采用醒目的大字号排版。
- 副标题精致克制，避免过多文字。
- 可根据滚动阶段平滑淡出、切换或更新为对应结构或零部件说明。
- 文案变化应与当前动画阶段对应，不可频繁闪烁。
- 禁止预设与产品无关的广告语。

### 3. 右上角产品信息 HUD

根据具体产品选择合适的信息。

例如可以是：

- 材质
- 结构
- 尺寸
- 性能指标
- 传感器
- 功耗
- 重量
- 组件状态
- 产品相关技术参数

不要求每种产品都显示相同内容。

应先理解产品，再选择真正相关的信息。

### 4. 左下角交互模式动态指示器

整个左下角只允许存在一个操作指示卡片。

禁止：

- 并排多个提示框
- 上下堆叠多个操作提示
- 同时显示“鼠标随动”和“视差滚动”

#### 静止时完全隐藏

页面初始加载以及用户长时间没有操作时，操作卡片必须完全隐藏：

```css
opacity: 0;
visibility: hidden;
pointer-events: none;
```

只有用户产生鼠标移动或滚轮操作时才淡入。

停止操作后延时平滑淡出。

#### 鼠标移动状态

当用户晃动鼠标时，卡片只显示：

`鼠标随动`

说明文字：

`微晃鼠标，多维感知产品细节`

#### 滚轮状态

当用户滚动滚轮时，卡片立即切换为：

`视差滚动`

说明文字：

`滚动滚轮，往复查看结构变化`

#### 排版要求

- 模式名称使用约 20～24px 粗体。
- 不增加“当前操作模式”“操作提示”等多余小标题。
- 状态切换必须平滑，但内容严格互斥。

### 5. 右下角产品信息卡片

根据产品属性动态生成对应的信息模块。

可以包含：

- 模块标题
- 产品材质
- 型号
- 尺寸
- 结构名称
- 当前组件
- 关键参数

标题与右侧参数标签之间必须保留明显的视觉呼吸空间。

建议：

```css
display: flex;
align-items: center;
gap: 16px;
```

并确保：

```css
white-space: nowrap;
flex-shrink: 0;
```

禁止：

- 标题与参数标签粘连
- 容器过窄导致参数折行
- 参数胶囊被压缩变形
- 为了塞入内容而牺牲合理留白

## 四、核心动效系统

页面包含两套主要交互系统：

1. 滚轮驱动的视差走帧
2. 鼠标驱动的 3D 空间随动

两套系统共享同一个 `requestAnimationFrame` 主循环，但状态与目标值必须相互解耦，并建立严格的滚动压制机制。

## 五、滚轮驱动视差走帧

### 1. Virtual Scroll

监听全局 `wheel` 事件，将滚轮位移累加至虚拟滚动变量，再映射到图片序列帧。

目标帧范围：

```javascript
0 → N - 1
```

向下滚动：

播放视频序列的正向变化。

向上滚动：

反向播放，使产品结构恢复。

用户可以随时停止、回滚或反向操作。

### 2. 动力学平滑插值

滚轮事件只更新 `targetFrame`。

实际显示帧由 `requestAnimationFrame` 中的惯性插值决定：

```javascript
currentFrame += (targetFrame - currentFrame) * 0.09;
```

不要让滚轮事件直接硬切图片帧。

目标：

- 平滑
- 有惯性
- 不拖沓
- 不明显跳帧
- 可以停在任意中间阶段

## 六、视频序列帧处理与预加载

用户提供的视频需要先转换或提取为连续 WebP 图片序列。

要求：

- 保持视频原始时间顺序。
- 保持帧与帧之间动作连续。
- 根据视频长度合理控制帧数量。
- 不应为了减少资源而造成明显跳帧。
- 不应提取大量视觉完全重复的帧。

首屏启动时并发预加载全部 WebP 序列帧，并建立 Image 对象缓存池。

要求：

- 图片完全加载前显示加载进度。
- 不能在图片尚未准备完成时开始完整交互。
- 滚动过程中禁止出现白闪、黑闪或空白帧。

如果目标帧尚未加载完成：

- 保持上一张有效帧。
- 不清空 Canvas。
- 不绘制未准备好的 Image 对象。

加载完成后再平滑切换到目标帧。

## 七、Canvas 绘制

每次绘制：

1. 清理 Canvas。
2. 根据当前视口计算 `contain` 尺寸。
3. 保持原图比例。
4. 将产品居中绘制。
5. 不因窗口尺寸变化而拉伸。
6. Resize 后重新计算 Canvas 物理尺寸与 DPR。

如果不同视频帧本身存在尺寸或位置变化，应尽量通过统一绘制边界保持产品视觉中心稳定，避免序列播放时整体画面跳动。

## 八、3D 空间鼠标随动

鼠标随动必须拥有清晰可感知的空间变化。

建议最大幅度：

- RotateY：`±10° ～ ±14°`
- RotateX：`±8° ～ ±12°`
- RotateZ：`±2° ～ ±3°`
- TranslateX：`±30px ～ ±40px`
- TranslateY：`±30px ～ ±40px`

实际数值可根据产品形态、视频构图和画面比例调整。

## 九、非线性感知映射

禁止简单使用线性映射：

```javascript
x / width
```

因为鼠标在产品主体附近移动时，线性归一化值通常过小，会造成明显中心死区。

必须引入非线性幂函数曲线：

```javascript
const normX = ((e.clientX / window.innerWidth) - 0.5) * 2;
const normY = ((e.clientY / window.innerHeight) - 0.5) * 2;

const swayFactorX =
  Math.sign(normX) * Math.pow(Math.abs(normX), 0.72);

const swayFactorY =
  Math.sign(normY) * Math.pow(Math.abs(normY), 0.72);
```

幂指数建议：

```text
0.70 ～ 0.75
```

目标效果：

- 鼠标在产品周围轻微晃动即可产生明显变化。
- 中心区域不能出现明显死区。
- 鼠标移动到屏幕边缘时平滑收敛到最大角度。
- 不出现突变、过冲或边缘失控。

## 十、鼠标随动动力学

不要直接将鼠标坐标赋值给 CSS Transform。

分别维护：

```javascript
targetRotateX
targetRotateY
targetRotateZ
targetTranslateX
targetTranslateY
```

以及：

```javascript
currentRotateX
currentRotateY
currentRotateZ
currentTranslateX
currentTranslateY
```

在 `requestAnimationFrame` 中进行阻尼插值，使运动具有惯性。

正常鼠标随动阶段采用柔和阻尼，使产品移动自然，而不是机械跟手。

## 十一、滚动与鼠标随动的互斥压制机制

滚动序列动画和鼠标空间倾斜不能同时完整生效。

当产品结构正在变化时，如果画面仍保持较大的 3D 倾角，容易造成透视错位、结构重叠以及眩晕感。

### 1. 滚动触发

捕获 `wheel` 事件后：

```javascript
isScrolling = true;
```

同时：

- 停止更新新的鼠标随动目标。
- 将所有 Rotate / Translate 目标值设为 0。
- 进入 Pure Flat 纯平复位状态。

### 2. 快速压平

滚动状态下，将随动系统 Lerp 系数提高到：

```text
0.22 ～ 0.25
```

目标是在约：

```text
100ms ～ 150ms
```

内快速将以下数值恢复至接近 0：

- RotateX
- RotateY
- RotateZ
- TranslateX
- TranslateY

滚动走帧期间保持产品基本纯平。

### 3. 滚动结束后恢复随动

每次 `wheel` 事件重新启动结束计时器。

用户停止滚动约：

```text
400ms
```

后：

```javascript
isScrolling = false;
```

此后鼠标随动系统重新接管。

如果鼠标已经停留在某个位置，根据当前鼠标坐标重新计算目标倾角，并平滑进入对应视角。

禁止瞬间跳回之前的倾斜角度。

## 十二、交互状态与主循环架构

所有视觉动画统一由一个 `requestAnimationFrame` 主循环协调。

主循环负责：

```text
更新 currentFrame
更新 Rotate / Translate
判断滚动压制状态
绘制当前有效图片帧
更新 3D Transform
更新 HUD 状态
处理交互提示卡片淡入淡出
```

不要为不同动画建立大量互相竞争的 `setInterval` 或重复动画循环。

`setTimeout` 只用于：

- 滚动停止判断
- 操作提示卡片延时隐藏

核心画面更新统一通过 `requestAnimationFrame` 完成。

## 十三、加载阶段

资源未加载完成前显示全屏 Loading。

加载界面可以包含：

- 产品名称
- 加载百分比
- 简洁进度条
- 当前资源加载状态

文字根据用户输入的产品动态生成，不使用固定产品名称。

要求：

- 加载完成后平滑淡出。
- 不突然消失。
- 正式内容加载完成前不可闪出半成品画面。
- 第一帧准备完成后才进入主视觉。

## 十四、窗口 Resize 处理

监听：

```javascript
resize
```

重新计算：

- Canvas CSS 尺寸
- Canvas DPR 物理尺寸
- 图片 contain 尺寸
- 产品主舞台比例
- 3D Transform 中心
- HUD 安全边距

Resize 不得重置用户当前动画进度。

当前帧和当前虚拟滚动位置必须保持不变。

## 十五、视觉细节要求

### 1. HUD

HUD 可以使用：

- 半透明深色背景
- 轻微背景模糊
- 细边框
- 弱高光
- 克制阴影

具体视觉语言应结合产品特征调整。

避免为了科技感而强行加入大量霓虹、扫描线、乱码、无意义参数或装饰性数据。

### 2. 字体层级

优先采用系统无衬线字体栈：

```css
font-family:
  Inter,
  -apple-system,
  BlinkMacSystemFont,
  "SF Pro Display",
  "Segoe UI",
  sans-serif;
```

主标题、正文、参数和辅助信息需要建立明确层级。

### 3. 产品主体

产品始终是页面最主要的视觉元素。

HUD、文字和边框必须退居第二层级。

不要因为 UI 设计复杂而削弱视频序列本身。

## 十六、严格禁止事项

### 1. 禁止自行假设产品

没有产品名称时必须询问。

不得默认任何品牌、型号或产品类型。

### 2. 禁止缺少视频时自行伪造序列

没有用户提供的视频时必须要求用户提供。

不得自行生成虚构的视频序列代替用户素材。

### 3. 禁止写死产品文案

产品名称、标题、参数、HUD 和说明内容必须基于用户实际输入生成。

不得在通用模板中写死具体品牌、型号或产品参数。

### 4. 禁止中心死区

鼠标随动不得使用单纯线性坐标映射。

必须采用非线性幂函数曲线，提高中心区域灵敏度。

### 5. 禁止滚动期间残留明显倾角

滚轮触发后必须快速进入 Pure Flat 状态。

禁止一边保持明显 RotateX / RotateY，一边播放结构序列。

### 6. 禁止浏览器原生页面滚动

页面必须：

```css
html,
body {
  width: 100%;
  height: 100%;
  margin: 0;
  overflow: hidden;
}
```

不允许通过创建超长页面实现动画进度。

### 7. 禁止忽略高分屏

Canvas 必须适配 DPR。

禁止只设置：

```javascript
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;
```

而不处理高分屏缩放。

### 8. 禁止绘制未加载图片

所有图片必须经过加载状态检查。

目标帧未就绪时保持上一有效帧，不允许 Canvas 出现空白。

### 9. 禁止使用重量级外部依赖

不得引入：

- Three.js
- GSAP
- React
- Vue
- WebGL 框架
- 第三方滚动动画库
- 第三方动力学库
- 构建工具链

最终交付必须是单一：

```text
index.html
```

CSS 与 JavaScript 全部内联。

文件应可以直接通过浏览器打开运行。

## 十七、最终交付要求

只有在用户已经提供：

- 产品名称
- 产品视频

之后，才开始生成最终页面。

最终只交付一个：

```text
index.html
```

要求：

- HTML、CSS、JavaScript 全部位于单文件中。
- 代码结构清晰。
- 关键动力学参数集中定义，方便调整。
- 对 Virtual Scroll、视频序列帧、图片预加载、DPR、非线性 Mouse Sway、滚动压制机制等关键逻辑添加必要注释。
- 不引入任何外部大型依赖。
- 页面可以直接打开运行。
- 所有交互状态切换自然、稳定、无闪烁。
- 所有产品文案、HUD 内容与参数信息，都应根据用户输入的具体产品生成，而不是使用模板中的固定示例。
````

````