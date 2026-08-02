# Turbo.sh

🌐 **Ngôn ngữ / Language**

- 🇻🇳 Tiếng Việt (Hiện tại)
- 🇺🇸 [English](README.md)

---

Turbo.sh là một script Shell mã nguồn mở giúp tối ưu hiệu năng Android mà không cần quyền Root. Script hỗ trợ nhiều chế độ tối ưu, chỉnh tần số quét màn hình, quản lý ứng dụng nền, chạy tác vụ bảo trì hệ thống và hỗ trợ Vulkan thử nghiệm thông qua ADB Shell, Brevent hoặc Terminal Emulator.

## Tải xuống

Tải phiên bản mới nhất tại:

[GitHub Releases](../../releases)

## Phiên bản

**v1.0**

## Tính năng

- Chế độ Safe, Balanced và Aggressive.
- Tắt hiệu ứng chuyển động hệ thống.
- Thiết lập tần số quét màn hình.
- Tắt chế độ tiết kiệm pin.
- Bật Fixed Performance Mode (nếu thiết bị hỗ trợ).
- Tối ưu ứng dụng đã cài đặt.
- Dừng ứng dụng chạy nền.
- Vô hiệu hóa hoặc khôi phục ứng dụng.
- Bật hoặc tắt Vulkan thử nghiệm.
- Khôi phục cài đặt mặc định.
- Tạo file Log sau khi chạy.

## Hỗ trợ

- Android 10 - Android 16.
- Không yêu cầu Root.
- Hỗ trợ ADB Shell, Brevent và Terminal Emulator.

## Yêu cầu

- Android 10 trở lên.
- ADB Shell, Brevent hoặc Terminal Emulator.
- Quyền truy cập bộ nhớ nếu chạy trực tiếp trên điện thoại.

---

# Cài đặt

## Chạy trực tiếp trên điện thoại (Không cần PC)

1. Tải `Turbo.sh` từ mục Releases.

2. Đặt file vào:

```text
/storage/emulated/0/Download/Turbo.sh
```

3. Mở Brevent Shell hoặc Terminal Emulator.

---

## Chế độ hoạt động

### Safe Mode (Ổn định)

```sh
sh /storage/emulated/0/Download/Turbo.sh safe 120
```

### Balanced Mode (Khuyến nghị)

```sh
sh /storage/emulated/0/Download/Turbo.sh balanced 120
```

### Aggressive Mode (Hiệu năng tối đa)

```sh
sh /storage/emulated/0/Download/Turbo.sh aggressive 120 com.tencent.ig
```

---

# Lệnh quản lý

## Dừng ứng dụng nền

```sh
sh /storage/emulated/0/Download/Turbo.sh stop-apps
```

## Vô hiệu hóa ứng dụng

```sh
sh /storage/emulated/0/Download/Turbo.sh disable-apps
```

## Khôi phục ứng dụng

```sh
sh /storage/emulated/0/Download/Turbo.sh restore-apps
```

---

# Vulkan thử nghiệm

## Bật Vulkan

```sh
sh /storage/emulated/0/Download/Turbo.sh experimental-vulkan
```

## Tắt Vulkan

```sh
sh /storage/emulated/0/Download/Turbo.sh disable-vulkan
```

---

# Khôi phục mặc định

```sh
sh /storage/emulated/0/Download/Turbo.sh restore
```

---

# Sử dụng ADB trên máy tính

Tải Android SDK Platform-Tools:

https://developer.android.com/tools/releases/platform-tools?hl=vi

Kiểm tra thiết bị:

```sh
adb devices
```

Đưa file vào điện thoại:

```sh
adb push "%USERPROFILE%\Downloads\Turbo.sh" /sdcard/Turbo.sh
```

Chạy:

```sh
adb shell sh /sdcard/Turbo.sh balanced 120
```

---

# File Log

Sau khi chạy script, log được lưu tại:

```text
/sdcard/Turbo.log
```

---

# Ví dụ kết quả

```text
========================================
Turbo.sh is starting

Author  : sonlwonp
Device  : Example Device
Chip    : Example Chipset
RAM     : Example RAM
Android : Example Version

========================================
Done

Thank you for trusting and using Turbo.sh

========================================
Log: /sdcard/Turbo.log
```

---

# Cảnh báo

- Sao lưu cài đặt quan trọng trước khi sử dụng.
- Một số lệnh yêu cầu quyền ADB Shell.
- Một số tính năng có thể bị giới hạn bởi nhà sản xuất.
- Không phải thiết bị nào cũng hỗ trợ Fixed Performance Mode hoặc Vulkan thử nghiệm.
- Hiệu quả tối ưu khác nhau tùy thiết bị.
- Không sử dụng Aggressive Mode nếu thiết bị không ổn định.

---

# Changelog

## v1.0

- Phát hành phiên bản đầu tiên.
- Thêm Safe, Balanced và Aggressive Mode.
- Thêm tối ưu Android không cần Root.
- Hỗ trợ ADB Shell, Brevent và Terminal Emulator.
- Thêm Vulkan thử nghiệm.

---

# Credits

Được tạo bởi **sonlwonp**.

---

# Giấy phép

MIT License
