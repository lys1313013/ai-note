# SearXNG

开源的元搜索引擎（meta search engine），可自部署、聚合多个搜索引擎结果，保护隐私。

## 核心特性

- 聚合 70+ 搜索引擎（Google/Bing/Baidu/DuckDuckGo 等）
- 完全开源、可自部署
- 无追踪、无广告
- 支持 JSON / RSS / CSV 输出
- 适合作为 AI 工具的搜索后端

## 本地启动（Docker）

```bash
docker run -d --name searxng \
  -p 8888:8080 \
  -v searxng-data:/etc/searxng \
  searxng/searxng
```

访问 http://localhost:8888

## API 调用

### Web 搜索（JSON）

```bash
curl -X POST "http://localhost:8080/search" \
  -d "q=test&format=json&engines=baidu"
```

### GET 形式

```bash
curl "http://localhost:8080/search?q=test&format=json&engines=google,bing"
```

### Python 示例

```python
import requests

def search(query, engines="baidu"):
    resp = requests.get(
        "http://localhost:8080/search",
        params={"q": query, "format": "json", "engines": engines},
    )
    return resp.json()["results"]

for r in search("AI agent"):
    print(r["title"], r["url"])
```

## 在 AI Agent 中使用

SearXNG 经常作为 LangChain / LangGraph Agent 的搜索工具后端：

```python
from langchain_community.utilities import SearxSearchWrapper
search = SearxSearchWrapper(searx_host="http://localhost:8080")
results = search.run("什么是 MCP 协议")
```

## 相关

- [SearXNG 官方文档](https://docs.searxng.org)
- [GitHub 仓库](https://github.com/searxng/searxng)
- [[多智能体]] — 智能体工具调用
