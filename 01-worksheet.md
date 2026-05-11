# Day 23 — Worksheet Product ROI Dashboard

File này dùng để nhóm điền trong lớp, sau đó copy nội dung cuối vào `03-product-roi-dashboard.md` trong repo cá nhân của từng thành viên.

## Quy tắc mới về nguồn (bắt buộc)

- Mọi **metric**, **baseline/target**, **dẫn chứng case** đều phải có nguồn cụ thể.
- Không dùng số liệu do AI tự sinh; nếu là ước lượng nội bộ thì ghi rõ "pilot nội bộ" + thời điểm + cỡ mẫu.
- Khi ghi nhận định, tách rõ **Fact từ nguồn** và **Phân tích nhóm**.

### Source map dùng chung cho worksheet

- **E1:** https://openai.com/index/morgan-stanley/
- **E2:** https://openai.com/index/klarna/
- **E3:** https://www.reuters.com/business/swedens-klarna-shifts-ai-focus-cost-cuts-growth-2025-09-10/
- **E4:** `05-reference-document.md` (Section 6, 7, 10)
- **I1:** Pilot log nội bộ nhóm Day 23 (cohort nhỏ 5-8 user, 2026-05-11)
- **I2:** Ghi chú red-team trong lớp (2026-05-11)

> Mẹo điền nhanh: ở cột `Data source`, ghi luôn mã nguồn (VD: `I1`, `E2+E3`) để truy vết.

---

## 0. Thông tin nhóm

| Trường | Trả lời |
|---|---|
| Nhóm | VinUni A20 — AI PT Copilot |
| Thành viên + phần phụ trách | Hoàng Kim Trí Thành (2A202600372) — điều phối + decision memo; Quách Gia Được (2A202600423) — workflow map + trust UX; Nguyễn Thành Nam (2A202600205) — case comparison + red-team log; Nguyễn Trọng Tiến (2A202600228) — metric design + data source/owner |
| Product chọn phân tích | AI PT Copilot (gợi ý rep/tempo/tư thế khi tập tại nhà) |
| Người dùng chính | Người tập tại nhà 18–45 tuổi, không có PT trực tiếp |
| Link repo / file nộp cuối | 01-case-evidence-matrix.md, 02-case-comparison.md, 03-product-roi-dashboard.md, 04-reflection.md |

---

## 1. Case Comparison

Tóm tắt bài học từ case study để dùng cho dashboard.

| Thành viên | Tình huống AI bị kẹt | Dấu hiệu bị kẹt | Giả thuyết ban đầu |
|---|---|---|---|
| Hoàng Kim Trí Thành (2A202600372) | | | |
| Quách Gia Được (2A202600423) | | | |
| Nguyễn Thành Nam (2A202600205) | | | |
| Nguyễn Trọng Tiến (2A202600228) | Ứng dụng AI để tự động hóa B24 translation cho sản phẩm, nhưng có nhiều trường hợp đặc biệt theo từng ngôn ngữ như tên sản phẩm phải giữ nguyên TA, đại từ xưng hô, từ chuyên ngành và các từ đa nghĩa | Reviewer phải yêu cầu sửa nhiều vòng, output không consistent giữa các ngôn ngữ, tốn nhiều token do prompt/retry liên tục | Chưa có bộ context và guideline chuẩn cho translation (glossary, reserved words, language rules, edge cases) để AI và intern follow thống nhất|

### Nhóm gom lại thành 3-5 pattern

| Pattern | Tình huống liên quan | Vì sao đáng chọn cho lab? |
|---|---|---|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |

**Thách thức nhóm chọn để làm lab:**  

```markdown
...
```

---

## 2. Bảng So Sánh Case Thành Công / Thất Bại

Mỗi nhóm phân tích 1 case thành công và 1 case thất bại/cảnh báo. Dùng `04-reference/case-clinic-summary.md` nếu cần.

