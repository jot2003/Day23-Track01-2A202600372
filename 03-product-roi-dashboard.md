# 03 — Product ROI Dashboard (Parts A–D) v2

**Sản phẩm:** AI PT Copilot  
**Phiên bản:** v2 (sau red-team Block 4–5)  
**Phụ trách tổng hợp file nhóm:** Hoàng Kim Trí Thành (2A202600372)

---

## Source map (bắt buộc cho mọi metric và dẫn chứng)

### A. Nguồn bên ngoài (external)
- **E1:** OpenAI — Morgan Stanley case study: https://openai.com/index/morgan-stanley/
- **E2:** OpenAI — Klarna case study: https://openai.com/index/klarna/
- **E3:** Reuters — Klarna shifts AI focus (2025): https://www.reuters.com/business/swedens-klarna-shifts-ai-focus-cost-cuts-growth-2025-09-10/
- **E4:** 05-reference-document.md (Section 6, 7.3, 7.5, 10)

### B. Nguồn nội bộ (internal evidence)
- **I1:** Pilot log nội bộ Day 23 (cohort nhỏ 5–8 user, buổi lab 2026-05-11), gồm event onboarding/session/confirm/override.
- **I2:** Ghi chú red-team trong lớp (vai CFO/User/Risk/Workflow Owner), 2026-05-11.
- **I3:** Quan sát nhóm về friction UX trong bài tập mô phỏng (không đại diện production scale).

> Quy tắc: số trong dashboard được coi là **pilot baseline nội bộ** từ I1 (sample nhỏ). Không được trình bày như benchmark thị trường.

---

## Part A — Adoption Context

### A.1 Thách thức nhóm chọn

| Trường | Trả lời | Nguồn |
|--------|---------|-------|
| Thách thức áp dụng AI | Người tập mở app tuần đầu nhưng **không tái sử dụng** theo chu kỳ; nghi ngờ gợi ý tư thế/rep; team đang đo nhầm “có bật AI”. | I1, I3 |
| Tình huống xuất phát từ ai / ở đâu? | Beta nội bộ + bạn bè (5–8 người), tập tại nhà. | I1 |
| Dấu hiệu bị kẹt | Session tuần 1 cao hơn tuần 2; override tăng ở set nặng; không hoàn thành chuỗi 3 buổi/tuần. | I1 |
| Vì sao thách thức này đáng giải quyết? | Rủi ro an toàn + không chứng minh được PMF nếu chỉ có “wow” ban đầu. | I3, E4 |

### A.2 Sản phẩm / công cụ AI

| Trường | Trả lời | Nguồn |
|--------|---------|-------|
| Tên sản phẩm / công cụ AI | **AI PT Copilot** — mobile app gợi ý rep, tempo và hiệu chỉnh tư thế. | I1 |
| Người dùng chính | Người tập tại nhà, trình độ trung bình, 18–45 tuổi. | I1 |
| Bối cảnh sử dụng | Tập một mình, camera điện thoại, môi trường không có PT trực tiếp. | I1, I3 |
| Mục tiêu kinh doanh / học tập / vận hành | Tăng retention tuần 2–4 + giảm rủi ro discomfort + giảm time-to-first-aha. | I1, E4 |
| Không nằm trong phạm vi | Huấn luyện viên chuyên nghiệp; thiết bị y khoa/chẩn đoán. | I3 |

### A.3 2–4 quy trình chính (core workflows)

| # | Tên quy trình | Vai trò AI | Điểm người kiểm tra | Khi AI sai thì xử lý thế nào? | Nguồn |
|---|----------------|------------|---------------------|--------------------------------|-------|
| 1 | Calibration & first session | Gợi ý góc camera + khung người | User xác nhận “thấy rõ khung” | Giảm độ tự động, chuyển preset an toàn + video minh họa | I1, I3 |
| 2 | Live set — rep & pose coaching | Cảnh báo pose lệch, gợi ý tempo/rep | User xác nhận sau set nặng | Hạ ngưỡng tăng tải, buộc review trước buổi sau | I1, I2 |
| 3 | Post-session recap | Tóm tắt volume/RPE, đề xuất nghỉ | User chỉnh RPE thực tế | Mismatch lớn thì flag, chuyển chỉnh thủ công | I1, I2 |

