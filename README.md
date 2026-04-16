# AI Daily Blog

从 Karpathy 推荐的 92 个顶级技术博客中抓取 RSS 源，由 AI 生成每日精选摘要日报。

## 特性

- **零依赖**: 使用 Node.js 原生 API，无需安装任何第三方包
- **多源聚合**: 覆盖 92 个顶级技术博客（Simon Willison、Paul Graham、geohot 等）
- **并发抓取**: 10 路并发，最短时间内获取最多内容
- **格式兼容**: 支持 RSS 2.0 和 Atom 两种主流格式
- **AI 驱动**: 利用 AI 理解文章内容，生成结构化摘要

## 目录结构

```
AI-Daily-Blog/
├── scripts/
│   └── rss-fetcher.ts    # RSS 抓取脚本
├── prompts/
│   └── digest-prompt.md  # AI 日报生成 Prompt
├── SKILL.md              # Claude Code Skill 配置
└── README.md
```

## 快速开始

### 前置要求

- Node.js 18+
- 支持 ES Modules 的运行环境（如 Claude Code）

### 获取文章列表

```bash
npx tsx scripts/rss-fetcher.ts --hours 48
```

参数说明：
- `--hours 48`: 抓取最近 48 小时内发布的文章（默认值为 48）

输出示例：
```json
{
  "sourceCount": 92,
  "totalArticles": 2488,
  "filteredArticles": 309,
  "timeWindow": 48,
  "articles": [...]
}
```

### 生成日报

将 `rss-fetcher.ts` 的输出作为输入，结合 `prompts/digest-prompt.md` 中的指令，让 AI 生成结构化日报。

## 输出文件

每天生成一个以日期命名的文件夹：

```
YYYY-MM-DD-AI-Daily-Blog/
├── AI-Daily-Blog-Summary.md   # 今日看点、数据概览、分类文章列表
└── AI-Daily-Blog-Top.md       # 今日必读 Top 3 完整正文
```

### AI-Daily-Blog-Summary.md

包含：
- **今日看点**: 3-5 句宏观趋势总结
- **数据概览**: 扫描源数、抓取文章数等统计
- **今日必读 Top 3**: 每篇包含推荐理由和关键词
- **分类文章列表**: 按 AI/机器学习、科技/技术、工具/开源、观点/杂谈 四个类别组织

### AI-Daily-Blog-Top.md

包含今日最重要的 3 篇文章的完整中文翻译，保持原文结构，包含所有图片引用。

## 技术细节

- **RSS 源数量**: 92 个
- **并发数**: 10 路
- **请求超时**: 15 秒
- **支持格式**: RSS 2.0, Atom
- **时间窗口**: 可配置（默认 48 小时）

## 集成 Claude Code

将 `SKILL.md` 和相关文件放入 Claude Code 的 skills 目录即可使用。

在 Claude Code 中输入 `AI每日Blog` 即可触发。

## RSS 源列表

本项目使用 Karpathy 推荐的 92 个顶级技术博客作为 RSS 源，包括但不限于：

- simonwillison.net
- paulgraham.com
- geohot.github.io
- krebsonsecurity.com
- daringfireball.net
- mitchellh.com
- overreacted.io
- 等等...

详见 `scripts/rss-fetcher.ts` 中的完整列表。

## License

MIT