| Trường | Case thành công | Case thất bại/cảnh báo |
|---|---|---|
| Case | Stripe | Klarna |
| AI được dùng trong workflow nào? | Dev workflow: AI draft -> PR review -> merge | CS/marketing workflow rollout rộng, nhấn mạnh coverage |
| Người dùng chính là ai? | Kỹ sư nội bộ có baseline cao | Nhân viên CS + stakeholder vận hành |
| Họ đo metric gì? | Cycle time, defect/rework sau review | Tỷ lệ dùng AI, thông điệp AI-first, coverage |
| Metric đó chứng minh được gì? | Productivity có qua cổng quality (review gate) | Khả năng triển khai nhanh và tạo hiệu ứng truyền thông |
| Metric đó chưa chứng minh được gì? | Chưa tự chứng minh ROI tài chính nếu thiếu cost model | Chưa chứng minh trust, CSAT, complaint sau scale |
| Thiếu metric nào? | Cost-to-serve theo giai đoạn | Escalation rate, QA pass sample, override reason |
| Bài học cho dashboard nhóm | Metric phải đi qua human review + quality | Không dùng usage/coverage làm bằng chứng thành công cuối cùng |

**Bài học nhóm sẽ áp dụng vào dashboard:**

```markdown
Mỗi workflow phải đo theo chuỗi: activation -> human confirm -> quality/trust -> value.
Không chốt thành công chỉ dựa vào session count hoặc prompt count.
```

---

## 2. Part A — Adoption Context

| Trường | Trả lời |
|---|---|
| Product | AI PT Copilot mobile |
| Người dùng chính | Người tập tại nhà, tập 3-5 buổi/tuần |
| Bối cảnh sử dụng | Dùng camera điện thoại để theo dõi tư thế + rep |
| Mục tiêu kinh doanh / học tập / vận hành | Tăng retention tuần 2-4, giảm discomfort escalation, giảm time-to-first-aha |
| Rào cản ADKAR chính | Knowledge + Reinforcement |

### 2-4 workflow chính

| # | Workflow | AI làm gì? | Con người kiểm tra ở đâu? | Khi AI sai thì xử lý thế nào? |
|---|---|---|---|---|
| 1 | Calibration & first session | Căn khung và tư thế baseline | User xác nhận khung rõ, pass checklist | Fallback sang preset an toàn + video hướng dẫn |
| 2 | Live set coaching | Gợi ý rep/tempo, cảnh báo pose lệch | User confirm sau set nặng (RPE>=7) | Không cho tăng tải buổi sau, buộc review |
| 3 | Post-session recap | Tóm tắt volume/RPE, gợi ý nghỉ | User chỉnh RPE thực tế | Nếu mismatch lớn thì flag và điều chỉnh plan thủ công |
| 4 | - | - | - | - |

### 3 tactic tăng adoption

| Tactic | Nhắm vào rào cản nào? | Áp dụng cho workflow nào? | Người phụ trách |
|---|---|---|---|
| Confirm-safe micro-flow cho set nặng | Knowledge + Trust | Workflow 2 | Thành + Tiến |
| Safety card 1-tap có giải thích ngắn | Trust | Workflow 1-2 | Được |
| Buddy week + recap có ngữ cảnh | Reinforcement | Workflow 3 | Nam |

---

## 3. Part B — ROI Dashboard

### B.1 Metric toàn product

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % user hoàn tất calibration + buổi đầu <=10 phút | 55% | 80% | Onboarding funnel | Thành | Chỉ đẹp onboarding, chưa chắc value | Theo dõi drop-off theo từng step |
| Engagement / Retention | % user có >=3 buổi có human confirm trong 14 ngày | 18% | 40% | Event `set_completed`, `human_confirm` | Tiến | Confirm quá dày gây mệt | Chỉ bắt buộc set nặng + QA sample |
| Trust / Quality / Value | Trust score sau buổi (khi pass calibration) | 3.1/5 | 4.0/5 | In-app survey có điều kiện | Được | Survey bias khi user bực | Hỏi theo trigger phù hợp + thêm passive signal |

### B.2 Metric theo workflow

Sao chép block dưới cho mỗi workflow đã chọn. Mỗi workflow cần ít nhất 4 layer, ưu tiên Productivity + Quality + Trust hoặc Value.