### A.4 ADKAR — barrier chính (product-level)

| Stage | Nhận định nhóm | Nguồn |
|-------|----------------|-------|
| Awareness | Ổn — user hiểu app “có AI”. | I3 |
| Desire | Trung bình — “thử cho vui” có, nhưng sợ sai khi bài nặng. | I1, I3 |
| Knowledge | **Yếu** — chưa rõ khi nào nên tin AI vs tự cảm nhận. | I2, I3 |
| Ability | Trung bình — calibration còn lỗi trên một số máy. | I1 |
| Reinforcement | **Yếu** — thiếu tín hiệu củng cố tin cậy sau buổi tập. | I1, I2 |

**Barrier chính:** Knowledge + Reinforcement (phụ: Trust/Quality).  
**Nguồn:** I1, I2, E4.

### A.5 3 tactic adoption (product-level)

| # | Tactic | Nhắm barrier | Quy trình | Owner | Hoàn thành | Nguồn chọn tactic |
|---|--------|---------------|-----------|-------|-------------|-------------------|
| 1 | Confirm-safe micro-flow sau set nặng | Knowledge + Trust | WF2 | PM + Eng | Tuần 2 pilot | I2, E4 |
| 2 | Thẻ an toàn 1-tap + giải thích ngắn | Trust | WF1–2 | UX | Tuần 1–2 | I2, E4 |
| 3 | Buddy week + recap có ngữ cảnh | Reinforcement | WF3 | Growth/PM | Tuần 3–4 | I2, E4 |

### A.6 Chẩn đoán nguyên nhân gốc (2–3 lens)

| Lens | Chẩn đoán | Evidence | Nguồn |
|------|-----------|----------|-------|
| Workflow | AI chưa nằm trọn trong chuỗi xác nhận an toàn | Session drop sau cảnh báo pose | I1 |
| Metrics | Đo session/prompt dễ thành vanity | Dashboard cũ thiếu confirm/override_reason | I1, E4 |
| Trust/Quality | Thiếu proxy chất lượng sau human confirm | Survey cũ không gắn theo workflow | I1, I2 |

**Nguyên nhân gốc (chốt):** thiếu human-in-the-loop có đo + thiếu metric trust/quality theo workflow.  
**Nguồn hỗ trợ case:** E1, E2, E3, E4.

---

## Part B — Product ROI Dashboard

### Ghi chú dữ liệu trước khi đọc bảng
- Tất cả baseline dưới đây là **pilot baseline nội bộ** từ I1 (sample nhỏ).
- Các metric được thiết kế dựa trên pattern “productivity phải đi với quality/trust” từ E4.
- Cột “Data source” phải truy được về I1/I2 (nội bộ) hoặc E* (external case logic).

### B.1 Chỉ số toàn sản phẩm (2–3 metric)

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu 60 ngày | Nguồn dữ liệu cụ thể | Owner | Rủi ro red-team | Fix v2 | Nguồn dẫn chứng |
|--------|--------|-------------|------------------|----------------------|-------|-----------------|--------|-----------------|
| Activation | % user hoàn tất calibration + buổi tập đầu <=10’ | 55% | 80% | I1: onboarding events (`calibration_complete`, `first_session_complete`) | PM | Chỉ đẹp onboarding, chưa chắc value | Thêm drop-off theo step | I1, I2 |
| Retention / Value | % user có >=3 buổi có `human_confirm=1` trong 14 ngày | 18% | 40% | I1: session log + confirm events theo user-day | PM/Data | Confirm quá dày gây mệt | Chỉ bắt buộc set nặng + QA sample | I1, I2, E4 |
| Trust / Quality | Trust score sau buổi (chỉ tính user pass calibration) | 3.1 | 4.0 | I1: in-app survey + filter `calibration_pass=1` | UX | Survey bias | Hỏi theo trigger hợp lý + thêm passive proxy | I1, I2, E4 |

