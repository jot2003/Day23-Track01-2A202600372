# 01 — Case Evidence Matrix (Block 2, cá nhân)

**Học viên:** Hoàng Kim Trí Thành — **Mã:** 2A202600372  
**Case cá nhân chọn:** Klarna — cảnh báo bẫy đo adoption bằng coverage/usage.

---

## Nguồn dùng cho case này (bắt buộc trích dẫn)

- **S1 (practitioner/company-published):** OpenAI — Klarna case study: https://openai.com/index/klarna/
- **S2 (major news):** Reuters — Klarna điều chỉnh trọng tâm AI năm 2025: https://www.reuters.com/business/swedens-klarna-shifts-ai-focus-cost-cuts-growth-2025-09-10/
- **S3 (teaching reference):** 05-reference-document.md (Section 6, 7.5, 10)

> Lưu ý: phần nào không có số liệu định lượng từ nguồn công khai thì ghi rõ là “nhận định phân tích”, không bịa thêm số.

---

## 8-field matrix

| # | Trường | Nội dung | Nguồn |
|---|---|---|---|
| 1 | **Case** | Klarna (giai đoạn truyền thông AI-first và các điều chỉnh sau đó). | S1, S2 |
| 2 | **Metric shown** | Các chỉ số được nhấn mạnh ở lớp case gồm coverage/khối lượng AI xử lý và narrative hiệu quả vận hành ban đầu. | S1 |
| 3 | **Metric layer** | Nghiêng về **Activation/Engagement/Productivity**; thiếu bằng chứng sâu cho **Quality/Trust/Value** theo workflow phức tạp. | S1 + phân tích từ S3 |
| 4 | **What this proves** | Tổ chức có thể rollout AI nhanh và đạt độ phủ cao ở bề mặt sử dụng. | S1 |
| 5 | **What this does NOT prove** | Không tự chứng minh chất lượng dịch vụ bền vững, mức tin cậy người dùng cuối, hay ROI dài hạn nếu thiếu các metric hậu kiểm. | Phân tích từ S1, S2, S3 |
| 6 | **Missing metric** | Escalation rate theo luồng AI, QA pass sample, override/rework có lý do, complaint theme sau AI. | S3 (metrics ladder + measurement trap) |
| 7 | **Biggest risk** | **Measurement trap**: xem coverage là thành công, rồi scale trước khi quality/trust ổn định. | S3, tham chiếu S2 |
| 8 | **Lesson for our dashboard** | Mỗi workflow phải có chuỗi đo: activation -> human confirm -> quality/trust -> value; không dùng prompt/session làm chỉ số chính. | S3 |

---

## Ghi chú thách thức cá nhân (gắn Block 1)

- **Tình huống cá nhân:** AI PT Copilot tuần đầu được dùng nhiều nhưng giảm mạnh tuần 2.
- **Dấu hiệu kẹt:** user override cao ở set nặng, completion không ổn định.
- **Giả thuyết:** thiếu human-in-the-loop có đo được và team đang đo usage thay vì trust/quality/value.
- **Nguồn bằng chứng nội bộ:** quan sát pilot nhóm trong buổi lab Day 23 (sample nhỏ, không external benchmark).
