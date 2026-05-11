# 04 — Reflect cá nhân (150–200 từ)

**Học viên:** Hoàng Kim Trí Thành — **Mã:** 2A202600372  
**Prompt:** Một metric tôi sẽ replace + tại sao (có evidence từ case)

---

Sau red-team, metric tôi chọn để **thay thế** là **“số lần gợi ý AI mỗi buổi tập”** (và các biến thể kiểu prompt count). Metric này nhìn có vẻ “sôi động” nhưng thực chất thưởng cho hành vi **spam gợi ý** hoặc UI buộc user chạm nhiều, không chứng minh người tập **tin và làm theo** đúng phần an toàn. Cơ chế vanity tương tự các case cảnh báo kiểu **Klarna**: khi báo cáo nhấn **coverage / có dùng AI**, tổ chức dễ scale nhầm trước khi có **quality + trust** theo workflow thật.

Tôi sẽ thay bằng **tỷ lệ set nặng có human confirm hoàn tất** và **override có lý do (bắt buộc tag)**, vì chỉ tăng khi có **điểm kiểm người** và dữ liệu gắn rủi ro. Trust survey chỉ tính sau khi pass calibration để tránh bias “vừa bực vừa chấm”. Học từ **Klarna** (thiếu outcome/trust) và **Stripe** (review gate): metric mạnh đi qua **cổng chất lượng**, không phải đếm hoạt động.

*(~185 từ tiếng Việt.)*
