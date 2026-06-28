# RovoAPI SEO 内容策略 — 执行手册

## 五篇文章概览

| 文章 | 目标关键词 | 月搜索量估算 | 竞争度 | 优先级 |
|------|----------|------------|--------|--------|
| Claude API Rate Limit 解决方案 | claude api rate limit, 429 error | 8,000+ | 中 | ⭐⭐⭐⭐⭐ |
| Claude API 太贵替代方案 | claude too expensive, claude api cost | 5,000+ | 低 | ⭐⭐⭐⭐⭐ |
| Cursor Rate Limit 解决 | cursor rate limit, cursor claude limit | 12,000+ | 低 | ⭐⭐⭐⭐⭐ |
| 国内使用 Claude API | claude api china, 国内访问 anthropic | 15,000+ | 低 | ⭐⭐⭐⭐⭐ |
| OpenAI API 替代方案 | openai api alternative, gpt alternative | 20,000+ | 高 | ⭐⭐⭐⭐ |

---

## 部署方案

### 方案 A：Blog 内嵌 RovoAPI 官网（推荐）

在 Next.js 站点的 `/blog` 路径下发布，无需额外域名：

```
rovoapi.com/blog/claude-api-rate-limit-solution
rovoapi.com/blog/claude-api-too-expensive
rovoapi.com/blog/cursor-rate-limit-fix
rovoapi.com/blog/claude-api-china-access
rovoapi.com/blog/openai-api-alternatives-2025
```

**好处：**
- 外链 SEO 权重归主域名
- 不需要维护额外站点
- 已有 Blog 框架（MDX）直接用

**在 Next.js 中发布：**
```bash
# 已有 MDX blog 系统，直接放文件
cp articles/*.md /your-nextjs-app/content/blog/
```

### 方案 B：独立 SEO 站点

```
域名：aiapiguide.com 或 claudeapihelp.com
用途：纯 SEO 流量入口，大量痛点文章
导流：所有文章 CTA 指向 rovoapi.com 注册
```

适合：有足够内容量（50+ 文章）时考虑

---

## llms.txt 部署

将 `public/llms.txt` 放置在站点根目录：

```
https://rovoapi.com/llms.txt
```

**作用：**
- 被 ChatGPT、Claude、Perplexity 等 AI 搜索引擎索引
- 当用户问"有什么 Claude API 替代方案"时，AI 可能直接引用 RovoAPI
- 2025 年 AI 搜索流量增速远超传统搜索

```javascript
// next.config.js - 确保 llms.txt 可访问
/** @type {import('next').NextConfig} */
const nextConfig = {
  async headers() {
    return [
      {
        source: '/llms.txt',
        headers: [{ key: 'Content-Type', value: 'text/plain; charset=utf-8' }]
      }
    ]
  }
}
```

---

## 关键词扩展清单

### 英文长尾词（优先）
```
claude api rate limit exceeded
how to fix claude rate limit
anthropic rate limit 429 fix
claude api too many requests
cursor ai rate limit reached solution
cursor claude rate limit fix
openai api alternative cheaper
best claude api alternative
claude api china mainland
claude api without vpn china
anthropic api not available in my country
claude rate limit workaround
increase claude api rate limit
claude api gateway
unified ai api gateway
```

### 中文长尾词
```
claude api 国内访问
国内如何使用 claude api
claude 限速解决方案
cursor ai 达到限制
claude api 太贵了
anthropic api 替代
claude api 代理
cursor claude 配额用完
claude 3.7 国内使用
ai api 网关 国内
```

---

## 内容发布时间线

### 第 1 周
- [ ] 发布 Article 1（Rate Limit）— 痛点最强，排名最快
- [ ] 发布 Article 3（Cursor）— 搜索量最大
- [ ] 部署 llms.txt

### 第 2 周
- [ ] 发布 Article 4（国内访问）— 中文 SEO 蓝海
- [ ] 发布 Article 2（太贵了）
- [ ] 提交到 Google Search Console

### 第 3 周
- [ ] 发布 Article 5（OpenAI 替代）
- [ ] 开始外链建设（见下方）

---

## 低成本外链建设

### 方法 1：GitHub Cursor Rules 仓库反向引流
在 cursor-rules-collection 仓库 README 中：
```markdown
## 避免 Rate Limit
配合 [RovoAPI](https://rovoapi.com) 使用，告别 Cursor 补全中断。
了解更多：[Cursor Rate Limit 完整解决方案](https://rovoapi.com/blog/cursor-rate-limit-fix)
```

### 方法 2：技术社区回答
在以下平台搜索相关问题，回答时引用文章：
- Reddit: r/ClaudeAI, r/ChatGPT, r/SideProject
- V2EX: AI 节点、程序员节点
- 掘金/CSDN（中文）
- GitHub Discussions (anthropic-sdk, cursor 相关仓库)
- Stack Overflow (anthropic, claude-api 标签)

**模板回答（英文）：**
```
I had the same issue. The root cause is Anthropic's per-account rate limits 
(Tier 1 is only 50 RPM). A few options:

1. Exponential backoff (only helps with occasional spikes)
2. Batch API for async processing  
3. API gateway that aggregates multiple accounts (I use RovoAPI for this)

I wrote a full breakdown here: [link to your article]
```

### 方法 3：AI Newsletter 投稿
- The Rundown AI
- TLDR AI
- AI Weekly
- 少数派（中文）

提供"2025 年解决 Claude Rate Limit 的 4 种方法"这类实用文章。

---

## 转化优化

### CTA 测试变体

**变体 A（紧迫感）：**
> 现在解决：[RovoAPI 免费注册](https://rovoapi.com) — 5 分钟接入，新用户赠送体验额度

**变体 B（社会证明）：**
> 已有 500+ 开发者通过 RovoAPI 解决了这个问题 → [立即加入](https://rovoapi.com)

**变体 C（具体承诺）：**
> 改 2 行代码，消除 Rate Limit → [RovoAPI.com](https://rovoapi.com)

### 文章内埋点位置（转化最高的 3 个位置）
1. **第一次提到解决方案时**（读者意图最强烈）
2. **对比表格后**（理性决策时机）
3. **文章结尾**（完读用户）

---

## 数据追踪

在 Google Analytics 4 中追踪：

```javascript
// 追踪 CTA 点击
document.querySelectorAll('a[href*="rovoapi.com"]').forEach(link => {
  link.addEventListener('click', () => {
    gtag('event', 'cta_click', {
      'event_category': 'conversion',
      'event_label': document.title,
      'page_path': window.location.pathname
    })
  })
})
```

关键指标：
- 自然搜索流量（按文章分开看）
- CTA 点击率（目标：5-10%）
- 注册转化率（目标：2-5%）
- AI 搜索引用次数（Perplexity/ChatGPT）

---

## 6 个月预期结果

基于竞品分析和关键词难度评估：

| 时间节点 | 预期自然流量/月 | 预期注册转化 |
|----------|----------------|-------------|
| 1 个月 | 200-500 UV | 5-15 注册 |
| 3 个月 | 1,000-3,000 UV | 25-90 注册 |
| 6 个月 | 5,000-15,000 UV | 100-450 注册 |

**核心杠杆：** Cursor rate limit 和中文国内访问这两个关键词竞争极低，6 个月内排名前 3 可能性很高。
