# 04 — Reflect cá nhân (150–200 từ)

**Học viên:** Hoàng Kim Trí Thành — **Mã:** 2A202600372  
**Prompt:** Một metric tôi sẽ replace + tại sao (có evidence từ case)

---

Sau red-team, metric tôi chọn để **thay thế** là **“số lần gợi ý AI mỗi buổi tập”** (và các biến thể kiểu prompt count). Metric này nhìn có vẻ “sôi động” nhưng thực chất thưởng cho hành vi **spam gợi ý** hoặc UI buộc user chạm nhiều, không chứng minh người tập **tin và làm theo** đúng phần an toàn. Cơ chế vanity tương tự các case cảnh báo kiểu **Klarna**: khi báo cáo nhấn **coverage / có dùng AI**, tổ chức dễ scale nhầm trước khi có **quality + trust** theo workflow thật.

Tôi sẽ thay bằng **tỷ lệ set nặng có “human confirm” hoàn tất** kết hợp **override có lý do**, vì hai tín hiệu này chỉ tăng khi luồng làm việc có **điểm kiểm người** rõ ràng và dữ liệu gắn **rủi ro**. Prevention cụ thể: schema event bắt buộc tag khi override, và chỉ tính trust survey sau khi user đã pass calibration — tránh bias “vừa bực vừa chấm điểm”. Cách đo này học trực tiếp từ phần **thiếu metric outcome/trust** trong matrix case Klarna và từ chiều **review gate** của case Stripe: metric mạnh là metric đi qua **cổng chất lượng**, không phải metric đếm hoạt động.
