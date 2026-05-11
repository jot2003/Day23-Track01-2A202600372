# 03 — Product ROI Dashboard (Parts A–D) v2

**Sản phẩm:** Adaptix  
**Phiên bản:** v2 (sau red-team Block 4–5)  
**Phụ trách tổng hợp file nhóm:** Hoàng Kim Trí Thành (2A202600372)

---

## Source map (bắt buộc)

### Product/internal sources
- **P1:** Lean Canvas — https://www.notion.so/Lean-canvas-342cfef431db801485acd15514d1b3b4?pvs=21
- **P2:** Customer Interview — https://www.notion.so/Customer-Interview-341cfef431db809da21feabdd5b4324d?pvs=21
- **P3:** MVP (27/4-29/4) — https://www.notion.so/MVP-27-4-29-4-34fcfef431db80868c8cc677effe21ee?pvs=21
- **P4:** Luồng người dùng — https://www.notion.so/Lu-ng-ng-i-d-ng-33dcfef431db8056ab77ef9cfb4a53bf?pvs=21
- **P5:** Thuật toán BKT — https://www.notion.so/Thu-t-to-n-Bayesian-Knowledge-Tracing-BKT-33ccfef431db80b38bc7f749633b7a27?pvs=21
- **P6:** Prototype — https://stitch.withgoogle.com/projects/18184059317337454809
- **I1:** Pilot nội bộ Day 23 (demo/walkthrough, cohort nhỏ, 2026-05-11)
- **I2:** Red-team notes trong lớp (2026-05-11)

### External references for decision logic
- **E1:** OpenAI Morgan Stanley — https://openai.com/index/morgan-stanley/
- **E2:** OpenAI Klarna — https://openai.com/index/klarna/
- **E3:** Reuters Klarna 2025 — https://www.reuters.com/business/swedens-klarna-shifts-ai-focus-cost-cuts-growth-2025-09-10/
- **E4:** `05-reference-document.md` (metric ladder + measurement trap)

---

## Part A — Adoption Context

### A.1 Thách thức nhóm chọn

| Trường | Trả lời | Nguồn |
|--------|---------|-------|
| Thách thức áp dụng AI | Learner học AI rời rạc, thiếu roadmap, thiếu memory xuyên session, không đo được tiến bộ thật | P2, P1 |
| Tình huống xuất phát từ ai / ở đâu? | ICP: CS graduate / 0-2 năm kinh nghiệm dev, chưa có AI production experience | P1, P2 |
| Dấu hiệu bị kẹt | Học nhiều tài nguyên nhưng không biết đang thiếu node nào; không có project để show CV | P2 |
| Vì sao đáng giải quyết? | Đây là barrier chính chặn hành trình từ self-learning -> interview-ready | P1, P3 |

### A.2 Sản phẩm / công cụ AI

| Trường | Trả lời | Nguồn |
|--------|---------|-------|
| Tên sản phẩm / công cụ AI | Adaptix |
| Người dùng chính | Sinh viên CS mới ra trường / early-career dev 0-2 năm | P1 |
| Bối cảnh sử dụng | Tự học 8-12h/tuần, dùng YouTube/docs/ChatGPT rời rạc | P2 |
| Mục tiêu kinh doanh / học tập / vận hành | Tăng mastery thực + tăng tỉ lệ có portfolio interview-ready | P1, P3 |
| Không nằm trong phạm vi | Không phải bootcamp full-time; không thay thế mentor 1:1 toàn phần | P3 |

### A.3 2–4 quy trình chính

| # | Tên quy trình | Vai trò AI | Điểm người kiểm tra | Khi AI sai thì xử lý thế nào? | Nguồn |
|---|----------------|------------|---------------------|--------------------------------|-------|
| 1 | Onboarding + diagnostic | Thu profile + phát hiện prerequisite gap | Learner confirm goal/timeline | Cho edit profile + rerun diagnostic | P4, I1 |
| 2 | Node learning session | Giải thích theo gap + quiz theo node | Learner debrief + feedback | Nếu fail transfer question thì quay lại prerequisite | P4, P5 |
| 3 | Persistent context + Learn next | Gợi ý bước tiếp theo theo mastery state | Learner accept/override | Override nhiều lần -> flag mismatch và điều chỉnh plan | P5, I1 |
| 4 | Portfolio checkpoint | Gợi ý mini-project theo node đã đạt | Mentor/peer review theo rubric | Fail rubric -> quay lại node yếu | P3, I2 |

### A.4 ADKAR — barrier chính

| Stage | Nhận định nhóm | Nguồn |
|-------|----------------|-------|
| Awareness | Ổn (người học biết AI quan trọng cho career) | P2 |
| Desire | Có nhưng thiếu niềm tin vì tiến bộ mơ hồ | P2 |
| Knowledge | Yếu (không biết thứ tự học và prerequisite) | P2, P4 |
| Ability | Trung bình (học được từng phần nhưng không nối thành pipeline) | P2 |
| Reinforcement | Yếu (không có hệ theo dõi mastery + portfolio checkpoint rõ) | P5, P3 |

**Barrier chính:** Knowledge + Reinforcement.  

