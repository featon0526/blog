---
title: "第4讲 Ai视频剪辑 & Skills"
nav_order: 4
date: 2026-09-22
layout: default
---

## 一、AI 口播剪辑工作流

### 口播粗剪

* **A-roll**：一条口播视频里，最核心的素材是 A-roll，也就是创作者本人出镜说话的主画面。内容讲什么，每一段持续多久，整期节奏如何推进，基本都由它决定。
* **B-roll**：产品录屏、MG 动画、图形组件和拼贴画面都属于 B-roll。它们跟随口播穿插出现，承担解释内容、丰富节奏和遮盖跳剪的任务。字幕、音乐和音效同样要对齐口播时间。

A-roll 中口误、长停顿、口头填充词和反复录制的片段还没清理完时（口播粗剪），提前制作 B-roll 会制造大量返工。口播长度每变化一次，下游素材的入点、出点和音乐节奏都要跟着移动。

#### 方案一：用 video-use skill

​[video-use](https://github.com/browser-use/video-use) 是 Browser Use 团队开源的视频编辑 Skill。它把逐字转写、剪辑策略、剪辑决策表和 FFmpeg 渲染串在一起，适合先验证 Agent 能把原始口播压缩到什么程度。

首次使用需要准备：

* 能调用终端的 Agent，例如 Codex 或 Claude Code。
* Python 环境，以及已加入系统路径的 ffmpeg 和 ffprobe。
* [ElevenLabs API Key](https://elevenlabs.io/app/developers/api-keys)。video-use 使用 Scribe 获取逐词起止时间、说话人和音频事件。
* 一份单独的素材目录。源文件保持不动，处理结果会进入目录下的 edit/。

最省事的安装方式，是打开项目主页，复制官方提供的安装提示词，交给 Codex 完成仓库克隆、依赖安装和 Skill 注册。

{% raw %}
```bash
et up https://github.com/browser-use/video-use for me.

Read install.md first to install this repo, wire up ffmpeg, register the skill with whichever agent you're running under, and set up the ElevenLabs API key — ask me to paste it when you need it. Then read SKILL.md for daily usage, and always read helpers/ because that's where the editing scripts live. After install, don't transcribe anything on your own — just tell me it's ready and wait for me to drop footage into a folder.
```
{% endraw %}

安装完成后，把原始口播和参考资料放进一个目录，在该目录启动 Agent，然后提出任务：

{% raw %}
```
$video-use @VID_20260716_183654.mp4 完成这条口播的粗剪
```
{% endraw %}

video-use 会先读取素材并生成逐词转写，再把准备保留的片段组织成 EDL，也就是剪辑决策表。确认策略后，它才会按词边界执行剪切、处理片段衔接并输出预览。

用一条 19 分 46 秒的科技口播做过测试。整个 Agent 流程大约执行 15 分钟，最终得到约 4 分钟的粗剪。原片中大量重复录制、口误和停顿都被清理掉，叙事主线也保留得比较完整。

video-use **交付的是渲染后的预览视频**。需要修改时，可以让 Agent 更新 EDL 后重新渲染；

如果你更习惯在剪辑软件里拖动切点、恢复片段，这种交付形态可能不太适合你。

#### 方案二：用 ChatCut

### HyperFrames 分镜

A-roll 锁定以后，下一份关键产物是带完整时间码的 SCRIPT.srt。它同时记录了“说了什么”和“这句话在第几秒出现”。

### 拼贴 B-roll

市面上成熟拼贴Skill

* [https://github.com/Alisa0808/vox-director](https://github.com/Alisa0808/vox-director)
* [https://github.com/CK42BB/vox-explainer-skill](https://github.com/CK42BB/vox-explainer-skill)
* [https://github.com/pyang5166/gbro-collage-broll](https://github.com/pyang5166/gbro-collage-broll)

Skill 只会询问两个基础选项：画幅选择 16:9 或 9:16，以及每条 B-roll 生成 1、2 或 3 张静帧候选。默认使用 openai/gpt-image-2 生成图片、bytedance/seedance-2.0-fast 生成 720p、5 秒的视频。

### Remotion 动画

​[Remotion](https://www.remotion.dev/) 使用 React 组件生成视频，适合制作章节标题、数据卡片、步骤条、交互演示和透明动画贴片。

直接用自然语言描述要做的动画。

HyperFrames 和 Remotion 的能力存在交集，可以按资产寿命分工：一次性的完整解释段落交给 HyperFrames，长期复用的频道动画交给 Remotion。生成式模型负责难以实拍的氛围与隐喻画面，真实界面继续使用录屏。


## 二、Skills

Skills 是一种把经验、流程、模板和判断标准沉淀给 AI Agent 使用的方法。它不是单纯的一段提示词，而是一套可复用的工作说明：什么时候触发、按什么步骤执行、需要读取哪些资料、输出什么结果、如何检查质量。

{% raw %}
```text
搜索：find skill
      ├── 内置skill
      ├── 外部skill
      └── 自创skill
安装：skill scanner
      ├── ~/.claude/skills/ → 全局可用（所有项目）
      └── 项目目录/.claude/skills/ → 局部可用（仅当前项目可用）
调用：\skillname
创建：create skill
```
{% endraw %}

### 什么是 Skills？

Skills 可以理解为给 Claude Code 准备的“专项工作说明书”。当用户的问题命中某个技能的使用场景时，Claude Code 会读取这个 Skill 的说明，并按照里面的流程完成任务。

它通常解决四类问题：

* 领域知识：比如代码审查标准、架构设计原则、内容写作规范。
* 流程自动化：比如 PR 检查、需求拆解、文档同步、故障排查。
* 上下文注入：只在需要时加载相关规则，避免每次都把全部背景塞进对话。
* 知识复用：让同一套方法在多次对话、多个人、多个项目里保持一致。

简单来说：**Prompt 是“一次性的指令”，Skill 是“可复用的能力包，以后同类任务都怎么做”。**

### Skills 和 MCP Servers 的区别

| **==对比项==** | **Skills**          | **==MCP Servers==** |
| ------------------------------------------------------- | ------------------- | --------------------------------------------------------------- |
| 主要用途                                                    | 提供知识、流程和行为约束        | 提供外部工具、数据和 API 能力                                               |
| 常见形式                                                    | Markdown 文档、模板、参考资料 | 可执行服务、工具接口                                                      |
| 影响方式                                                    | 指导 Claude 如何思考和行动   | 让 Claude 能调用新的工具                                                |
| 典型例子                                                    | 代码审查清单、写作规范、同步流程    | 数据库查询、浏览器控制、飞书 API                                              |

一个实用判断：

* 如果你要告诉 Agent “应该怎么做”，优先做 Skill。
* 如果你要让 Agent “能操作某个外部系统”，优先考虑 MCP 或工具。
* 如果一个工作既有流程又要调用外部系统，可以 Skill + MCP 组合使用。

### 一个 Skill 的基本结构

一个典型 Skill 通常放在项目或用户配置目录的 skills 目录下。最小结构如下：

{% raw %}
```
.claude/
└── skills/
    └── my-skill/
        └── SKILL.md
```
{% endraw %}

更完整的结构可以这样组织：

{% raw %}
```
.claude/
└── skills/
    └── my-skill/
        ├── SKILL.md
        ├── reference.md
        ├── templates/
        │   └── template.ts
        ├── scripts/
        │   └── validate.py
        └── config.json
```
{% endraw %}

各部分的作用：

* SKILL.md：主说明文件，必须存在。
* reference.md：放详细背景、标准、扩展说明。
* templates/：放可复用模板，比如代码模板、文档模板、配置模板。
* scripts/：放校验、转换、生成等辅助脚本。
* config.json：放结构化规则、枚举项、评分标准等数据。

### Skills 是怎么工作的？

可以把 Skill 的运行过程拆成三步：

**第一步：发现**

* Claude Code 扫描 skills 目录，识别包含 SKILL.md 的技能。

**第二步：触发**

* 当用户请求匹配 Skill 的描述、关键词或明确点名某个 Skill 时，加载对应说明。

**第三步：执行**

* Claude 按照 Skill 中的流程、约束、参考文件和脚本完成任务。

这意味着一个 Skill 的核心不是“写得多”，而是“触发清楚、流程明确、校验可执行”。

### 创建第一个 Skill

下面做一个最小可用 Skill，目标是让 Claude Code 帮你生成规范的提交信息。

#### 第一步：创建目录

{% raw %}
```bash
mkdir -p .claude/skills/commit-message
```
{% endraw %}

#### 第二步：创建 SKILL.md

{% raw %}
```markdown
# Commit Message

Generate clear and consistent Git commit messages.

## When to Use

Use this skill when:
- The user asks for a commit message.
- The user wants to summarize staged changes.
- The user uses the command `/commit-msg`.

## Process

1. Read the staged changes with `git diff --cached`.
2. Identify the main change type.
3. Choose a concise scope.
4. Write a subject line under 50 characters.
5. Add a body only when the change needs explanation.

## Output

Return one suggested commit message.
```
{% endraw %}

#### 第三步：测试 Skill

{% raw %}
```
Use the commit-message skill to help me write a commit message.
```
{% endraw %}

也可以在你的 Skill 里设计更明确的触发方式，比如：

{% raw %}
```
/commit-msg
```
{% endraw %}

一个最小 Skill 不需要复杂文件。只要能稳定告诉 Agent “什么时候用、怎么做、输出什么”，它就已经有价值。

### SKILL.md 应该包含什么

一个成熟的 SKILL.md 通常包含下面几类内容。

#### **（1）标题和描述**

标题要直接说明用途，描述要能让 Agent 判断是否该使用它。

{% raw %}
```markdown
# API Designer

Design RESTful APIs with consistent resources, request formats, error handling, and documentation.
```
{% endraw %}

#### **（2）When to Use**

这一节决定 Skill 能不能被正确触发。不要写得太泛，要写具体场景。

{% raw %}
```markdown
## When to Use

Use this skill when:
- The user asks to design API endpoints.
- The user wants to review REST API structure.
- The user needs an OpenAPI draft.
```
{% endraw %}

#### **（3）Capabilities**

说明这个 Skill 能做什么，也能帮你控制边界。

{% raw %}
```markdown
## Capabilities

- Design endpoint structure.
- Define request and response formats.
- Create error response conventions.
- Produce API documentation outlines.
```
{% endraw %}

#### **（4）Process**

把任务拆成明确步骤。步骤越清楚，Agent 越不容易跑偏。

{% raw %}
```markdown
## Process

Clarify the target resource and user goal.
List required operations.
Design endpoint paths and HTTP methods.
Define request and response bodies.
Check naming, pagination, errors, and versioning.
Output Format
```
{% endraw %}

#### **（5）Output Format**

明确最终交付格式，避免 Agent 输出一堆散乱解释。

{% raw %}
```markdown
## Output Format

Return:
- Endpoint list.
- Request and response examples.
- Error catalog.
- Open questions.
```
{% endraw %}

#### **（6）Examples**

示例会显著提升 Skill 的稳定性，尤其适合复杂任务。

{% raw %}
```markdown
## Examples

User: Design an API for managing users.

Output:
- GET /users
- POST /users
- GET /users/{id}
- PUT /users/{id}
- DELETE /users/{id}
```
{% endraw %}

### 什么时候需要支持文件

不是每个 Skill 都需要额外文件。判断标准是：主说明文件是否已经太长，或者是否存在需要复用的资料。

#### **参考文档**

如果有大量背景知识、规范细则、案例解释，可以放到 reference.md。

{% raw %}
```
my-skill/
├── SKILL.md
└── reference.md
```
{% endraw %}

在 SKILL.md 中只保留核心流程：

{% raw %}
```markdown
For detailed rules, read `reference.md` when needed.
```
{% endraw %}

#### **模板文件**

如果输出内容有固定结构，可以放到 templates/。

{% raw %}
```
my-skill/
├── SKILL.md
└── templates/
    └── component.tsx
```
{% endraw %}

适用场景：

* 代码组件模板
* PR 描述模板
* API 文档模板
* 周报、复盘、方案模板

#### **配置数据**

如果规则是结构化的，放 JSON 更适合。

{% raw %}
```json
{
  "rules": [
    {
      "name": "no-empty-error-handling",
      "severity": "error"
    }
  ]
}
```
{% endraw %}

适用场景：

* 检查清单
* 分类规则
* 评分权重
* 可选策略列表

#### **辅助脚本**

当某些步骤必须稳定执行，不适合靠自然语言描述时，可以加脚本。

{% raw %}
```python
def validate(data):
    """Validate output according to skill rules."""
    return True
```
{% endraw %}

适用场景：

* 校验 Markdown 格式
* 扫描代码质量
* 生成目录
* 转换文件格式
* 检查是否遗漏字段

### 高级写法

#### **多阶段工作流**

复杂任务不要只写一串步骤，可以拆成阶段。

{% raw %}
```markdown
## Workflow

### Phase 1: Discovery
1. Understand the request.
2. Gather project context.
3. Identify constraints.

### Phase 2: Design
1. Draft the approach.
2. Validate against local patterns.
3. Surface tradeoffs.

### Phase 3: Implementation
1. Make scoped changes.
2. Run verification.
3. Report results.
```
{% endraw %}

#### **决策树**

当不同场景需要不同处理路径时，可以写决策规则。

{% raw %}
```markdown
## Language-Specific Rules

### If TypeScript
- Prefer explicit types for public APIs.
- Keep runtime validation near boundaries.

### If Python
- Use type hints.
- Prefer dataclasses for structured data.

### If Go
- Handle errors explicitly.
- Pass context through I/O boundaries.
```
{% endraw %}

#### **与其他 Skills 配合**

有些 Skill 适合作为主流程，有些适合作为校验流程。

{% raw %}
```markdown
## Related Skills

After implementation:
- Use `code-reviewer` to check regressions.
- Use `test-writer` if behavior changed.
```
{% endraw %}

#### **用户确认点**

如果任务风险较高，可以明确哪些节点需要停下来确认。

{% raw %}
```markdown
## Checkpoints

Pause for confirmation:
1. Before deleting or overwriting files.
2. Before changing public API behavior.
3. Before publishing external-facing content.
```
{% endraw %}

### 最佳实践

#### **推荐做法**

* 写清楚触发条件，不要只写“当需要时使用”。
* 把流程拆成可执行步骤。
* 给出输入输出示例。
* 写明不该做什么，避免越界。
* 保留验证步骤，让结果可检查。
* 把长背景放到参考文件，不要塞满 SKILL.md。

#### **避免做法**

* 不要写“请做好”“请专业一点”这种无法执行的要求。
* 不要把一个 Skill 做成万能工具。
* 不要假设 Agent 已经知道你的业务背景。
* 不要缺少失败处理和验收标准。
* 不要把临时经验写成永久规则，除非它经过验证。

#### **命名建议**

Skill 目录名建议使用小写加连字符：

{% raw %}
```text
skills/
├── code-reviewer/
├── system-architect/
├── api-generator/
└── test-writer/
```
{% endraw %}

一个好名字应该具备三个特征：

* 能看出用途。
* 不依赖内部黑话。
* 不和其他 Skill 混淆。

### 示例一：提交信息生成器

{% raw %}
```markdown
# Commit Message Generator

Generate consistent, descriptive commit messages.

## When to Use

Use this skill when:
- The user asks for commit message help.
- The user uses `/commit-msg`.

## Format

type(scope): subject

body

footer

## Types

- feat: new feature
- fix: bug fix
- docs: documentation
- style: formatting
- refactor: code restructuring
- test: adding tests
- chore: maintenance

## Process

1. Analyze staged changes with `git diff --cached`.
2. Identify the primary change type.
3. Determine the affected scope.
4. Write a concise subject.
5. Add a body only if the change needs explanation.
```
{% endraw %}

输出示例：

{% raw %}
```text
feat(auth): add OAuth2 login support

Implement OAuth2 flow with Google and GitHub providers.
Includes token refresh and session management.
```
{% endraw %}

### 示例二：API 设计师

{% raw %}
```markdown
# API Designer

Design RESTful APIs following practical engineering standards.

## When to Use

Use this skill when:
- Designing new API endpoints.
- Reviewing API design.
- Creating API documentation.

## Capabilities

- Endpoint structure.
- Request and response formats.
- Error handling.
- Versioning strategy.
- Documentation outline.

## Process

1. Gather resource entities and operations.
2. Design endpoint paths.
3. Choose HTTP methods.
4. Define request and response schemas.
5. Check pagination, errors, authentication, and versioning.
6. Produce examples.

## Output

Return:
1. Endpoint list.
2. Request examples.
3. Response examples.
4. Error catalog.
5. Open questions.
```
{% endraw %}

API 路径示例：

{% raw %}
```text
GET    /users
POST   /users
GET    /users/{id}
PUT    /users/{id}
DELETE /users/{id}
```
{% endraw %}

错误响应示例：

{% raw %}
```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Human readable message",
    "details": [
      {
        "field": "email",
        "message": "Invalid format"
      }
    ]
  }
}
```
{% endraw %}

### 常见问题排查

#### **Skill 没有加载**

检查：

* 是否放在正确的 skills 目录下。
* 目录里是否存在 SKILL.md。
* 文件名大小写是否正确。
* Markdown 是否存在明显语法错误。

#### **Skill 没有触发**

检查：

* When to Use 是否太模糊。
* 是否缺少明确关键词。
* 是否需要添加命令式触发方式。
* Skill 描述是否能覆盖用户真实说法。

#### **输出不稳定**

改进方式：

* 增加示例。
* 写清楚边界条件。
* 明确输出格式。
* 加入验证步骤。
* 把复杂规则拆到参考文件。

### 最小可用模板

如果你只想快速开始，可以直接使用这个模板：

{% raw %}
```markdown
# Skill Name

One-line description of what this skill does.

## When to Use

Use this skill when:
- Trigger condition 1.
- Trigger condition 2.

## Process

1. Step one.
2. Step two.
3. Step three.

## Output

Describe the expected output format.

## Verification

Check:
- Requirement A is satisfied.
- Requirement B is satisfied.
- No unrelated changes are introduced.
```
{% endraw %}

### 完整 Skill 的推荐结构

{% raw %}
```text
skill-name/
├── SKILL.md
├── references/
│   └── workflow.md
├── templates/
│   └── output-template.md
├── scripts/
│   └── validate.py
└── config.json
```
{% endraw %}

推荐拆分方式：

* SKILL.md 只放核心触发、流程、约束和验证。
* references/ 放详细解释和背景资料。
* templates/ 放可复用输出样式。
* scripts/ 放稳定执行的自动化动作。
* config.json 放结构化规则。

### 练习：设计你自己的第一个 Skill

可以按下面问题设计：

1. 这个 Skill 解决什么重复任务？
2. 用户通常会怎么提出这个需求？
3. Agent 第一步应该做什么？
4. 哪些动作不能自动做，必须确认？
5. 最终输出应该长什么样？
6. 怎么判断它做对了？

建议先从一个小任务开始，比如：

* 写周报。
* 生成提交信息。
* 审查 PR（**Pull Request**）。
* 整理会议纪要。
* 生成文章标题。
* 检查飞书文档是否有遗漏。

不要一开始就做万能 Skill。一个真正好用的 Skill，通常来自一个边界清楚、经常重复、结果可检查的工作流。

### 一句话总结

Prompt 是临时指令，Skill 是可复用流程。把高频、稳定、可检查的工作做成 Skill，就能让 AI Agent 不只是在“回答问题”，而是在持续复用你的方法。

### 三、作业提交

1. 注册Github账号（your-username）和cloudeflare
2. steam++，加速Github访问
3. 创建your-username.github.io仓库（pubilc）
4. 安装ngnix，本地发布（测试网站）
5. 上传网页与视频，复制网址
6. 填写作业表单，**作业发布后的链接地址**
7. 命名规范：
   1. 大目录命名：学号姓名（如，2025106001张三）
   2. 作业目录命名：第一次作业（如，Assignment1）

{% raw %}
```
2025106001张三/
└── Assignment1/
    ├── images/
    ├── mp4/
        
    ├── mp3/
    ├── css/
    ├── js/
    └── index.html
├── Assignment2/
├── Assignment3/
├── Assignment4/

└── Assignment5/
```
{% endraw %}

8. 首页（index.html）内容：如，作业一
   1. 选题
   2. 策划
   3. 文案
   4. 素材
   5. 方法
   6. 工具
   7. 视频
   8. 总结

​
