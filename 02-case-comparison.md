# 02 — Bảng so sánh case thành công / thất bại (nhóm — bản copy cá nhân)

**Sản phẩm nhóm đang áp dụng dashboard:** Adaptix  
**Người đồng bộ file:** Hoàng Kim Trí Thành (2A202600372)

---

## Nguồn trích dẫn dùng trong bảng

- **E1 (practitioner):** OpenAI — Morgan Stanley case: https://openai.com/index/morgan-stanley/
- **E2 (practitioner):** OpenAI — Klarna case: https://openai.com/index/klarna/
- **E3 (major news):** Reuters — Klarna shifts AI focus: https://www.reuters.com/business/swedens-klarna-shifts-ai-focus-cost-cuts-growth-2025-09-10/
- **E4 (teaching reference):** `05-reference-document.md` (Section 6, 7.3, 7.5, 10)

---

## Bảng điền

| Trường | Case thành công | Case thất bại / cảnh báo |
|--------|-----------------|---------------------------|
| **Case** | **Morgan Stanley** | **Klarna** |
| **AI được dùng trong workflow nào?** | AI assistant hỗ trợ advisor truy xuất tri thức nội bộ trong workflow có compliance gate | AI hỗ trợ xử lý customer-service volume quy mô lớn, nhấn mạnh hiệu suất ban đầu |
| **Người dùng chính là ai?** | Advisor chuyên môn cao, môi trường rủi ro cao | Nhân sự CS/vận hành và khách hàng cuối |
| **Họ đo metric gì?** | Adoption trong workflow + trust architecture (review/control) + hiệu suất nghiệp vụ | Volume/coverage và narrative hiệu quả vận hành |
| **Chỉ số đó thuộc lớp nào?** | Activation + Productivity + Trust | Activation + Productivity (giai đoạn đầu) |
| **Chỉ số đó chứng minh được gì?** | Có thể mở rộng AI trong domain nhạy cảm khi trust/control được thiết kế trước | AI có thể tăng throughput và giảm thời gian xử lý ở lớp vận hành |
| **Chỉ số đó chưa chứng minh được gì?** | Chưa tự chứng minh toàn bộ business outcome dài hạn nếu thiếu lớp value độc lập | Chưa đủ chứng minh chất lượng dịch vụ bền vững, trust của user cuối |
| **Thiếu chỉ số nào?** | Cost-to-serve chuẩn hóa theo giai đoạn | Escalation/complaint/quality sample theo workflow |
| **Rủi ro lớn nhất** | Quá tin vào success narrative từ vendor | Measurement trap: coverage cao bị hiểu nhầm là value bền vững |
| **Bài học cho dashboard nhóm** | Thiết kế cổng quality/trust trước khi scale | Không dùng usage làm KPI chính cho quyết định continue/pivot/kill |

---

## Câu chốt của nhóm

```markdown
Case thành công dạy nhóm tôi rằng: muốn AI được adopt thật thì phải có trust architecture và owner rõ theo workflow.

Case cảnh báo dạy nhóm tôi rằng: throughput/coverage chỉ là tín hiệu giai đoạn đầu, không thay cho metric quality/trust/value.

Vì vậy dashboard Adaptix phải đo được mastery thực và outcome nghề nghiệp, không chỉ đo learner activity.
```

---

## Áp dụng sang Adaptix

- Đổi từ metric bề mặt (session count/prompt count) sang metric năng lực: mastery movement, transfer accuracy, project rubric pass.
- Mỗi metric trong dashboard đều có nguồn (Notion docs nội bộ hoặc reference bên ngoài) và owner hành động khi chỉ số đỏ.