### A.5 3 tactic adoption

| # | Tactic | Nhắm barrier | Quy trình | Owner | Hoàn thành | Nguồn |
|---|--------|---------------|-----------|-------|-------------|-------|
| 1 | Visual knowledge graph + node state | Knowledge | WF1-2-3 | Tiến | Tuần 1-2 | P4, P5 |
| 2 | Persistent learner model context | Reinforcement | WF2-3 | Được | Tuần 2-3 | P5 |
| 3 | Portfolio milestone theo rubric | Desire + Reinforcement | WF4 | Thành + Nam | Tuần 3-4 | P3, I2 |

### A.6 Chẩn đoán nguyên nhân gốc

| Lens | Chẩn đoán | Evidence | Nguồn |
|------|-----------|----------|-------|
| Workflow | Học theo tài nguyên rời rạc, chưa có hành trình theo node | interview notes cho thấy learner tự ghép tài nguyên | P2 |
| Metrics | Người học tự đo bằng giờ học/prompt => đo sai value | measurement trap theo tài liệu lớp | E4, P2 |
| Trust/Quality | Không có tín hiệu “đã hiểu thật” và “sẵn sàng apply” | thiếu mastery tracking + portfolio rubric | P5, P3 |

**Nguyên nhân gốc chốt:** thiếu learner-state memory và thiếu hệ metric mastery->outcome.

---

## Part B — Product ROI Dashboard

### Ghi chú dữ liệu
- Baseline trong bảng là pilot nội bộ I1 (sample nhỏ, chỉ dùng để quyết định iteration).
- Không dùng như benchmark thị trường.

### B.1 Chỉ số toàn sản phẩm

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu 60 ngày | Nguồn dữ liệu cụ thể | Owner | Rủi ro red-team | Fix v2 | Nguồn dẫn chứng |
|--------|--------|-------------|------------------|----------------------|-------|-----------------|--------|-----------------|
| Activation | % learner hoàn tất onboarding+diagnostic trong 48h | 58% | 85% | I1 onboarding events + P4 flow | PM | Form dài/drop giữa chừng | Rút số trường bắt buộc | I1, P4 |
| Retention / Engagement | % learner quay lại >=3 sessions/14 ngày | 24% | 50% | I1 session logs | Growth | Activity cao nhưng học hời hợt | Pair với debrief completion | I1, E4 |
| Trust/Quality/Value | % learner đạt mastery>=0.7 ở >=5 core nodes/30 ngày | 12% | 35% | P5 BKT + I1 quiz events | Learning Lead | Mastery có thể bị gaming | Add transfer questions + cap jump | P5, I2, E4 |

### B.2 Theo từng workflow

#### Workflow 1 — Onboarding + diagnostic

| Lớp đo | Chỉ số | Baseline | Target | Nguồn dữ liệu cụ thể | Owner | Red-team risk | Fix v2 |
|--------|--------|----------|--------|----------------------|-------|----------------|--------|
| Activation | % hoàn tất profile+diagnostic | 58% | 85% | I1 funnel events | PM | Form quá dài | Step-by-step onboarding |
| Engagement | Median thời gian hoàn tất diagnostic | 22m | <=12m | I1 timestamps | PM | Trả lời hời hợt | confidence check question |
| Productivity | % roadmap generate <=5 phút | 65% | 95% | I1 backend job logs | Tiến | Queue chậm | precompute base paths |
| Quality | % roadmap pass prerequisite validator | 72% | 95% | I1 rule logs | Tiến | Sai mapping node | add validator + test cases |
| Trust | % learner rate roadmap >=4/5 | 31% | 60% | I1 feedback form | Được | Rating bias | collect reason tag |
| Value | % learner bắt đầu node 1 trong 24h | 44% | 75% | I1 next-step events | Thành | 24h window cứng | thêm 72h backup metric |

#### Workflow 2 — Node learning session

| Lớp đo | Chỉ số | Baseline | Target | Nguồn dữ liệu cụ thể | Owner | Red-team risk | Fix v2 |
|--------|--------|----------|--------|----------------------|-------|----------------|--------|
| Activation | % learner mở node session đầu tiên | 67% | 88% | I1 session_start | Growth | Mở nhưng bỏ giữa chừng | min dwell threshold |
| Engagement | % learner hoàn tất debrief+quiz | 29% | 65% | I1 session_end + quiz_submit | Được | Quiz quá khó | adaptive difficulty |
| Productivity | Mean time-to-understand (self>=4/5) | 41m | <=25m | I1 survey + events | Learning Lead | self-report bias | pair with accuracy |
| Quality | % transfer-question đúng | 18% | 45% | I1 transfer quiz logs | Nam | học tủ | rotate scenario bank |
| Trust | % learner chọn “tutor đúng chỗ tôi kẹt” | 36% | 70% | I1 micro-poll | Được | wording bias | fixed rubric options |
| Value | % learner tăng >=0.1 mastery sau 2 sessions | 22% | 50% | P5 BKT state delta | Tiến | inflated mastery | cap delta / add decay |

#### Workflow 3 — Persistent context + Learn next

