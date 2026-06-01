# Streamable HTTP对接流程

## 1. 调用Streamable HTTP接口

```bash
curl --location 'http://0.0.0.0:25822/mcp' \
--header 'Content-Type: application/json' \
--data '{
    "jsonrpc": "2.0",
    "id": 1,
    "method": "tools/list"
}'
```

**说明**：
- Streamable HTTP 使用单端点 `/mcp` 进行所有通信
- 不再需要 SSE 连接，所有交互通过标准 HTTP POST 请求完成
- 支持流式传输但不强制

## 2. 初始化

```json
{
    "jsonrpc": "2.0",
    "id": 1,
    "method": "initialize",
    "params": {
        "protocolVersion": "2025-03-26",
        "capabilities": {
            "roots": {
                "listChanged": true
            }
        },
        "clientInfo": {
            "name": "Visual Studio Code - Insiders",
            "version": "1.100.0-insider"
        }
    }
}
```

**说明**：
- `protocolVersion`: 指定 MCP 协议版本
- `capabilities`: 客户端能力声明
- `clientInfo`: 客户端信息（名称和版本）

## 3. 初始化完成

```json
{
  "method": "notifications/initialized",
  "jsonrpc": "2.0"
}
```

**说明**：
- 通知服务器客户端已完成初始化
- 这是一个通知消息，不需要 `id` 字段

## 4. 获取工具

```json
{
  "jsonrpc": "2.0",
  "id": 2,
  "method": "tools/list",
  "params": {}
}
```

**说明**：
- 获取 MCP 服务器提供的所有可用工具列表
- 返回工具名称、描述和参数结构

## 5. 调用工具

```json
{
    "jsonrpc": "2.0",
    "id": 3,
    "method": "tools/call",
    "params": {
        "name": "get_user_info",
        "arguments": {
            "userId": "xxxx"
        }
    }
}
```

**说明**：
- `name`: 调用的工具名称
- `arguments`: 工具参数，根据具体工具定义传递

## Streamable HTTP 与 SSE 的主要区别

| 特性 | SSE | Streamable HTTP |
|------|-----|-----------------|
| 端点 | `/sse` 和 `/sse/messages` 双端点 | `/mcp` 单端点 |
| 连接方式 | 需要建立持久 SSE 连接 | 标准 HTTP POST 请求 |
| 传输机制 | POST + SSE 双通道 | HTTP 单通道 |
| 状态管理 | 有状态 | 支持无状态服务器 |
| 流式支持 | 强制 SSE 流式 | 可选流式传输 |
| 基础设施兼容性 | 需要特殊 SSE 支持 | 兼容标准 HTTP 基础设施 |

## 参考资料
- https://www.cnblogs.com/xiao987334176/p/18845151.html
- http://m.toutiao.com/group/7527100355356852774/
- http://m.toutiao.com/group/7539830284129190452/
