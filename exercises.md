# Ngày 1 — Bài Tập & Phản Ánh

## Nền Tảng LLM API | Phiếu Thực Hành

**Thời lượng:** 1:30 giờ  
**Cấu trúc:** Lập trình cốt lõi (60 phút) → Bài tập mở rộng (30 phút)

---

## Phần 1 — Lập Trình Cốt Lõi (0:00–1:00)

Chạy các ví dụ trong Google Colab tại: https://colab.research.google.com/drive/172zCiXpLr1FEXMRCAbmZoqTrKiSkUERm?usp=sharing

Triển khai tất cả TODO trong `template.py`. Chạy `pytest tests/` để kiểm tra tiến độ.

**Điểm kiểm tra:** Sau khi hoàn thành 4 nhiệm vụ, chạy:

```bash
python template.py
```

Bạn sẽ thấy output so sánh phản hồi của GPT-4o và GPT-4o-mini.

---

## Phần 2 — Bài Tập Mở Rộng (1:00–1:30)

### Bài tập 2.1 — Độ Nhạy Của Temperature

Gọi `call_openai` với các giá trị temperature 0.0, 0.5, 1.0 và 1.5 sử dụng prompt **"Hãy kể cho tôi một sự thật thú vị về Việt Nam."**

**Bạn nhận thấy quy luật gì qua bốn phản hồi?** (2–3 câu)

> _Khi temperature thấp như 0.0, câu trả lời thường ổn định, ngắn gọn và ít thay đổi giữa các lần chạy. Khi tăng lên 0.5, 1.0 và 1.5, phản hồi trở nên đa dạng, sáng tạo hơn nhưng cũng dễ lan man hoặc kém nhất quán hơn._

**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**

> _Em sẽ đặt temperature khoảng 0.2–0.3 cho chatbot hỗ trợ khách hàng. Vì chatbot dạng này cần trả lời chính xác, nhất quán, dễ kiểm soát và hạn chế bịa thông tin hơn là tạo ra câu trả lời quá sáng tạo_

---

### Bài tập 2.2 — Đánh Đổi Chi Phí

Xem xét kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người thực hiện 3 lần gọi API, mỗi lần trung bình ~350 token.

**Ước tính xem GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này:**

> _Số token mỗi ngày là: 10.000 × 3 × 350 = 10.500.000 token/ngày.Vì GPT-4o có giá input và output đều cao hơn GPT-4o-mini khoảng 16.7 lần, nên với workload này GPT-4o cũng đắt hơn GPT-4o-mini khoảng 16.7 lần._

**Mô tả một trường hợp mà chi phí cao hơn của GPT-4o là xứng đáng, và một trường hợp GPT-4o-mini là lựa chọn tốt hơn:**

> _GPT-4o xứng đáng dùng khi tác vụ yêu cầu độ chính xác và khả năng suy luận cao, ví dụ phân tích tài liệu phức tạp, hỗ trợ ra quyết định quan trọng, xử lý yêu cầu đa bước hoặc các tình huống cần hiểu ngữ cảnh sâu. GPT-4o-mini phù hợp hơn cho các tác vụ đơn giản, số lượng lớn và cần tiết kiệm chi phí, ví dụ chatbot FAQ, phân loại intent, tóm tắt ngắn, sinh câu trả lời cơ bản hoặc xử lý tự động hàng loạt._

---

### Bài tập 2.3 — Trải Nghiệm Người Dùng với Streaming

**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì non-streaming lại phù hợp hơn?** (1 đoạn văn)

> _Streaming quan trọng nhất khi phản hồi dài hoặc người dùng cần cảm giác hệ thống đang phản hồi ngay, ví dụ chatbot hội thoại, trợ lý viết nội dung, giải thích bài tập hoặc sinh báo cáo dài. Việc hiển thị từng phần giúp giảm cảm giác chờ đợi và cải thiện trải nghiệm người dùng. Ngược lại, non-streaming phù hợp hơn khi phản hồi ngắn, cần xử lý toàn bộ kết quả trước khi hiển thị, hoặc khi hệ thống cần kiểm tra, định dạng, validate JSON hay lưu kết quả hoàn chỉnh trước khi trả về cho người dùng._

## Danh Sách Kiểm Tra Nộp Bài

- [ ] Tất cả tests pass: `pytest tests/ -v`
- [ ] `call_openai` đã triển khai và kiểm thử
- [ ] `call_openai_mini` đã triển khai và kiểm thử
- [ ] `compare_models` đã triển khai và kiểm thử
- [ ] `streaming_chatbot` đã triển khai và kiểm thử
- [ ] `retry_with_backoff` đã triển khai và kiểm thử
- [ ] `batch_compare` đã triển khai và kiểm thử
- [ ] `format_comparison_table` đã triển khai và kiểm thử
- [ ] `exercises.md` đã điền đầy đủ
- [ ] Sao chép bài làm vào folder `solution` và đặt tên theo quy định
