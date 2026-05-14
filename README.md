# AIPM-Vibecoding-Skill

> AI 时代产品经理的 vibe coding 方法论 skill 库,为 Claude Code / Cursor / Lovable 等 AI 编程工具提供工作流增强。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Skills](https://img.shields.io/badge/skills-1-blue)](#-skill-列表)
[![Status](https://img.shields.io/badge/status-active-success)](#)

---

## 📖 这个仓库是什么

**Vibe Coding(氛围编程)** 是 AI 时代的新工作方式 —— 产品经理用自然语言指挥 AI 编程工具直接产出代码,而不是写 PRD 给开发团队。

这种工作方式与传统软件开发流程**完全不同**:
- PRD 的读者是 AI,不是开发团队
- 模糊度必须更低、验收必须可观测、边界必须显式
- 文档结构必须模块化、AI 友好、可独立增删

**本仓库**沉淀的是产品经理在 vibe coding 实战中提炼的可复用 skill,每个 skill 都是一个完整的工作流封装,可以直接安装到 `~/.claude/skills/` 让 Claude Code 触发使用。

---

## 🧩 Skill 列表

> 每加一个 skill,在这里加一行。版本变更同步更新 README。

| Skill | 功能 | 适用阶段 | 状态 | 文档 |
|-------|------|---------|------|------|
| **vibe-coding-prd-writer** | 撰写 vibe coding PRD(写给 AI 看的产品需求文档) | 需求阶段 | v0.2.0 ✅ | [详细 README](./vibe-coding-prd-writer/README.md) |

### 计划中(roadmap)

| Skill | 功能 | 状态 |
|-------|------|------|
| vibe-project-init | 模糊想法→清晰文档骨架的项目启动漏斗 | 🟡 设计中 |
| vibe-coding-doc-auditor | 项目文档完备性审查器 | 🟡 设计中 |
| vibe-coding-prompt-engineer | AI 角色 prompt 工程化(防幻觉) | 🟡 设计中 |
| engineering-control-review | 用钱学森工程控制论审查代码完备性 | ⚪ 构思中 |
| prototype-first | 视觉原型先行的标准流程 | ⚪ 构思中 |
| mvp-gatekeeper | MVP 边界守门员(scope creep 拦截) | ⚪ 构思中 |

---

## 🚀 怎么安装使用

### 前提条件

1. 已安装 [Claude Code](https://docs.claude.com/en/docs/claude-code)
2. 终端能用 `git` 命令

### 安装(选一种)

#### 方式 A:克隆全部 skill(推荐)

```bash
# 1. 克隆到本地任意位置
cd ~/Documents/Github  # 或你想放的位置
git clone https://github.com/HTk77/AIPM-Vibecoding-Skill.git

# 2. 把每个 skill 软链接到 Claude Code 的 skill 目录
ln -s ~/Documents/Github/AIPM-Vibecoding-Skill/vibe-coding-prd-writer ~/.claude/skills/vibe-coding-prd-writer

# 3. 重启 Claude Code,新 skill 应自动出现在 skill 列表
```

#### 方式 B:只装某一个 skill(轻量)

```bash
# 直接复制单个 skill 文件夹到 ~/.claude/skills/
cd ~/.claude/skills
git clone --depth 1 --filter=blob:none --sparse https://github.com/HTk77/AIPM-Vibecoding-Skill.git temp
cd temp && git sparse-checkout set vibe-coding-prd-writer
mv vibe-coding-prd-writer ../
cd .. && rm -rf temp
```

### 验证安装

打开 Claude Code,新对话里说一句明确触发词(如 "我要写一个 vibe coding PRD"),
对应 skill 会自动激活。

---

## 🎯 设计哲学

每个 skill 都遵循以下原则:

| 原则 | 解释 |
|------|------|
| **流程优先于内容** | 先定流程框架,再填内容。模糊需求 = 模糊代码,卡住流程比赶进度重要。 |
| **触发词分三档** | 明确 / 模糊 / 严禁,避免污染同事日常工作流。 |
| **模板 + 微示例** | 不用完整案例(会让 AI 输出"看着像上次的项目"),用填空模板 + 多行业微示例。 |
| **AI 友好结构** | 所有内容模块化、解耦、可独立增删,便于 AI 读和长期维护。 |
| **真实材料锚定** | 涉及人物 / 框架 / 案例的部分,必须基于公开互联网资料,有出处链接,严禁凭空捏造。 |

完整方法论参见各 skill 的 `METHODOLOGY.md`。

---

## 📚 适合谁用

✅ **适合:**
- 不会写代码 / 写得少 但要做产品的 PM
- 用 Claude Code / Cursor / Lovable / Bolt / Windsurf 等 AI 编程工具的人
- 想把 vibe coding 实践工程化、避免每次重新踩坑的从业者
- 需要给团队 PM 同事推广 vibe coding 方法论的产品负责人

❌ **不适合:**
- 给传统开发团队写 PRD 的场景(请用传统 PRD 模板)
- 已有完整敏捷开发流程的成熟团队
- 不打算用 AI 编程工具的项目

---

## 🛠 怎么贡献 / 反馈

### 提 Issue

发现 skill 触发不准、模板字段缺失、某行业微示例不够 —— 欢迎在 [Issues](https://github.com/HTk77/AIPM-Vibecoding-Skill/issues) 反馈。

### 提交新 skill

如果你在 vibe coding 实战中沉淀了新 skill,欢迎提 PR:

1. Fork 本仓库
2. 在根目录新建你的 skill 文件夹(命名规范 `vibe-XXX` 或 `<功能>-XXX`)
3. 必须包含:`SKILL.md`、`README.md`、`CHANGELOG.md`、`METHODOLOGY.md`(参考 `vibe-coding-prd-writer/` 的目录结构)
4. 在本 README 的 [Skill 列表](#-skill-列表) 添加你的 skill
5. 提交 PR

---

## 🗓 仓库更新规则

> 这个仓库会持续迭代,以下是维护承诺:

| 触发条件 | 必须更新 |
|---------|---------|
| 新增 skill | 本 README 的 Skill 列表 + Roadmap 表 |
| skill 版本更新(v0.x → v0.y) | 本 README 列表中的版本号 + 该 skill 的 CHANGELOG |
| 设计哲学变化 | 本 README §🎯 章节 |
| 安装方式变化 | 本 README §🚀 章节 |

**版本号约定:** 顶层仓库版本 = 各 skill 版本的并集快照,不强制统一。各 skill 独立维护自己的 SemVer 版本。

---

## 📝 License

[MIT](./LICENSE) © 2026 赫庭 (HTk77)

完全开源,自由使用、修改、分发。**唯一要求:保留原作者署名**。

---

## 📮 联系

| 渠道 | 链接 |
|------|------|
| GitHub | [@HTk77](https://github.com/HTk77) |
| Issues | https://github.com/HTk77/AIPM-Vibecoding-Skill/issues |

---

> **当前仓库版本:** v0.1.0(初始发布,含 1 个 skill)
> **最后更新:** 2026-05-04
# AIPM-Vibecoding-Skill

> AI 时代产品经理的 vibe coding 方法论 skill 库,为 Claude Code / Cursor / Lovable 等 AI 编程工具提供工作流增强。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Skills](https://img.shields.io/badge/skills-1-blue)](#-skill-列表)
[![Status](https://img.shields.io/badge/status-active-success)](#)

---

## 📖 这个仓库是什么

**Vibe Coding(氛围编程)** 是 AI 时代的新工作方式 —— 产品经理用自然语言指挥 AI 编程工具直接产出代码,而不是写 PRD 给开发团队。

这种工作方式与传统软件开发流程**完全不同**:
- PRD 的读者是 AI,不是开发团队
- 模糊度必须更低、验收必须可观测、边界必须显式
- 文档结构必须模块化、AI 友好、可独立增删

**本仓库**沉淀的是产品经理在 vibe coding 实战中提炼的可复用 skill,每个 skill 都是一个完整的工作流封装,可以直接安装到 `~/.claude/skills/` 让 Claude Code 触发使用。

---

## 🧩 Skill 列表

> 每加一个 skill,在这里加一行。版本变更同步更新 README。

| Skill | 功能 | 适用阶段 | 状态 | 文档 |
|-------|------|---------|------|------|
| **vibe-coding-prd-writer** | 撰写 vibe coding PRD(写给 AI 看的产品需求文档) | 需求阶段 | v0.2.0 ✅ | [详细 README](./vibe-coding-prd-writer/README.md) |

### 计划中(roadmap)

| Skill | 功能 | 状态 |
|-------|------|------|
| vibe-project-init | 模糊想法→清晰文档骨架的项目启动漏斗 | 🟡 设计中 |
| vibe-coding-doc-auditor | 项目文档完备性审查器 | 🟡 设计中 |
| vibe-coding-prompt-engineer | AI 角色 prompt 工程化(防幻觉) | 🟡 设计中 |
| engineering-control-review | 用钱学森工程控制论审查代码完备性 | ⚪ 构思中 |
| prototype-first | 视觉原型先行的标准流程 | ⚪ 构思中 |
| mvp-gatekeeper | MVP 边界守门员(scope creep 拦截) | ⚪ 构思中 |

---

## 🚀 怎么安装使用

### 前提条件

1. 已安装 [Claude Code](https://docs.claude.com/en/docs/claude-code)
2. 终端能用 `git` 命令

### 安装(选一种)

#### 方式 A:克隆全部 skill(推荐)

```bash
# 1. 克隆到本地任意位置
cd ~/Documents/Github  # 或你想放的位置
git clone https://github.com/HTk77/AIPM-Vibecoding-Skill.git

# 2. 把每个 skill 软链接到 Claude Code 的 skill 目录
ln -s ~/Documents/Github/AIPM-Vibecoding-Skill/vibe-coding-prd-writer ~/.claude/skills/vibe-coding-prd-writer

# 3. 重启 Claude Code,新 skill 应自动出现在 skill 列表
```

#### 方式 B:只装某一个 skill(轻量)

```bash
# 直接复制单个 skill 文件夹到 ~/.claude/skills/
cd ~/.claude/skills
git clone --depth 1 --filter=blob:none --sparse https://github.com/HTk77/AIPM-Vibecoding-Skill.git temp
cd temp && git sparse-checkout set vibe-coding-prd-writer
mv vibe-coding-prd-writer ../
cd .. && rm -rf temp
```

### 验证安装

打开 Claude Code,新对话里说一句明确触发词(如 "我要写一个 vibe coding PRD"),
对应 skill 会自动激活。

---

## 🎯 设计哲学

每个 skill 都遵循以下原则:

| 原则 | 解释 |
|------|------|
| **流程优先于内容** | 先定流程框架,再填内容。模糊需求 = 模糊代码,卡住流程比赶进度重要。 |
| **触发词分三档** | 明确 / 模糊 / 严禁,避免污染同事日常工作流。 |
| **模板 + 微示例** | 不用完整案例(会让 AI 输出"看着像上次的项目"),用填空模板 + 多行业微示例。 |
| **AI 友好结构** | 所有内容模块化、解耦、可独立增删,便于 AI 读和长期维护。 |
| **真实材料锚定** | 涉及人物 / 框架 / 案例的部分,必须基于公开互联网资料,有出处链接,严禁凭空捏造。 |

完整方法论参见各 skill 的 `METHODOLOGY.md`。

---

## 📚 适合谁用

✅ **适合:**
- 不会写代码 / 写得少 但要做产品的 PM
- 用 Claude Code / Cursor / Lovable / Bolt / Windsurf 等 AI 编程工具的人
- 想把 vibe coding 实践工程化、避免每次重新踩坑的从业者
- 需要给团队 PM 同事推广 vibe coding 方法论的产品负责人

❌ **不适合:**
- 给传统开发团队写 PRD 的场景(请用传统 PRD 模板)
- 已有完整敏捷开发流程的成熟团队
- 不打算用 AI 编程工具的项目

---

## 🛠 怎么贡献 / 反馈

### 提 Issue

发现 skill 触发不准、模板字段缺失、某行业微示例不够 —— 欢迎在 [Issues](https://github.com/HTk77/AIPM-Vibecoding-Skill/issues) 反馈。

### 提交新 skill

如果你在 vibe coding 实战中沉淀了新 skill,欢迎提 PR:

1. Fork 本仓库
2. 在根目录新建你的 skill 文件夹(命名规范 `vibe-XXX` 或 `<功能>-XXX`)
3. 必须包含:`SKILL.md`、`README.md`、`CHANGELOG.md`、`METHODOLOGY.md`(参考 `vibe-coding-prd-writer/` 的目录结构)
4. 在本 README 的 [Skill 列表](#-skill-列表) 添加你的 skill
5. 提交 PR

---

## 🗓 仓库更新规则

> 这个仓库会持续迭代,以下是维护承诺:

| 触发条件 | 必须更新 |
|---------|---------|
| 新增 skill | 本 README 的 Skill 列表 + Roadmap 表 |
| skill 版本更新(v0.x → v0.y) | 本 README 列表中的版本号 + 该 skill 的 CHANGELOG |
| 设计哲学变化 | 本 README §🎯 章节 |
| 安装方式变化 | 本 README §🚀 章节 |

**版本号约定:** 顶层仓库版本 = 各 skill 版本的并集快照,不强制统一。各 skill 独立维护自己的 SemVer 版本。

---

## 📝 License

[MIT](./LICENSE) © 2026 赫庭 (HTk77)

完全开源,自由使用、修改、分发。**唯一要求:保留原作者署名**。

---

## 📮 联系

| 渠道 | 链接 |
|------|------|
| GitHub | [@HTk77](https://github.com/HTk77) |
| Issues | https://github.com/HTk77/AIPM-Vibecoding-Skill/issues |

---

> **当前仓库版本:** v0.1.0(初始发布,含 1 个 skill)
> **最后更新:** 2026-05-04
# AIPM-Vibecoding-Skill

> AI 时代产品经理的 vibe coding 方法论 skill 库,为 Claude Code / Cursor / Lovable 等 AI 编程工具提供工作流增强。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Skills](https://img.shields.io/badge/skills-1-blue)](#-skill-列表)
[![Status](https://img.shields.io/badge/status-active-success)](#)

---

## 📖 这个仓库是什么

**Vibe Coding(氛围编程)** 是 AI 时代的新工作方式 —— 产品经理用自然语言指挥 AI 编程工具直接产出代码,而不是写 PRD 给开发团队。

这种工作方式与传统软件开发流程**完全不同**:
- PRD 的读者是 AI,不是开发团队
- 模糊度必须更低、验收必须可观测、边界必须显式
- 文档结构必须模块化、AI 友好、可独立增删

**本仓库**沉淀的是产品经理在 vibe coding 实战中提炼的可复用 skill,每个 skill 都是一个完整的工作流封装,可以直接安装到 `~/.claude/skills/` 让 Claude Code 触发使用。

---

## 🧩 Skill 列表

> 每加一个 skill,在这里加一行。版本变更同步更新 README。

| Skill | 功能 | 适用阶段 | 状态 | 文档 |
|-------|------|---------|------|------|
| **vibe-coding-prd-writer** | 撰写 vibe coding PRD(写给 AI 看的产品需求文档) | 需求阶段 | v0.2.0 ✅ | [详细 README](./vibe-coding-prd-writer/README.md) |

### 计划中(roadmap)

| Skill | 功能 | 状态 |
|-------|------|------|
| vibe-project-init | 模糊想法→清晰文档骨架的项目启动漏斗 | 🟡 设计中 |
| vibe-coding-doc-auditor | 项目文档完备性审查器 | 🟡 设计中 |
| vibe-coding-prompt-engineer | AI 角色 prompt 工程化(防幻觉) | 🟡 设计中 |
| engineering-control-review | 用钱学森工程控制论审查代码完备性 | ⚪ 构思中 |
| prototype-first | 视觉原型先行的标准流程 | ⚪ 构思中 |
| mvp-gatekeeper | MVP 边界守门员(scope creep 拦截) | ⚪ 构思中 |

---

## 🚀 怎么安装使用

### 前提条件

1. 已安装 [Claude Code](https://docs.claude.com/en/docs/claude-code)
2. 终端能用 `git` 命令

### 安装(选一种)

#### 方式 A:克隆全部 skill(推荐)

```bash
# 1. 克隆到本地任意位置
cd ~/Documents/Github  # 或你想放的位置
git clone https://github.com/HTk77/AIPM-Vibecoding-Skill.git

# 2. 把每个 skill 软链接到 Claude Code 的 skill 目录
ln -s ~/Documents/Github/AIPM-Vibecoding-Skill/vibe-coding-prd-writer ~/.claude/skills/vibe-coding-prd-writer

# 3. 重启 Claude Code,新 skill 应自动出现在 skill 列表
```

#### 方式 B:只装某一个 skill(轻量)

```bash
# 直接复制单个 skill 文件夹到 ~/.claude/skills/
cd ~/.claude/skills
git clone --depth 1 --filter=blob:none --sparse https://github.com/HTk77/AIPM-Vibecoding-Skill.git temp
cd temp && git sparse-checkout set vibe-coding-prd-writer
mv vibe-coding-prd-writer ../
cd .. && rm -rf temp
```

### 验证安装

打开 Claude Code,新对话里说一句明确触发词(如 "我要写一个 vibe coding PRD"),
对应 skill 会自动激活。

---

## 🎯 设计哲学

每个 skill 都遵循以下原则:

| 原则 | 解释 |
|------|------|
| **流程优先于内容** | 先定流程框架,再填内容。模糊需求 = 模糊代码,卡住流程比赶进度重要。 |
| **触发词分三档** | 明确 / 模糊 / 严禁,避免污染同事日常工作流。 |
| **模板 + 微示例** | 不用完整案例(会让 AI 输出"看着像上次的项目"),用填空模板 + 多行业微示例。 |
| **AI 友好结构** | 所有内容模块化、解耦、可独立增删,便于 AI 读和长期维护。 |
| **真实材料锚定** | 涉及人物 / 框架 / 案例的部分,必须基于公开互联网资料,有出处链接,严禁凭空捏造。 |

完整方法论参见各 skill 的 `METHODOLOGY.md`。

---

## 📚 适合谁用

✅ **适合:**
- 不会写代码 / 写得少 但要做产品的 PM
- 用 Claude Code / Cursor / Lovable / Bolt / Windsurf 等 AI 编程工具的人
- 想把 vibe coding 实践工程化、避免每次重新踩坑的从业者
- 需要给团队 PM 同事推广 vibe coding 方法论的产品负责人

❌ **不适合:**
- 给传统开发团队写 PRD 的场景(请用传统 PRD 模板)
- 已有完整敏捷开发流程的成熟团队
- 不打算用 AI 编程工具的项目

---

## 🛠 怎么贡献 / 反馈

### 提 Issue

发现 skill 触发不准、模板字段缺失、某行业微示例不够 —— 欢迎在 [Issues](https://github.com/HTk77/AIPM-Vibecoding-Skill/issues) 反馈。

### 提交新 skill

如果你在 vibe coding 实战中沉淀了新 skill,欢迎提 PR:

1. Fork 本仓库
2. 在根目录新建你的 skill 文件夹(命名规范 `vibe-XXX` 或 `<功能>-XXX`)
3. 必须包含:`SKILL.md`、`README.md`、`CHANGELOG.md`、`METHODOLOGY.md`(参考 `vibe-coding-prd-writer/` 的目录结构)
4. 在本 README 的 [Skill 列表](#-skill-列表) 添加你的 skill
5. 提交 PR

---

## 🗓 仓库更新规则

> 这个仓库会持续迭代,以下是维护承诺:

| 触发条件 | 必须更新 |
|---------|---------|
| 新增 skill | 本 README 的 Skill 列表 + Roadmap 表 |
| skill 版本更新(v0.x → v0.y) | 本 README 列表中的版本号 + 该 skill 的 CHANGELOG |
| 设计哲学变化 | 本 README §🎯 章节 |
| 安装方式变化 | 本 README §🚀 章节 |

**版本号约定:** 顶层仓库版本 = 各 skill 版本的并集快照,不强制统一。各 skill 独立维护自己的 SemVer 版本。

---

## 📚 推荐资源

> PM 同行可能用得上的优质仓库 —— 业内被反复验证的 awesome list 与官方资料,持续筛选迭代。

### 🎯 AI 产品经理方法论

| Repo | 一句话价值 |
|------|----------|
| [dend/awesome-product-management](https://github.com/dend/awesome-product-management) | 业界最权威的 PM 资源精选 awesome list |
| [deanpeters/Product-Manager-Skills](https://github.com/deanpeters/Product-Manager-Skills) | 47 个可直接装进 Claude Code 的 PM Skill 包 |
| [deanpeters/product-manager-prompts](https://github.com/deanpeters/product-manager-prompts) | 50+ PM 实战用的 ChatGPT / Claude / Gemini prompt 模板 |
| [Shubhamsaboo](https://github.com/Shubhamsaboo) | Google Cloud Senior AI PM 个人主页,AI Agent 教程产出者 |

### 🧠 LLM & Prompt 工程基础

| Repo | 一句话价值 |
|------|----------|
| [Hannibal046/Awesome-LLM](https://github.com/Hannibal046/Awesome-LLM) | LLM 领域最全资源汇总(论文 / 框架 / 模型 / 课程) |
| [dair-ai/Prompt-Engineering-Guide](https://github.com/dair-ai/Prompt-Engineering-Guide) | Prompt / Context Engineering 黄金教程,66k+ stars |
| [anthropics/claude-cookbooks](https://github.com/anthropics/claude-cookbooks) | Anthropic 官方 Claude 用法 cookbook(分类 / RAG / 工具使用 / 子 Agent) |

### 🤖 AI 应用案例 & Agent 框架

| Repo | 一句话价值 |
|------|----------|
| [Shubhamsaboo/awesome-llm-apps](https://github.com/Shubhamsaboo/awesome-llm-apps) | 100+ 可直接 run 的 Agent / RAG / MCP / Voice 模板,105k+ stars |
| [kaushikb11/awesome-llm-agents](https://github.com/kaushikb11/awesome-llm-agents) | LLM Agent 框架精选(含 CrewAI 等 50k+ 星项目) |
| [InftyAI/Awesome-LLMOps](https://github.com/InftyAI/Awesome-LLMOps) | 生产级 LLMOps 工具链精选 |

### ⚡ Vibe Coding 工具链 & Skill 生态

| Repo | 一句话价值 |
|------|----------|
| [taskade/awesome-vibe-coding](https://github.com/taskade/awesome-vibe-coding) | Vibe Coding 完整指南(工具 / 框架 / 最佳实践) |
| [jqueryscript/awesome-claude-code](https://github.com/jqueryscript/awesome-claude-code) | Claude Code 工具 / IDE / 框架精选 |
| [bradAGI/awesome-cli-coding-agents](https://github.com/bradAGI/awesome-cli-coding-agents) | 终端原生 AI 编程代理目录(Aider / Goose / Codex / Gemini CLI) |
| [Prat011/awesome-llm-skills](https://github.com/Prat011/awesome-llm-skills) | LLM Skill 精选(Claude Code / Codex / Gemini CLI 通用) |

---

## 📝 License

[MIT](./LICENSE) © 2026 赫庭 (HTk77)

完全开源,自由使用、修改、分发。**唯一要求:保留原作者署名**。

---

## 📮 联系

| 渠道 | 链接 |
|------|------|
| GitHub | [@HTk77](https://github.com/HTk77) |
| Issues | https://github.com/HTk77/AIPM-Vibecoding-Skill/issues |

---

> **当前仓库版本:** v0.1.0(初始发布,含 1 个 skill)
> **最后更新:** 2026-05-04
