# 03 — Product ROI Dashboard (Parts A–D) v2

**Sản phẩm:** AI PT Copilot  
**Phiên bản:** v2 (sau red-team Block 4–5)  
**Phụ trách tổng hợp file nhóm:** Hoàng Kim Trí Thành (2A202600372)

---

## Part A — Adoption Context

### A.1 Thách thức nhóm chọn

| Trường | Trả lời |
|--------|---------|
| Thách thức áp dụng AI | Người tập mở app tuần đầu nhưng **không tái sử dụng** theo chu kỳ; nghi ngờ gợi ý tư thế/rep; team đang đo nhầm “có bật AI”. |
| Tình huống xuất phát từ ai / ở đâu? | Beta nội bộ + bạn bè (5–8 người), tập tại nhà. |
| Dấu hiệu bị kẹt | Session count cao tuần 1 → giảm tuần 2–3; nhiều **override** gợi ý; không hoàn thành chuỗi 3 buổi/tuần. |
| Vì sao thách thức này đáng giải quyết? | Rủi ro an toàn (tư thế sai) + không chứng minh được PMF nếu chỉ có “wow” ban đầu. |

### A.2 Sản phẩm / công cụ AI

| Trường | Trả lời |
|--------|---------|
| Tên sản phẩm / công cụ AI | **AI PT Copilot** — mobile app gợi ý rep, tempo và hiệu chỉnh tư thế (pose keypoints). |
| Người dùng chính | Người tập tại nhà, trình độ trung bình, 18–45 tuổi. |
| Bối cảnh sử dụng | Tập một mình; thi thoảng có video soi gương; mạng ổn định vừa phải. |
| Mục tiêu kinh doanh / học tập / vận hành | **Retention tuần 2–4** + **an toàn** (giảm chỉnh sai nặng) + thời gian tới “aha” buổi tập đầu ≤ 10 phút. |
| Không nằm trong phạm vi | Huấn luyện viên chuyên nghiệp; thiết bị đo EMG; y khoa chẩn đoán. |

### A.3 2–4 quy trình chính (core workflows)

| # | Tên quy trình | Vai trò AI | Điểm người kiểm tra | Khi AI sai thì xử lý thế nào? |
|---|----------------|------------|---------------------|--------------------------------|
| 1 | **Calibration & first session** | Gợi ý góc camera + khung người; checklist khởi động | User xác nhận “thấy rõ khung”; fallback wizard | Giảm độ tin cậy gợi ý; chuyển **preset bài tập không AI** + link video minh họa |
| 2 | **Live set — rep & pose coaching** | Gợi ý tempo/rep; cảnh báo pose lệch ngưỡng | User **bấm xác nhận** sau set; optional coach async review mẫu | Ngưỡng cảnh báo **strict hơn**; bắt buộc xác nhận trước khi tăng load tuần sau |
| 3 | **Post-session recap** | Tóm tắt volume RPE; đề xuất ngày nghỉ / progres | User chỉnh RPE thực tế; rule an toàn Product | Nếu mismatch lớn → flag cho PM + template điều chỉnh plan thủ công |

### A.4 ADKAR — barrier chính (product-level)

| Stage | Nhận định nhóm |
|-------|----------------|
| Awareness | Ổn — user hiểu app “có AI”. |
| Desire | Trung bình — “thử cho vui” có, nhưng **sợ sai** khiến không muốn phụ thuộc. |
| Knowledge | **Yếu** — không rõ khi nào nên tin AI vs tự cảm nhận. |
| Ability | Trung bình — UX calibration còn lỗi trên vài máy. |
| Reinforcement | **Yếu** — thiếu phản hồi **tin cậy sau buổi tập** (chỉ có streak, không có “bạn đã làm đúng phần nào”). |

**Barrier chính:** **Knowledge + Reinforcement**, phụ **Trust/Quality** (không tin output + không có vòng lặp củng cố tin).

### A.5 3 tactic adoption (product-level)

| # | Tactic | Nhắm barrier | Quy trình | Owner | Hoàn thành |
|---|--------|---------------|-----------|-------|-------------|
| 1 | **“Confirm-safe” micro-flow** sau mỗi set nặng | Knowledge + Trust | WF2 | PM + Eng | Tuần 2 pilot |
| 2 | **Thẻ an toàn 1-tap** (“khớp khớp / không khớp”) + copy ngắn giải thích *vì sao* | Trust | WF1–2 | UX | Tuần 1–2 |
| 3 | **Buddy week** — gợi ý tập cùng bạn, so sánh RPE ẩn danh | Reinforcement | WF3 | Growth/PM | Tuần 3–4 |

### A.6 Chẩn đoán nguyên nhân gốc (2–3 lens)

