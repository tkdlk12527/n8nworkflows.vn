```mdx
---
title: "📝 Tự động Thu thập Lead từ Web Form vào HubSpot qua Submitrax"
description: "Giải pháp no-code giúp các sếp tạo form thu thập khách hàng tiềm năng và tự động đồng bộ vào HubSpot CRM ngay lập tức mà không cần lập trình backend."
slug: tu-dong-thu-thap-lead-submitrax-hubspot
tags: [n8n, automation, no-code, hubspot, submitrax]
---

# 📝 Tự động Thu thập Lead từ Web Form vào HubSpot qua Submitrax

Các sếp đang gặp khó khăn trong việc thu thập thông tin khách hàng từ website? Việc phải thuê lập trình viên viết code cho form, quản lý database rồi mới nhập tay vào CRM vừa tốn kém, vừa chậm trễ và dễ sai sót. **Workflow Thu thập Lead qua Submitrax** chính là giải pháp tự động hóa giúp các sếp triển khai một hệ thống thu thập lead chuyên nghiệp, đồng bộ dữ liệu thời gian thực vào HubSpot mà hoàn toàn không cần đụng đến một dòng code nào.

:::info[Gợi ý hạ tầng cho n8n]
Để workflow chạy ổn định 24/7, các sếp nên cài n8n trên VPS riêng (Self-hosted).
👉 [Đăng ký VPS TinoHost](https://tino.vn/?php=3883) (🎁 Mã giảm giá: **VPSN8N** - giảm tới 39%)
👉 [Đăng ký VPS Xeon 4GB chỉ 50k/tháng](https://my.bnix.one/aff.php?aff=172)
:::

🎯 Kết quả các sếp nhận được

:::tip[LỢI ÍCH CỐT LÕI]
* **Triển khai siêu tốc:** Tạo form HTML chuyên nghiệp và host miễn phí qua Submitrax mà không cần thuê server riêng cho website.
* **Đồng bộ dữ liệu tức thì:** Lead vừa nhấn "Submit" là thông tin tự động xuất hiện trong HubSpot CRM, không có độ trễ.
* **Quản lý Lead thông minh:** Tự động hóa việc "Tạo mới hoặc Cập nhật" (Create or Update), giúp các sếp tránh trùng lặp dữ liệu khách hàng.
* **Loại bỏ chi phí vận hành:** Không cần trả phí cho các nền tảng form đắt đỏ hay thuê dev bảo trì backend.
:::

🔧 Yêu cầu cần thiết

:::info[CHUẨN BỊ TRƯỚC KHI CÀI ĐẶT]
* Tài khoản **Submitrax** (để tạo và quản lý form).
* Tài khoản **HubSpot** (đã kết nối qua OAuth2 trong n8n).
* Bản n8n đã được cài đặt và kích hoạt (khuyên dùng bản Self-hosted trên VPS).
:::

🚀 Cách import & Lưu ý khi "lên đồ"

### 1. Import Workflow 📥
Các sếp có thể đưa workflow này vào n8n theo 2 cách đơn giản:
* **Cách 1 - Import từ file:** Tải file JSON của workflow về máy. Tại giao diện n8n Editor, chọn **Import from file** và chọn file JSON vừa tải.
* **Cách 2 - Paste JSON:** Copy toàn bộ đoạn mã JSON của workflow. Tại giao diện n8n Editor, chọn **Paste JSON** và dán vào.

### 2. Các thông số BẮT BUỘC phải chỉnh 📌
Workflow này hoạt động theo 3 giai đoạn, các sếp lưu ý thực hiện đúng trình tự:

* **Giai đoạn 1 (Thiết lập Form):**
    * Tại Node **SubmitraX account**: Kết nối API Key của Submitrax.
    * Chạy node **Click here to start** $\rightarrow$ Hệ thống sẽ tự tạo Form. Các sếp hãy copy **Form ID** thu được từ kết quả đầu ra của node JavaScript.
* **Giai đoạn 2 (Hiển thị Form):**
    * Tại Node **Get a form**: Dán **Form ID** vừa copy ở trên vào mục `Form ID`. 
    * Khi truy cập vào URL của node **Form viewer**, các sếp sẽ thấy form hiện ra chuyên nghiệp trên trình duyệt.
* **Giai đoạn 3 (Đẩy dữ liệu về CRM):**
    * Tại Node **SubmitraX Trigger**: Dán chính xác **Form ID** vào đây để n8n "lắng nghe" mỗi khi có khách điền form.
    * Tại Node **HubSpot**: Kết nối tài khoản HubSpot và kiểm tra lại mapping các trường thông tin (Name $\rightarrow$ First Name, Company $\rightarrow$ Company Name, v.v.).

### 3. Kích hoạt & Vận hành ⚡️
1. **Chạy thử (Test run):** Mở URL production của node **Form viewer**, điền thông tin mẫu và nhấn gửi.
2. **Kiểm tra HubSpot:** Vào HubSpot xem contact mới đã được tạo hoặc cập nhật chính xác chưa.
3. **Bật Tự động:** Khi mọi thứ đã chuẩn xác, chuyển công tắc góc trên bên phải sang trạng thái **Active**.

:::note[✅ HOÀN TẤT!]
Workflow đã sẵn sàng thu thập lead cho các sếp! Giờ đây, các sếp chỉ cần tập trung vào việc chốt đơn, còn việc nhập liệu đã có n8n lo.
:::

✍️ Mẹo & Gợi ý nâng cao

* **Tùy chỉnh giao diện:** Các sếp có thể thay đổi màu sắc, font chữ hoặc thêm trường thông tin trong phần `customHtml` của node **Create a form** để phù hợp với nhận diện thương hiệu của mình.
* **Thông báo tức thì:** Thêm một Node **Telegram** hoặc **Slack** ngay sau node HubSpot để mỗi khi có lead mới, điện thoại các sếp sẽ "ting ting" thông báo ngay lập tức.
* **Phân loại Lead:** Sử dụng **Filter Node** để lọc các lead từ website công ty lớn (dựa trên domain email) để ưu tiên xử lý trước.
* **Trang cảm ơn:** Thay vì phản hồi văn bản đơn giản, các sếp có thể tạo một trang "Cảm ơn" đẹp mắt bằng HTML trong node **Respond to Webhook**.

📌 Kết luận

Tự động hóa luồng thu thập lead từ Web Form vào HubSpot giúp các sếp chuẩn hóa quy trình tiếp cận khách hàng, không bỏ sót bất kỳ cơ hội kinh doanh nào. Hãy áp dụng ngay workflow này để giải phóng sức lao động và tập trung vào những chiến lược tăng trưởng quan trọng hơn!
```