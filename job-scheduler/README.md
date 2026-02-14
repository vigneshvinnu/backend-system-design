# Distributed Job Scheduler

## 1. Requirements

### Functional
- Schedule jobs to run at specific times
- Support recurring and one-time jobs
- Allow job execution retries

### Non-Functional
- High reliability
- Fault tolerance
- Idempotent execution
- Scalability

---

## 2. High-Level Architecture
- Scheduler Service
- Job Metadata Store
- Message Queue
- Worker Nodes

---

## 3. Data Model
- Job(id, type, schedule_time, status, retry_count)
- JobExecution(job_id, execution_time, status)

---

## 4. API Design
POST /jobs  
GET /jobs/{jobId}

---

## 5. Scaling Strategy
- Partition jobs by execution time
- Distribute jobs via message queues
- Scale workers horizontally

---

## 6. Failure Handling
- Retry jobs with exponential backoff
- Ensure idempotent job execution
- Reassign jobs if worker crashes

---

## 7. Trade-offs
- Time-based polling vs event-driven execution
- Exactly-once execution vs system complexity
