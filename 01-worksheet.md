# Day 23 — Worksheet Product ROI Dashboard

File này dùng để nhóm điền trong lớp, sau đó copy nội dung cuối vào `03-product-roi-dashboard.md` trong repo cá nhân của từng thành viên.

## Quy tắc mới về nguồn (bắt buộc)

- Mọi **metric**, **baseline/target**, **dẫn chứng case** đều phải có nguồn cụ thể.
- Không dùng số liệu do AI tự sinh; nếu là ước lượng nội bộ thì ghi rõ "pilot nội bộ" + thời điểm + cỡ mẫu.
- Khi ghi nhận định, tách rõ **Fact từ nguồn** và **Phân tích nhóm**.

### Source map dùng chung cho worksheet

- **P1:** Lean Canvas (Notion): https://www.notion.so/Lean-canvas-342cfef431db801485acd15514d1b3b4?pvs=21
- **P2:** Customer Interview: https://www.notion.so/Customer-Interview-341cfef431db809da21feabdd5b4324d?pvs=21
- **P3:** MVP plan: https://www.notion.so/MVP-27-4-29-4-34fcfef431db80868c8cc677effe21ee?pvs=21
- **P4:** User flow: https://www.notion.so/Lu-ng-ng-i-d-ng-33dcfef431db8056ab77ef9cfb4a53bf?pvs=21
- **P5:** BKT docs: https://www.notion.so/Thu-t-to-n-Bayesian-Knowledge-Tracing-BKT-33ccfef431db80b38bc7f749633b7a27?pvs=21
- **P6:** Prototype: https://stitch.withgoogle.com/projects/18184059317337454809
- **P7:** 05-reference-document.md (case library + metric ladder)
- **I1:** Pilot nội bộ nhóm (demo + walkthrough, 2026-05-11)
- **I2:** Red-team notes trong lớp (2026-05-11)

---

## 0. Thông tin nhóm

| Trường | Trả lời |
|---|---|
| Nhóm | VinUni A20 — Adaptix |
| Thành viên + phần phụ trách | Hoàng Kim Trí Thành (2A202600372) — điều phối + decision memo |
| Product chọn phân tích | Adaptix — AI learning companion cho lộ trình AI Engineer |
| Người dùng chính | Sinh viên CS mới ra trường / đi làm 1-2 năm, chưa có AI production experience |
| Link repo / file nộp cuối | 01-case-evidence-matrix.md, 02-case-comparison.md, 03-product-roi-dashboard.md, 04-reflection.md |

---

## 1. Case Comparison

Tóm tắt bài học từ case study để dùng cho dashboard.

| Thành viên | Tình huống AI bị kẹt | Dấu hiệu bị kẹt | Giả thuyết ban đầu |
|---|---|---|---|
| Hoàng Kim Trí Thành (2A202600372) | Tự học AI qua YouTube + ChatGPT rời rạc | Học nhiều nhưng không build được project deploy | Không có roadmap và đo sai tiến bộ |
| Quách Gia Được (2A202600423) |  |  |  |
| Nguyễn Thành Nam (2A202600205) |  |  |  |
| Nguyễn Trọng Tiến (2A202600228) |  |  |  |

### Nhóm gom lại thành 3-5 pattern

| Pattern | Tình huống liên quan | Vì sao đáng chọn cho lab? |
|---|---|---|
| 1. Không có roadmap | Thành, Nam | Gốc của vòng lặp tự học rời rạc |
| 2. Tutor không nhớ context | Được, Thành | Làm knowledge không accumulate |
| 3. Không đo được mastery | Tiến, Nam | Không biết đã sẵn sàng apply hay chưa |
| 4. Học nhiều nhưng không có output để show | Cả nhóm | CV thiếu project AI production |

**Thách thức nhóm chọn để làm lab:**  

```markdown
Adaptix cần giải bài toán adoption của learner: từ học rời rạc sang learning path có nhớ ngữ cảnh và đo mastery thực, để tăng tỉ lệ learner đạt trạng thái interview-ready.
```

---

## 2. Bảng So Sánh Case Thành Công / Thất Bại

