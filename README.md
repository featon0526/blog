# 新媒体交互设计 · 课程讲义

《新媒体交互设计》全套课程讲义的静态网站源码，使用 **Jekyll + just-the-docs** 构建，发布于 GitHub Pages：

**🌐 线上地址：** https://featon0526.github.io/blog/

## 内容

| 讲次 | 标题 | 文件 |
|------|------|------|
| 第1讲 | 课程介绍 | `docs/01-course-intro.md` |
| 第2讲 | 音视频制作 | `docs/02-audio-video.md` |
| 第3讲 | Agent 基础知识 | `docs/03-agent-basics.md` |
| 第4讲 | AI 视频剪辑 & Skills | `docs/04-ai-video-skills.md` |
| 第5讲 | WorkBuddy 使用指南 | `docs/05-workbuddy-guide.md` |
| 第6讲 | 案例讲解 | `docs/06-case-study.md` |
| 第7讲 | 互联网发展史 | `docs/07-internet-history.md` |
| 第8讲 | Markdown | `docs/08-markdown.md` |

## 目录结构

```
.
├── _config.yml            # 站点配置（标题/baseurl/主题/搜索）
├── Gemfile                # Ruby 依赖
├── index.md               # 落地页
├── docs/                  # 各讲讲义（带 front matter）
├── assets/img/            # 全部配图（原 attachment/ 迁移而来）
├── .github/workflows/     # GitHub Actions 自动构建部署
└── .archive/              # 原始笔记备份（不入库）
```

## 本地预览（可选）

需要 Ruby 3.x：

```bash
bundle install
bundle exec jekyll serve --baseurl "/blog"
# 浏览器打开 http://localhost:4000/blog/
```

## 部署

推送 `main` 分支即触发 `.github/workflows/deploy.yml` 自动构建并发布到 GitHub Pages。
首次部署需在仓库 **Settings → Pages → Source** 选择 **GitHub Actions**。

## 如何新增一讲

1. 在 `docs/` 下新建 `NN-topic-slug.md`，头部写：

   ```yaml
   ---
   title: "第N讲 标题"
   nav_order: N
   permalink: /NN-topic-slug/     # ← 决定线上地址，务必写，且与文件名一致
   date: 2026-01-01
   layout: default
   ---
   ```

2. 在 `index.md` 的「课程目录」里补一条：`[第N讲 标题]({{ site.baseurl }}/NN-topic-slug/)`。
3. 配图放入 `assets/img/`，正文中用 `![]({{ site.baseurl }}/assets/img/xxx.webp)` 引用。
4. 提交并推送，`nav_order` 决定侧边栏顺序。

> **URL 约定**：每讲的线上地址由该篇 front matter 里的 `permalink` 决定，例如
> `permalink: /01-course-intro/` → `https://featon0526.github.io/blog/01-course-intro/`。
> 文件名、`permalink`、`index.md` 里的链接三者要保持一致。
>
> ⚠️ 仅在 `_config.yml` 的 `collections.docs` 里写 `permalink` 是**不生效**的
> （实测该集合级模板会被 Jekyll 忽略、回退成默认的 `/docs/xx.html`），必须逐篇写在 front matter 里。

## 已知事项

- 第7讲原有 19 张腾讯云带签名图床图，源链接已失效（403），目前保留外链，显示不出来的需重新上传到 `assets/img/` 后替换引用。
- 仓库已通过 `.gitignore` 排除 `.workbuddy/`、`.archive/` 等个人/临时文件。
