# 开源项目的 SEO & GEO 优化指南

> 让你的开源项目在搜索引擎和 AI 搜索中持续获得开发者关注

## 为什么开源项目需要 SEO/GEO？

开源项目的流量来源：
- **GitHub 搜索**: 依赖 README、topic tags、description
- **Google/Bing 搜索**: 开发者搜索 "best [类目] library"、"[问题] solution"
- **AI 搜索**: ChatGPT/Perplexity 推荐工具时会引用文档和 GitHub

SEO/GEO 让你的项目在**所有渠道**都能被发现。

---

## 📦 GitHub 仓库 SEO

### Repository 基础设置

**Description (一句话)**
```
✅ Open-source [品类] that [核心价值]. Self-hosted alternative to [知名竞品].
❌ A cool project I made
```

**Topics (标签)**
- 添加 10-15 个相关 topics
- 包含：品类词、技术栈、使用场景
- 例：`notion-alternative`, `open-source`, `self-hosted`, `typescript`, `collaboration`

### README SEO 优化

**Title (H1)**
```markdown
# 项目名 - 一句话价值主张

例: # AFFiNE - The Open Source Alternative to Notion & Miro
```

**开头100词**
- 直接说明项目是什么
- 包含核心关键词
- 链接到官网和文档

**结构化章节**
```markdown
## Features          ← 功能列表，用 checkbox
## Quick Start       ← 安装命令，便于复制
## Documentation     ← 链接到完整文档
## Community         ← Discord/社区链接
## Contributing      ← 贡献指南
## License           ← 开源协议
```

**SEO 友好元素**
- 使用清晰的 H2/H3 层级
- 功能用 bullet list 展示
- 安装命令放在代码块
- 包含架构图/截图（带描述性文件名）

---

## 🌐 官网 & 文档 SEO

### 技术基础

- [ ] HTTPS + 移动端适配
- [ ] Core Web Vitals 达标
- [ ] XML Sitemap 提交
- [ ] **IndexNow 实施** — 文档更新秒级索引

### 首页优化

**Title 公式**
```
[项目名] - [品类] | Open Source [竞品] Alternative
例: AFFiNE - Knowledge Base | Open Source Notion Alternative
```

**Schema 实施**
```json
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "项目名",
  "operatingSystem": "Web, Desktop, Mobile",
  "applicationCategory": "DeveloperApplication",
  "offers": {
    "@type": "Offer",
    "price": "0",
    "priceCurrency": "USD"
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.8",
    "ratingCount": "1000"
  }
}
```

### 文档 SEO

| 文档类型 | Title 格式 | 目标关键词 |
|----------|-----------|-----------|
| 安装指南 | Installation Guide - [项目名] | install [项目名], setup [项目名] |
| API 文档 | [功能] API Reference - [项目名] | [项目名] api, [功能] api |
| 教程 | How to [任务] with [项目名] | how to [任务], [任务] tutorial |
| 迁移指南 | Migrate from [竞品] to [项目名] | [竞品] alternative, migrate from [竞品] |

### 关键页面

**vs 竞品对比页**
```
/compare/notion
/compare/obsidian  
/compare/roam
```
- 每个竞品单独页面
- 功能对比表格
- 迁移指南链接

---

## 🤖 GEO: AI 搜索优化

### 为什么重要

开发者越来越多用 AI 搜索：
- "What's the best open source Notion alternative?"
- "Recommend a self-hosted note-taking app"
- "Compare AFFiNE vs Obsidian"

AI 会从你的 README、文档、博客中提取答案。

### IndexNow 配置

每次发布新版本，立即推送：

```bash
curl -X POST https://www.bing.com/indexnow \
  -H "Content-Type: application/json" \
  -d '{
    "host": "yourproject.com",
    "key": "YOUR-KEY",
    "urlList": [
      "https://yourproject.com/docs/changelog",
      "https://yourproject.com/blog/v2-release",
      "https://yourproject.com/docs/new-feature"
    ]
  }'
```

### AI 引用优化

**FAQ 页面**
```json
{
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "What is [项目名]?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "[项目名] is an open-source [品类] that [价值主张]. It's a self-hosted alternative to [竞品]."
      }
    },
    {
      "@type": "Question",
      "name": "Is [项目名] free?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "[项目名] is free and open-source under the [协议] license. We also offer a cloud version with additional features."
      }
    }
  ]
}
```

**内容格式**
- 开头直接给答案（AI 喜欢引用）
- 使用表格对比功能
- 提供具体数据和数字

### robots.txt

```
User-agent: ChatGPT-User
Allow: /

User-agent: OAI-SearchBot
Allow: /

User-agent: GPTbot
Allow: /docs/
Allow: /blog/
Disallow: /admin/

User-agent: Bingbot
Allow: /
```

---

## 📈 开源项目 SEO 策略

### 长尾内容矩阵

| 内容类型 | 关键词模式 | 示例 |
|----------|-----------|------|
| 教程 | how to [任务] with [项目] | How to build a wiki with AFFiNE |
| 集成 | [项目] + [工具] integration | AFFiNE Zapier integration |
| 迁移 | migrate from [竞品] to [项目] | Migrate from Notion to AFFiNE |
| 对比 | [项目] vs [竞品] | AFFiNE vs Obsidian |
| 用例 | [项目] for [场景] | AFFiNE for team collaboration |

### 反向链接策略

**高价值来源**
- Awesome Lists (awesome-[品类])
- 技术博客评测
- 开发者新闻站 (Hacker News, Dev.to)
- 官方框架/工具的生态页面

**行动步骤**
1. 提交到相关 Awesome Lists
2. 邀请技术博主评测
3. 在 Hacker News 发布 "Show HN"
4. 申请加入框架官方生态列表

---

## ⚡ 开源项目 SEO 清单

### 发布前

- [ ] GitHub Description + Topics 优化
- [ ] README 结构化 + 关键词
- [ ] 官网 Title/Meta 优化
- [ ] SoftwareApplication Schema
- [ ] XML Sitemap + IndexNow

### 发布时

- [ ] IndexNow 推送所有新页面
- [ ] 提交到 Product Hunt
- [ ] 提交到 Awesome Lists
- [ ] Hacker News "Show HN"

### 持续优化

- [ ] 每次版本发布 IndexNow 推送
- [ ] 创建对比页面（vs 竞品）
- [ ] 创建迁移指南
- [ ] 监测 GitHub 搜索排名
- [ ] 追踪 AI 搜索中的引用

---

*基于 SEO & GEO 行动手册 v1.0*