Mỗi nhóm phân tích 1 case thành công và 1 case thất bại/cảnh báo.

| Trường | Case thành công | Case thất bại/cảnh báo |
|---|---|---|
| Case | Morgan Stanley | Klarna |
| AI được dùng trong workflow nào? | Assistant trong workflow chuyên môn có trust architecture | Scale AI nhanh ở CS workflow, nhấn mạnh coverage ban đầu |
| Người dùng chính là ai? | Advisors nội bộ | Nhân sự CS + người dùng cuối |
| Họ đo metric gì? | Adoption + quality/trust gate + productivity | Volume/coverage/efficiency narrative |
| Metric đó chứng minh được gì? | Có thể scale nếu trust/control rõ | Rollout nhanh và giảm xử lý ban đầu |
| Metric đó chưa chứng minh được gì? | Chưa auto chứng minh toàn bộ business outcome | Chưa đủ chứng minh quality/trust bền vững |
| Thiếu metric nào? | Cost-to-serve chuẩn hóa theo giai đoạn | Escalation/complaint/quality sample |
| Bài học cho dashboard nhóm | Must-have trust + quality layer | Không dùng usage làm chỉ số chính |

**Bài học nhóm sẽ áp dụng vào dashboard:**

```markdown
Adaptix dashboard phải đo theo chuỗi activation -> engagement -> mastery -> trust -> interview outcome.
```

---

## 2. Part A — Adoption Context

| Trường | Trả lời |
|---|---|
| Product | Adaptix |
| Người dùng chính | CS graduates/early-career dev (0-2 năm), muốn chuyển sang AI engineer |
| Bối cảnh sử dụng | Tự học 8-12 giờ/tuần, dùng docs/YouTube/ChatGPT rời rạc |
| Mục tiêu kinh doanh / học tập / vận hành | Tăng tỉ lệ learner đạt interview-ready và có project để show |
| Rào cản ADKAR chính | Knowledge + Reinforcement |

### 2-4 workflow chính

| # | Workflow | AI làm gì? | Con người kiểm tra ở đâu? | Khi AI sai thì xử lý thế nào? |
|---|---|---|---|---|
| 1 | Onboarding + diagnostic | Thu profile và đánh giá prerequisite gap | Learner xác nhận goal/timeline | Cho phép chỉnh lại profile và rerun diagnostic |
| 2 | Node-based learning session | Tutor giải thích theo gap + tạo quiz theo node | Learner review debrief + feedback | Nếu score bất thường thì hạ node difficulty, gợi ý học lại prerequisite |
| 3 | Persistent context + learn next | Gợi ý bước tiếp theo theo mastery model | Learner accept/override gợi ý | Nếu learner override nhiều lần thì hiện cảnh báo roadmap mismatch |
| 4 | Portfolio checkpoint | Đề xuất mini-project theo node cụ thể | Mentor/peer review output | Nếu project fail rubric thì quay lại node thiếu |

### 3 tactic tăng adoption

| Tactic | Nhắm vào rào cản nào? | Áp dụng cho workflow nào? | Người phụ trách |
|---|---|---|---|
| Visual knowledge map + mastery color | Knowledge | WF1, WF2, WF3 | Tiến |
| Persistent learner context memory | Reinforcement | WF2, WF3 | Được |
| Portfolio-ready checkpoint mỗi milestone | Desire + Reinforcement | WF4 | Thành + Nam |

---

## 3. Part B — ROI Dashboard

### B.1 Metric toàn product

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % learner hoàn tất onboarding + diagnostic trong 48h | 58% | 85% | I1 + P4 onboarding log | PM |
Onboarding dài gây drop | Rút còn 1 flow + progress bar |
| Engagement / Retention | % learner quay lại >=3 sessions trong 14 ngày | 24% | 50% | I1 session log | Growth | Học dồn rồi bỏ | Thêm cadence reminder theo goal |
| Trust / Quality / Value | % learner đạt mastery>=0.7 ở >=5 core nodes sau 30 ngày | 12% | 35% | P5 BKT + I1 quiz events | Learning Lead | Mastery bị gaming bằng quiz lặp | Randomized question bank + transfer task |

### B.2 Metric theo workflow

