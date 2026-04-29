# 案例:AI Slides(D5 内部产品)

> 用 Claude Code Skills 体系做 PPTX → Typst 模板生成的工作流产品。

## 产品定位

> "模板是给 AI 看的,不是给人看的"

通过 8 个互相协作的 Claude Code Skills 完成完整工作流:从 PPTX 提取 → Typst 代码生成 → 可复用模板化。

## 8 个 Skills(从 README 看到)

| Skill | 一句话职责 |
|---|---|
| ppt-master | 总控:管理状态机、分派任务、制定叙事策略 |
| interview | 通过结构化提问收集需求 → 输出 Brief |
| text2semantic | 文档 → SemanticOutline YAML |
| semantic2ppt | SemanticOutline + 模板 → content.typ → PDF |
| (其余 4 个待 Daryth 自己阅读 README 补充) | - |

## 代码仓库

`E:\D5_code\ai-slides`

**关键文件**:
- `README.md`(产品介绍)
- `CLAUDE.md`(给 Claude Code 用的项目说明)
- `SPEC.md`(技术规范)
- `REGISTRY.md`(可能是模板注册表)
- `skills/`(8 个 skill 目录)

## 为什么这是黄金教学案例 ⭐⭐⭐

1. **Daryth 学的 skill 体系跟公司用的是同一套** — 学会怎么读 / 写 / 改 skill,直接是工作能力
2. **真实的多 Agent 协作** — 不是教科书理论,是生产环境
3. **完整的工作流编排案例** — 8 个 skill 怎么互相调用、怎么传数据,模块 1 W6 + 模块 2 W2 都用得上

## 教练用法

### 模块 1 W6(Agent / Workflow)
**核心作业**:让 Daryth 阅读 ai-slides 的 SKILL.md 文件们(至少 3 个),写一份《AI Slides Skills 协作分析》:
- 谁是总控?
- 状态怎么传递?
- 一个 PPT 是怎么从用户输入变成输出的?
- 如果让你加一个新 skill,你会加什么?

### 模块 2 W2(Workflow 设计)
对照 ai-slides 设计自己的"AI 设计稿评审工作流":
- 哪些子任务可以拆成独立 skill?
- 怎么定义状态和接口?
- 失败兜底怎么做?

### 模块 4(独立 MVP)
可以作为重要参考,做一个简化的 skill 工作流产品

## 实战提示

鼓励 Daryth 主动找 ai-slides 的工程师交流:
- "这个 skill 一开始为什么这么设计?"
- "迭代过程中遇到什么坑?"

这种沟通本身就是 AI PM 必备能力训练。
