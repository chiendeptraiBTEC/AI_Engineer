# 📘 GIÁO TRÌNH AI ENGINEER — KẾ HOẠCH TỔNG THỂ THEO BUỔI

> Đây là bản chi tiết theo từng buổi của lộ trình tổng quan trong [`../lo-trinh-ai-engineer.md`](../lo-trinh-ai-engineer.md).
> Mỗi module là một file riêng trong `syllabus/`.

---

## 1. Quy ước

- **1 buổi = ~2.5 giờ học thật.**
- Nhịp đề xuất: **5 buổi/tuần** + 2 ngày đệm.
- Tổng syllabus khoảng **210 buổi / 42 tuần** nếu giữ nhịp đều.
- Con số buổi chỉ là **ước lượng lịch học**, không phải tiêu chí tốt nghiệp.

> Quy tắc chính: **không chuyển module chỉ vì đã xem hết tài liệu. Chuyển module khi đã có artifact và bằng chứng đạt yêu cầu.**

## 2. Cấu trúc một buổi học

| Khối | Thời lượng | Làm gì |
|---|---:|---|
| Khởi động | 10' | Đọc lại note / kiểm tra kiến thức buổi trước |
| Học mới | 60–70' | Đọc tài liệu / xem video có mục tiêu cụ thể |
| Code / thực hành | 60–70' | Tự gõ, sửa, phá, benchmark, debug |
| Chốt | 10' | Ghi lại điều hiểu được, lỗi gặp phải và bằng chứng |

Trục Toán học song song Module 0–3 nhưng **không được chiếm chỗ của project execution**.

## 3. Hệ thống bằng chứng

Sau mỗi block học đáng kể, ưu tiên tạo ít nhất một trong các loại bằng chứng:

- code tự viết;
- test;
- benchmark/metric;
- notebook có kết luận;
- README/note kỹ thuật bằng lời của mình;
- bug report + cách debug;
- demo chạy được.

Theo dõi trong [`../PROGRESS.md`](../PROGRESS.md).

## 4. Bảng module và output

| Module | Tên | Số buổi dự kiến | Output chính |
|---|---|---:|---|
| 0 | Setup & Refresh | 5 | CLI nhỏ + Git workflow |
| 1 | Python Data + SQL | 20 | **DA1: EDA** |
| 2 | Machine Learning cốt lõi | 40 | **DA2: ML end-to-end** |
| 3 | Deep Learning từ gốc | 45 | **DA3: Image + nanoGPT/from-scratch** |
| 4 | LLM & AI Engineering | 50 | **DA4: RAG v1 → v2 có evaluation** |
| 5 | MLOps & Deploy | 30 | **Nâng DA4 thành production-oriented service + deploy** |
| 6 | Xin việc VN | 20 | CV + Portfolio + application/interview evidence |

> DA5 không bắt buộc phải là một app hoàn toàn mới. Nếu DA4 được nâng cấp đủ sâu qua Module 5, chính quá trình **prototype → measured system → production-oriented service** là câu chuyện portfolio tốt hơn.

## 5. Evidence Gate theo milestone

| Mốc | Không chỉ cần “đã học” | Bằng chứng tối thiểu |
|---|---|---|
| Xong Module 0 | Setup/Python/Git | CLI nhỏ chạy được từ máy sạch + README + commit history |
| Xong Module 1 | Data/SQL | DA1 có cleaning, visualization, insight và giải thích lựa chọn |
| Xong Module 2 | ML core | DA2 có baseline, metric, error analysis, reproducibility |
| Xong Module 3 | DL | Train được model + hiểu/backprop/attention qua code hoặc giải thích từ gốc |
| Giữa Module 4 | LLM/RAG cơ bản | RAG v1 + eval dataset nhỏ + citations/out-of-scope tests |
| Xong Module 4 | AI Engineering | RAG v2 chứng minh tốt hơn baseline bằng số đo |
| Xong Module 5 | Production | API + Docker + tests + observability + reliability/security checks + deploy |
| Xong Module 6 | Job ready | CV/portfolio phản ánh project thật + mock interviews + application tracker |

## 6. Quality Gate chung cho project

Dùng [`../PORTFOLIO_STANDARD.md`](../PORTFOLIO_STANDARD.md).

Một project chưa được tính là portfolio-ready nếu thiếu:

- baseline và metric;
- README có architecture/how-to-run;
- failure case/error analysis;
- test cho logic quan trọng;
- reproducible environment;
- secrets/config đúng cách;
- trade-offs/next steps.

## 7. Production AI Upgrade

Sau khi DA4 chạy end-to-end, học và áp dụng có chọn lọc phần:

[`07-production-ai-engineering-upgrade.md`](./07-production-ai-engineering-upgrade.md)

Nội dung gồm:

- async/streaming/backend service boundaries;
- PostgreSQL/Redis/background jobs khi có lý do;
- timeout/retry/rate limiting/reliability;
- structured logs/tracing;
- RAG evaluation regression;
- prompt injection/data isolation/tool security;
- load/cost measurement;
- CI quality gates.

> Không thêm công nghệ chỉ để “trông production”. Mỗi thành phần phải giải quyết một bottleneck hoặc requirement cụ thể.

## 8. Khi nào bắt đầu quan sát thị trường việc làm?

Không cần chờ đến Module 6.

- Từ tháng đầu: đọc JD AI/ML/LLM để biết kỹ năng nào xuất hiện lặp lại.
- Từ khi có DA2/DA3: bắt đầu so portfolio với JD thực tế.
- Khi có RAG v1 + 2–3 project có chiều sâu: có thể thử CTV/intern phù hợp.
- Apply là một **feedback loop**, không phải phần thưởng sau khi học xong mọi thứ.

## 9. Danh sách file giáo trình

- [`module-0-setup.md`](./module-0-setup.md)
- [`module-1-data-sql.md`](./module-1-data-sql.md)
- [`module-2-ml-core.md`](./module-2-ml-core.md)
- [`module-3-deep-learning.md`](./module-3-deep-learning.md)
- [`module-4-llm-ai-eng.md`](./module-4-llm-ai-eng.md)
- [`module-5-mlops.md`](./module-5-mlops.md)
- [`module-6-job-prep.md`](./module-6-job-prep.md)
- [`07-production-ai-engineering-upgrade.md`](./07-production-ai-engineering-upgrade.md)

## 10. Quy tắc cuối

> **Execution > Planning.** Nếu roadmap đã đủ để biết hôm nay phải làm gì, không tiếp tục tối ưu roadmap. Hãy code, debug, đo và ship.