| Lớp đo | Chỉ số | Baseline | Target | Nguồn dữ liệu cụ thể | Owner | Red-team risk | Fix v2 |
|--------|--------|----------|--------|----------------------|-------|----------------|--------|
| Activation | % session context inject thành công | 74% | 98% | I1 context logs | Tiến | fail silent | alert + fallback path |
| Engagement | % learner accept Learn-next suggestion | 33% | 62% | I1 recommendation events | Growth | đề xuất lệch lịch học | add time-budget filter |
| Productivity | % giảm câu hỏi lặp concept/2 tuần | baseline | -35% | I1 question clustering | Nam | cluster sai | sample manual audit |
| Quality | % recommendation hit-rate đúng gap | 40% | 75% | I1 + I2 mentor spot-check | Thành | overfit behavior | rolling recalibration |
| Trust | % learner rate “tutor nhớ đúng context”>=4/5 | 27% | 65% | I1 weekly survey | Được | novelty effect | measure at week 3+ |
| Value | % learner giữ streak >=4 tuần | 14% | 32% | I1 streak logs | Growth | streak hack | pair with mastery gain |

#### Workflow 4 — Portfolio checkpoint

| Lớp đo | Chỉ số | Baseline | Target | Nguồn dữ liệu cụ thể | Owner | Red-team risk | Fix v2 |
|--------|--------|----------|--------|----------------------|-------|----------------|--------|
| Activation | % learner bắt đầu mini-project milestone 1 | 20% | 55% | I1 project module log | Nam | bắt đầu rồi bỏ | giảm scope milestone |
| Engagement | % learner nộp draft đúng hạn | 11% | 35% | I1 deadline events | Nam | deadline cứng | adaptive deadline |
| Productivity | Median ngày từ start -> first deploy | 21 | 12 | Deploy logs (Railway/Vercel) | Thành | deploy != quality | pair with rubric |
| Quality | % project pass rubric interview-ready v1 | 8% | 25% | I2 reviewer rubric | Thành | reviewer inconsistency | calibration session |
| Trust | % learner tự tin đưa project vào CV >=4/5 | 19% | 50% | I1 post-checkpoint survey | Được | overconfidence | evidence checklist |
| Value | % learner có >=1 project public + case note | 9% | 30% | GitHub tracker (I1) | Growth | repo public nhưng rỗng | require rubric pass |

---

## Part C — Dashboard Mock

```text
┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 1: PRODUCT HEALTH             │ │ TILE 2: WF1 DIAGNOSTIC             │
│ Metric: 14d return >=3 sessions    │ │ Metric: onboarding completion       │
│ Current: 24%  Target: 50%          │ │ Current: 58%  Target: 85%           │
│ Status: AMBER                      │ │ Status: AMBER                       │
│ Source: I1                         │ │ Source: I1 + P4                     │
└────────────────────────────────────┘ └────────────────────────────────────┘

┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 3: WF2 LEARNING QUALITY       │ │ TILE 4: WF3 PERSISTENT CONTEXT     │
│ Metric: transfer-question accuracy │ │ Metric: context trust score         │
│ Current: 18%  Target: 45%          │ │ Current: 27%  Target: 65%           │
│ Status: RED                        │ │ Status: RED                         │
│ Source: I1                         │ │ Source: I1                          │
└────────────────────────────────────┘ └────────────────────────────────────┘

┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 5: WF4 PORTFOLIO VALUE        │ │ TILE 6: DECISION                   │
│ Metric: project rubric pass         │ │ Continue (pilot)                    │
│ Current: 8%  Target: 25%           │ │ Strongest: mastery + project pass   │
│ Status: RED                         │ │ Before scale: stabilize WF2-3       │
│ Source: I2 + I1                     │ │ Source: E4 + I1                     │
└────────────────────────────────────┘ └────────────────────────────────────┘
```

---

## Part D — Decision Memo

```markdown
# Memo Quyết Định Cuối — Adaptix

1. Nhóm khuyến nghị: continue (pilot có kiểm soát).

2. Chỉ số mạnh nhất để bảo vệ quyết định là:
   % learner tăng mastery >=0.1 sau 2 sessions (WF2) + % project pass rubric interview-ready (WF4).

3. Chỉ số nhóm đã sửa sau phản biện:
   V1: session count/prompt count.
   V2: debrief+quiz completion, transfer-question accuracy, mastery movement, project rubric pass.
   Vì sao tốt hơn: đo năng lực thực và outcome nghề nghiệp.

4. Trước khi scale:
   1. Chốt event schema onboarding/session/mastery/recommendation.
   2. Chạy pilot 30-50 learners trong 4 tuần.
   3. Calibrate rubric với 2 reviewer độc lập.
```

---

## >=2 thay đổi bắt buộc v1 -> v2

| # | V1 | V2 | Nguồn |
|---|----|----|-------|
| 1 | Engagement = session/prompt | Engagement = debrief+quiz complete + recommendation acceptance | I2, E4 |
| 2 | Success = active learner | Success = mastery movement + transfer accuracy + project rubric pass | I2, P5 |
| 3 | Nguồn metric ghi chung chung | Source map cụ thể P*/I*/E* cho từng metric | I2 |
