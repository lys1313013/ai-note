


```
export LANGFUSE_PUBLIC_KEY="pk-lf-24694c07-7991-404b-b0b7-9e183343d4e4"
export LANGFUSE_SECRET_KEY="sk-lf-6f14386e-a6fc-40cb-b9a9-71cb9e27ae98"
export LANGFUSE_BASE_URL="http://localhost:3000"

CURRENT_TIME=$(date -u +"%Y-%m-%dT%H:%M:%SZ")
RANDOM_ID=$(uuidgen || echo $RANDOM)

echo "Executing curl with ID: trace-${RANDOM_ID}"

curl -s -X POST "${LANGFUSE_BASE_URL}/api/public/ingestion" \
  -u "${LANGFUSE_PUBLIC_KEY}:${LANGFUSE_SECRET_KEY}" \
  -H "Content-Type: application/json" \
  -d '{
    "batch": [
      {
        "id": "event-'"${RANDOM_ID}"'",
        "type": "trace-create",
        "timestamp": "'"${CURRENT_TIME}"'",
        "body": {
          "id": "trace-'"${RANDOM_ID}"'",
          "name": "curl-robust-trace",
          "userId": "test-user-123",
          "sessionId": "session-123",
          "environment": "dev",
          "input": "This is a robust curl test!",
          "output": "It should show up immediately.",
          "tags": ["curl-test"]
        }
      }
    ]
  }'

echo -e "\nWaiting 2 seconds for worker to process..."
sleep 2

echo "Verifying trace was created via API:"
curl -s -X GET "${LANGFUSE_BASE_URL}/api/public/traces/trace-${RANDOM_ID}" \
  -u "${LANGFUSE_PUBLIC_KEY}:${LANGFUSE_SECRET_KEY}"

```