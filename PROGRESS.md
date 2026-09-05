# Progress Tracker

> Cập nhật file này theo **bằng chứng đã làm**, không theo cảm giác “đã học qua”.

## Trạng thái tổng

| Module | Trạng thái | Artifact chính | Bằng chứng |
|---|---|---|---|
| 0 — Setup & Refresh | ✅ Hoàn thành | CLI nhỏ + Git workflow | Đã hoàn thành Module 0 |
| 1 — Data + SQL | 🟡 Đang làm | DA1 — EDA | ✅ Buổi 1–4 — NumPy |
| 2 — ML Core | ⬜ Chưa bắt đầu | DA2 — ML end-to-end | — |
| 3 — Deep Learning | ⬜ Chưa bắt đầu | DA3 — Image + nanoGPT | — |
| 4 — LLM / AI Engineering | ⬜ Chưa bắt đầu | DA4 — Production RAG v1/v2 | — |
| 5 — MLOps / Production | ⬜ Chưa bắt đầu | Production hardening + deploy | — |
| 6 — Job Prep | ⬜ Chưa bắt đầu | CV + portfolio + applications | — |

## Cách cập nhật

Mỗi buổi hoặc mỗi block học đáng kể, thêm một dòng:

| Ngày | Buổi/Chủ đề | Tôi đã tự làm gì? | Bằng chứng | Vướng mắc / Bài học |
|---|---|---|---|---|
| 2026-08-27 | Module 1 · Buổi 1 — NumPy Refresh + tạo mảng | Hoàn thành 15 bài đầu numpy-100; ôn array, shape, dtype, indexing/slicing, mean và axis | 15 bài đã làm và review trong buổi học | Hiểu `axis`; sửa cách dùng `np.empty`, random vector và indexing biên |
| 2026-08-27 | Module 1 · Buổi 2 — Boolean & fancy indexing | Lọc số dương, lọc nhiều điều kiện, thay giá trị theo điều kiện, lấy phần tử bằng danh sách index; áp dụng trên dữ liệu điểm 2D | 7/7 bài thực hành đúng | Phân biệt Boolean indexing = chọn theo điều kiện; Fancy indexing = chọn theo vị trí |
| 2026-09-02 | Module 1 · Buổi 3 — Broadcasting & vectorization | Thực hiện phép toán trên toàn array không dùng vòng lặp; broadcast vector và `(n,1)` vào dữ liệu 2D; chuẩn hóa Z-score theo từng thuộc tính | Bài thực hành broadcasting + chuẩn hóa `(x - mean) / std` đã review | Hiểu vectorization đẩy vòng lặp xuống NumPy; broadcasting theo shape; mean/std theo `axis=0`; Z-score đưa mean về 0 và std về 1 |
| 2026-09-05 | Module 1 · Buổi 4 — Phép toán ma trận & axis | Dùng `@`/dot product, dự đoán shape, transpose, reshape; tổng hợp bằng `sum`, `mean`, `max` theo axis | Bài tập shape, transpose, reshape và axis đã hoàn thành | Hiểu `(m,n) @ (n,p) -> (m,p)`; transpose đổi vai trò các chiều; reshape giữ nguyên số phần tử |

## Module 1 — Chi tiết tiến độ

- [x] Buổi 1 — NumPy Refresh + tạo mảng
- [x] Buổi 2 — Boolean & fancy indexing
- [x] Buổi 3 — Broadcasting & vectorization
- [x] Buổi 4 — Phép toán ma trận & axis
- [ ] Buổi 5 — Tổng hợp NumPy (mini-project)
- [ ] Buổi 6–10 — Pandas phần 1
- [ ] Buổi 11–15 — Làm sạch & trực quan hóa
- [ ] Buổi 16–19 — SQL
- [ ] Buổi 20 — Dự án 1: EDA hoàn chỉnh

## Weekly Review

Mỗi cuối tuần trả lời 5 câu:

1. Tôi ship được artifact gì?
2. Tôi có thể giải thích phần nào mà không nhìn tutorial?
3. Bug khó nhất tuần này là gì và tôi debug thế nào?
4. Metric/test nào chứng minh code hoặc model tốt hơn?
5. Tuần sau bỏ bớt thứ gì để tập trung hơn?

## Evidence Gate

Không chuyển module chỉ vì đã xem hết tài liệu. Chỉ chuyển khi đáp ứng gate:

- [ ] Có artifact chạy được.
- [ ] Có README/note giải thích bằng lời của mình.
- [ ] Có test hoặc tiêu chí kiểm tra kết quả.
- [ ] Có ít nhất một lỗi/failure case đã debug.
- [ ] Có commit history phản ánh quá trình làm, không chỉ upload kết quả cuối.

## Current Focus

**Module 1 — Data + SQL**

Tiến độ hiện tại:

- [x] Buổi 1 — NumPy Refresh + tạo mảng.
- [x] Buổi 2 — Boolean & fancy indexing.
- [x] Buổi 3 — Broadcasting & vectorization.
- [x] Buổi 4 — Phép toán ma trận & axis.
- [ ] Buổi 5 — Tổng hợp NumPy (mini-project).

Ưu tiên tiếp theo:

- [ ] Làm tiếp numpy-100 tới khoảng bài 40.
- [ ] Viết hàm tính khoảng cách Euclid giữa các điểm chỉ bằng NumPy.
- [ ] Ráp indexing, broadcasting, vectorization, axis và phép toán ma trận vào một notebook NumPy tổng hợp.
- [ ] Commit notebook NumPy lên GitHub.
