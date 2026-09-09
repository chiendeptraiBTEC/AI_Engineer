# Progress Tracker

> Cập nhật file này theo **bằng chứng đã làm**, không theo cảm giác “đã học qua”.

## Trạng thái tổng

| Module | Trạng thái | Artifact chính | Bằng chứng |
|---|---|---|---|
| 0 — Setup & Refresh | ✅ Hoàn thành | CLI nhỏ + Git workflow | Đã hoàn thành Module 0 |
| 1 — Data + SQL | 🟡 Đang làm | DA1 — EDA | ✅ Buổi 1–4 NumPy; 🟡 Buổi 5 NumPy; ✅ Buổi 6 Pandas |
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
| 2026-09-06 | Module 1 · Buổi 5 — Tổng hợp NumPy (đang hoàn thiện) | Hoàn thành mini-project khách hàng: Boolean indexing, mean/std theo thuộc tính, Z-score, Euclidean distance trên dữ liệu gốc và chuẩn hóa; làm numpy-100 tới khoảng bài 28 | Notebook NumPy + note lý thuyết đã review | Hiểu khoảng cách chịu ảnh hưởng bởi thang đo; `axis` phải xuất phát từ ý nghĩa dữ liệu; numpy-100 bài 29+ để backlog |
| 2026-09-09 | Module 1 · Buổi 6 — Pandas: Series, DataFrame, đọc & khảo sát dữ liệu | Đọc workbook Excel nhiều sheet; dùng `shape`, `head`, `tail`, `info`, `describe`; lấy Series; phát hiện missing, dtype đáng nghi và min/max bất thường mà chưa vội cleaning | Notebook `Pandas_Buoi6_BaiTap_ThucTe.ipynb` đã nộp lại và review | Hiểu `NaN` không đồng nghĩa lỗi; phân biệt dòng giao dịch với đơn hàng; biết khảo sát dataset trước khi xử lý |

## Module 1 — Chi tiết tiến độ

- [x] Buổi 1 — NumPy Refresh + tạo mảng
- [x] Buổi 2 — Boolean & fancy indexing
- [x] Buổi 3 — Broadcasting & vectorization
- [x] Buổi 4 — Phép toán ma trận & axis
- [ ] Buổi 5 — Tổng hợp NumPy (mini-project)
  - [x] Mini-project khách hàng bằng NumPy
  - [x] Euclidean distance bằng vectorization
  - [x] Chuẩn hóa từng thuộc tính trước khi tính khoảng cách
  - [x] Note lý thuyết NumPy
  - [x] numpy-100 tới khoảng bài 28
  - [ ] numpy-100 bài 29–40 (backlog, làm dần)
  - [ ] Commit notebook NumPy lên GitHub
- [x] Buổi 6 — Pandas: Series, DataFrame, đọc dữ liệu, `head/tail/info/describe/shape`
- [ ] Buổi 7 — Chọn & lọc dữ liệu (`loc`, `iloc`, Boolean filtering)
- [ ] Buổi 8 — Biến đổi dữ liệu
- [ ] Buổi 9 — Groupby & tổng hợp
- [ ] Buổi 10 — Merge / Join / Concat
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

- [x] Buổi 1–4 — NumPy core.
- [ ] Buổi 5 — Tổng hợp NumPy (phần chính đã làm; numpy-100 bài 29–40 và commit notebook để backlog).
- [x] Buổi 6 — Pandas: Series, DataFrame, đọc và khảo sát dữ liệu.
- [ ] Buổi 7 — Chọn & lọc dữ liệu.

Ưu tiên tiếp theo:

- [ ] Học `loc` vs `iloc`.
- [ ] Chọn cột và lọc dòng theo điều kiện.
- [ ] Kết hợp nhiều điều kiện Boolean trong Pandas.
- [ ] Tiếp tục numpy-100 backlog khi có thời gian, không chặn tiến độ Pandas.