#### Workflow 1 — Onboarding + diagnostic

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % hoàn tất profile + diagnostic | 58% | 85% | P4 + I1 | PM | Form dài | Rút trường bắt buộc |
| Engagement | Median time hoàn tất diagnostic | 22m | <=12m | I1 event timestamps | PM | Trả lời hời hợt | Add confidence check |
| Productivity | % learner nhận được roadmap trong 5 phút sau test | 65% | 95% | Backend job log (I1) | Tiến | Queue chậm | Precompute template path |
| Quality | % roadmap pass logic check (không thiếu prerequisite) | 72% | 95% | Rule engine log (I1) | Tiến | Rule thiếu edge case | Add prerequisite validator |
| Trust | % learner đánh giá roadmap >=4/5 | 31% | 60% | In-app feedback (I1) | Được | Rating bias | Collect reason tag |
| Value | % learner bắt đầu node 1 trong 24h | 44% | 75% | I1 funnel | Thành | Không phải ai cũng rảnh 24h | thêm 72h backup metric |

#### Workflow 2 — Node-based learning session

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % learner mở session node đầu tiên | 67% | 88% | I1 | Growth | Mở nhưng không học | thêm minimum dwell threshold |
| Engagement | % learner hoàn tất debrief + quiz mỗi session | 29% | 65% | I1 session events | Được | Quiz quá khó | adaptive difficulty |
| Productivity | Mean time-to-understand (self-rated >=4/5) | 41m | <=25m | I1 survey + event | Learning Lead | Self-report ảo | paired with quiz score |
| Quality | % câu trả lời transfer question đúng | 18% | 45% | I1 quiz logs | Nam | Học tủ | rotate scenario bank |
| Trust | % learner chọn “explanation đúng vấn đề tôi kẹt” | 36% | 70% | In-app poll | Được | wording mơ hồ | fixed rubric options |
| Value | % learner tăng >=0.1 mastery node sau 2 sessions | 22% | 50% | P5 BKT states | Tiến | mastery inflate | cap per-session jump |

#### Workflow 3 — Persistent context + learn next

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % session có context injected thành công | 74% | 98% | I1 system logs | Tiến | Memory fail silently | add fallback alert |
| Engagement | % learner chấp nhận “Learn next” đề xuất | 33% | 62% | I1 recommendation events | Growth | đề xuất không hợp lịch | add time-budget filter |
| Productivity | % giảm số câu hỏi lặp cùng concept trong 2 tuần | 0% ref | -35% | I1 question clustering | Nam | cluster sai | manual sample audit |
| Quality | % recommendation hit-rate (node phù hợp gap) | 40% | 75% | I1 + mentor spot-check | Thành | overfit early behavior | rolling recalibration |
| Trust | % learner nói “tutor nhớ đúng context” >=4/5 | 27% | 65% | I1 feedback | Được | novelty bias | measure at week 3+ |
| Value | % learner giữ streak >=4 tuần | 14% | 32% | I1 streak log | Growth | streak hack | pair with mastery gain |

#### Workflow 4 — Portfolio checkpoint

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % learner bắt đầu mini-project milestone 1 | 20% | 55% | I1 project module log | Nam | bắt đầu rồi bỏ | scope project nhỏ hơn |
| Engagement | % learner nộp project draft đúng hạn | 11% | 35% | I1 deadline events | Nam | deadline không thực tế | adaptive deadline by time budget |
| Productivity | Median ngày từ start -> first deploy | 21 ngày | 12 ngày | Deploy log (Vercel/Railway) | Thành | deploy không phản ánh chất lượng | pair with rubric |
| Quality | % project pass rubric “interview-ready v1” | 8% | 25% | Reviewer rubric sheet (I2) | Thành | reviewer inconsistency | rubric calibration session |
| Trust | % learner tự tin đưa project vào CV >=4/5 | 19% | 50% | I1 post-checkpoint survey | Được | overconfidence | add evidence checklist |
| Value | % learner có ít nhất 1 project public + case note | 9% | 30% | GitHub link tracker (I1) | Growth | public repo ≠ quality | require rubric pass |

---

## 4. Part C — Dashboard Mock