### B.2 Theo từng workflow

#### Workflow 1 — Calibration & first session

| Lớp đo | Chỉ số | Baseline | Target | Nguồn dữ liệu cụ thể | Owner | Red-team risk | Fix v2 | Nguồn dẫn chứng |
|--------|--------|----------|--------|----------------------|-------|----------------|--------|-----------------|
| Activation | % hoàn tất calibration | 62% | 85% | I1: onboarding funnel step-by-step | Eng | Quy trình dài gây drop | Cắt 1 bước, lưu partial state | I1, I2 |
| Engagement | Time-to-first-working-rep | 8 phút | <=6 phút | I1: session timeline (start -> first valid rep) | Eng | Loading model chậm | Cache model nhẹ + skeleton UI | I1 |
| Productivity | Retry calibration / user | 2.1 | <=1.5 | I1: retry_count | Eng | Support cost tăng | Diagnostic tự phục hồi | I1, I2 |
| Quality | % calibration pass QA frame rule | 70% | 90% | I1: CV logs + rule check | Eng | False pass | Bắt buộc user confirm khung rõ | I1, I2 |
| Trust | % user bấm “không khớp” ở bước khung | 12% | <8% | I1: UI button events | UX | User không hiểu nút | Tooltip + icon động | I1 |
| Value | % user vào WF2 trong 24h | 48% | 70% | I1: cross-workflow funnel | PM | Chưa phản ánh bền vững | Thêm cohort 7-day | I1, E4 |

#### Workflow 2 — Live set (rep & pose coaching)

| Lớp đo | Chỉ số | Baseline | Target | Nguồn dữ liệu cụ thể | Owner | Red-team risk | Fix v2 | Nguồn dẫn chứng |
|--------|--------|----------|--------|----------------------|-------|----------------|--------|-----------------|
| Activation | % set bật AI cue | 90% | 85% *(giảm spam)* | I1: feature flag + cue event | Eng | Bật AI != dùng đúng | Đổi KPI: % set có applied cue | I1, I2 |
| Engagement | % set nặng có confirm | 22% | 55% | I1: `confirm_tap` filtered by RPE>=7 | PM | Confirm gây friction | Chỉ bắt buộc set nặng/compound | I1, I2 |
| Productivity | Median time/rep variance | baseline | -5% variance an toàn | I1: motion + timer logs | Eng | Đẩy nhanh gây nguy hiểm | Cap tempo + hard stop pose red | I1, I2 |
| Quality | % override có tag lý do | 65% | 100% | I1: override event schema | PM | Thiếu lý do override | Bắt buộc tag khi override | I1, I2 |
| Trust | Post-set trust (1–5) | 3.0 | 4.2 | I1: survey theo set loại nặng | UX | Bias theo độ mệt | Hỏi theo trigger set phù hợp | I1, I2 |
| Value | % session discomfort escalation | 3.5% | <2% | I1: safety ticket + escalation log | PM/Risk | Under-report | Anonymous log + hotline copy | I1, I2, E4 |

#### Workflow 3 — Post-session recap

| Lớp đo | Chỉ số | Baseline | Target | Nguồn dữ liệu cụ thể | Owner | Red-team risk | Fix v2 | Nguồn dẫn chứng |
|--------|--------|----------|--------|----------------------|-------|----------------|--------|-----------------|
| Activation | % mở recap trong 2h | 40% | 60% | I1: push_sent -> recap_opened | Growth | Spam notification | Chỉ gửi sau buổi có confirm | I1, I2 |
| Engagement | % chỉnh RPE thực tế | 15% | 35% | I1: recap_edit events | PM | Form dài | Prefill + slider 1-tap | I1 |
| Productivity | Thời gian chỉnh recap | 75s | <45s | I1: UX telemetry duration | UX | Mất chi tiết | Template ngắn theo goal | I1 |
| Quality | % recap khớp log set (±10%) | 50% | 80% | I1: cross-check recap vs set log | Data | Cost pipeline | Reconcile mẫu 30% trước full | I1, I2 |
| Trust | % tin đề xuất ngày nghỉ | 28% | 45% | I1: accept/override button log | PM | Copy khó hiểu | Thêm “vì sao nghỉ” 1 câu | I1, I2 |
| Value | 7-day return sau recap mở | 20% | 38% | I1: cohort retention (recap opened) | PM | Nhiễu lịch cá nhân | So sánh cohort có/không recap | I1, E4 |

