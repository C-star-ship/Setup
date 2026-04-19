# ⚙️ Tool Setup Guides

Kho hướng dẫn setup tool với hệ thống **Admin bảo vệ bằng mật khẩu** — chỉ Admin mới thêm/xóa được, người dùng thường chỉ đọc.

---

## 🗂 Cấu Trúc

```
tool-guides/
├── index.html   ← Toàn bộ app (1 file duy nhất)
└── README.md    ← File này
```

---

## 🔐 Hệ Thống Phân Quyền

| Quyền | 👤 Guest | 👑 Admin |
|---|---|---|
| Xem hướng dẫn | ✅ | ✅ |
| Sao chép lệnh | ✅ | ✅ |
| Thêm hướng dẫn | ❌ | ✅ |
| Xóa hướng dẫn | ❌ | ✅ |
| Đổi mật khẩu | ❌ | ✅ |

---

## 🔑 Mật Khẩu Mặc Định

```
admin123
```

> ⚠️ **Đổi ngay sau lần đầu dùng!** Vào góc trên phải → click **Admin** → **Đổi mật khẩu**.

---

## 🛡️ Tính Năng Bảo Mật

- **Mật khẩu được hash SHA-256** — không lưu plain text
- **Giới hạn 5 lần nhập sai** → tự khóa 30 giây
- **Session-based** — đăng xuất tự động khi đóng tab
- **Không có nút thêm/xóa** khi chưa đăng nhập

---

## 🚀 Cách Dùng

### Mở trang
Chỉ cần mở `index.html` bằng trình duyệt — hoặc host lên GitHub Pages.

### Thêm hướng dẫn (Admin)
1. Click **🔒 Guest** góc trên phải → nhập mật khẩu
2. Click **＋ Thêm hướng dẫn**
3. Upload file `.html` hoặc nhập thủ công

### Format file HTML upload

```html
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta name="guide-title"       content="Tên Hướng Dẫn">
  <meta name="guide-icon"        content="📱">
  <meta name="guide-description" content="Mô tả ngắn">
  <meta name="guide-order"       content="1">
  <meta charset="UTF-8">
</head>
<body>
  <h1>Tiêu đề</h1>
  <div class="command-box" id="cmd1">lệnh ở đây</div>
  <button class="copy-btn" data-target="cmd1">📋 Sao chép</button>
</body>
</html>
```

---

## 🌐 Deploy GitHub Pages

1. **Settings → Pages → main branch → Save**
2. Truy cập: `https://yourusername.github.io/tool-guides/`

---

## ⚙️ Tùy Chỉnh Nâng Cao

Mở `index.html`, tìm phần **CONFIG** ở đầu script:

```javascript
const DEFAULT_PW = 'admin123';  // Mật khẩu mặc định
const MAX_TRIES  = 5;           // Số lần sai tối đa
const LOCK_SECS  = 30;          // Giây bị khóa
```

---

## 📄 License

MIT — Tự do sử dụng và phân phối.
