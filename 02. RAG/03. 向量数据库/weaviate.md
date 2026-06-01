# Weaviate

Weaviate 是开源的向量搜索引擎，原生支持向量 + 标量混合检索。

## 启动（Docker）

```bash
# macOS / Linux
docker run -d --name weaviate \
  --restart=always \
  -p 38080:8080 \
  -p 50051:50051 \
  -e AUTHENTICATION_APIKEY_ENABLED=true \
  -e AUTHENTICATION_APIKEY_ALLOWED_KEYS=test-secret-key \
  -e AUTHENTICATION_APIKEY_USERS=test@example.com \
  -e AUTHORIZATION_ADMINLIST_ENABLED=true \
  -e AUTHORIZATION_ADMINLIST_USERS=test@example.com \
  -e WEAVIATE_HOSTNAME=0.0.0.0 \
  semitechnologies/weaviate:latest

# Windows (PowerShell)
docker run -d --name weaviate ^
  --restart=always ^
  -p 38080:8080 ^
  -p 50051:50051 ^
  -e AUTHENTICATION_APIKEY_ENABLED=true ^
  -e AUTHENTICATION_APIKEY_ALLOWED_KEYS=test-secret-key ^
  semitechnologies/weaviate:latest
```

API 接口文档：http://localhost:8080/v1/docs

## 核心特性

- **GraphQL API** — 灵活查询
- **模块化向量** — 内置多种向量化模块
- **混合搜索** — BM25 + 向量检索
- **CRUD 完整** — 数据全生命周期管理
- **多租户** — 企业级支持

## 常见错误

> `java.lang.IllegalArgumentException: no graphql provider present, this most likely because no schema is present. Import a schema first!`

**原因**：未定义 Schema，需先用 API 或客户端创建 Class。

## 启动简化版

```bash
docker run -p 38080:8080 -p 50051:50051 cr.weaviate.io/semitechnologies/weaviate:1.30.0
```

## 相关

- [Weaviate 官方文档](https://weaviate.io/developers/weaviate)
- [Docker 安装文档](https://weaviate.io/developers/weaviate/installation/docker-compose)
- [[Milvus/01. 概念|Milvus]]
- [[Qdrant]]
