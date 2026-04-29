# 模块 1:AI 技术地基(8 周深度版)

**周期**:8 周(56 天) | **目标**:能跟工程师对话不被忽悠,理解技术原理,能看懂代码做了什么

---

## 模块整体目标

完成本模块后,Daryth 应能:

1. 跟工程师讨论技术方案时,听懂 90% 的术语
2. 给一个伪需求,能做基本的技术可行性评估
3. 能看懂别人的 Python / TS 代码大概做了什么(不需要会写)
4. 能给一个 AI 产品场景独立选型(模型 / 技术路线 / 评测方案)
5. 至少 8 篇周笔记 + 8 个周作业入仓库

---

## Week 1:LLM 工作原理(基础打底)

### 学习目标
理解 LLM 是怎么工作的(浅层),能跟工程师说清楚 token / 上下文 / 温度的含义。

### 核心要点

1. **预训练 + RLHF 极简版**:为什么 GPT 这么聪明?(预测下一个 token + 人类反馈)
2. **Token 是什么**:为啥它决定速度和成本(粗略:1 个汉字 ≈ 1.5-2 token)
3. **上下文窗口**:为啥会"遗忘"前面的对话
4. **Temperature / Top_p**:控制 AI 输出"创造力"的旋钮
5. **流式输出 vs 非流式**:对用户体验的影响

### 推荐学习资源

**视频(优先)**:
- 3Blue1Brown《直观理解神经网络》系列(B 站有中文字幕版)
- Andrej Karpathy《深入了解 GPT》中字版(B 站搜)

**文章**:
- 公众号:Hugging Face 中文社区《什么是大语言模型》
- 阮一峰科技爱好者周刊里的 LLM 入门篇

**实操**:
- 在 Anthropic Console 或 OpenAI Playground 用同一个 prompt 跑 3 个不同 temperature(0.0 / 0.7 / 1.5),观察差异

### Day-by-Day 节奏建议(每天 2-3 小时)

| 日 | 任务 |
|---|---|
| Day 1 | 写"学习宣言" + 启动仓库 + 看 3Blue1Brown 第 1 集 |
| Day 2 | 看 3Blue1Brown 第 2-3 集 + 整理 token 概念笔记 |
| Day 3 | 看 Karpathy 视频 + 阅读"什么是 LLM" |
| Day 4 | 实操 — 在 Console 跑 3 个 temperature,对比输出 |
| Day 5 | 写《LLM 基础理解》笔记 800 字 |
| Day 6 | 副线任务:挑一个 AI 产品做拆解笔记 + 读 1 篇 AI 商业化文章 |
| Day 7 | 周复盘 + commit + push |

### 周作业(交付物)

**作业 1**:`notes/module-1/W1/llm-basics.md`
- 至少 800 字
- 必须用自己的话解释:Token / 上下文窗口 / Temperature
- 必须包含 3 次 temperature 对比的实操记录(贴 prompt 和输出对比)

**作业 2**(副线):`notes/weekly-product-teardown/2026-W18.md`
- 任选一个 AI 产品(国内外都行)
- 400-800 字拆解(产品价值 / 核心 AI 能力 / UX 亮点 / 商业模式)

### 教练验收要点

- 笔记里"用自己的话"是关键 — 如果只是抄概念,不算理解,要 Daryth 重写
- 实操记录要有 prompt + 实际输出截图,不能编造
- 周末提示她做 git push

---

## Week 2:模型生态 + 多模态 + 选型

### 学习目标
能给一个 AI 产品场景独立做模型选型,知道选型决策的关键变量。

### 核心要点

1. **主流模型矩阵**:
   - 国外:Claude (Sonnet/Opus/Haiku)、GPT-4o/o1、Gemini、DeepSeek
   - 国内:Qwen、豆包、Kimi、智谱 GLM
2. **多模态模型** ⭐ 你公司业务核心:
   - 文本 + 图像(GPT-4o, Claude vision, Gemini)
   - 视频生成(可灵、Sora)
   - 语音(TTS / ASR)
3. **大模型 vs 小模型 vs 蒸馏**:什么场景选小模型
4. **选型决策树**:任务难度 / 速度要求 / 成本预算 / 数据敏感度

### 推荐资源

- 公众号:量子位、机器之心 — 经常出模型对比文
- 网站:LMSys Chatbot Arena 排行榜(看实际能力对比)
- 实操:同一个真实任务在 Claude / GPT / DeepSeek / Qwen 上各跑一次

### 周作业

**作业 1**:`notes/module-1/W2/model-matrix.md` 或 Excel
- 做一张《主流大模型对比矩阵》
- 维度:模型名 / 上下文长度 / 价格 / 多模态支持 / 强项 / 弱项
- 至少包含 8 个主流模型

