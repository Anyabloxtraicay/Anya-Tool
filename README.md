# Anya Client Launch

Tool Termux gọn nhẹ cho **1 client Roblox** (mặc định `com.roblox.client`), hỗ trợ đăng nhập bằng cookie `.ROBLOSECURITY` (cần root `su`) và mở game theo PlaceID / link Roblox / link server VIP.

## Cài đặt & chạy trên Termux

Không cần cài thư viện Python ngoài (dùng thư viện chuẩn Python):

```sh
pkg update -y && pkg install -y openssl ca-certificates python termux-am git
git clone https://github.com/Anyabloxtraicay/Anya-Tool.git ~/Anya-Tool
cd ~/Anya-Tool
python launch.py
```

## Các cách dùng nhanh

1. **Menu tương tác (khuyên dùng trên điện thoại):**
   ```sh
   python launch.py
   ```
   - `[1]` Nhập cookie `.ROBLOSECURITY`, xác thực tài khoản qua API Roblox, nạp an toàn vào WebView `Cookies` DB của client (có backup & rollback nếu lỗi) rồi mở app.
   - `[2]` Nhập PlaceID (vd `2753915549`) hoặc link Roblox / server VIP để vào thẳng game.
   - `[3]` Nạp cookie rồi vào thẳng game luôn.
   - `[4]` Mở giao diện Roblox để đăng nhập thủ công / Quick Login.
   - `[5]` Cài đặt Webhook Discord (thông báo khi nạp cookie/mở game hoặc định kỳ kèm ảnh chụp màn hình + RAM/CPU theo giây, tối thiểu 20s).
   - `[6]` Cài đặt Autoexec Script (dán script, đặt tên `.txt`/`.lua`, tự tìm thư mục Executor như `/storage/emulated/0/Arceus X/Autoexec/`, xóa file cũ và tự ghi ngay khi bạn vào game lần đầu).

2. **Chạy thẳng bằng tham số dòng lệnh:**
   ```sh
   python launch.py --cookie
   python launch.py 2753915549
   python launch.py --cookie 2753915549
   python launch.py --login
   ```
   *(Nếu muốn nhắm tới một package khác ngoài `com.roblox.client`, thêm `--package <ten.package>`).*

> **Lưu ý:** Để nạp cookie bằng root, app Roblox cần có sẵn file `Cookies` trong `app_webview/Default/` (nếu mới cài app lần đầu, hãy mở Roblox lên và bấm vào màn hình **Log In** 1 lần rồi thử lại).
