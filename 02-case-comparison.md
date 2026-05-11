# 02 — Bảng so sánh case thành công / thất bại (nhóm — bản copy cá nhân)

**Sản phẩm nhóm đang áp dụng dashboard:** AI PT Copilot (ứng dụng gợi ý rep & tư thế khi tập)  
**Người đồng bộ file:** Hoàng Kim Trí Thành (2A202600372)

---

## Bảng điền

| Trường | Case thành công | Case thất bại / cảnh báo |
|--------|-----------------|---------------------------|
| **Case** | **Stripe** — AI hỗ trợ dev nội bộ / tự động hóa tác vụ kỹ thuật có kiểm soát | **Klarna** — narrative AI-first và áp lực adoption rộng, sau đó điều chỉnh công khai truyền thông / phạm vi |
| **AI được dùng trong quy trình nào?** | Lặp vòng: dev hỏi → AI gợi ý → **PR + review** → merge; có guardrail nội bộ | Customer service / marketing: draft tự động, routing, trả lời nhanh — thiếu **chuỗi đo chất lượng ticket** rõ trước khi khoe scale |
| **Người dùng chính là ai?** | Kỹ sư có kỹ năng baseline cao; có **owner workflow** (team platform) | Nhân viên CS + quản lý vận hành + stakeholder bên ngoài (khách) |
| **Họ đo chỉ số gì?** | Chỉ số gắn **throughput + chất lượng** (ví dụ: cycle time, defect/rework sau thay đổi code) — theo tinh thần case “engineering org” | Số liệu kiểu **dùng AI / phủ sóng** (tỷ lệ tác vụ qua AI, messaging “AI-first”) |
| **Chỉ số đó thuộc lớp nào?** | **Productivity + Quality (+ Trust nội bộ qua review)** | **Activation / Engagement** (có dùng, có coverage) |
| **Chỉ số đó chứng minh được gì?** | Cải thiện có thể kiểm chứng trong **hệ thống ticket code** và gate CI | Khả năng **triển khai nhanh** và tạo **wow** truyền thông |
| **Chỉ số đó chưa chứng minh được gì?** | Không tự chứng minh **ROI tài chính tổng** nếu không gắn cost model | Không chứng minh **CSAT / complaint / SLA** sau khi scale cho khách |
| **Thiếu chỉ số nào?** | Cost to serve engineering (tuỳ giai đoạn) | **Escalation rate**, **QA sample pass**, **theme khiếu nại** theo luồng AI |
| **Rủi ro lớn nhất** | Over-rely AI → nợ kỹ thuật nếu bỏ review | **Measurement trap** + scale trước khi trust/quality ổn định |
| **Bài học cho dashboard nhóm** | Gắn metric vào **artifact có review** (log buổi tập + xác nhận người dùng / coach) | Không báo cáo “% bật AI” là thành công; cần **trust + outcome** theo từng workflow |

---

## Câu chốt của nhóm

```markdown
Case thành công dạy nhóm tôi rằng: metric mạnh là metric đi qua **cổng kiểm chất lượng** (review / rework thấp), không chỉ throughput.

Case thất bại/cảnh báo dạy nhóm tôi rằng: **wow và coverage** dễ thành vanity nếu không đo **hậu quả trên người dùng cuối**.

Vì vậy dashboard nhóm tôi phải tránh: chỉ báo cáo session count, prompt count, hoặc “% user bật AI” mà không có nhánh **quality/trust/value**.
```