**作业 2**:`notes/module-1/W2/d5-model-selection.md`
- 给 D5 公司 4 个产品(Clawtics、数字人、获客、律师助手)各推荐主用模型 + 备选
- 每个推荐写 200 字理由

### 教练验收要点

- 选型理由必须涉及"成本"和"性能"两个维度的权衡
- 律师助手必须考虑数据安全 → 推国内模型 / 私有部署

---

## Week 3:Prompt 工程系统化

### 学习目标
从"会写 prompt"升级到"系统化设计 prompt 的能力体系"。

### 核心要点

1. **结构化 Prompt**:Role / Context / Task / Format / Constraints / Examples
2. **Zero-shot vs Few-shot**:什么时候给例子有用
3. **思维链(CoT)** 和 **ReAct** 模式
4. **System Prompt vs User Prompt**:权重和用途差异
5. **Prompt Caching** ⭐ 直接影响成本(Anthropic / OpenAI 都支持)
6. **结构化输出**:让 AI 返回 JSON 而不是自由文本(JSON Schema / Function Calling)

### 推荐资源

- Anthropic 官方 Prompt Engineering 教程(有中文翻译版)
- 李继刚《结构化提示词》系列(B 站、知乎)
- 实操:Anthropic Console 的 Prompt Generator 工具

### 周作业

**作业**:`notes/module-1/W3/prompt-iteration-log.md`
- 挑一个真实工作场景(比如"自动写设计稿评审反馈")
- 设计初版 prompt,然后迭代 5 轮(v1 → v5)
- 每轮记录:发现了什么问题 + 怎么改 + 改后的效果对比
- 最终版必须包含:结构化模板 + 至少 1 个 few-shot 示例 + 输出格式约束

### 教练验收要点

- "迭代日志"是核心 — 看她有没有真的发现问题并改进
- 如果 v1 已经很完美就要重新出题,故意给她容易失败的场景

---

## Week 4:三种"教 AI"方式对比 ⭐ 重头戏

### 学习目标
能在工作中独立判断"这个需求该用 prompt / RAG / 微调",并解释清楚成本和效果差异。

### 核心要点

1. **三种方式的本质区别**:
   - Prompt 工程:在调用时给 AI 上下文(零训练成本,效果有上限)
   - RAG:让 AI 实时查资料(中等成本,适合知识更新)
   - Fine-tuning(微调):重新训练模型一部分(高成本,效果上限高)
2. **决策矩阵**:
   - 数据量小 → Prompt
   - 知识需更新 → RAG
   - 行业垂直 + 风格固定 → 微调
   - 多种结合也常见
3. **成本-效果对比**:实际项目里这是核心权衡

### 推荐资源

- Anthropic 博客:Building effective agents 中文翻译
- 《大模型应用开发极简入门》第 3-5 章

### 周作业 ⭐(重要)

**作业**:`notes/module-1/W4/lawyer-assistant-tech-selection.md`
- 给 D5 公司"律师助手"产品做完整技术方案选型报告
- 至少 2000 字,必须包含:
  - 业务需求拆解(律师每天用什么功能)
  - 三种方式的可行性分析
  - 选型决策(主推方案 + 备选)
  - 成本测算(粗估即可)
  - 风险评估
- 这份文档可以直接给老板看

### 教练验收要点

- 这是模块 1 最重要的作业之一,必须深度评审
- 律师助手涉及法律责任,必须谈到"幻觉"和"数据隐私"
- 鼓励她拿这份报告去公司征求工程师意见(实战机会)

---

## Week 5:RAG 深入 + 知识库构建

### 学习目标
理解 RAG 完整链路 + 能动手搭建一个 RAG 知识库 bot 并评测。

### 核心要点

1. **向量是什么**:为什么 AI 要"先转向量"
2. **完整链路**:文档分块(Chunking) → 嵌入(Embedding) → 检索(Retrieval) → 重排(Reranking) → 注入(Injection)
3. **常见失败模式**:
   - 检索不准(分块太大/太小)
   - 回答幻觉(检索到无关内容也硬答)
   - 上下文超长(注入太多)
4. **RAG 评估方法**:命中率 / 精确率 / 答案质量人工打分

### 推荐资源

- 视频:LangChain 中文教学(B 站)
- 实操平台:Coze 或 Dify(国内可用)

### 周作业

**作业**:`projects/rag-bot-W5/`
- 在 Coze 或 Dify 上搭建一个知识库 bot
- 选题建议:用你自己的设计原则文档/前端规范当知识库
- **手动测 20 个问题**,每个问题打分(命中 ✅ / 部分对 ⚠️ / 错误 ❌)
- 写评测报告 `notes/module-1/W5/rag-evaluation.md`,至少 1000 字
  - 哪些问题答得好/差,原因猜测
  - 改进方案

### 教练验收要点

