# LoTube · 让 LLM 像水电一样按用量付费

> **AI 基础设施消费平台** — 人民币充值，按 Token / 次数 / 时长 / 页数计费，调用 GPT / Claude / DeepSeek / GLM 等主流大模型。
> 官网：**https://lotube.letsdeep.com**

---

## 为什么做 LoTube？

全球 LLM API 市场年增速 60%+，但**中国开发者用 AI 仍然很难**：

- 海外平台**充值链路复杂**（信用卡 + 翻墙 + 汇率不透明）
- **汇率波动**让成本不可控
- 不知道**实际花了多少**（很多平台按 token 计费但 token 含义不透明）
- 个人开发者 / 中小企业**没有议价权**

**LoTube 的解法：人民币直充 + 多维计量 + 明码标价。**

```
你（人民币充值 → 账户余额）
   ↓
LoTube（AI 消费平台，多维计量，自主定价）
   ↓ 实际用量 × 单价结算
底层算力层（Frey 兜底，按 RMB 结算）
   ↓
GPT / Claude / DeepSeek / GLM / Kimi / 智谱 等模型
```

## 核心特性

### 1. 人民币直充

- 支付宝 / 微信 / 银行卡
- 1 元起充，**无汇率风险**
- 实时到账，余额永不过期

### 2. 多维计量（不是只按 Token！）

| 类型 | 场景 | 示例定价 |
|------|------|---------|
| **Token** | 文本生成 | DeepSeek ¥0.001/1K tokens |
| **按次** | API 调用 | ¥0.01/次 |
| **按时长** | 音频 / 视频 | ¥0.10/秒 |
| **按页** | PPT / 图片生成 | ¥0.50/页 |

不同模型单价不同，**全平台明码标价**。

### 3. 自主定价

LoTube 自有定价权，**差价 = 用户支付价 - 底层采购价**（固定，公开）。
不靠 token 隐藏利润，**每一分钱花在哪都看得见**。

### 4. 全人群覆盖

| 用户类型 | 适合套餐 |
|---------|---------|
| 个人开发者 | 充值即用，按量计费 |
| 创业团队 | 月度账单，成本可控 |
| 中小企业 | 团队子账号，权限分级 |
| AI 重度用户 | 多模型切换，性价比最优 |

## 第 1 期 · 开放公测（6/8 上线）

**免注册登录 + 自动赠券**：

- 访问 [lotube.letsdeep.com](https://lotube.letsdeep.com)
- **微信扫码** 或 **邮箱登录** 即可使用
- 首次登录自动送 **¥10 体验券**（直接到账）
- 登录后即拿到 **API key**，**不用申请、不用等审核**

### 快速开始

1. 打开 [lotube.letsdeep.com](https://lotube.letsdeep.com)
2. 点"立即免费试用" / "登录"
3. 选 **微信扫码** 或 **邮箱登录**（邮箱首次登录会自动注册）
4. 进控制台，¥10 体验券已到账 + API key 已生成

**整个流程 30 秒搞定**。

## 快速开始（拿到 API key 后）

```python
import openai

client = openai.OpenAI(
    api_key="YOUR_LOTUBE_KEY",
    base_url="https://api.lotube.letsdeep.com/v1",  # 兼容 OpenAI 协议
)

resp = client.chat.completions.create(
    model="deepseek-chat",
    messages=[{"role": "user", "content": "用一句话介绍 LoTube"}],
    max_tokens=200,
)
print(resp.choices[0].message.content)
# 费用: 1.2K tokens × ¥0.001/1K = ¥0.0012
```

**完全兼容 OpenAI / Anthropic 协议**——一行 `base_url` 改指向，**已有项目零迁移**。

## 路线图

| 阶段 | 周期 | 目标 | 状态 |
|------|------|------|------|
| 第 1 期 · 内测 | 30 天 | 100 注册 / 20 复购 | **6/8 开放** |
| 第 2 期 · 开放测试 | 30 天 | 500 注册 / 100 复购 | Q3 2026 |
| 第 3 期 · 全面开放 | 60 天 | 1000 注册 / 500 复购 | Q4 2026 |
| 第 4 期 · 智能运维 | — | AGENT 运维 | 2027 |

## 技术栈（开源计划）

- **前端**：Vue 3 + TypeScript
- **后端**：Go + Gin
- **计费**：自研多维计量引擎（Token / 次数 / 时长 / 页数）
- **协议兼容**：OpenAI / Anthropic / Gemini / Responses API
- **算力层**：自建 + 合作（包含 Frey 等供应商）

后续会**逐步开源**核心计费与计量模块，**先商用 → 再开源**。

## 加入我们

| 角色 | 联系方式 |
|------|---------|
| **官网登录** | https://lotube.letsdeep.com （微信扫码 / 邮箱登录） |
| **商务合作** | business@lotube.letsdeep.com |
| **媒体咨询** | press@lotube.letsdeep.com |
| **GitHub Issues** | [本仓库 issues](https://github.com/drxbate/lotube/issues) |
| **微信群** | 登录后在控制台首页扫码加入 |

## License

平台本体暂不开源（商业产品）。
**API SDK 客户端**：MIT（后续开源）。
本文档：CC BY-SA 4.0。

---

<div align="center">

**让 AI 消费像扫码支付一样简单。**

[官网登录](https://lotube.letsdeep.com) · [API 文档](https://lotube.letsdeep.com/docs) · [Issues](https://github.com/drxbate/lotube/issues)

</div>
