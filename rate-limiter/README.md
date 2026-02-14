# Rate Limiter

## 1. Requirements

### Functional
- Limit API requests per client
- Support different rate limits per API
- Enforce limits in real time

### Non-Functional
- Low latency
- High throughput
- Distributed consistency

---

## 2. High-Level Architecture
- API Gateway
- Rate Limiter Service
- Distributed Cache (Redis)

---

## 3. Data Model
- RateLimitKey(client_id, api)
- Counter(key, count, window_start)

---

## 4. API Design
Internal middleware integration

---

## 5. Scaling Strategy
- Use Redis for distributed counters
- Partition keys by client_id
- Apply sliding window or token bucket algorithms

---

## 6. Failure Handling
- Fail-open for non-critical APIs
- Fallback to local counters if Redis is unavailable
- Monitor limit breaches

---

## 7. Trade-offs
- Accuracy vs latency
- Strong consistency vs availability