- 必须提供 bot 的访问链接或截图证据
- 20 个问题的打分要诚实,不能为了 bot 表现好挑简单问题

---

## Week 6:Agent + Function Calling + MCP

### 学习目标
理解 Agent 是什么、跟工作流的区别,知道 MCP 这个新兴标准。

### 核心要点

1. **Agent 三件套**:Memory / Planning / Reflection
2. **单 Agent / 多 Agent / 工作流**的区别和适用场景
3. **Function Calling 工作原理**:让 AI 调用工具(查天气、搜数据库等)
4. **MCP(Model Context Protocol)** ⭐ Anthropic 推出,业界正在采纳
   - 它跟 Function Calling 的关系
   - 为什么它是"AI 时代的 USB"

### 推荐资源

- Anthropic 官方:MCP 介绍(有中文翻译)
- 你公司的 `ai-slides` 项目 — 直接读它的 README,看 8 个 skills 怎么协作 ⭐⭐⭐
- 视频:Coze Studio 工作流入门

### 周作业

**作业**:`notes/module-1/W6/agent-design.md`
- 选 D5 公司一个产品(推荐 Clawtics 或 AI Slides),设计 Agent 能力框架
- 至少 1500 字,包含:
  - 这个 Agent 解决什么问题
  - 它的 Memory(记什么)/ Planning(怎么分解任务)/ Reflection(怎么自检)设计
  - 它需要哪些 Tool(Function Calling)
  - 失败场景和兜底设计

### 教练验收要点

- 鼓励她真的去翻 ai-slides 代码,看真实的 skill 长什么样
- 这是为模块 2 工作流设计打基础

---

## Week 7:评测 + 安全 + 数据飞轮(产品上线必备)

### 学习目标
建立"AI 产品上线全链路质量保障"的认知,知道有哪些坑要防。

### 核心要点

1. **评测体系**:
   - Benchmark(MMLU / HumanEval 这些跑分)
   - 业务评测(自己造的题库)
   - 在线评测(用户反馈数据)
2. **安全相关**:
   - 幻觉(Hallucination)
   - 越狱(Jailbreak)
   - Prompt 注入(Prompt Injection)
3. **数据飞轮 / 用户反馈闭环**:产品长期护城河
4. **成本管理**:Token 计费 / 模型路由 / 缓存

### 推荐资源

- 公众号:智源研究院(中文 AI 安全前沿)
- Anthropic 安全相关博客

### 周作业

**作业**:`notes/module-1/W7/d5-product-evaluation-and-safety.md`
- 给 D5 一个产品(推荐律师助手,因为最敏感)写"评测方案 + 安全方案"
- 至少 1500 字,包含:
  - 评测方案(测什么 / 用什么数据集 / 怎么打分 / 多久评一次)
  - 安全方案(可能的攻击 / 兜底 / 用户教育)
  - 数据飞轮(用户反馈怎么进入下一轮迭代)

---

## Week 8:代码可读性 + API 实战 + 模块验收

### 学习目标
- 能看懂 Python / TypeScript 代码大概在做什么
- 能直接调用 API 并理解参数
- 通过模块 1 验收

### 核心要点

1. **Python 基础语法速通**(2 小时即可):
   - 变量、函数、类、控制流
   - import 是啥意思
   - JSON / YAML 长什么样
2. **目录结构**:看一个项目目录大概知道做什么
3. **错误日志**:怎么找到关键报错信息
4. **API 调用基础**:
   - 在 Anthropic Console 直接调
   - 核心参数:model / messages / temperature / max_tokens / system
   - 流式输出 streaming
   - 成本计算

### 推荐资源

- 视频:菜鸟教程 Python 基础(挑前 3 节看)
- 实操:Anthropic Console / OpenAI Playground

### 周作业

**作业 1**:`notes/module-1/W8/code-walkthrough.md`
- 选你之前 vibe coding 过的一个项目,让 AI(Claude / Cursor)给你逐行讲解
- 写 1500 字"我学到了什么代码原理"

**作业 2**:`notes/module-1/W8/api-experiments.md`
- 在 Anthropic Console 手动调 5 次 API,记录:
  - 5 次的 prompt + 参数(temperature / max_tokens / system 各种组合)
  - 实际响应
  - 你观察到的差异
- (不需要写代码,Console 是图形界面)

**模块 1 验收**:见 `validation/module-1-exam.md`

---

## 模块完成标准

- ✅ 8 周作业全部完成并入 GitHub
- ✅ 模块验收 ≥ 70 分
- ✅ 至少 8 篇周笔记
- ✅ 至少 4 篇副线产品拆解笔记
- ✅ 至少 2 个产出可以拿给同事/老板看(选型报告 + 评测安全方案)

完成后:升级到模块 2 + 把所有作业归档到 `portfolio/module-1/`
