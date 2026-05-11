# 02 — Bảng so sánh case thành công / thất bại (nhóm — bản copy cá nhân)

**Sản phẩm nhóm đang áp dụng dashboard:** AI PT Copilot (ứng dụng gợi ý rep & tư thế khi tập)  
**Người đồng bộ file:** Hoàng Kim Trí Thành (2A202600372)

---

## Nguồn trích dẫn dùng trong bảng

- **C1 (practitioner/company-published):** OpenAI — Morgan Stanley case study: https://openai.com/index/morgan-stanley/
- **C2 (practitioner/company-published):** OpenAI — Klarna case study: https://openai.com/index/klarna/
- **C3 (major news):** Reuters — Klarna shifts AI focus (2025): https://www.reuters.com/business/swedens-klarna-shifts-ai-focus-cost-cuts-growth-2025-09-10/
- **C4 (teaching reference):** 05-reference-document.md (Section 6, 7.3, 7.5, 10)

> Quy tắc dùng nguồn: chỉ khẳng định định lượng khi có link; phần suy luận chiến lược ghi rõ “phân tích nhóm”.

---

## Bảng điền

| Trường | Case thành công | Case thất bại / cảnh báo |
|--------|-----------------|---------------------------|
| **Case** | **Morgan Stanley** — triển khai AI assistant trong môi trường compliance cao | **Klarna** — tín hiệu rollout nhanh + cảnh báo về trưởng thành hệ metric |
| **AI được dùng trong quy trình nào?** | Wealth advisor tra cứu tri thức nội bộ và chuẩn bị trả lời khách hàng, có quy trình kiểm soát | Customer service workflow với mục tiêu xử lý volume lớn và tối ưu vận hành |
| **Người dùng chính là ai?** | Advisors / nhân sự nghiệp vụ tài chính | Nhân sự CS, vận hành, và người dùng cuối chịu tác động chất lượng dịch vụ |
| **Họ đo chỉ số gì?** | Case nhấn mạnh adoption + tốc độ truy xuất tri thức + trust architecture (eval/feedback/compliance) | Case nhấn mạnh khối lượng AI xử lý, hiệu quả vận hành ban đầu, câu chuyện scale |
| **Chỉ số đó thuộc lớp nào?** | Activation + Productivity + Trust (có compliance gate) | Activation / Productivity (coverage-volume) |
| **Chỉ số đó chứng minh được gì?** | Có thể mở rộng AI trong môi trường rủi ro cao khi trust được thiết kế từ đầu | Có thể tăng tốc xử lý và tạo hiệu ứng triển khai nhanh |
| **Chỉ số đó chưa chứng minh được gì?** | Chưa tự động chứng minh toàn bộ client outcome dài hạn nếu thiếu lớp business impact độc lập | Chưa đủ chứng minh chất lượng dịch vụ bền vững ở các case phức tạp |
| **Thiếu chỉ số nào?** | Cost-to-serve/impact tài chính chuẩn hóa theo giai đoạn | Escalation quality, complaint theme, QA sample pass, trust sau handoff |
| **Rủi ro lớn nhất** | Dựa quá mạnh vào success narrative vendor mà thiếu external triangulation | Measurement trap: coverage cao bị hiểu thành value bền vững |
| **Bài học cho dashboard nhóm** | Thiết kế trust architecture + owner + failure path trước khi scale | Không báo cáo “% bật AI” như KPI chính; bắt buộc có quality/trust/value theo workflow |

---

## Câu chốt của nhóm

```markdown
Case thành công dạy nhóm tôi rằng: adoption bền vững cần trust architecture (human review, compliance gate, feedback loop), không chỉ metric hoạt động.

Case cảnh báo dạy nhóm tôi rằng: coverage/volume chỉ là tín hiệu giai đoạn đầu; nếu thiếu quality/trust metric thì quyết định scale rất dễ lệch.

Vì vậy dashboard nhóm tôi phải tránh: chỉ báo cáo session count, prompt count, hoặc % user bật AI mà không có bằng chứng outcome theo workflow.
```

---

## Traceability note

- Mọi claim định lượng/public trong file này phải truy vết được về C1/C2/C3.
- Mọi nhận định suy luận của nhóm dựa trên bài giảng và synthesis được ghi rõ qua C4.