---

## Part C — Dashboard Mock (4–6 tiles)

```text
┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 1: PRODUCT HEALTH             │ │ TILE 2: WF1 CALIBRATION            │
│ Metric: 3-session confirm rate 14d │ │ Metric: calib completion <=10'     │
│ Current: 18%  Target: 40%          │ │ Current: 55%  Target: 80%          │
│ Status: AMBER                      │ │ Status: AMBER                      │
│ Action: ship confirm-lite v2       │ │ Action: cut 1 step + save state    │
│ Source: I1                         │ │ Source: I1                         │
└────────────────────────────────────┘ └────────────────────────────────────┘

┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 3: WF2 LIVE SET               │ │ TILE 4: TRUST / SAFETY             │
│ Metric: confirm on heavy sets      │ │ Metric: discomfort escalation %    │
│ Current: 22%  Target: 55%          │ │ Current: 3.5%  Target: <2%         │
│ Status: RED                        │ │ Status: AMBER                      │
│ Action: mandatory confirm RPE>=7   │ │ Action: copy + anonymous log       │
│ Source: I1 + I2                    │ │ Source: I1 + I2                    │
└────────────────────────────────────┘ └────────────────────────────────────┘

┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 5: WF3 RECAP VALUE            │ │ TILE 6: DECISION                   │
│ Metric: 7-day return after recap   │ │ Continue — metric: confirm+trust   │
│ Current: 20%  Target: 38%          │ │ Before scale: schema + QA checks   │
│ Status: AMBER                      │ │ Source: I1 + E4                    │
│ Action: A/B safety-first copy      │ │                                    │
│ Source: I1                         │ │                                    │
└────────────────────────────────────┘ └────────────────────────────────────┘
```

---

## Part D — Decision Memo

```markdown
# Memo Quyết Định Cuối — AI PT Copilot

1. Nhóm khuyến nghị: **tiếp tục** (Continue) theo pilot có kiểm soát.

2. Chỉ số mạnh nhất để bảo vệ quyết định là:
   **% buổi tập set nặng có human confirm hoàn tất** + **trust score sau buổi**,
   vì chuỗi này nối usage -> quality/trust -> retention và khó bị “chạy số”.

3. Chỉ số nhóm đã sửa sau phản biện:
   V1: session volume/prompt volume.
   V2: confirm completion + override_reason + trust có điều kiện.
   Vì sao tốt hơn: bám workflow rủi ro cao, có cổng kiểm chất lượng.

4. Trước khi scale sản phẩm, nhóm phải:
   1. Chốt schema event `confirm` / `override_reason` (nguồn kiểm: I1).
   2. Chạy pilot cohort 30-user có safety cap rõ (thiết kế theo E4, evidence nội bộ I1).
   3. Review mẫu video hằng tuần bằng human spot-check (I2).
```

---

## ≥2 thay đổi bắt buộc v1 -> v2 (tóm tắt)

| # | V1 | V2 | Nguồn red-team/evidence |
|---|----|----|--------------------------|
| 1 | Engagement = session + prompt volume | Engagement = confirm completion (set rủi ro) + applied cue rate | I2, E4 |
| 2 | Survey trust ngẫu nhiên | Trust sau buổi đạt calibration + sampling hợp lý | I2, I1 |
| 3 | Override không bắt buộc lý do | Override bắt buộc `reason_tag` | I2, I1 |
