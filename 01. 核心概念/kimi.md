# Kimi

月之暗面（Moonshot AI）推出的智能助手产品。

## 入口

- 官网：https://www.kimi.com
- 代码助手：https://www.kimi.com/code/console

## 核心能力

- **长上下文** — 早期主打 200K 上下文窗口
- **文件解析** — PDF、Word、Excel、PPT、图片
- **联网搜索** — 实时信息获取
- **代码助手** — Kimi Code 编程辅助
- **深度研究** — 自动多轮检索 + 综合

## 主要产品线

- **Kimi 智能助手** — 通用对话
- **Kimi K2** — 编程与 Agent 能力强
- **Kimi 视觉** — 图像理解

## API

兼容 OpenAI 接口，base_url 替换即可：

```python
from openai import OpenAI
client = OpenAI(
    api_key="sk-xxx",
    base_url="https://api.moonshot.cn/v1",
)
resp = client.chat.completions.create(
    model="moonshot-v1-8k",
    messages=[{"role": "user", "content": "你好"}],
)
print(resp.choices[0].message.content)
```

## 相关

- [月之暗面官网](https://www.moonshot.cn)
- [[05. 大模型/01. 基础理论/05. 术语|术语]] — LLM 相关术语
