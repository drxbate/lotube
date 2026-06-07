# LoTube · 让 AI 触手可及

> **AI 聚合平台** —— 人民币直充，微信扫码 / 邮箱登录即可使用。
> 首次登录即送 **¥10 抵用券**，**6/7 抢先体验**。
> 官网：**https://lotube.letsdeep.com**

---

## 我们做这件事的初衷

希望让更多人能享受到这一波 AI 的红利，而不是被各种坑劝退。

我们看到很多开发者朋友想用 AI，却被充值链路、汇率、token 黑盒、计费不透明、模型莫名降智这些问题拦住。

**LoTube 想把这些事情变简单。**

```
你（人民币充值 → 账户余额）
   ↓
LoTube（AI 聚合平台）
   ↓ 按实际用量结算
GPT / Claude / DeepSeek / GLM / Kimi / 智谱 等模型
```

## 我们想做到的几件事

### 1. 人民币直充

- 支付宝 / 微信 / 银行卡
- 1 元起充
- 实时到账，余额永不过期

### 2. 用多少算多少（不藏）

我们不希望用户在月底才看账单。每次调用前能看到预估费用，调用后能看到实际扣费。**每一分钱花在哪都看得见。**

### 3. 直连算力集群

不走三方转售，**每一分钱进模型**。

### 4. 锁定模型

今天是 GPT-4o，明天还是 GPT-4o。**不会莫名其妙降智**。

### 5. 多维计量（不只 token）

| 计量 | 场景 | 示例 |
|------|------|------|
| Token | 文本生成 | DeepSeek ¥0.001/1K |
| 按次 | API 调用 | ¥0.01/次 |
| 按时长 | 音频 / 视频 | ¥0.10/秒 |
| 按页 | PPT / 图片 | ¥0.50/页 |

### 6. 协议兼容 —— 已有项目 0 迁移

OpenAI / Anthropic / Gemini / Responses API 4 套协议，改一行 `base_url` 就能切过来。

## 6/7 抢先体验

**不用申请，不用审核，登录即用**：

- 访问 [lotube.letsdeep.com](https://lotube.letsdeep.com)
- **微信扫码** 或 **邮箱登录**
- 首次登录自动送 **¥10 抵用券**（直接到账）
- 同时下发 **API key**

整个流程 **5 秒** 搞定。

## 快速开始（拿到 API key 后）

```python
import openai

client = openai.OpenAI(
    api_key="YOUR_LOTUBE_KEY",
    base_url="https://api.lotube.letsdeep.com/api",
)

resp = client.chat.completions.create(
    model="deepseek-chat",
    messages=[{"role": "user", "content": "用一句话介绍 LoTube"}],
)
print(resp.choices[0].message.content)
```

## 用户福利（抢先体验用户专享）

- 首次登录即送 **¥10 抵用券**
- 优先接入新模型（**24 小时内** LoTube 上线）
- 1v1 技术支持（**7×12** 小时响应）
- 抢先体验结束**保留账户 + 余额**

## 路线图

| 阶段 | 周期 | 目标 |
|------|------|------|
| 抢先体验 | 30 天 | 验证流程、稳定服务 |
| 开放测试 | 30 天 | 性能调优 |
| 全面开放 | 60 天 | 智能运维 |

## 加入我们

| 角色 | 入口 |
|------|------|
| **抢先体验** | https://lotube.letsdeep.com（微信扫码 / 邮箱登录）|
| **API 文档** | https://lotube.letsdeep.com/docs |
| **GitHub 仓库** | https://github.com/drxbate/lotube |
| **Issues** | https://github.com/drxbate/lotube/issues |
| **商务合作** | business@lotube.letsdeep.com |

---

<div align="center">

**希望更多人能享受这一波 AI 红利，而不是被各种坑劝退。** —— LoTube Team

[官网](https://lotube.letsdeep.com) · [API 文档](https://lotube.letsdeep.com/docs) · [Issues](https://github.com/drxbate/lotube/issues)

</div>
