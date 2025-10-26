# 🧠 DECISION.md — HNG13 Stage 2

## 🔍 Design Rationale

I chose Docker Compose for orchestration due to its simplicity and native support for multi-container setups. NGINX was configured with upstream failover using `max_fails`, `fail_timeout`, and `backup` directives to ensure seamless switch from Blue to Green.

## 🔧 Failover Strategy

- Blue is the primary upstream
- Green is marked as `backup`
- Failover triggers on timeout or 5xx errors
- NGINX retries within the same client request

## 🧪 Testing Approach

- Used `/chaos/start` to simulate failure
- Verified switch to Green using `/version`
- Ensured headers (`X-App-Pool`, `X-Release-Id`) were preserved

## 🧰 Tools Used

- Docker Compose
- NGINX
- curl for endpoint testing
- envsubst for templating

## 🧼 Idempotency

The setup supports re-runs without breaking. Containers restart cleanly, and NGINX config is regenerated dynamically.

## 🧠 Learnings

This task deepened my understanding of reverse proxy behavior, upstream health checks, and automated failover in production-like environments.
