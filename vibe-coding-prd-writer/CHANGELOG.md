# Changelog

本 skill 的版本历史。遵循 [Keep a Changelog](https://keepachangelog.com/) 规范。

---

## [0.2.0] - 2026-05-04

> 重大重构。修了 v0.1.0 的核心问题,调结构 + 加流程 + 区分 AI 与功能产品。

### Added(新增)
- **§2 撰写流程(4 阶段 + 3 个用户确认点)** — 核心新增,把"自说自话写 PRD"改为"和用户对齐协作"
- **§1 AI 产品 vs 功能产品差异速查** — 显式区分,AI 项目额外 5 项必写
- **AI 三要素公式自检**(项目级 + 功能级双层)— 用户痛点 × 数据可获得性 × 算法可实现性
- **写作铁律 #6:字不如表,表不如图** — 行业核心口诀
- **`references/templates.md`** — 各模块填空骨架(替换原 example-prd.md)
- **`references/micro-examples.md`** — 6 行业微示例(C 端 / B 端 / AI 客服 / 多 Agent / UGC / 工具流)
- **`references/ai-product-extras.md`** — AI 项目专属:三要素详解 / 评测指标 / 数据采集三渠道 / POC 流程 / 合规风险清单
- **checklist.md ★流程合规章节** — 8 条最高优先级,跳过流程 = 不合格
- **触发词智能识别**(明确 / 模糊 / 严禁三档)— description 重写

### Changed(改动)
- **触发词聚焦** — 去掉太通用的"写 PRD / 撰写产品需求 / 写产品文档 / 输出 PRD / 做产品规格";保留 vibe-specific 词;模糊词需先反问场景
- **5 模块字段升级** — 功能契约必含用户故事("作为 X 我想要 Y 以便 Z");AI 项目每条功能必含评测指标
- **失败模式表扩展** — 从 7 条扩展到 11 条,新增 AI 项目专属失败模式

### Removed(删除)
- **`references/example-prd.md`(基于赫庭 AI 圆桌的完整示例)** — 迁移性差,被 templates + micro-examples 取代
- **§10 输出语 git 相关话术** — 过早提及,删除
- **checklist 里的 git 检查项** — 同上

### Fixed(修复)
- 触发词太宽,会污染传统 PRD 工作流的问题
- 缺少撰写流程基本节点(理解 → 架构 → 撰写 → 二次确认)
- 示例过于精准,迁移到不同行业时 AI 仍按"赫庭项目"风格输出
- 缺 AI 三要素 / 评测 / 合规等 AI 项目灵魂级内容

---

## [0.1.0] - 2026-05-04

> 初始版本。基础 5 模块 + 自查清单 + 完整示例。

### Added
- SKILL.md 主体:5 必写模块定义 + 6 选填模块 + 5 写作铁律 + 解耦输出格式 + 22 条精简自查
- `references/example-prd.md`(基于赫庭 AI 圆桌项目简化版)
- `references/checklist.md`(70 条详细自查)
- 触发词 12 个(中英)

### Known Issues(v0.1.0 已知问题,v0.2.0 修复)
- 缺少撰写流程
- 示例过于精准
- 触发词太宽
- 错误提及 git
- 缺 AI 项目专属内容

---

## 计划中(unreleased)

### v0.3.0(实战验证后)
- [ ] 跑 3-5 个不同行业项目验证后,根据真实失败 case 完善 checklist 反例
- [ ] 触发词进一步基于实测调优
- [ ] 增加端特定子文件(iOS / 小程序 / Android 上线 checklist)

### v1.0.0(经过 5+ 项目实战且团队推广后)
- [ ] 给同事用 1-2 个月,收集 false positive / false negative 修正
- [ ] 写一份 SHARING-GUIDE.md 教其他 PM 怎么用本 skill
- [ ] 与 vibe-project-init / prototype-first / vibe-coding-prompt-engineer 串成 skill 链
