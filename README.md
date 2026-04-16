<div align="center">


# 🤖 AI Daily Blog

> 从 Karpathy 推荐的 92 个顶级技术博客中抓取 RSS 源，由 AI 生成每日精选摘要日报

![Node.js Version](https://img.shields.io/badge/node-%3E%3D%2018.0.0-brightgreen.svg)
![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)
![RSS Sources](https://img.shields.io/badge/RSS%20Sources-92-blue.svg)
![Pure Node.js](https://img.shields.io/badge/Pure%20Node.js-Zero%20Deps-green.svg)
![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-orange.svg)

<img width="516" height="273" alt="image" src="https://github.com/user-attachments/assets/1366843f-139d-45b0-8462-b3ae26171070" />

</div>

---

## 📋 目录

- [🚀 特性](#-特性)
- [⚡ 快速开始](#️-快速开始)
- [🔄 工作流程](#-工作流程)
- [📄 输出文件](#-输出文件)
- [⚙️ 技术细节](#️-技术细节)
- [💻 集成 Claude Code](#-集成-claude-code)
- [📁 项目结构](#-项目结构)
- [📚 RSS 源列表](#-rss-源列表)
- [🔧 故障排除](#️-故障排除)

---

## 🚀 特性

| ✨ 特性         | 📖 说明                                      |
| -------------- | ------------------------------------------- |
| 🔌 **零依赖**   | 使用 Node.js 原生 API，无需安装任何第三方包 |
| 🌐 **多源聚合** | 覆盖 92 个顶级技术博客                      |
| ⚡ **并发抓取** | 10 路并发，最短时间内获取最多内容           |
| 📡 **格式兼容** | 支持 RSS 2.0 和 Atom 两种主流格式           |
| 🤖 **AI 驱动**  | 利用 AI 理解文章内容，生成结构化摘要        |

---

## ⚡ 快速开始

### 📌 一键安装

```bash
# 方法一：git clone
git clone https://github.com/Xiaooooo434680/AI-Daily-Blog.git
cd AI-Daily-Blog

# 方法二：直接使用 npx（无需安装）
npx tsx https://raw.githubusercontent.com/Xiaooooo434680/AI-Daily-Blog/main/scripts/rss-fetcher.ts --hours 48
```

### 🎯 运行

```bash
npx tsx scripts/rss-fetcher.ts --hours 48
```

### 📊 参数说明

| 参数         | 说明                         | 默认值 |
| ------------ | ---------------------------- | ------ |
| `--hours 48` | 抓取最近 48 小时内发布的文章 | 48     |

### 📦 输出示例

<img width="713" height="496" alt="image" src="https://github.com/user-attachments/assets/ef88d3af-76ff-430a-9809-60fa4cefbbea" />


### 🤝 生成日报

将 `rss-fetcher.ts` 的输出 JSON 作为输入，结合 `prompts/digest-prompt.md` 中的指令，让 AI 生成结构化日报。

---

## 🔄 工作流程

```
┌─────────────────────────────────────────────────────────────┐
│                    🤖 AI Daily Blog 工作流程                 │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│   1️⃣  执行 rss-fetcher.ts 抓取 RSS 源                        │
│       ⬇️                                                     │
│   2️⃣  获取 JSON 格式的文章列表                               │
│       ⬇️                                                     │
│   3️⃣  将 JSON 交给 AI（结合 digest-prompt.md）               │
│       ⬇️                                                     │
│   4️⃣  AI 生成 Markdown 报告                                 │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📄 输出文件

每天生成一个以日期命名的文件夹：

```
📂 YYYY-MM-DD-AI-Daily-Blog/
├── 📝 AI-Daily-Blog-Summary.md   # 今日看点、数据概览、分类文章列表
└── 📰 AI-Daily-Blog-Top.md       # 今日必读 Top 3 完整正文
```

### 📝 AI-Daily-Blog-Summary.md

包含：

| 📌 部分               | 📖 说明                             |
| -------------------- | ---------------------------------- |
| **📈 今日看点**       | 3-5 句宏观趋势总结                 |
| **📊 数据概览**       | 扫描源数、抓取文章数等统计         |
| **🏆 今日必读 Top 3** | 每篇包含推荐理由、来源时间和关键词 |
| **📚 分类文章列表**   | 按四个类别组织                     |

**示例：**

```markdown
## 🏆 今日必读 Top 3

1. [**文章标题**](https://example.com/article)
   - ✅ 推荐理由：一句话推荐
   - 📍 来源: 博客名 | 2026-04-16
   - 🏷️ 关键词: `AI` `机器学习`
```

### 📰 AI-Daily-Blog-Top.md

包含今日最重要的 3 篇文章的**完整中文翻译**，保持原文结构，包含所有图片引用。

---

## ⚙️ 技术细节

| 🔧 指标       | 📊 值                       |
| ------------ | -------------------------- |
| 📡 RSS 源数量 | 92 个                      |
| ⚡ 并发数     | 10 路                      |
| ⏱️ 请求超时   | 15 秒                      |
| 📡 支持格式   | RSS 2.0, Atom              |
| ⏰ 时间窗口   | 可配置（默认 48 小时）     |
| 📦 依赖       | 零第三方依赖（纯 Node.js） |

---

## 💻 集成 Claude Code

### 📥 一键安装

在 Claude Code 中运行：

```bash
# 克隆到 skills 目录
git clone https://github.com/Xiaooooo434680/AI-Daily-Blog.git ~/.claude/skills/ai-daily-blog
```

### 🎮 使用

在 Claude Code 中输入 **`AI每日Blog`** 即可触发。

---

## 📁 项目结构

```
📂 AI-Daily-Blog/
├── 📄 README.md              # 本文件
├── 📄 package.json           # npm 配置
├── 📄 SKILL.md              # Claude Code Skill 配置
├── 📂 scripts/
│   └── 📜 rss-fetcher.ts    # RSS 抓取脚本
└── 📂 prompts/
    └── 📄 digest-prompt.md  # AI 日报生成 Prompt
```

---

## 📚 RSS 源列表

本项目使用 Karpathy 推荐的 92 个顶级技术博客，包括但不限于：

### 🤖 AI / 技术博客

- 🔗 simonwillison.net
- 🔗 Gary Marcus (garymarcus.substack.com)
- 🔗 overreacted.io
- 🔗 gwern.net

### 💻 黑客 / 开发者博客

- 🔗 geohot.github.io
- 🔗 antirez.com
- 🔗 mitchellh.com
- 🔗 matklad.github.io

### 🔒 安全博客

- 🔗 krebsonsecurity.com
- 🔗 troyhunt.com
- 🔗 diversifier.it

### 📱 科技评论

- 🔗 daringfireball.net
- 🔗 paulgraham.com
- 🔗 blog.jim-nielsen.com

### 📌 更多源

详见 `scripts/rss-fetcher.ts` 中的 `FEEDS` 数组

---

## 🔧 故障排除

### ❌ 抓取失败

```bash
# 检查超时设置
# 默认超时 15 秒，某些慢速站点可能需要增加

# 查看详细错误输出
npx tsx scripts/rss-fetcher.ts --hours 48 2>&1
```

### ❌ Node.js 版本问题

```bash
# 确保使用 Node.js 18+
node --version

# 如需更新 Node.js，推荐使用 nvm
nvm install 18
nvm use 18
```

### ❌ 输出为空

- ✅ 检查时间窗口是否正确（默认 48 小时）
- ✅ 确认 RSS 源是否可访问：`curl -I <rss-url>`
- ✅ 部分博客可能有反爬限制

---

## 📜 License

MIT

---

> ⭐ 如果这个项目对您有帮助，请给个 Star！| ------------ | ---------------------------- | ------ |
| `--hours 48` | 抓取最近 48 小时内发布的文章 | 48     |

### 📦 输出示例

```json
{
  "sourceCount": 92,
  "totalArticles": 2488,
  "filteredArticles": 309,
  "timeWindow": 48,
  "articles": [
    {
      "title": "文章标题",
      "link": "https://...",
      "source": "博客名",
      "published": "2026-04-16T10:00:00.000Z",
      "summary": "文章摘要..."
    }
  ]
}
```

### 🤝 生成日报

将 `rss-fetcher.ts` 的输出 JSON 作为输入，结合 `prompts/digest-prompt.md` 中的指令，让 AI 生成结构化日报。

---

## 🔄 工作流程

```
┌─────────────────────────────────────────────────────────────┐
│                    🤖 AI Daily Blog 工作流程                 │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│   1️⃣  执行 rss-fetcher.ts 抓取 RSS 源                        │
│       ⬇️                                                     │
│   2️⃣  获取 JSON 格式的文章列表                               │
│       ⬇️                                                     │
│   3️⃣  将 JSON 交给 AI（结合 digest-prompt.md）               │
│       ⬇️                                                     │
│   4️⃣  AI 生成 Markdown 报告                                 │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📄 输出文件

每天生成一个以日期命名的文件夹：

```
📂 YYYY-MM-DD-AI-Daily-Blog/
├── 📝 AI-Daily-Blog-Summary.md   # 今日看点、数据概览、分类文章列表
└── 📰 AI-Daily-Blog-Top.md       # 今日必读 Top 3 完整正文
```

### 📝 AI-Daily-Blog-Summary.md

包含：

| 📌 部分               | 📖 说明                             |
| -------------------- | ---------------------------------- |
| **📈 今日看点**       | 3-5 句宏观趋势总结                 |
| **📊 数据概览**       | 扫描源数、抓取文章数等统计         |
| **🏆 今日必读 Top 3** | 每篇包含推荐理由、来源时间和关键词 |
| **📚 分类文章列表**   | 按四个类别组织                     |

**示例：**

```markdown
## 🏆 今日必读 Top 3

1. [**文章标题**](https://example.com/article)
   - ✅ 推荐理由：一句话推荐
   - 📍 来源: 博客名 | 2026-04-16
   - 🏷️ 关键词: `AI` `机器学习`
```

### 📰 AI-Daily-Blog-Top.md

包含今日最重要的 3 篇文章的**完整中文翻译**，保持原文结构，包含所有图片引用。

---

## ⚙️ 技术细节

| 🔧 指标       | 📊 值                       |
| ------------ | -------------------------- |
| 📡 RSS 源数量 | 92 个                      |
| ⚡ 并发数     | 10 路                      |
| ⏱️ 请求超时   | 15 秒                      |
| 📡 支持格式   | RSS 2.0, Atom              |
| ⏰ 时间窗口   | 可配置（默认 48 小时）     |
| 📦 依赖       | 零第三方依赖（纯 Node.js） |

---

## 💻 集成 Claude Code

### 📥 安装

1. 将 `SKILL.md` 放入 Claude Code 的 skills 目录
2. 将 `scripts/` 和 `prompts/` 目录一起放入

```
📂 ~/.claude/skills/ai-daily-blog/
├── 📄 SKILL.md
├── 📂 scripts/
│   └── 📜 rss-fetcher.ts
└── 📂 prompts/
    └── 📄 digest-prompt.md
```

### 🎮 使用

在 Claude Code 中输入 **`AI每日Blog`** 即可触发。

---

## 📁 项目结构

```
📂 AI-Daily-Blog/
├── 📄 README.md              # 本文件
├── 📄 package.json           # npm 配置
├── 📄 SKILL.md              # Claude Code Skill 配置
├── 📂 scripts/
│   └── 📜 rss-fetcher.ts    # RSS 抓取脚本
└── 📂 prompts/
    └── 📄 digest-prompt.md  # AI 日报生成 Prompt
```

---

## 📚 RSS 源列表

本项目使用 Karpathy 推荐的 92 个顶级技术博客，包括但不限于：

### 🤖 AI / 技术博客

- 🔗 simonwillison.net
- 🔗 Gary Marcus (garymarcus.substack.com)
- 🔗 overreacted.io
- 🔗 gwern.net

### 💻 黑客 / 开发者博客

- 🔗 geohot.github.io
- 🔗 antirez.com
- 🔗 mitchellh.com
- 🔗 matklad.github.io

### 🔒 安全博客

- 🔗 krebsonsecurity.com
- 🔗 troyhunt.com
- 🔗 diversifier.it

### 📱 科技评论

- 🔗 daringfireball.net
- 🔗 paulgraham.com
- 🔗 blog.jim-nielsen.com

### 📌 更多源

详见 `scripts/rss-fetcher.ts` 中的 `FEEDS` 数组

---

## 🔧 故障排除

### ❌ 抓取失败

```bash
# 检查超时设置
# 默认超时 15 秒，某些慢速站点可能需要增加

# 查看详细错误输出
npx tsx scripts/rss-fetcher.ts --hours 48 2>&1
```

### ❌ Node.js 版本问题

```bash
# 确保使用 Node.js 18+
node --version

# 如需更新 Node.js，推荐使用 nvm
nvm install 18
nvm use 18
```

### ❌ 输出为空

- ✅ 检查时间窗口是否正确（默认 48 小时）
- ✅ 确认 RSS 源是否可访问：`curl -I <rss-url>`
- ✅ 部分博客可能有反爬限制

---

## 📜 License

MIT

---

> ⭐ 如果这个项目对您有帮助，请给个 Star！
