# Config SO Builder – website (GitHub Pages)

Trang tĩnh, không cần build. Cấu trúc:

```
index.html                    trang chính (HTML/CSS/JS trong 1 file)
404.html                      trang lỗi 404
.nojekyll                     tắt Jekyll để GitHub phát nguyên file
downloads/Config_SO_Builder.zip   bộ builder cho nút "Tải builder"
CNAME.example                 mẫu file CNAME cho tên miền riêng
```

## Cách 1: dùng luôn địa chỉ github.io (miễn phí, không cần mua domain)

1. Tạo tài khoản và một repository **public** trên github.com, ví dụ `config-so-builder`.
2. Bấm **Add file → Upload files**, kéo thả toàn bộ nội dung thư mục này (nhớ cả `.nojekyll` và thư mục `downloads`), bấm **Commit changes**.
3. Vào **Settings → Pages**. Ở mục *Build and deployment*, chọn **Source: Deploy from a branch**, **Branch: main**, thư mục **/ (root)**, bấm **Save**.
4. Đợi 1 đến 3 phút. Trang chạy tại:
   - `https://TEN_TAI_KHOAN.github.io/config-so-builder/`
   - Nếu đặt tên repo đúng là `TEN_TAI_KHOAN.github.io` thì địa chỉ là `https://TEN_TAI_KHOAN.github.io/`

## Cách 2: dùng tên miền riêng (DNS trỏ về GitHub Pages)

1. Làm xong Cách 1 trước.
2. **Settings → Pages → Custom domain**, nhập tên miền (ví dụ `builder.example.com`), Save. GitHub tự tạo file `CNAME` trong repo.
3. Ở nơi quản lý DNS của tên miền, thêm bản ghi:

   **Subdomain** (`builder.example.com`):

   | Type  | Name    | Value                     |
   |-------|---------|---------------------------|
   | CNAME | builder | `TEN_TAI_KHOAN.github.io` |

   **Domain gốc** (`example.com`):

   | Type | Name | Value             |
   |------|------|-------------------|
   | A    | @    | `185.199.108.153` |
   | A    | @    | `185.199.109.153` |
   | A    | @    | `185.199.110.153` |
   | A    | @    | `185.199.111.153` |
   | AAAA | @    | `2606:50c0:8000::153` |
   | AAAA | @    | `2606:50c0:8001::153` |
   | AAAA | @    | `2606:50c0:8002::153` |
   | AAAA | @    | `2606:50c0:8003::153` |

   Nếu muốn cả `www`: thêm `CNAME www → TEN_TAI_KHOAN.github.io`.
4. Chờ DNS cập nhật (vài phút đến vài giờ), quay lại **Settings → Pages**, tick **Enforce HTTPS** khi tùy chọn này sáng lên.

Địa chỉ IP trên là của GitHub Pages tại thời điểm viết; nếu có sự cố, đối chiếu tài liệu chính thức: docs.github.com → GitHub Pages → Managing a custom domain.

## Cập nhật nội dung

Sửa `index.html` (hoặc thay `downloads/Config_SO_Builder.zip`) rồi commit. GitHub Pages tự xuất bản lại.
