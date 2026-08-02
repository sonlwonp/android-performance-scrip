# Turbo.sh

🌐 **Language / Ngôn ngữ**

- 🇺🇸 English (Current)
- 🇻🇳 [Tiếng Việt](README.vi.md)

---

Turbo.sh is an open-source Shell script that helps optimize Android performance without Root access. It supports multiple optimization modes, display refresh rate configuration, background application management, system maintenance tasks, and experimental Vulkan support through ADB Shell, Brevent, or Terminal Emulator.

## Download

Download the latest version from:

[GitHub Releases](../../releases)

## Version

**v1.1**

## Features

- Safe, Balanced, and Aggressive performance modes.
- Disable system animations.
- Set display refresh rate (validated within 30-165 Hz).
- Disable battery saving mode.
- Enable Fixed Performance Mode (Android 12+, if supported).
- Optimize installed applications.
- Stop background applications.
- Disable or restore applications.
- Enable or disable experimental Vulkan.
- Restore default settings.
- Installer-style output with per-stage status ([ OK ] / [FAIL] / [WARN]).
- Automatic warning if a device manufacturer restricts system settings.
- Create a log file after execution.

## Support

- Android 10 - Android 16.
- No Root required.
- Supports ADB Shell, Brevent, and Terminal Emulator.

## Requirements

- Android 10 or higher.
- ADB Shell, Brevent, or Terminal Emulator.
- Storage permission if running directly on Android phone.

---

# Installation

## Run directly on Android phone (No PC required)

1. Download `Turbo.sh` from Releases.

2. Place the file here:

```text
/storage/emulated/0/Download/Turbo.sh
```

3. Open Brevent Shell or Terminal Emulator.

---

# Performance Modes

## Safe Mode (Stable)

```sh
sh /storage/emulated/0/Download/Turbo.sh safe 120
```

## Balanced Mode (Recommended)

```sh
sh /storage/emulated/0/Download/Turbo.sh balanced 120
```

## Aggressive Mode (Maximum performance)

```sh
sh /storage/emulated/0/Download/Turbo.sh aggressive 120 com.tencent.ig
```

---

# App Management Commands

## Stop background applications

```sh
sh /storage/emulated/0/Download/Turbo.sh stop-apps
```

## Disable applications

```sh
sh /storage/emulated/0/Download/Turbo.sh disable-apps
```

## Restore applications

```sh
sh /storage/emulated/0/Download/Turbo.sh restore-apps
```

---

# Experimental Vulkan

## Enable Vulkan

```sh
sh /storage/emulated/0/Download/Turbo.sh experimental-vulkan
```

## Disable Vulkan

```sh
sh /storage/emulated/0/Download/Turbo.sh disable-vulkan
```

---

# Restore Default Settings

```sh
sh /storage/emulated/0/Download/Turbo.sh restore
```

---

# Using ADB on PC

Download Android SDK Platform-Tools:

https://developer.android.com/tools/releases/platform-tools?hl=en

Check device:

```sh
adb devices
```

Push the script:

```sh
adb push "%USERPROFILE%\Downloads\Turbo.sh" /sdcard/Turbo.sh
```

Run:

```sh
adb shell sh /sdcard/Turbo.sh balanced 120
```

---

# Log File

After running the script, the log is saved at:

```text
/sdcard/Turbo.log
```

---

# Example Output

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

# Warning

- Backup important settings before using.
- Some commands require ADB Shell permission.
- Some devices restrict system settings at the OEM level; the script will report this automatically as skipped commands with a manufacturer note.
- Not all devices support Fixed Performance Mode or experimental Vulkan.
- Optimization results may vary depending on the device.
- Do not use Aggressive Mode if your device is unstable.

---

# Changelog

## v1.1

### Fixed
- Removed leftover placeholder package `com.example.app` from uninstall/restore lists.
- Removed redundant duplicate compile call in the package optimizer.
- Added refresh rate validation (30-165 Hz) with a clear warning instead of silently writing invalid values.
- Fixed Performance Mode now checks Android SDK >= 31 before calling.
- Vulkan disable now restores the renderer to `skiagl` instead of an empty string.

### Added
- Installer-style output: each stage shows one aligned result line ([ OK ] / [FAIL] / [WARN]).
- Summary line with applied/skipped counts and % complete.
- Dynamic device-manufacturer warning when any command is skipped.

## v1.0

- Initial release.
- Added Safe, Balanced, and Aggressive modes.
- Added Android optimization without Root.
- Added ADB Shell, Brevent, and Terminal Emulator support.
- Added experimental Vulkan support.

---

# Credits

Created by **sonlwonp**.

---

# License

MIT License
