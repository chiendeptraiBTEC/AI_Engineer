# Portfolio Engineering Standard

Tài liệu này là **quality gate** cho mọi project dùng trong CV/portfolio.

## 1. Project phải chứng minh điều gì?

Một project tốt không chỉ chứng minh “biết dùng thư viện”. Nó phải cho thấy:

- xác định bài toán;
- thiết kế baseline;
- lựa chọn metric;
- thử nghiệm có kiểm soát;
- debug failure case;
- viết code có cấu trúc;
- test và tái lập được;
- hiểu trade-off về chất lượng, latency, cost và complexity.

## 2. README bắt buộc

README của mỗi project nên có:

1. **Problem** — bài toán và người dùng.
2. **Dataset / Inputs** — dữ liệu từ đâu, giới hạn gì.
3. **Architecture** — sơ đồ pipeline/hệ thống.
4. **Baseline** — phiên bản đơn giản đầu tiên.
5. **Experiments** — đã thay đổi gì và vì sao.
6. **Results** — bảng metric, latency/cost nếu phù hợp.
7. **Failure cases** — trường hợp hệ thống làm sai.
8. **How to run** — setup từ máy sạch.
9. **Tests** — chạy test thế nào.
10. **Trade-offs / Next steps** — điều chưa làm và lý do.

## 3. Chuẩn repo tối thiểu

Ví dụ:

```text
project/
├── src/                 # hoặc app/
├── tests/
├── configs/
├── scripts/
├── notebooks/           # chỉ exploratory; logic chính không nằm hết ở notebook
├── .env.example
├── .gitignore
├── README.md
├── pyproject.toml        # hoặc requirements.txt
└── Dockerfile            # khi project cần deploy
```

## 4. Evaluation gate

Không dùng câu “model tốt” hoặc “RAG chính xác hơn” nếu chưa có số đo.

### ML

Tối thiểu:

- baseline;
- train/validation/test split hợp lý;
- metric đúng với bài toán;
- confusion matrix/error analysis nếu classification;
- seed/config để chạy lại.

### RAG / LLM

Tối thiểu nên theo dõi:

- retrieval hit/recall@k hoặc metric tương đương;
- answer correctness/relevance theo eval set;
- groundedness/citation correctness nếu có nguồn;
- latency;
- token/cost khi dùng paid API;
- test câu hỏi ngoài phạm vi.

Mỗi thay đổi lớn như embedding model, chunk size, reranker, prompt hay LLM phải được so với baseline.

## 5. Security gate cho AI app

Trước khi gọi một app là production-oriented, kiểm tra:

- [ ] Secrets không nằm trong Git.
- [ ] Có `.env.example` nhưng không chứa key thật.
- [ ] Input được validate.
- [ ] Có timeout/retry hợp lý cho external API.
- [ ] Không để LLM tự do gọi tool nguy hiểm.
- [ ] Tool parameters được validate server-side.
- [ ] Test prompt injection cơ bản.
- [ ] Test indirect prompt injection từ tài liệu RAG.
- [ ] Dữ liệu user/tenant được cô lập khi app đa người dùng.
- [ ] Không log secret hoặc dữ liệu nhạy cảm ngoài ý muốn.

## 6. Production gate

Flagship project nên tiến dần qua các mức:

### Level 1 — Local prototype

- chạy end-to-end;
- README;
- baseline/eval nhỏ;
- error handling cơ bản.

### Level 2 — Engineering project

- FastAPI/service layer;
- test;
- Docker;
- config/secrets;
- structured logging;
- CI.

### Level 3 — Production-oriented

- PostgreSQL khi cần persistence;
- Redis/cache khi có lý do đo được;
- async/streaming;
- rate limiting/auth nếu public;
- tracing/metrics;
- load test;
- retry/backoff/timeout;
- evaluation regression suite.

Không thêm công nghệ chỉ để README dài hơn. Mỗi dependency phải trả lời được: **nó giải quyết bottleneck nào?**

## 7. Flagship RAG — tiêu chuẩn mục tiêu

```text
Client
  ↓
API
  ├── authentication / rate limiting
  ├── PostgreSQL
  └── Redis
  ↓
Retrieval
  ├── vector search
  ├── BM25/hybrid search
  └── reranker
  ↓
LLM
  ↓
answer + citations
  ↓
traces / metrics / feedback / eval
```

### Eval layout gợi ý

```text
eval/
├── dataset.jsonl
├── retrieval_eval.py
├── generation_eval.py
├── regression_test.py
└── results/
```

## 8. Interview readiness gate

Một project đủ tốt cho CV khi có thể trả lời mà không né tránh:

1. Tại sao chọn architecture này?
2. Baseline đầu tiên là gì?
3. Metric nào quyết định project tốt hơn?
4. Failure case khó nhất là gì?
5. Nếu traffic tăng 100 lần thì bottleneck đầu tiên ở đâu?
6. Nếu bỏ framework đang dùng, bạn có tự dựng lại core flow được không?

Nếu chưa trả lời được, project vẫn đang ở trạng thái học — chưa phải flagship portfolio.
