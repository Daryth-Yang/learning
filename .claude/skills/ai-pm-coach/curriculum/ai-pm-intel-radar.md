# 📡 AI PM 资讯雷达(定时情报收集 SOP)

> **缘起**:2026-06-11 用户要求建立**定时爬取机制**,保持课程跟上时代。
> 用户原话:"定时去爬取相关内容,先找网站网页,然后找相关内容、关键词,热议的、权威的,都搜集下来然后整理。"
> 关联项目规定:SKILL.md「课程内容广度与时效性」铁律二。

## 🎯 目的

定期(定时)扫描全网最新 AI PM 资讯 → 筛选权威/热议内容 → 整理成周报 → 评估是否更新课表。**让课程不过时**。

## 🔄 执行 SOP(4 步)

### Step 1 · 找信息源(权威 + 热议)

**英文(权威方法论):**
- ChatPRD(chatprd.ai/learn)、Productside、Product Leadership、Lenny's Newsletter、a16z、Reforge
- 官方:OpenAI / Anthropic / Google 产品发布博客
- 社区热议:Hacker News、Reddit r/ProductManagement、X(AI PM 大V)

**中文(本土实践 + 招聘风向):**
- 人人都是产品经理(woshipm.com)、知乎「AI产品经理」话题、36氪、机器之心、量子位
- 招聘风向:BOSS直聘/拉勾 AI PM JD 关键词变化
- 公众号(待补具体名单)

### Step 2 · 按关键词爬取

- 中文:`AI产品经理 工作流/趋势/技能/工具/案例`、`AI产品方法论`、`大模型产品`
- 英文:`AI PM workflow`、`AI-native product`、`agent product`、`evaluation-driven`、`data flywheel`、`model selection`
- 时效:最新模型发布、新协议(MCP/A2A 等)、新工具

### Step 3 · 筛选标准(4 把尺子)

1. **权威性**:知名机构 / 资深从业者 / 官方发布
2. **热议度**:高互动 / 被反复引用 / 上热榜
3. **时效性**:近期(优先本月)
4. **相关性**:对 AI PM 能力/工作流/面试真有用(过滤噱头)

### Step 4 · 整理成周报(模板)

```
## AI PM 雷达周报 · YYYY-MM-DD
| 来源 | 标题 | 链接 | 一句话摘要 | 对课程的启示 |
|---|---|---|---|---|
| ... | ... | ... | ... | 纳入哪块/更新哪讲/仅了解 |

### 本周判断:课表要不要动?
- [ ] 新增/更新:____
- [ ] 暂存观察:____
```

## 🗂️ 归档位置

- 周报累积到 `learning-materials/ai-pm-radar/`(按日期)
- 重要趋势 → 回写进 [ai-pm-workflow.md](ai-pm-workflow.md) / 对应 curriculum
- 链接验证后 → 进 `learning-materials/`(绝不编 URL)

## ⏰ 定时设置

- **频率**:待用户定(建议每周一次,AI 变化快但每周够)
- **实现**:Claude Code 定时任务(schedule / cron)→ 按本 SOP 自动爬取整理 → 产出周报 → 提示教练评估课表
- **状态**:待用户确认频率后创建

---

> 更新日志
> - 2026-06-11 创建 SOP(信息源 + 关键词 + 筛选 + 周报模板),待设定时任务
