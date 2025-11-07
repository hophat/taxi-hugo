# Taxi Ninh Bình Website

Website giới thiệu dịch vụ taxi tại Ninh Bình được xây dựng bằng Hugo.

## Cấu trúc dự án

```
├── content/           # Nội dung trang web
│   ├── _index.md     # Trang chủ
│   ├── services/     # Trang dịch vụ
│   ├── fleet/        # Trang đội xe
│   └── contact/      # Trang liên hệ
├── themes/taxidongha/ # Theme tùy chỉnh
├── static/           # File tĩnh (hình ảnh, CSS, JS)
└── hugo.toml         # Cấu hình Hugo
```

## Chạy website local

```bash
# Khởi động server development
hugo server --buildDrafts

# Truy cập tại: http://localhost:1313
```

## Build website cho production

```bash
# Tạo file tĩnh trong thư mục public/
hugo

# Upload thư mục public/ lên hosting
```

## Cập nhật nội dung

### Thay đổi thông tin liên hệ
Chỉnh sửa file `hugo.toml`:
- `phone`: Số điện thoại hotline
- `email`: Email liên hệ  
- `address`: Địa chỉ công ty

### Thêm/sửa nội dung trang
Chỉnh sửa các file `.md` trong thư mục `content/`

### Thay đổi giao diện
Chỉnh sửa các file trong `themes/taxidongha/layouts/`

## Tính năng

- ✅ Responsive design (tương thích mobile)
- ✅ Tối ưu SEO cơ bản
- ✅ Tốc độ tải nhanh
- ✅ Giao diện đơn giản, chuyên nghiệp
- ✅ Thông tin liên hệ rõ ràng
- ✅ Không có lỗi JavaScript

## Hosting khuyến nghị

- **Netlify** (miễn phí, tự động deploy)
- **Vercel** (miễn phí, tích hợp Git)  
- **GitHub Pages** (miễn phí)
- **Shared hosting** (upload thư mục public/)

## Liên hệ hỗ trợ

Nếu cần hỗ trợ kỹ thuật, vui lòng liên hệ developer.
