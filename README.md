# AI Engineer — Learning & Shipping Roadmap

Repository này là **hệ thống học + theo dõi tiến độ** để đi từ nền tảng Software Engineering đến AI Engineer, tập trung vào **ML/DL foundation, LLM/Generative AI, RAG và production AI systems**.

> Mục tiêu của repo không phải là “hoàn thành 210 buổi học”. Mục tiêu là sau mỗi giai đoạn phải có **code, benchmark, test, demo hoặc sản phẩm chạy được** để chứng minh năng lực.

## Trạng thái hiện tại

- Curriculum và syllabus Module 0–6: đã thiết kế.
- Quá trình thực hành: đang bắt đầu từ Module 0.
- Các dự án portfolio: **chưa hoàn thành** và sẽ được cập nhật bằng link repo thật khi ship.
- Theo dõi tiến độ: [`PROGRESS.md`](./PROGRESS.md).

## Nội dung chính

- [`lo-trinh-ai-engineer.md`](./lo-trinh-ai-engineer.md) — lộ trình tổng quan theo tuần.
- [`syllabus/`](./syllabus/) — giáo trình chi tiết theo buổi.
- [`syllabus/00-master-plan.md`](./syllabus/00-master-plan.md) — milestone và tiêu chí qua module.
- [`syllabus/07-production-ai-engineering-upgrade.md`](./syllabus/07-production-ai-engineering-upgrade.md) — phần nâng cấp về production, security và evaluation.
- [`PORTFOLIO_STANDARD.md`](./PORTFOLIO_STANDARD.md) — chuẩn bắt buộc cho các dự án portfolio.
- [`tai-nguyen-bo-tro.md`](./tai-nguyen-bo-tro.md) — tài nguyên bổ trợ.

## Nguyên tắc vận hành

1. **Execution > Planning** — không chỉnh roadmap liên tục nếu chưa ship artifact của module hiện tại.
2. **Mỗi module phải tạo bằng chứng** — repo/code/notebook có kết quả, test, benchmark hoặc demo.
3. **Không copy tutorial thành portfolio** — project phải có quyết định kỹ thuật, failure cases và số đo.
4. **Framework đến sau fundamentals** — hiểu primitive trước khi dùng abstraction như LangChain/LlamaIndex.
5. **Production mindset từ sớm** — config, logging, test, reproducibility, secrets và error handling được luyện xuyên suốt.
6. **Đo trước khi tối ưu** — mọi cải tiến ML/RAG/LLM phải có baseline và metric so sánh.

## Roadmap & bằng chứng đầu ra

| Giai đoạn | Trọng tâm | Bằng chứng bắt buộc |
|---|---|---|
| Module 0 | Setup, Python/OOP, Git | CLI nhỏ chạy được + README |
| Module 1 | NumPy, Pandas, SQL, EDA | DA1: EDA dataset thật + insight |
| Module 2 | ML core | DA2: ML end-to-end + baseline + metrics |
| Module 3 | Deep Learning | DA3: image classifier + nanoGPT/from-scratch work |
| Module 4 | LLM / RAG / Agents | DA4: RAG có evaluation, citations và demo |
| Module 5 | Production / MLOps | Nâng DA4 thành service: API + Docker + test + monitoring |
| Module 6 | Job prep | CV + portfolio + interview evidence + application tracker |

## Portfolio target

Thay vì cố tạo nhiều project nhỏ, ưu tiên **3–5 project có chiều sâu**:

- [ ] **DA1 — Data/EDA:** dataset thật, data cleaning, visualization, insight có ý nghĩa.
- [ ] **DA2 — ML system:** baseline → feature/model experiments → evaluation → reproducibility.
- [ ] **DA3 — DL fundamentals:** image model + một phần implementation từ gốc để chứng minh hiểu bản chất.
- [ ] **DA4 — Flagship Production RAG:** retrieval, reranking/hybrid search, evaluation, citations, FastAPI, database/cache, observability, security tests.
- [ ] **DA5 — không bắt buộc là app mới:** có thể là phiên bản production-grade của DA4 được deploy online.

## Definition of Done cho một project

Một project chỉ được đánh dấu hoàn thành khi có tối thiểu:

- README giải thích bài toán, kiến trúc và cách chạy.
- Environment/dependencies tái lập được.
- Baseline và metric định lượng.
- Ít nhất một failure case được ghi lại và phân tích.
- Test cho logic quan trọng.
- Không hardcode secrets.
- Demo/screenshot hoặc endpoint chạy được nếu phù hợp.
- Phần “Trade-offs / What I would improve next”.

## Flagship architecture mục tiêu

```text
Client
  ↓
FastAPI
  ├── Auth / Rate limit
  ├── PostgreSQL
  ├── Redis cache
  ↓
Retriever
  ├── Vector search
  ├── BM25 / hybrid search
  └── Reranker
  ↓
LLM
  ↓
Answer + citations
  ↓
Logs / traces / latency / cost / feedback
```

Không cần đạt kiến trúc này ngay từ đầu. DA4 sẽ được xây theo phiên bản **v1 → đo → v2 → production**.

## Quy tắc chống tutorial hell

> Nếu một tuần học nhiều nhưng GitHub không xuất hiện code, benchmark, test, note kỹ thuật hoặc demo mới, coi như tuần đó **chưa tạo đủ bằng chứng học tập**.

Mỗi tuần ưu tiên ít nhất một commit có ý nghĩa: code tự viết, test, benchmark, tài liệu kỹ thuật hoặc cải tiến project — không commit chỉ để giữ streak.
