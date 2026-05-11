# 04 — Reflect cá nhân (150–200 từ)

**Học viên:** Hoàng Kim Trí Thành — **Mã:** 2A202600372  
**Prompt:** Một metric tôi sẽ replace + tại sao (có evidence từ case)

---

Metric tôi chọn để **thay** là **“số lần gợi ý AI mỗi buổi tập”** (và các biến thể kiểu prompt count). Metric này dễ đẹp trên dashboard nhưng không chứng minh người dùng có tin gợi ý và thực hiện đúng động tác an toàn hay không. Bài học này đến từ case **Klarna**: các tín hiệu coverage/khối lượng xử lý ban đầu có thể rất ấn tượng, nhưng không tự đại diện cho chất lượng dịch vụ bền vững nếu thiếu lớp trust/quality theo workflow ([OpenAI Klarna case](https://openai.com/index/klarna/); góc nhìn điều chỉnh chiến lược thêm ở [Reuters 2025](https://www.reuters.com/business/swedens-klarna-shifts-ai-focus-cost-cuts-growth-2025-09-10/)).

Tôi thay bằng bộ metric: **% set nặng có human confirm hoàn tất** + **% override có lý do**. Hai tín hiệu này bám trực tiếp vào bước rủi ro cao nên khó bị “chạy số”. Tôi cũng chỉ đo trust survey sau khi user pass calibration để giảm bias. Cách làm này bám nguyên tắc trong tài liệu lớp: productivity phải đi cùng quality/trust, không chỉ đếm activity (xem `05-reference-document.md`, Section 6 và 10).