#### Workflow 1 — Calibration & first session

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % hoàn tất calibration | 62% | 85% | Onboarding events | Tiến | Quy trình dài gây drop | Cắt 1 bước + lưu trạng thái tạm |
| Engagement | Time-to-first-working-rep | 8m | <=6m | Session timeline | Tiến | Loading chậm | Cache model nhẹ + skeleton UI |
| Productivity | Retry calibration/user | 2.1 | <=1.5 | Retry count | Được | Support cost tăng | Diagnostic tự phục hồi |
| Quality | % pass QA frame rule | 70% | 90% | CV logs | Tiến | False pass | Bắt buộc user confirm khung rõ |
| Trust | % user chọn “không khớp” | 12% | <8% | UI event | Được | User không hiểu nút | Tooltip + icon hướng dẫn |
| Value | % user vào WF2 trong 24h | 48% | 70% | Cross-workflow funnel | Thành | Chưa nói được bền vững | Theo dõi thêm retention 7 ngày |

#### Workflow 2 — Live set coaching

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % set bật AI cue | 90% | 85% | Feature flag log | Tiến | Bật AI != dùng đúng | Đổi KPI thành % set có applied cue |
| Engagement | % set nặng có confirm | 22% | 55% | `confirm_tap` | Thành | Friction khi confirm | Chỉ bắt buộc RPE>=7/compound |
| Productivity | Median time/rep variance | baseline | -5% an toàn | Motion + timer | Tiến | Đẩy nhanh quá mức | Cap tempo + hard stop pose red |
| Quality | % override có tag lý do | 65% | 100% | Event schema | Nam | Thiếu dữ liệu lý do | Bắt buộc tag khi override |
| Trust | Post-set trust score | 3.0/5 | 4.2/5 | Survey theo set | Được | Bias theo độ mệt | Chỉ hỏi ở mốc hợp lý |
| Value | % discomfort escalation | 3.5% | <2% | Safety ticket | Thành | Under-report | Anonymous log + hotline copy |

#### Workflow 3 — Post-session recap

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % mở recap trong 2h | 40% | 60% | Push + open log | Nam | Spam notification | Chỉ gửi sau buổi có confirm |
| Engagement | % chỉnh RPE thực tế | 15% | 35% | Recap form | Nam | Form dài | Prefill + slider 1 chạm |
| Productivity | Thời gian chỉnh recap | 75s | <45s | UX telemetry | Được | Mất chi tiết | Template ngắn theo goal |
| Quality | % recap khớp log set (+/-10%) | 50% | 80% | Cross-check data | Tiến | Cost pipeline | Reconcile mẫu 30% trước full |
| Trust | % tin đề xuất ngày nghỉ | 28% | 45% | Accept/override event | Thành | Copy khó hiểu | Thêm câu “vì sao nghỉ” |
| Value | 7-day return sau recap mở | 20% | 38% | Cohort retention | Thành | Nhiễu lịch cá nhân | So sánh cohort có/không recap |

#### Workflow 4 — [nếu có]

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | - | - | - | - | - | - | - |
| Engagement | - | - | - | - | - | - | - |
| Productivity | - | - | - | - | - | - | - |
| Quality | - | - | - | - | - | - | - |
| Trust | - | - | - | - | - | - | - |
| Value | - | - | - | - | - | - | - |

---

## 4. Part C — Dashboard Mock

Vẽ 4-6 ô. Ô đầu tiên là tình trạng toàn product, các ô sau là tín hiệu theo workflow hoặc quyết định.

