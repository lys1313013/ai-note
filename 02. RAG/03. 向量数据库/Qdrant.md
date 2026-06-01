# Qdrant

Qdrant 是用 Rust 编写的高性能向量数据库，主打低延迟、生产级。

## 启动

```bash
docker run -d -p 6333:6333 -p 6334:6334 qdrant/qdrant
```

## 端口

- **6333** — REST API
- **6334** — gRPC API
- 访问 Web Dashboard：http://localhost:6333/dashboard

## 核心特性

- Rust 实现，性能优异
- 内置 HNSW 索引
- 支持 payload 过滤（标量字段）
- 支持稀疏向量（BM42）
- 支持 named vectors（一条记录多个向量）
- 提供云服务（Qdrant Cloud）

## Python SDK

```python
from qdrant_client import QdrantClient
from qdrant_client.models import PointStruct, VectorParams, Distance

client = QdrantClient(url="http://localhost:6333")

# 创建 collection
client.create_collection(
    collection_name="my_docs",
    vectors_config=VectorParams(size=768, distance=Distance.COSINE),
)

# 插入
client.upsert(
    collection_name="my_docs",
    points=[
        PointStruct(id=1, vector=[0.1]*768, payload={"text": "hello"}),
        PointStruct(id=2, vector=[0.2]*768, payload={"text": "world"}),
    ],
)

# 检索
hits = client.search(
    collection_name="my_docs",
    query_vector=[0.15]*768,
    limit=5,
)
```

## 与 Milvus 对比

| 维度 | Qdrant | Milvus |
|------|--------|--------|
| 语言 | Rust | Go + C++ |
| 性能 | 非常高 | 高 |
| 分布式 | 较简单 | 完善 |
| 生态 | 较新 | 成熟 |
| 部署 | 单二进制 | 需 etcd + MinIO 等 |

## 相关

- [Qdrant 官方文档](https://qdrant.tech/documentation/)
- [[Milvus/01. 概念|Milvus]]
- [[weaviate]]
