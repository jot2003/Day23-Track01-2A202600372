# 06 — Phân Công Nhiệm Vụ Nhóm Day 23

**Nhóm:** VinUni A20 — AI PT Copilot  
**Mục tiêu:** Hoàn thiện đầy đủ deliverables Day 23 và đồng bộ vào repo cá nhân từng thành viên.

---

## 1) Danh sách thành viên

1. Hoàng Kim Trí Thành — 2A202600372
2. Quách Gia Được — 2A202600423
3. Nguyễn Thành Nam — 2A202600205
4. Nguyễn Trọng Tiến — 2A202600228

---

## 2) Phân công nhiệm vụ chính

| Thành viên | Nhiệm vụ chính | Deliverable phụ trách | Deadline nội bộ | Trạng thái |
|---|---|---|---|---|
| Quách Gia Được (2A202600423) | Tổng hợp phần thách thức nhóm từ input 4 thành viên; chốt 3-5 pattern | `01-case-evidence-matrix.md` (phần nhóm), `01-worksheet.md` mục 1 | [điền giờ] | [ ] |
| Nguyễn Thành Nam (2A202600205) | Lead nghiên cứu case thành công + case thất bại/cảnh báo; điền bảng so sánh | `02-case-comparison.md`, `01-worksheet.md` mục 2 | [điền giờ] | [ ] |
| Nguyễn Trọng Tiến (2A202600228) | Lead dashboard ROI: chỉ số product-level + workflow-level; đề xuất data source & owner | `03-product-roi-dashboard.md`, `01-worksheet.md` mục 6-7 | [điền giờ] | [ ] |
| Hoàng Kim Trí Thành (2A202600372) | Điều phối tổng hợp, rà checklist, ghi decision memo, chuẩn hóa file và push cuối | `03-product-roi-dashboard.md` mục memo + sửa v2, `README.md` | [điền giờ] | [ ] |

---

## 3) Nhiệm vụ bắt buộc cho MỖI thành viên

Mỗi thành viên phải tự thực hiện trong repo cá nhân của mình:

- Copy đủ 4 file nộp:
  - `01-case-evidence-matrix.md`
  - `02-case-comparison.md`
  - `03-product-roi-dashboard.md`
  - `04-reflection.md` (trong 24h)
- Commit và push lên `main`.
- Đảm bảo repo public trước khi nộp link.

---

## 4) Quy tắc phối hợp nhanh

- Mọi thay đổi nội dung nhóm phải chốt trên `01-worksheet.md` trước rồi mới copy sang file nộp.
- Không chỉ dùng usage metrics (login/prompt count/DAU-MAU); bắt buộc có quality/trust/value.
- Sau phản biện red-team, phải sửa ít nhất 2 điểm từ v1 sang v2 và ghi rõ trong file.

### Quy định mới: bắt buộc dẫn nguồn cho mọi metric/evidence

- Mỗi claim về case phải có link nguồn cụ thể (ví dụ: OpenAI case, Reuters, tài liệu tham khảo lớp).
- Mỗi metric trong dashboard phải ghi rõ data source và mã nguồn truy vết (E1/E2/E3/E4 hoặc I1/I2).
- Nếu là số nội bộ/pilot thì phải ghi rõ: thời điểm, cỡ mẫu, phạm vi (không trình bày như benchmark thị trường).
- Tách rõ **Fact từ nguồn** và **Phân tích nhóm**; không dùng số liệu AI tự sinh.
- Mỗi thành viên tự chịu trách nhiệm kiểm tra source trong phần mình phụ trách trước khi merge.

---

## 5) Checklist bàn giao nội bộ

- [ ] Đủ 2-4 workflow chính
- [ ] Đủ 1-2 nguyên nhân gốc + evidence
- [ ] Có roadmap 30/60/90 ngày + owner
- [ ] Có dashboard product-level + workflow-level
- [ ] Có mục rủi ro phản biện + sửa v2
- [ ] Có memo quyết định continue/pivot/kill
- [ ] Mỗi thành viên đã copy file vào repo cá nhân và push