| Lens | Chẩn đoán | Evidence |
|------|-----------|----------|
| Workflow | AI **chưa nằm trong** “chuỗi xác nhận an toàn” — chỉ overlay trên video. | Nhiều session bỏ giữa chừng sau cảnh báo pose. |
| Metrics | Đo **session + prompt** → vanity theo học từ case **Klarna**/JPM-style dashboard. | Dashboard nội bộ cũ không có **confirm rate** / **override lý do**. |
| Trust/Quality | Thiếu proxy **chất lượng chuyển động** sau human confirm. | Post-session survey không gắn theo workflow. |

**Nguyên nhân gốc (chốt):** thiếu **human-in-the-loop có đo** + metric **trust/quality** gắn workflow, khiến team tưởng adoption tốt khi usage cao tuần 1.

---

## Part B — Product ROI Dashboard

### B.1 Chỉ số toàn sản phẩm (2–3 metric)

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu 60 ngày | Nguồn dữ liệu | Owner | Rủi ro red-team (col 7) | Fix v2 (col 8) |
|--------|--------|-------------|------------------|---------------|-------|-------------------------|----------------|
| Activation | **% user hoàn tất calibration + buổi tập đầu ≤10’** | 55% | 80% | Funnel onboarding | PM | CFO: chi phí dev không tương xứng nếu chỉ đẹp onboarding | Gắn **drop-off step** trong funnel để biết sửa UX vs model |
| Retention / Value | **% user có ≥3 buổi có “completed confirm” trong 14 ngày** | 18% | 40% | Event `set_completed` + `human_confirm` | PM/Data | User: fatigue vì quá nhiều xác nhận | V1: hỏi mỗi set → **V2: chỉ set nặng + random QA 20%** |
| Trust / Quality | **Trust score** = trung bình thẻ 1–5 sau buổi (“tin gợi ý”) | 3.1 | 4.0 | In-app micro-survey | UX | Risk: survey bias khi user bực | V2: **chỉ hỏi sau buổi PASS** calibration + sample off-session |

### B.2 Theo từng workflow

#### Workflow 1 — Calibration & first session

| Lớp đo | Chỉ số | Baseline | Target | Nguồn | Owner | Red-team risk | Fix v2 |
|--------|--------|----------|--------|-------|-------|----------------|--------|
| Activation | % hoàn tất calibration | 62% | 85% | Onboarding events | Eng | Workflow owner: bỏ qua bước vì dài | Rút **1 bước**; lưu partial state |
| Engagement | Time-to-first working rep | 8 phút | ≤6 phút | Session timeline | Eng | User: vẫn thấy “loading model” lâu | Cache model nhỏ + skeleton UI |
| Productivity | # lần thử lại calibration / user | 2.1 | ≤1.5 | Retry count | Eng | CFO: tốn support | Thêm **diagnostic tự phục hồi** |
| Quality | % calibration **pass QA rule** (frame OK) | 70% | 90% | CV pipeline logs | Eng | Risk: false positive an toàn | Giảm ngưỡng “pass” nhưng **bắt buộc** user confirm “tôi thấy rõ” |
| Trust | % user chọn “không khớp” ở bước khung | 12% | <8% | Button events | UX | User: không hiểu nút | Tooltip + icon động |
| Value | **% user vào WF2 trong 24h sau WF1** | 48% | 70% | Cross-workflow funnel | PM | — | Giữ nguyên, thêm cohort view |

#### Workflow 2 — Live set (rep & pose coaching)

| Lớp đo | Chỉ số | Baseline | Target | Nguồn | Owner | Red-team risk | Fix v2 |
|--------|--------|----------|--------|-------|-------|----------------|--------|
| Activation | % set có bật AI cue | 90% | 85% *(giảm cố ý spam)* | Feature flag | Eng | CFO: “bật AI” ≠ dùng đúng | Thay KPI nội bộ: **% set có ≥1 applied cue** (user không skip) |
| Engagement | % set hoàn thành có **confirm** | 22% | 55% | `confirm_tap` | PM | User: phiền | V2: chỉ set RPE≥7 hoặc **compound** |
| Productivity | Median time / rep (vs baseline user) | — | −5% variance an toàn | Motion + timer | Eng | Risk: khuyến khích tempo nguy hiểm | Cap tempo + **hard stop** khi pose red |
| Quality | **Override rate có tag lý do** | 35% không tag | 100% tag | Event schema | PM | — | V2: bắt buộc tag khi override |
| Trust | **Post-set trust** (1–5) | 3.0 | 4.2 | Survey | UX | — | Gắn survey **theo độ khó set** |
| Value | **% session có escalation “pain/discomfort” <2%** | 3.5% | <2% | Safety ticket | PM/Risk | Risk: under-report | Hotline micro-copy + anonymous log |

