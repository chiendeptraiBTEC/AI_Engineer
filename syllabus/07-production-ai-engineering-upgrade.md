# Module 7 — Production AI Engineering Upgrade

> Đây là phần **nâng cấp sau khi đã có DA4/RAG chạy end-to-end**. Không học trước chỉ để tích công nghệ.

Mục tiêu: biến một AI prototype thành hệ thống có thể giải thích, test, quan sát và vận hành tốt hơn.

---

## 1. Backend & Data Layer

### Chủ đề

- FastAPI service boundaries.
- Async I/O và concurrency.
- Streaming response cho LLM.
- PostgreSQL cho metadata, users, conversations, documents.
- Redis cho cache/rate-limit/session khi có nhu cầu thực tế.
- Background jobs/queue cho ingestion hoặc tác vụ dài.

### Bài thực hành

- Tách RAG prototype thành API service.
- Thêm streaming chat.
- Lưu metadata/conversation có schema rõ.
- Đo latency trước và sau cache; chỉ giữ cache nếu có lợi ích đo được.

### Gate

- API có schema validation.
- Timeout và error response rõ.
- Không block event loop bằng workload không phù hợp.
- Có integration test cho endpoint quan trọng.

---

## 2. Reliability

### Chủ đề

- timeout;
- retry với exponential backoff;
- circuit-breaker concept;
- idempotency;
- rate limiting;
- graceful degradation;
- dependency failure.

### Bài thực hành

Chủ động mô phỏng:

- LLM provider timeout;
- vector DB lỗi;
- document parsing fail;
- rate limit từ upstream;
- request duplicate.

### Gate

README phải mô tả ít nhất 3 failure modes và cách hệ thống xử lý.

---

## 3. Observability

### Tối thiểu log/đo

- request ID;
- latency end-to-end;
- retrieval latency;
- LLM latency;
- error rate;
- token usage/cost nếu applicable;
- model/provider/version;
- feedback signal.

### Tracing

Một request nên có thể lần theo:

```text
request
  → query preprocessing
  → retrieval
  → rerank
  → prompt construction
  → LLM call
  → response
```

Không log API key hoặc dữ liệu nhạy cảm.

---

## 4. RAG Evaluation as Engineering

### Eval dataset

Tạo dataset có:

- question;
- expected evidence/source;
- expected answer hoặc rubric;
- category/difficulty;
- câu ngoài phạm vi.

### Retrieval

Theo dõi metric phù hợp như:

- recall@k / hit@k;
- MRR/nDCG nếu cần;
- retrieval latency.

### Generation

Theo dõi:

- correctness/relevance;
- groundedness;
- citation correctness;
- refusal/out-of-scope behavior;
- latency/cost.

### Regression

Khi đổi:

- chunk size;
- embedding model;
- search strategy;
- reranker;
- prompt;
- model;

phải chạy lại eval suite và lưu kết quả.

Không merge thay đổi chỉ vì “test vài câu thấy hay hơn”.

---

## 5. AI Security

### Threat model cơ bản

Hệ thống LLM/RAG có thể gặp:

- direct prompt injection;
- indirect prompt injection trong document/web content;
- data exfiltration;
- cross-user/cross-tenant retrieval;
- unsafe tool calls;
- privilege escalation qua agent/tool;
- malicious file/input;
- secret leakage qua log/prompt.

### Nguyên tắc

- LLM output là **untrusted input** khi dùng để gọi tool.
- Authorize ở server/tool layer, không dựa vào system prompt.
- Validate mọi tool parameter.
- Dùng allowlist cho action nguy hiểm.
- Tách dữ liệu theo user/tenant bằng filter enforce ở backend.
- Không đưa secret vào prompt nếu không cần.

### Security tests tối thiểu

- [ ] “Ignore previous instructions” direct injection.
- [ ] Document chứa instruction độc hại.
- [ ] User A cố truy vấn document User B.
- [ ] Agent cố gọi tool ngoài quyền.
- [ ] Input quá lớn / malformed.
- [ ] Output model tạo tool argument sai schema.

---

## 6. Load & Cost Engineering

### Đo trước khi tối ưu

Chạy load test nhỏ và quan sát:

- p50/p95 latency;
- throughput;
- error rate;
- connection/resource bottleneck;
- cost/request.

### Câu hỏi phải trả lời

1. Bottleneck hiện tại là retrieval, database hay LLM?
2. Cache phần nào an toàn và hiệu quả?
3. Nếu traffic tăng 10×/100×, thành phần nào hỏng trước?
4. Có cần queue hay chỉ đang over-engineer?

---

## 7. CI/CD & Quality Gate

Pipeline tối thiểu:

```text
push / pull request
  ↓
lint / format
  ↓
unit tests
  ↓
integration tests
  ↓
selected eval regression
  ↓
build image
```

Không cần đưa toàn bộ expensive LLM eval vào mỗi commit; có thể chạy small deterministic/sampled suite trong CI và full eval thủ công hoặc theo release.

---

## 8. Definition of Done

Hoàn thành phần nâng cấp khi flagship project có:

- [ ] API/service architecture rõ.
- [ ] Docker + reproducible setup.
- [ ] Persistent storage nếu bài toán cần.
- [ ] Test suite.
- [ ] Eval dataset + baseline + regression results.
- [ ] Structured logs/tracing cơ bản.
- [ ] Timeout/retry/error handling.
- [ ] Security test cho prompt injection/tool/data isolation.
- [ ] Latency/cost measurement.
- [ ] CI chạy quality gate.
- [ ] README ghi rõ trade-offs và scaling plan.

> Mục tiêu không phải nhét Redis/Postgres/queue vào project. Mục tiêu là chứng minh bạn biết **khi nào cần, vì sao cần và đo được tác động**.
