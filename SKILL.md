---
name: AI-Daily-Blog
description: "从 Karpathy 推荐的 92 个技术博客抓取 RSS，生成 AI 精选摘要日报。不需要 API Key。当用户输入中包含"AI每日Blog"时触发。"
---

# AI Daily Blog

从 Karpathy 推荐的 92 个顶级技术博客中抓取最新文章，由 AI 直接生成每日精选摘要日报。

## 触发条件

当用户输入中包含"**AI每日Blog**"时触发此 Skill。

## 工作流程

```
1. 执行 rss-fetcher.ts 抓取 RSS 源
2. 接收 JSON 格式的文章列表
3. AI 根据 digest-prompt.md 生成结构化摘要
4. AI 生成 Markdown 报告并保存到输出目录
```

## 执行命令

```bash
npx tsx scripts/rss-fetcher.ts --hours 48
```

## 输出目录结构

每天生成一个独立文件夹，命名格式：`YYYY-MM-DD-AI-Daily-Blog`

```
AI_Daily_Blog/
└── 2026-04-16-AI-Daily-Blog/
    ├── AI-Daily-Blog-Summary.md   # 今日看点、数据概览、分类文章列表
    └── AI-Daily-Blog-Top.md       # 今日必读 Top 3 详细摘要
```

## 文件规范

### AI-Daily-Blog-Summary.md

```markdown
# AI Daily Blog - YYYY-MM-DD

> 基于 Karpathy 推荐的 92 个顶级技术博客，AI 精选摘要

## 📝 今日看点
[3-5 句宏观趋势总结]

## 📊 数据概览
| 指标 | 数值 |
|------|------|
| 扫描源数 | 92 |
| 抓取文章 | X 篇 |
| 精选文章 | X 篇 |

## 📚 分类文章列表

### 🤖 AI / 机器学习
1. [**中文标题**](完整URL)
   - 来源: 来源名 | 相对时间
   - 简要摘要（1-2 句）
   - 关键词: `标签1` `标签2`

### 💻 科技 / 技术
[同上格式]

### 🔧 工具 / 开源
[同上格式]

### 💭 观点 / 杂谈
[同上格式]
```

### AI-Daily-Blog-Top.md

```markdown
# AI Daily Blog 今日必读 Top 3 - YYYY-MM-DD

> 每日精选 3 篇最重要文章，附完整正文中文翻译

---

## 1. [中文标题](完整URL)

**推荐理由**：一句话推荐理由

**来源**: 来源名

**发布时间**: YYYY-MM-DD

---

### 完整正文

[原文完整中文翻译，保持原文段落结构、分隔线、换行]

[图片引用：如果原文有图片，在原文对应位置插入 Markdown 图片链接，URL 必须是完整可访问的绝对地址]

---

## 2. [中文标题](完整URL)
...

## 3. [中文标题](完整URL)
...
```

**格式规范**：
- **所有链接必须为完整的可跳转 URL**，格式：`[标题](URL)`
- 分类文章列表中每个条目都必须是完整的 Markdown 链接
- 今日必读 Top 3 必须包含推荐理由
- **Summary 中的 Top 3 摘要包含关键词，Top 中的正文不包含关键词**
- Top 正文内容必须与原文结构一致，包含所有图片的完整 URL
- 使用中文标点符号，标题使用 Markdown 语法

## 技术细节

- 使用 Node.js 原生 API（**零第三方依赖**）
- 并发抓取 92 个 RSS 源（10 路并发）
- 支持 RSS 2.0 和 Atom 格式
- 默认时间窗口：48 小时
- 输出 JSON 格式文章列表供 AI 处理
