# Notification Service

## 1. Requirements
### Functional
- Send notifications via email and in-app
- Support scheduled and event-driven notifications

### Non-Functional
- High availability
- At-least-once delivery
- Low latency for real-time notifications

---

## 2. High-Level Architecture
- API Gateway
- Notification Service
- Message Queue (RabbitMQ)
- Worker Services
- Database

---

## 3. Data Model
- Notification(id, user_id, type, status, created_at)
- UserPreferences(user_id, channels)

---

## 4. API Design
POST /notifications  
GET /notifications/{userId}

---

## 5. Scaling Strategy
- Horizontal scaling of workers
- Queue-based load leveling
- Partitioning by user_id

---

## 6. Failure Handling
- Retry with exponential backoff
- Dead-letter queues
- Idempotent message processing

---

## 7. Trade-offs
- Eventual consistency vs real-time guarantees
- At-least-once delivery vs duplicates
