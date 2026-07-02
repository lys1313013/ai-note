


```
export LANGFUSE_PUBLIC_KEY="pk-lf-24694c07-7991-404b-b0b7-9e183343d4e4"
export LANGFUSE_SECRET_KEY="sk-lf-6f14386e-a6fc-40cb-b9a9-71cb9e27ae98"
export LANGFUSE_BASE_URL="http://localhost:3000"

curl -X POST "${LANGFUSE_BASE_URL}/api/public/ingestion" \
  -u "${LANGFUSE_PUBLIC_KEY}:${LANGFUSE_SECRET_KEY}" \
  -H "Content-Type: application/json" \
  -d '{
    "batch": [
      {
        "id": "event-uuid-001",
        "type": "trace-create",
        "timestamp": "2026-07-02T12:00:00.000Z",
        "body": {
          "id": "trace-uuid-001",
          "name": "curl-test-trace",
          "userId": "test-user-123",
          "sessionId": "session-123",
          "input": "Hello from curl!",
          "output": "Success!",
          "tags": ["curl"]
        }
      }
    ]
  }'
```