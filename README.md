# 老手 · Laoshou v0.2.0

**A portable agent skill for commercial instinct: find money, sell what you have, test in the market, and keep score.**

给 Personal Agent 装上现实眼力，也装上主动经营的本能。不是 64 个人格，不是一个只会挑错的专家委员会。会看局、找货、组货、摆摊、吆喝、接钱、养摊、记烂账。

v0.1.x 的四样本事（定向、验货、试单、记账）保留；v0.2.0 修正只擅长判断已有机会、却不主动创造交易的缺口。低风险行动优先于漫长研究，重要决策仍需证据。行为改善有待对照实验，不宣称已提高收入。

## 使用

- 支持 Skill：将仓库作为 laoshou 技能目录，入口 `SKILL.md`；ChatGPT 元数据在 `agents/openai.yaml`。
- 纯提示词 Agent：直接粘贴 `prompts/MASTER_PROMPT.txt`，不依赖其他文件；上下文受限用 `prompts/QUICK_START.txt`。
- 经营任务示例：“从现有资产里挑一个可以卖的东西，做出今天能拿出去的真实商品与报价”；“把刚完成的开源项目转成有真实价值的公开内容，并为可能的付费需求做一个承接”；“这条 X 赚钱帖子到底是谁在付钱，能否低成本验证一个有权做的机会？”

## 文件

| 路径 | 内容 |
|---|---|
| SKILL.md | 核心经营本能、判断与执行规则 |
| prompts/ | 与主入口同步的完整版与极简版 |
| references/atoms.md | 按触发场景调用的思维原子 |
| references/fieldbook.md | 从盘货、摆摊、内容到结算的实战手册 |
| references/cases.md | 历史判断案例，含复核状态 |
| references/market-cases.md | 可追溯市场样本与边界 |
| references/evaluation.md | 回归场景、对照实验和实际效果验收 |
| templates/ | 可选的机会条与结算账 |
| agents/openai.yaml | 安装入口元数据 |

## 与其他商业 Skill 的关系

Laoshou 负责经营意识与前置判断；Consumer Demand Arbitrage 负责从消费和市场需求反推产品；Edge Operator 负责更复杂的执行、实验与校准。已有后端时不另造后端，简单经营任务不强制串联三个 Skill。

## 维护

改行为规则必须同步三个入口及相关原子/模板。案例必须区分第一手、自述、二手、假设与未复核。可验证结果比文档规模重要；真实市场验证前不宣称能力提高。公共版本不写入私人账号、凭证、客户数据或经营秘密。

MIT License. Attribution: Kvxw1105, 2026.
