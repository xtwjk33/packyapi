# PackyAPI 评测：注册送 $1、首充 9 折，国内用 Claude Code / Codex 最省心的 API 中转

想在国内跑 Claude Code 或者 Codex，多半得先过三道坎：翻墙、绑海外信用卡、祈祷账号别被封。折腾一圈下来，可能代码一行没写，先把自己累成狗了。

PackyAPI（原名 PackyCode）就是专门来解决这件事的。简单说就是一个 AI API 聚合中转平台，你不需要出墙、不需要海外卡，直接人民币充值，就能正常调用 Claude、Codex、Gemini 等主流模型。而且注册就送 $1 余额，首次充值还有 9 折优惠——试错成本基本为零。

👉 [免费注册 PackyAPI，领取 $1 体验余额](https://www.packyapi.com/register?aff=YuAi)

<img width="2718" height="1539" alt="image" src="https://github.com/user-attachments/assets/c93a3815-b5df-4bdf-8081-c870799705d6" />

---

## PackyAPI 到底解决了什么问题

说白了，自己搭 API 中转当然可以——买台海外服务器、搞定账号、处理网络抖动，理论上没啥问题。但用起来之后会发现，麻烦的从来不是搭环境，是**维护**。

PackyAPI 的做法是把运维这件事整个包圆：稳定性、渠道兜底、缓存优化、计费统一，你只需要注册、充值、填个 base_url，然后开始写代码就行。

目前平台支持的主力场景：

- **Claude / Claude Code**：Anthropic 官方渠道、AWS 正规渠道，多分组可选
- **Codex / GPT-5 系列**：OpenAI Codex，另有独立包月站
- **Gemini CLI**：逆向自 Google Antigravity IDE，价格有优势
- **其他模型**：Azure GPT 分组、多种实验性渠道

模型分组超过 27 种，计费倍率各不相同，最低可以拿到 5 折价格。

---

## 充值规则和费用怎么算

主站采用**按量付费**模式，充值比例是 **1 元人民币 = 1 美元额度**，计费标准直接对标 Claude / OpenAI 官网原价，没有额外折算。

这个汇率换算下来比直接充 Anthropic 官网便宜不少——官网需要绑海外卡，还有汇损，折算下来综合成本要高一截。

### 主要优惠

| 优惠类型 | 内容 |
|---------|------|
| 注册赠金 | 直接送 $1 余额，可用于按量消费 |
| 首充折扣 | 使用优惠码 `cc-switch` 享首充 9 折（Stripe 付款页面填入） |
| $1 余额等值 | ≈ Codex $10 用量 / Claude Code $2 用量 |

> 注意：首充折扣仅限从未充值过的新用户，填在 Stripe 付款页的优惠券栏位即可。

👉 [立即注册，首充用「cc-switch」享 9 折](https://www.packyapi.com/register?aff=YuAi)

---

## 各分组对比：我该选哪个？

这是很多新用户进来最容易懵的地方，整理一下核心分组的区别：

| 分组 | 适用场景 | 价格 | 稳定性 | 备注 |
|------|---------|------|--------|------|
| **CC 分组** | Claude Code 专用 | 官网同价 | ⭐⭐⭐⭐⭐ | 不能接第三方工具（Cline 等），违规封号退款 |
| **AWS 分组** | 高稳定性需求 | 稍贵 | ⭐⭐⭐⭐⭐ | 亚马逊官方渠道购买，适合生产环境兜底 |
| **AWS-Q 分组** | 省钱日常使用 | 极低 | ⭐⭐⭐ | 200K 上下文，支持思考模式，偶发 422 报错 |
| **Codex 分组** | Codex 专用 | 按量计费 | ⭐⭐⭐⭐ | 可接第三方工具；另有独立包月站 |
| **Antigravity 分组** | Gemini CLI | 有折扣 | ⭐⭐⭐⭐ | 逆向自 Google 最新 IDE |
| **Azure 分组** | GPT 系列 | 稍便宜 | ⭐⭐⭐ | 5 分钟缓存，随时可能下架 |

简单记忆规则：
- **用 Claude Code → CC 分组**，稳定第一
- **要省钱 → AWS-Q 分组**，日常够用
- **用 Codex → Codex 分组**，或上包月站

---

## Codex 包月站是什么

除了主站按量付费，PackyAPI 旗下还有 Codex 独立包月站（`codex.packycode.com`）。

- 每人每月限购一枚激活码，售价 **¥60**
- 超出限购后按 **¥80** 一枚
- 包月站的 base_url 和主站不一样，配置时注意区分

如果你 Codex 用量大，包月站的性价比更划算；偶尔用的话，主站按量消费更灵活。

---

## 怎么配置 Claude Code 接入

配置本身不复杂，找到 Claude Code 的 `settings.json` 文件，添加以下内容：

json
{
  "env": {
    "ANTHROPIC_BASE_URL": "https://www.packyapi.com",
    "ANTHROPIC_AUTH_TOKEN": "你的API Key",
    "CLAUDE_CODE_ATTRIBUTION_HEADER": "0"
  }
}


API Key 在注册后的控制台里创建令牌时选 CC 分组就能拿到。

如果觉得手动改配置文件麻烦，官方推荐配合 **CC-Switch** 这个开源桌面工具使用——图形界面操作，一键切换 API 配置，内置了 PackyAPI 的配置模板，对新手相当友好。

👉 [注册 PackyAPI，按步骤配置完成即可开用](https://www.packyapi.com/register?aff=YuAi)

---

## 平台口碑怎么样

从 Linux DO、V2EX、Telegram 频道等开发者社区的反馈来看，PackyAPI 的整体评价还不错，有人说是"目前稳定性排在第一梯队的 Claude Code 中转服务之一，文档很有用心的感觉"。

比较被提到的优点：

- **缓存优化做得扎实**：对 Codex 的缓存优化比较激进，官方数据是 $60 额度能覆盖约 1500～2500 次任务，实际用下来 token 消耗确实比自建低
- **文档写得清楚**：Claude Code、Codex、Gemini CLI 的配置教程都有，按步骤走不会出错
- **客服有人**：TG 频道 @Packycode 和 QQ 售后群都有，响应速度算快的

当然也有要注意的地方：CC 分组不能接第三方工具（Cline、OpenCode 等），这是平台为了维护号池稳定做的限制，踩了会封号退款，用之前记清楚。

---

## 总结：适合谁用

**很适合：**
- 国内开发者，想本地跑 Claude Code / Codex，不想折腾翻墙和海外卡
- 多模型切换需求，想用统一入口管 Claude、GPT、Gemini
- 刚开始探索 AI 编程，想低成本试试水

**不太适合：**
- 已经有稳定的海外账号体系和自建中转，运维成本可控的团队

新用户注册本身有 $1 余额直接可用，首充再叠个 9 折，进来试一圈的成本很低。不妨先跑跑看效果，再决定要不要长期用。

👉 [注册 PackyAPI，免费领 $1 体验额度](https://www.packyapi.com/register?aff=YuAi)