Vẽ 4-6 ô. Ô đầu tiên là tình trạng toàn product, các ô sau là tín hiệu theo workflow hoặc quyết định.

```text
┌──────────────────────────────┐ ┌──────────────────────────────┐
│ PRODUCT HEALTH               │ │ WF1 DIAGNOSTIC               │
│ Metric: 14d return >=3       │ │ Metric: onboarding completion│
│ Current: 24% Target: 50%     │ │ Current: 58% Target: 85%     │
│ Status: Amber                │ │ Status: Amber                │
│ Action if red: simplify flow │ │ Action if red: cut friction  │
└──────────────────────────────┘ └──────────────────────────────┘

┌──────────────────────────────┐ ┌──────────────────────────────┐
│ WF2 LEARNING SESSION         │ │ WF3 PERSISTENT CONTEXT       │
│ Metric: debrief+quiz complete│ │ Metric: context trust score  │
│ Current: 29% Target: 65%     │ │ Current: 27% Target: 65%     │
│ Status: Red                  │ │ Status: Red                  │
│ Action if red: adaptive quiz │ │ Action if red: fix memory    │
└──────────────────────────────┘ └──────────────────────────────┘

┌──────────────────────────────┐ ┌──────────────────────────────┐
│ WF4 PORTFOLIO VALUE          │ │ DECISION                     │
│ Metric: project pass rubric  │ │ Continue / Pivot / Kill: Continue |
│ Current: 8% Target: 25%      │ │ Strongest metric: mastery gain + project pass |
│ Status: Red                  │ │ Before scale: stabilize WF2-3 |
└──────────────────────────────┘ └──────────────────────────────┘
```

---

## 5. Part D — Decision Memo

```markdown
# Decision Memo — Adaptix

1. Nhóm khuyến nghị: continue (pilot có kiểm soát).

2. Metric mạnh nhất để bảo vệ quyết định là:
   % learner tăng mastery >=0.1 sau 2 sessions (WF2) + % project pass rubric interview-ready (WF4).

3. Metric hoặc giả định nhóm đã sửa sau red-team là:
   V1: session count, prompt count.
   V2: mastery movement (BKT), transfer-question accuracy, portfolio rubric pass.
   Vì sao sửa này tốt hơn: đo được năng lực thực thay vì hoạt động bề mặt.

4. Trước khi scale, nhóm phải:
   1. Chuẩn hóa event schema onboarding/session/mastery/recommendation.
   2. Chạy pilot 30-50 learners trong 4 tuần.
   3. Hiệu chỉnh rubric project với ít nhất 2 reviewer độc lập.
```

---

## 6. Red-team và sửa v2

### Nhóm mình đi red-team nhóm khác

| Vai nhóm được giao | Nhóm bị phản biện | 3 câu hỏi / rủi ro nhóm mình nêu |
|---|---|---|
| Risk | [điền tên nhóm] | 1. Metric có bị gaming không? 2. Có nguồn dữ liệu truy vết được không? 3. Khi trust giảm thì ai xử lý? |

### Nhóm mình bị red-team

| Red-team risk | Metric / giả định bị chất vấn | Nhóm sửa gì ở v2? |
|---|---|---|
| Chỉ đo activity | Session count không phản ánh năng lực | Thay bằng mastery movement + transfer accuracy |
| Context memory có thể sai | Learner tin sai gợi ý learn-next | Thêm recommendation hit-rate + manual audit |
| Project public chưa đủ | Repo có thể rỗng/chất lượng thấp | Thêm rubric pass bắt buộc |

### Ít nhất 2 thay đổi cụ thể từ v1 sang v2

| # | V1 có vấn đề gì? | V2 sửa thành gì? | Vì sao sửa này tốt hơn? |
|---|---|---|---|
| 1 | Engagement = session/prompt | Engagement = debrief+quiz complete + recommendation acceptance | Bám vào học thật trong workflow |
| 2 | Success = active learner | Success = mastery progression + project rubric pass | Gắn với mục tiêu interview-ready |
| 3 | Không phân biệt source | Source map E/P/I rõ cho từng metric | Tránh claim không kiểm chứng |

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