#### Workflow 3 — Post-session recap

| Lớp đo | Chỉ số | Baseline | Target | Nguồn | Owner | Red-team risk | Fix v2 |
|--------|--------|----------|--------|-------|-------|----------------|--------|
| Activation | % mở recap trong 2h | 40% | 60% | Push + open | Growth | User: spam notification | V1: daily ping → **V2: chỉ sau buổi có confirm** |
| Engagement | % chỉnh RPE thực tế | 15% | 35% | Form | PM | — | Prefill + slider 1-tap |
| Productivity | Thời gian chỉnh recap | 75s | <45s | UX telemetry | UX | — | Template ngắn theo goal |
| Quality | % recap **khớp** log set (±10%) | 50% | 80% | Cross-check | Data | CFO: cost data pipeline | V2: **sampled reconcile** 30% trước khi full |
| Trust | % “tin đề xuất ngày nghỉ” | 28% | 45% | Button | PM | — | Giải thích 1 câu “vì sao nghỉ” |
| Value | **7-day return** sau recap mở | 20% | 38% | Cohort | PM | — | A/B copy “nhắc an toàn” vs “nhắc PR” |

---

## Part C — Dashboard Mock (4–6 tiles)

```text
┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 1: PRODUCT HEALTH             │ │ TILE 2: WF1 CALIBRATION            │
│ Metric: 3-session confirm rate 14d │ │ Metric: calib completion ≤10'      │
│ Current: 18%  Target: 40%          │ │ Current: 55%  Target: 80%        │
│ Status: AMBER                      │ │ Status: AMBER                    │
│ Action: ship confirm-lite v2     │ │ Action: cut 1 step + save state   │
└────────────────────────────────────┘ └────────────────────────────────────┘

┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 3: WF2 LIVE SET               │ │ TILE 4: TRUST / SAFETY           │
│ Metric: confirm on heavy sets      │ │ Metric: discomfort escalation %   │
│ Current: 22%  Target: 55%         │ │ Current: 3.5%  Target: <2%       │
│ Status: RED                        │ │ Status: AMBER                    │
│ Action: mandatory confirm RPE≥7   │ │ Action: copy + anonymous log      │
└────────────────────────────────────┘ └────────────────────────────────────┘

┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 5: WF3 RECAP VALUE            │ │ TILE 6: DECISION                  │
│ Metric: 7-day return after recap   │ │ Continue — metric: confirm+trust  │
│ Current: 20%  Target: 38%         │ │ Before scale: QA rule + tag override│
│ Status: AMBER                    │ │ Owner: PM (Tri Thanh) + Eng lead   │
│ Action: A/B safety-first copy     │ │                                    │
└────────────────────────────────────┘ └────────────────────────────────────┘
```

---

## Part D — Decision Memo

```markdown
# Memo Quyết Định Cuối — AI PT Copilot

1. Nhóm khuyến nghị: **tiếp tục** (Continue) — với điều kiện ưu tiên trust workflow trước growth.

2. Chỉ số mạnh nhất để bảo vệ quyết định là:
   **% buổi tập có “human confirm” hoàn tất trên set nặng (RPE≥7)** kết hợp **trust score sau buổi**,
   vì đây là chuỗi duy nhất nối **usage → quality/trust → retention** mà không bị cheat bằng mở app nhiều lần.

3. Chỉ số nhóm đã sửa sau phản biện:
   **V1:** “AI prompts per session” và “weekly active sessions” làm thước engagement.
   **V2:** thay bằng **confirm completion rate** + **override có tag lý do** + **trust score có điều kiện (post-calibration)**.
   V1 yếu vì dễ gaming và học sai từ các case kiểu **Klarna** (đo coverage). V2 đo hành vi có trách nhiệm trong workflow.

4. Trước khi scale sản phẩm, nhóm phải:
   1. Chốt schema event `confirm` / `override_reason` — Owner Eng — hết tuần 2 pilot.
   2. Chạy 30-user cohort với **safety cap** tempo — Owner PM — tuần 3–4.
   3. Review mẫu 20 video **human spot-check** / tuần — Owner Product + advisor — liên tục 8 tuần.
```

---

## ≥2 thay đổi bắt buộc v1 → v2 (tóm tắt)

| # | V1 | V2 |
|---|----|----|
| 1 | Engagement = session + prompt volume | Engagement = **confirm completion** trên set có rủi ro + applied cue rate |
| 2 | Survey trust ngẫu nhiên | Trust **sau buổi đạt calibration** + giảm tần suất hỏi để tránh fatigue (học red-team User) |
