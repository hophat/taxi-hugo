# 📋 Hướng Dẫn Sử Dụng File Cấu Hình Website

## 📁 Cấu Trúc File Cấu Hình

Tất cả các file cấu hình được đặt trong thư mục `/data/`:

```
/data/
├── contact.yaml      # Thông tin liên hệ và công ty
├── images.yaml       # Cấu hình hình ảnh
├── services.yaml     # Dịch vụ và khu vực phục vụ
├── fleet.yaml        # Thông tin đội xe
└── seo.yaml         # Cấu hình SEO và Meta tags
```

## 🔧 Cách Sử Dụng Trong Template

### 1. Thông Tin Liên Hệ (`contact.yaml`)

```html
<!-- Tên công ty -->
{{ site.Data.contact.company.name }}

<!-- Số điện thoại -->
{{ site.Data.contact.contact.phone }}

<!-- Email -->
{{ site.Data.contact.contact.email }}

<!-- Địa chỉ đầy đủ -->
{{ site.Data.contact.address.full_address }}

<!-- Tọa độ GPS -->
{{ site.Data.contact.coordinates.latitude }}
{{ site.Data.contact.coordinates.longitude }}

<!-- Mạng xã hội -->
{{ site.Data.contact.social.facebook }}
{{ site.Data.contact.social.zalo }}
```

### 2. Hình Ảnh (`images.yaml`)

```html
<!-- Logo -->
<img src="{{ site.Data.images.logo.main }}" alt="{{ site.Data.images.logo.alt }}">

<!-- Banner hero -->
<img src="{{ site.Data.images.banners.hero }}" alt="{{ site.Data.images.banners.hero_alt }}">

<!-- Hình ảnh đội xe -->
<img src="{{ site.Data.images.fleet.car_4_seats }}" alt="{{ site.Data.images.fleet.car_4_seats_alt }}">
```

### 3. Dịch Vụ (`services.yaml`)

```html
<!-- Lặp qua các dịch vụ -->
{{ range site.Data.services.services }}
  <h3>{{ .icon }} {{ .name }}</h3>
  <p>{{ .description }}</p>
  <span>{{ .price }}</span>
{{ end }}

<!-- Khu vực phục vụ -->
{{ range site.Data.services.service_areas.local }}
  <li>{{ . }}</li>
{{ end }}
```

### 4. Đội Xe (`fleet.yaml`)

```html
<!-- Lặp qua các loại xe -->
{{ range site.Data.fleet.vehicles }}
  <div class="vehicle-card">
    <img src="{{ .image }}" alt="{{ .name }}">
    <h3>{{ .name }}</h3>
    <p>{{ .models }}</p>
    <p>{{ .description }}</p>
    <strong>{{ .price }}</strong>
  </div>
{{ end }}
```

### 5. SEO (`seo.yaml`)

```html
<!-- Meta tags -->
<title>{{ site.Data.seo.meta.title }}</title>
<meta name="description" content="{{ site.Data.seo.meta.description }}">
<meta name="keywords" content="{{ site.Data.seo.meta.keywords }}">

<!-- Open Graph -->
<meta property="og:site_name" content="{{ site.Data.seo.og.site_name }}">
<meta property="og:image" content="{{ site.Data.seo.og.image }}">
```

## ✏️ Cách Chỉnh Sửa Thông Tin

### Thay Đổi Thông Tin Công Ty
Mở file `/data/contact.yaml` và sửa:

```yaml
company:
  name: "Tên Công Ty Mới"
  full_name: "Tên Đầy Đủ Mới"
  slogan: "Slogan Mới"

contact:
  phone: "Số điện thoại mới"
  email: "email@moi.com"
```

### Thay Đổi Hình Ảnh
Mở file `/data/images.yaml` và sửa:

```yaml
logo:
  main: "/logo-moi.png"
  alt: "Logo mới"

banners:
  hero: "/banner-moi.jpg"
  hero_alt: "Mô tả banner mới"
```

### Thêm Dịch Vụ Mới
Mở file `/data/services.yaml` và thêm:

```yaml
services:
  - name: "Dịch Vụ Mới"
    description: "Mô tả dịch vụ mới"
    price: "Giá mới"
    icon: "🚖"
```

## 🎯 Ví Dụ Thực Tế

### Thay Đổi Từ Bắc Ninh Sang Thành Phố Khác

1. **Sửa file `contact.yaml`:**
```yaml
company:
  name: "Taxi Đà Nẵng"  # Thay đổi tên
address:
  city: "Đà Nẵng"       # Thay đổi thành phố
  province: "Đà Nẵng"   # Thay đổi tỉnh
coordinates:
  latitude: "16.0471"   # Tọa độ mới
  longitude: "108.2068" # Tọa độ mới
```

2. **Sửa file `services.yaml`:**
```yaml
service_areas:
  local:
    - "Nội thành Đà Nẵng"  # Thay đổi khu vực
  inter_province:
    - "Quảng Nam"          # Thay đổi tỉnh lân cận
    - "Thừa Thiên Huế"
```

## 🚀 Lợi Ích

✅ **Dễ bảo trì**: Chỉ cần sửa 1 file thay vì nhiều template
✅ **Tránh lỗi**: Giảm thiểu sai sót khi copy/paste
✅ **Tái sử dụng**: Dùng chung cho nhiều trang
✅ **Quản lý tập trung**: Tất cả thông tin ở một nơi
✅ **Thay đổi nhanh**: Đổi thông tin toàn site trong vài phút

## ⚠️ Lưu Ý

- Sau khi sửa file `.yaml`, cần restart Hugo server
- Kiểm tra syntax YAML trước khi lưu
- Backup file cấu hình trước khi thay đổi lớn
- Test trên local trước khi deploy
