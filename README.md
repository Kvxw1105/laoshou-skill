# 老手 · Laoshou — Agent 的现实眼力

**A portable agent skill for seasoned judgment: orient before acting, verify the money, test small, keep score.**

给 Personal Agent 装的不是人格，是一套看世界的顺序：**先定向 → 会验货 → 敢试单 → 记烂账**。

## 为什么做这个

同一个问题问四个顶级模型，答案的骨架惊人地一致：高手与普通人的差距不在知识，在判断的四个节点上执行的纪律——定向时先找反例、验货时追付费方、行动时先算最坏损失、事后拿结算而不是拿感觉校准。这个项目把这套纪律蒸馏成一份**以语言为主体**的 Skill：因为对语言模型来说，语言不只是表达，语言就是思维的轨道。

它刻意不做的事：

- 不建人格库。64 个原型互相交接，是失败率最高的架构；原型只配当视角，不配当 Agent。
- 不搞流程制度。三张卡、五道门禁跑不动就是废纸；这里只有一张五项的机会条，其余全是本能。
- 不承诺能力提升。Skill 有没有用，靠装上它的 Agent 在真实任务里的结算记录说话，不靠 README 说话。

## 与 edge-operator 的分工

| | edge-operator | laoshou（本项目） |
|---|---|---|
| 管什么 | 执行：找需求、算单位经济、多 Agent 协作、全链路兑现；v1.2 起内置完整校准后端（概率冻结、Brier 评分、原子生命周期、脚本） | 判断入口：看局的顺序、证据的等级、下注的纪律；手工盘口账只是无脚本环境下的最小版 |
| 形态 | 主系统（playbooks + 脚本 + 模板） | 轻量触发器（一份主 Skill + 速查 + 判例，纯语言、零依赖） |
| 关系 | 可叠加：先用 laoshou 判断值不值得做，再用 edge-operator 把它做成、算清账 | 同左 |

**定位修正（v0.1.1，2026-11-21）**：本项目 v0.1.0 的评审基于 edge-operator v1.1.0；v1.2.0 已补齐判断校准回路，laoshou 不再自称独立的结算体系。它真实的位置是**前置的轻量判断触发器**：管机会进入评估之前的那几秒（先定向、先分清托与跟风、先问为什么轮到我），以及在没有脚本、没有 Skill 系统的模型上靠纯语言生效。主系统选 edge，入口用 laoshou。两者谁更强，不靠 README 吵，靠同题对打的结算记录（见 CHANGELOG 的待办）。

## 目录

| 路径 | 内容 |
|---|---|
| `SKILL.md` | 主体：四样本事 + 说话规矩 + 边界，纯语言，无流程 |
| `references/atoms.md` | 20 枚思维原子速查（土名版），每枚一行，按战绩进出 |
| `references/cases.md` | 已核验判例集：每个案例标注口径与核验状态，禁止引用未核数字 |
| `templates/opportunity-note.md` | 唯一的结构：五项机会条 |
| `templates/ledger.md` | 盘口账格式：判断、把握、结算日、结果、归因 |
| `prompts/MASTER_PROMPT.txt` | 给不支持 Skill 的模型（Muse、Grokbot、手机 Agent 等）粘贴的完整版 |
| `prompts/QUICK_START.txt` | 上下文受限时用的极简版（四句问话 + 三种钱 + 五级证据） |

## 用法

- **支持 Skill 的 Agent**：克隆本仓库，把 Agent 的 skill 管理指向 `SKILL.md`。
- **纯提示词 Agent**：粘贴 `prompts/MASTER_PROMPT.txt` 作为长期指令；上下文紧时用 `QUICK_START.txt`。
- 提示词不授予工具、账号或权限；授权范围由使用方另行设定。

## 维护规则

1. 原子进出看战绩：在真实任务里被结算证明有用才留下，反复误导判断的降级或删除，并记入 CHANGELOG。
2. 判例只收核验过的：数字必须有出处与口径；核验状态变化要更新，不许让过期数字冒充现行事实。
3. 主 Skill 只增本能、不增流程：任何让 Agent 变慢、变怯、变成填表机器的修改，默认拒绝。

MIT License. Attribution: Kvxw1105, 2026.