```text
┌──────────────────────────────┐ ┌──────────────────────────────┐
│ PRODUCT HEALTH               │ │ WORKFLOW 1                   │
│ Metric: 3-session confirm    │ │ Metric: calib <=10'          │
│ Current: 18% Target: 40%     │ │ Current: 55% Target: 80%     │
│ Status: Amber                │ │ Status: Amber                │
│ Action if red: confirm-lite  │ │ Action if red: cut 1 step    │
└──────────────────────────────┘ └──────────────────────────────┘

┌──────────────────────────────┐ ┌──────────────────────────────┐
│ WORKFLOW 2                   │ │ QUALITY / TRUST              │
│ Metric: heavy-set confirm    │ │ Metric: trust score          │
│ Current: 22% Target: 55%     │ │ Current: 3.1 Target: 4.0     │
│ Status: Red                  │ │ Status: Amber                │
│ Action if red: force RPE>=7  │ │ Action if red: adjust trigger│
└──────────────────────────────┘ └──────────────────────────────┘

┌──────────────────────────────┐ ┌──────────────────────────────┐
│ VALUE                         │ │ DECISION                     │
│ Metric: 7-day return          │ │ Continue / Pivot / Kill: Continue |
│ Current: 20% Target: 38%      │ │ Metric mạnh nhất: confirm+trust |
│ Status: Amber                 │ │ Before scale: pilot 60 ngày   |
└──────────────────────────────┘ └──────────────────────────────┘
```

---

## 5. Part D — Decision Memo

```markdown
# Decision Memo — AI PT Copilot

1. Nhóm khuyến nghị: continue (pilot có kiểm soát).

2. Metric mạnh nhất để bảo vệ quyết định là:
   % heavy-set có human confirm hoàn tất + trust score sau buổi.

3. Metric hoặc giả định nhóm đã sửa sau red-team là:
   V1: prompt/session và session/week.
   V2: confirm completion + override reason + trust có điều kiện.
   Vì sao sửa này tốt hơn: khó bị cheat, đo đúng hành vi trong workflow có rủi ro.

4. Trước khi scale, nhóm phải:
   1. Chốt schema event confirm/override trong 2 tuần.
   2. Chạy pilot 30-50 user có safety cap.
   3. Review mẫu video hằng tuần trước rollout rộng.
```

---

## 6. Red-team và sửa v2

### Nhóm mình đi red-team nhóm khác

| Vai nhóm được giao | Nhóm bị phản biện | 3 câu hỏi / rủi ro nhóm mình nêu |
|---|---|---|
| Risk | [điền tên nhóm] | 1. AI sai ai chịu trách nhiệm? 2. Có audit trail theo workflow không? 3. Khi metric đỏ thì ai hành động? |

### Nhóm mình bị red-team

| Red-team risk | Metric / giả định bị chất vấn | Nhóm sửa gì ở v2? |
|---|---|---|
| Confirm quá dày gây phiền | Engagement đo bằng confirm mọi set | Chỉ bắt buộc confirm cho set nặng |
| Trust survey bias | Survey hỏi ngẫu nhiên | Hỏi sau pass calibration, sampling hợp lý |
| Data pipeline tốn chi phí | Reconcile chất lượng full-scan | Đổi sang sampled reconcile 30% |

### Ít nhất 2 thay đổi cụ thể từ v1 sang v2

| # | V1 có vấn đề gì? | V2 sửa thành gì? | Vì sao sửa này tốt hơn? |
|---|---|---|---|
| 1 | Đo prompt/session là engagement chính | Đo heavy-set confirm rate + applied cue rate | Gắn vào hành vi an toàn trong workflow |
| 2 | Hỏi trust ngẫu nhiên | Hỏi trust theo điều kiện + giảm tần suất | Giảm fatigue, tăng độ tin cậy dữ liệu |
| 3 | Không bắt buộc lý do override | Bắt buộc tag override reason | Có dữ liệu sửa model/UX đúng điểm nghẽn |

---

## 7. Checklist trước khi nộp

- [x] Có 1 product cụ thể, không chọn "AI cho cả công ty".
- [x] Có 2-4 workflow chính.
- [x] Mỗi workflow có vai trò AI, human review và failure path.
- [x] Có rào cản ADKAR chính.
- [x] Dashboard có metric toàn product và metric theo workflow.
- [x] Không chỉ đo usage: login, prompt count, DAU/MAU.
- [x] Có baseline, target, data source và owner cho các metric chính.
- [x] Có ít nhất 1 metric Quality, Trust hoặc Value.
- [x] Có Red-team risk và Fix.
- [x] Có ít nhất 2 thay đổi rõ từ v1 sang v2.
- [x] Decision Memo có continue / pivot / kill.
