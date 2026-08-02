# Turbo.sh

🌐 **Ngôn ngữ**

- 🇻🇳 **Tiếng Việt (Hiện tại)**
- 🇺🇸 [English](README.md)

---

Turbo.sh là một tập lệnh Shell mã nguồn mở giúp tối ưu hiệu năng Android mà **không cần Root**. Tập lệnh hỗ trợ nhiều chế độ tối ưu, cấu hình tần số quét màn hình, quản lý ứng dụng chạy nền, bảo trì hệ thống và hỗ trợ Vulkan thử nghiệm thông qua **ADB Shell**, **Brevent** hoặc **Terminal Emulator**.

## Tải xuống

Tải phiên bản mới nhất tại:

[GitHub Releases](../../releases)

## Phiên bản

**v1.1**

## Tính năng

- Chế độ hiệu năng **Safe**, **Balanced** và **Aggressive**.
- Tắt hiệu ứng động của hệ thống.
- Thiết lập tần số quét màn hình (được kiểm tra trong khoảng **30–165 Hz**).
- Tắt chế độ tiết kiệm pin.
- Bật **Fixed Performance Mode** (Android 12 trở lên, nếu thiết bị hỗ trợ).
- Tối ưu hóa các ứng dụng đã cài đặt.
- Dừng các ứng dụng chạy nền.
- Vô hiệu hóa hoặc khôi phục ứng dụng.
- Bật hoặc tắt Vulkan thử nghiệm.
- Khôi phục cài đặt mặc định.
- Hiển thị kết quả theo kiểu trình cài đặt với trạng thái từng bước (**[ OK ] / [FAIL] / [WARN]**).
- Tự động cảnh báo nếu nhà sản xuất thiết bị hạn chế thay đổi cài đặt hệ thống.
- Tạo tệp nhật ký sau khi thực thi.

## Hỗ trợ

- Android 10 - Android 16.
- Không cần Root.
- Hỗ trợ ADB Shell, Brevent và Terminal Emulator.

## Yêu cầu

- Android 10 trở lên.
- ADB Shell, Brevent hoặc Terminal Emulator.
- Quyền truy cập bộ nhớ nếu chạy trực tiếp trên điện thoại Android.

---

# Cài đặt

## Chạy trực tiếp trên điện thoại Android (Không cần máy tính)

1. Tải `Turbo.sh` từ mục Releases.

2. Đặt tệp tại:

```text
/storage/emulated/0/Download/Turbo.sh
```

3. Mở Brevent Shell hoặc Terminal Emulator.

---

# Các chế độ hiệu năng

## Safe Mode (Ổn định)

```sh
sh /storage/emulated/0/Download/Turbo.sh safe 120
```

## Balanced Mode (Khuyến nghị)

```sh
sh /storage/emulated/0/Download/Turbo.sh balanced 120
```

## Aggressive Mode (Hiệu năng tối đa)

```sh
sh /storage/emulated/0/Download/Turbo.sh aggressive 120 com.tencent.ig
```

---

# Các lệnh quản lý ứng dụng

## Dừng ứng dụng chạy nền

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

# Khôi phục cài đặt mặc định

```sh
sh /storage/emulated/0/Download/Turbo.sh restore
```

---

# Sử dụng ADB trên máy tính

Tải Android SDK Platform-Tools:

https://developer.android.com/tools/releases/platform-tools?hl=en

Kiểm tra thiết bị:

```sh
adb devices
```

Chép tập lệnh:

```sh
adb push "%USERPROFILE%\Downloads\Turbo.sh" /sdcard/Turbo.sh
```

Chạy:

```sh
adb shell sh /sdcard/Turbo.sh balanced 120
```

---

# Tệp nhật ký

Sau khi chạy, tệp nhật ký được lưu tại:

```text
/sdcard/Turbo.log
```

---

# Ví dụ kết quả

```text
Turbo.sh v1.1
sonlwonp | Example Device (Example Chipset) | Android 16 | SDK 36

Mode: balanced | Target: 90Hz

  Animations .............................. [ OK ]
  Refresh rate ............................. [ OK ]
  Power settings ............................ [ OK ]
  Background limits ......................... [ OK ]
  Package optimize .......................... [ OK ]
  Maintenance ................................ [ OK ]

  18 applied - 0 skipped - 100% complete

Log written to /sdcard/Turbo.log
```

---

# Cảnh báo

- Sao lưu các cài đặt quan trọng trước khi sử dụng.
- Một số lệnh yêu cầu quyền ADB Shell.
- Một số thiết bị giới hạn thay đổi cài đặt hệ thống ở cấp nhà sản xuất (OEM); tập lệnh sẽ tự động báo các lệnh bị bỏ qua cùng ghi chú về nhà sản xuất.
- Không phải tất cả thiết bị đều hỗ trợ Fixed Performance Mode hoặc Vulkan thử nghiệm.
- Hiệu quả tối ưu có thể khác nhau tùy thiết bị.
- Không nên sử dụng **Aggressive Mode** nếu thiết bị hoạt động không ổn định.

---

# Nhật ký thay đổi

## v1.1

### Đã sửa

- Xóa gói mẫu `com.example.app` còn sót lại khỏi danh sách gỡ bỏ/khôi phục.
- Loại bỏ lệnh biên dịch trùng lặp trong trình tối ưu ứng dụng.
- Thêm kiểm tra tần số quét hợp lệ (**30–165 Hz**) cùng cảnh báo rõ ràng thay vì ghi giá trị không hợp lệ.
- Fixed Performance Mode hiện kiểm tra Android **SDK >= 31** trước khi thực thi.
- Khi tắt Vulkan, trình kết xuất được khôi phục về `skiagl` thay vì để trống.

### Đã thêm

- Hiển thị theo kiểu trình cài đặt: mỗi giai đoạn hiển thị một dòng trạng thái (**[ OK ] / [FAIL] / [WARN]**).
- Dòng tổng kết hiển thị số lượng thay đổi đã áp dụng, số lượng bỏ qua và tỷ lệ hoàn thành.
- Cảnh báo động theo nhà sản xuất khi có bất kỳ lệnh nào bị bỏ qua.

## v1.0

- Phát hành phiên bản đầu tiên.
- Thêm các chế độ Safe, Balanced và Aggressive.
- Thêm khả năng tối ưu Android không cần Root.
- Hỗ trợ ADB Shell, Brevent và Terminal Emulator.
- Thêm hỗ trợ Vulkan thử nghiệm.

---

# Ghi nhận

Được tạo bởi **sonlwonp**.

---

# Giấy phép

MIT License