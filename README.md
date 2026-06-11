# Ghi nhận

Dự án được phát triển dựa trên mã nguồn và ý tưởng từ dự án **n8nworkflows.xyz** của [nusquama](https://github.com/nusquama/n8nworkflows.xyz)
  
Xin chân thành cảm ơn tác giả đã đóng góp cho cộng đồng n8n:

[https://github.com/nusquama/n8nworkflows.xyz](https://github.com/nusquama/n8nworkflows.xyz)

# [https://n8nworkflows.vn](https://n8nworkflows.vn)

Kho lưu trữ độc lập các workflow n8n được tổng hợp từ thư viện workflow chính thức của n8n. Dự án cho phép lưu trữ, quản lý phiên bản và tái sử dụng các workflow dưới định dạng JSON tối giản, sẵn sàng để import và sử dụng ngoại tuyến.

**Website:** [https://n8nworkflows.vn](https://n8nworkflows.vn)


---

## 📋 Mục lục

* [Cấu trúc kho lưu trữ](#-cau-truc-kho-luu-tru)
* [Định dạng luồng công việc được lưu trữ](#-dinh-dang-luong-cong-viec-duoc-luu-tru)
* [Cách sử dụng](#-cach-su-dung)
* [Tóm tắt các luồng công việc](#-tom-tat-cac-luong-cong-viec)
* [Giấy phép](#-giay-phep)

---

## 📁 Cấu trúc kho lưu trữ

```text
n8nworkflows.xyz/
├── archive/
│   └── workflows/
│       ├── workflow-name-id-1/
│       │   ├── readme.md
│       │   ├── workflow.json
│       │   ├── metadata.json
│       │   └── workflow-name-id-1.webp
│       ├── workflow-name-id-2/
│       │   └── ...
│       └── ...
└── README.md

```

Mỗi luồng công việc được tách riêng vào một thư mục độc lập để giúp bạn dễ dàng tìm kiếm, quản lý phiên bản và nhập (import) từng phần lẻ.

---

## 🔗 Các liên kết hữu ích

* 🌐 [Trang web n8nworkflows.xyz](https://n8nworkflows.xyz)
* 📖 [Tài liệu chính thức của n8n](https://docs.n8n.io)
* 💬 [Cộng đồng n8n](https://community.n8n.io)
* 🐙 [n8n trên GitHub](https://github.com/n8n-io/n8n)

---

## 📝 Giấy phép

Kho lưu trữ này lưu lại các luồng công việc công khai từ [n8n.io/workflows](https://n8n.io/workflows). Mỗi luồng công việc vẫn giữ nguyên giấy phép ban đầu của nó. Vui lòng xem thông tin siêu dữ liệu (metadata) của từng luồng để biết thêm chi tiết.

Mã nguồn lưu trữ và cấu trúc kho lưu trữ được cấp phép theo [MIT](LICENSE).

---

## ⚠️ Tuyên bố miễn trừ trách nhiệm

Đây là một dự án **độc lập** và không trực tiếp liên kết chính thức với n8n. Nó là một sáng kiến cá nhân nhằm giúp mọi người dễ dàng truy cập và lưu giữ các luồng công việc n8n công khai.

**Được tạo ra với ❤️ dành cho cộng đồng n8n**

---

## 📄 Định dạng luồng công việc được lưu trữ

Mỗi thư mục luồng công việc chứa **chính xác 4 tệp**:

* **`readme.md`**: Mô tả chi tiết về luồng công việc dưới dạng văn bản Markdown (được lấy từ trường `readme` của mẫu gốc).
* **`workflow.json`**: Bản trích xuất (export) thô của luồng công việc dưới định dạng JSON, dùng để nhập (import) trực tiếp vào nền tảng n8n.
* **`metadata.json`**: Các dữ liệu đính kèm (siêu dữ liệu) bao gồm tên tác giả (`user_*`), thẻ phân loại (tags), ngày tạo, và đường dẫn công khai đến `https://n8n.io/workflows/<workflowId>`.
* **`<slug-and-id>.webp`**: Ảnh chụp màn hình tổng quan của luồng công việc (ảnh hiển thị chính từ kho dữ liệu `worklowscreenshot` của Supabase).

---

