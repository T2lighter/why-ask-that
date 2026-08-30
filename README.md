# why-ask-that

> **配套技能**：本技能分析 [remeet-me](https://github.com/T2lighter/remeet-me) 自我采访中的提问，需先安装 remeet-me 并产生提问日志。

<p align="center">
  <a href="./LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License"></a>
  &nbsp;
  <img src="https://img.shields.io/badge/runtime-Multi--Runtime-7c3aed.svg" alt="Multi-Runtime">
  &nbsp;
  <img src="https://img.shields.io/badge/lang-中文-22c55e.svg" alt="Language">
  &nbsp;
  <img src="https://img.shields.io/badge/requires-remeet_me-f59e0b.svg" alt="Requires remeet-me">
</p>

> 把 AI 采访者"为什么这么问"拆开看——从提问日志生成提问档案与情境练习，把提问手艺变成你自己能带走的能力。

## English (brief)

**why-ask-that** is a companion skill to [remeet-me](https://github.com/T2lighter/remeet-me), following the Agent Skills Standard — it runs in any skills-compatible runtime. During a self-interview, remeet-me silently logs every question it asks — the exact wording, what triggered it, the technique used, the goal, the alternative it rejected, and how you responded. why-ask-that turns that log into a **learnable archive of questioning craft**:

- Per-question "why" cards: context / trigger / technique / purpose / discarded alternative / **effect** (did it open you up, or hit a wall — judged honestly, no sugar-coating)
- **Transferable principles**: one-line questioning rules that still hold with a different person and a different topic
- **Scenario drills**: 3 exercises rebuilt from real moments of your interview — the context is given, the original question hidden. Your turn: how would you ask?

It never interviews you and never analyzes *you* — only the questions. It doesn't run inside your interview; it runs after, on the log.

## 工作原理：一条日志，两份工作

remeet-me 采访你时，每个提问背后都是一串现场决策：为什么追这条线不追那条、为什么用"怎么"不用"为什么"、哪个问法被考虑过又放弃了。这些决策对你是黑盒——为了访谈的沉浸感，刻意不说。

提问日志（`remeet-me/question-log.md`）把黑盒打开了一半，why-ask-that 打开另一半，分工是七个维度：

| 维度 | 内容 | 谁来写 |
|---|---|---|
| ① 上下文 ② 触发 ③ 技法 ④ 目的 ⑥ 弃用的备选 | 当时问了什么、为什么问、怎么问的 | **日志现场记**（remeet-me） |
| ⑤ 效果 | 这一问实际打开了什么——给出具体事件 / 触及情绪 / 承认矛盾，还是单字敷衍 / 防御 / 绕开 | **why-ask-that**（依据日志里你的`回应`行，如实评，无效不美化） |
| ⑦ 可迁移原则 | 一句话问法规律，检验标准：**换个人、换个话题，还用得上吗？** | **why-ask-that** |

### 逐问卡片长这样

日志里每个提问按顺序编号（Q1、Q2、Q3……跨会话连续递增），每问一块。比如第三问：

```markdown
### Q3 · 追问
- 原文："那段时间没法动，心里什么感受？"
- 触发：他说"摔伤后整个人很烦躁"（情绪强度高+重复出现，压过体检报告那条线）
- 技法：五层·第2层（感受）
- 目的：从事件落到情绪，测这条线值得挖多深
- 弃用："你为什么烦躁"（"为什么"引防御）
- 回应：说了"闷得慌，像节奏被人按了暂停"（触及情绪+自发比喻）
```

why-ask-that 在卡片末尾补两行：**效果**（触及情绪+自发比喻 → 打开了）和**原则**（如"用户给出模糊情绪词时，先落具体事件再进感受，跳层会得到'还行'式敷衍"）。

### 情境练习长这样

> 你刚说完："那段时间没法动，心里挺烦躁的。"
> （日志显示：情绪强度高、这个词已是第二次出现）
> **此刻，你会怎么问下一问？**
> ——先自己答，再看参考思路（原问 + 为什么那么问）。对照的差异，才是学习发生的地方。

## 两种分析模式

| | 快速分析（会话级） | 完整分析（任意范围） |
|---|---|---|
| 何时 | 一次访谈结束，remeet-me 提议后你说"跑吧" | 你说"完整分析"，或点名一段范围（"把这半年的快照都分析了"） |
| 范围 | 日志最新一个会话 | 所指范围内的日志 + progress + report（多份快照逐份读、合并分析） |
| 产出 | 对话内逐问简表 + 1-2 条观察，不写文件 | md + html + index.md 原则库 + 3 道情境练习 |

## 完整分析产出什么

```
why-ask-that/                        （独立目录，与 remeet-me/ 平级；
                                       remeet-me 的归档、清空、丢弃不碰它）
├── 2026H1-职业转折-analysis.md     ← 主档：总览（类型/透镜/层级三张分布表）
│                                      + 全部逐问卡片 + 模式观察 + 练习
├── 2026H1-职业转折-analysis.html    ← 单文件静态页，零外部依赖，双击即开、可直接分享
└── index.md                        ← 跨周期累积：原则库（去重聚类）+
                                       透镜使用台账 + 你的"易展开/易防御"话题
```

**模式观察**只写数据真支撑的：哪条线被追到五层、哪条一触即收（收得早是判断对了还是放过了）；哪种透镜在你身上最撬得开；翻回答找**被放过的强信号**（"该问没问"的矿藏）；开放式 vs 挑战式在你身上的打开率差异；**收口合规**——每个收口动作是否都出现在你说"就到这里"之后（remeet-me"停止权在你"规则的执行质检）。

## 安装

先装 remeet-me（必需），再装 why-ask-that——把两个仓库 clone 到你的 agent skills 目录：

```bash
git clone https://github.com/T2lighter/remeet-me.git <skills目录>/remeet-me
git clone https://github.com/T2lighter/why-ask-that.git <skills目录>/why-ask-that
```

各 runtime 的 skills 目录（`~` 在 Windows 即 `%USERPROFILE%`）：

| Runtime | Skills 目录 |
|---|---|
| Claude Code | `~/.claude/skills/` |
| Codex | `~/.codex/skills/` |
| Cursor | `~/.cursor/skills/` |
| 其他 skills-compatible runtime | 见各自文档，装法相同 |

装好后正常用 remeet-me 采访即可，日志默认开启。访谈结束后问一句"为什么这么问"，或对它"要不要跑一份提问分析"的提议说"好，跑吧"，本技能自动触发。

## 边界

- 只分析**提问技艺**，不分析你本人——"挑战式问法在这个话题上两次遇防御"可以写，"你是个防御型的人"不可以。定义权在你手里。
- 日志不存在（没做过 remeet-me / 关了日志 / 旧周期）就如实说明，不反推对话。
- 发现"该问没问"的强信号，写成练习和观察，不怂恿你回去重开访谈。
- 发现疑似硬造的日志条目（为凑格式编的弃用/权重）如实指出——宁缺毋假。

## License

[MIT](./LICENSE) © T2lighter
