# ⌨️ ZDD Lab

**Make your keypad yours.**

[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011%20(64--bit)-blue?style=flat-square&logo=windows)](#download--installation)
[![Version](https://img.shields.io/badge/Version-1.0.0-brightgreen?style=flat-square)](#download--installation)
[![Driver](https://img.shields.io/badge/USB%20Driver-None%20Required%20(HID)-lightgrey?style=flat-square)](#how-it-works)
[![Hardware Tested](https://img.shields.io/badge/Tested%20Hardware-AliExpress%202--Key%20CH552-yellow?style=flat-square)](#hardware-compatibility--testing-notice)
[![Source Code](https://img.shields.io/badge/Source%20Code-Coming%20Soon%20(TBA)-orange?style=flat-square)](#open-source--roadmap)
[![Website](https://img.shields.io/badge/Live%20Demo-zddlab.freedev.app-purple?style=flat-square)](https://zddlab.freedev.app/?i=1)

**ZDD Lab** is a fast, modern, distraction-free desktop configurator built specifically for **CH552-based ZDD USB programmable keypads**. Designed to replace clunky, outdated vendor utilities, ZDD Lab gives you complete control over 2-key and 8-key layouts, complex multi-step macros, system hotkeys, media controls, and onboard RGB lighting—writing everything straight to your keypad's hardware memory in a single click.

> **📢 Open Source Notice:** The full source code for ZDD Lab will be released publicly soon! An exact release date has not been set yet—watch or star this repository to get notified as soon as the codebase goes live.

> **⚠️ Hardware Testing Disclaimer:** This software has been tested **only on an AliExpress 2-key CH552 keyboard**. Other models (including 8-key variants or other CH552 revisions) have **not been tested yet**. Use with untested hardware at your own risk, and feel free to report your results!

---

## 📖 Table of Contents

* [Why ZDD Lab?](#-why-zddlab)
* [Hardware Compatibility & Testing Notice](#-hardware-compatibility--testing-notice)
* [Key Features](#-key-features)
* [How It Works](#-how-it-works)
* [Hardware & Firmware Architecture](#-hardware--firmware-architecture)
* [Macro & Modifier Delay Deep Dive](#-macro--modifier-delay-deep-dive)
* [Hidden Developer Mode](#-hidden-developer-mode)
* [Download & Installation](#-download--installation)
* [Open Source & Roadmap](#-open-source--roadmap)
* [Troubleshooting & FAQ](#-troubleshooting--faq)
* [Privacy & Terms of Use](#-privacy--terms-of-use)

---

## 💡 Why ZDD Lab?

Many budget mechanical macro pads powered by the **WCH CH552** microcontroller ship with legacy configuration tools that are poorly translated, difficult to navigate, or require sketchy driver workarounds. ZDD Lab solves this by speaking the exact same native **USB HID configuration protocol** as the original setup tool while wrapping it in a clean, responsive, and reliable interface:

* **Zero Background Bloat:** Once you flash your configuration to the keypad, your settings live inside the device's non-volatile **DataFlash** memory. Close ZDD Lab, unplug your keypad, and plug it into any Windows, macOS, or Linux machine—your keys and macros keep working natively.
* **No Custom Drivers:** Built directly on top of standard Windows USB HID APIs. Plug in your keypad and start editing immediately.
* **Completely Offline & Account-Free:** No logins, no cloud sync walls, and zero telemetry tracking your keystrokes.

---

## 🧪 Hardware Compatibility & Testing Notice

* **Verified Hardware:** Tested exclusively on a generic **AliExpress 2-key CH552 programmable keypad**.
* **Untested Hardware:** All other layouts and models—including **8-key CH552 keypads**, rotary encoder variants, or other vendor firmware revisions—have **not been tested**. While ZDD Lab implements the 8-key slot protocol used by the factory software, compatibility with unverified hardware cannot be guaranteed.

---

## ✨ Key Features

### 🎛️ Flexible 2-Key & 8-Key Layouts
Switch between compact **2-key** (`KEY1–KEY2`) and full **8-key** (`KEY1–KEY8`) hardware layouts with a single click *(note: only the 2-key AliExpress CH552 model has been physically verified)*. Select any key slot and click an input on the interactive on-screen keyboard—both the key assignment and visual glow update in real time. Pressing `Delete` clears any active slot cleanly.

### 🔌 Automatic Plug & Play Detection
ZDD Lab continuously monitors USB HID connections in the background. Plug in your keypad and the editor unlocks automatically; unplug it (or let it perform its scheduled 24-hour firmware refresh) and ZDD Lab smoothly transitions to its waiting screen and reconnects the instant the device returns.

### 🎹 Comprehensive Input Library
Three organized input tabs cover virtually every desktop, gaming, and productivity workflow:
* **Full Keyboard Matrix:** Standard alphanumeric keys, navigation clusters, numpad keys, extended function keys (**`F13` through `F24`**), and the standard **`Menu`** key (mapped in place of the right Windows key).
* **Mouse Actions:** Dedicated **Left Click**, **Middle Click**, and **Right Click** bindings.
* **Media & System Controls:** **Volume Up**, **Volume Down**, **Mute**, **Play / Pause**, **Next Track**, and **Previous Track**.

### ⚡ Hotkeys & Multi-Step Macros
* **Instant Hotkeys:** Combine any standard key with `Ctrl`, `Win`, `Alt`, or `Shift` (e.g., `Ctrl + C`, `Win + R`, `Shift + F4`, `Alt + Tab`) on a single key press.
* **Custom Macro Builder:** Switch on **Macro Mode** to chain together sequences of keystrokes, modifier combinations, and timed pauses (`0.0s` to `25.5s` in `0.1s` steps).

### 💡 Instant RGB Lighting Control
Toggle your keypad's onboard RGB lighting **On** or **Off** with immediate hardware feedback *(available on RGB-equipped keypad models)*.

### 🌗 Crisp White & Pitch-Black Themes
Work comfortably day or night by toggling between a clean **Light Mode** and a true **OLED Pitch-Black Mode** directly from the title bar or Settings menu. Your theme preference is saved locally on your machine.

---

## 🚀 How It Works

Configuring your keypad takes less than a minute:

1. **Plug In Your Keypad**  
   Connect your ZDD keypad to an available USB port. ZDD Lab automatically detects the CH552 HID interface and opens the layout editor.
2. **Select a Layout & Map Your Keys**  
   Choose **2 Keys** or **8 Keys** to match your physical hardware. Click a key slot, then assign a single key, a modifier hotkey, a mouse button, a media control, or a multi-step macro.
3. **Download to Keypad**  
   Click **Download to keypad**. ZDD Lab writes the complete configuration payload to the keypad's onboard memory and verifies every step. Once complete, your keypad is ready to use anywhere.

---

## 🔧 Hardware & Firmware Architecture

ZDD Lab communicates directly with the **CH552** microcontroller over standard USB HID feature/interrupt reports, ensuring compatibility with factory firmware expectations.

| Specification | Details |
| :--- | :--- |
| **Microcontroller** | WCH CH552 (8-bit Enhanced E8051 core with integrated USB) |
| **Verified Hardware** | AliExpress 2-key CH552 keypad *(other models untested)* |
| **Interface Protocol** | Standard USB HID (Driverless on Windows 10 & 11) |
| **Firmware Key Slots** | 10 internal slots (`2` or `8` active slots edited in ZDD Lab) |
| **Supported Input Types** | Standard keys (`F1–F24`, `Menu`), Hotkeys, Macros, Mouse (`L/M/R`), Media |
| **Non-Volatile Storage** | Onboard Keypad DataFlash (retains layout indefinitely without power) |
| **Firmware Watchdog** | Automatic self-restart after **24 hours** of continuous USB power |

---

## ⏱️ Macro & Modifier Delay Deep Dive

Because the CH552 microcontroller has a compact onboard memory footprint, ZDD Lab enforces exact hardware boundaries so your configuration never overflows or corrupts the keypad's DataFlash:

* **Total Macro Step Pool:** Up to **34 macro steps** shared across all programmed keys on the keypad.
* **Modifier Step Limit:** Up to **10 steps** containing modifier keys (`Ctrl`, `Win`, `Alt`, `Shift`) across the macro pool.
* **Delay Step Limit:** Up to **10 delay steps**, adjustable from **`0.0` seconds to `25.5` seconds** in **`0.1`-second** increments.
* **Macro Input Restrictions:** Mouse clicks (`L/M/R`) and media keys cannot be placed inside multi-step macros—this is a strict constraint of the underlying keypad firmware.

### Modifier Delay (11 Precision Levels)
Some operating systems, remote desktop clients, or games drop rapid keystrokes when a modifier (`Ctrl`, `Win`, `Alt`, `Shift`) is pressed simultaneously with a target key. ZDD Lab exposes **11 configurable modifier delay levels** in Settings:

```text
Off  ·  5 ms  ·  10 ms  ·  20 ms  ·  30 ms  ·  50 ms  ·  100 ms  ·  150 ms  ·  200 ms  ·  300 ms  ·  500 ms
```

> *Note: Modifier delay configuration requires keypad firmware that supports configuration command `0x0e`. If you do not touch this setting in ZDD Lab, your keypad's existing modifier delay setting remains untouched.*

---

## 🛠️ Hidden Developer Mode

For hardware hackers, firmware tinkerers, and curious users, ZDD Lab includes a built-in **Developer Mode**:

* **Raw Frame Inspection:** View live hexadecimal `TX` (transmitted) and `RX` (received) USB HID packet logs in real time.
* **Custom Command Testing:** Send raw byte frames directly to the keypad and test lighting values on the fly.

```text
TX  0f 01 00 00 ...
RX  55 55 55
```

> ⚠️ **Caution:** Developer Mode sends raw low-level commands directly to your device. Only use raw frame injection if you understand the CH552 HID protocol.

---

## 📥 Download & Installation

* **Windows 10 & 11 (64-bit):** [Download ZDD Lab v1.0.0](https://zddlab.freedev.app/?i=1#download)
* **Interactive Web Demo:** Try the UI directly in your browser at [zddlab.freedev.app](https://zddlab.freedev.app/?i=1#demo) *(Note: the web demo previews the editor interface; the desktop app is required to flash hardware).*
* **Linux & macOS:** *Currently in development.*

### Windows SmartScreen Notice
Because the `v1.0.0` installer is not yet code-signed with an EV certificate, Windows Defender SmartScreen may display a *"Windows protected your PC"* warning on launch. To proceed:
1. Click **More info** on the SmartScreen dialog.
2. Click **Run anyway**.

---

## 🗺️ Open Source & Roadmap

* **Source Code Release (Coming Soon):** We plan to open-source ZDD Lab so the community can inspect the HID protocol implementation, contribute improvements, and package builds for additional platforms. **The exact release date is not known yet**, so check back or watch this repository for updates.
* **Expanded Hardware Testing:** Currently tested **only on an AliExpress 2-key CH552 keyboard**; testing and verification on 8-key and other CH552 variants is still pending.
* **Cross-Platform Builds:** Native **Linux** and **macOS** versions are currently in the works.

---

## ❓ Troubleshooting & FAQ

<details>
<summary><strong>Which keypads have been tested with ZDD Lab?</strong></summary>
<br>
ZDD Lab has been tested <strong>only on an AliExpress 2-key CH552 keyboard</strong>. Other keyboards (including 8-key CH552 models or other firmware versions) have not been tested yet.
</details>

<details>
<summary><strong>Do I need to install any USB drivers?</strong></summary>
<br>
No. ZDD Lab communicates using the native Human Interface Device (HID) stack built into Windows 10 and 11.
</details>

<details>
<summary><strong>Will flashing from ZDD Lab overwrite macros I created with the original factory tool?</strong></summary>
<br>
Yes. Clicking <strong>Download to keypad</strong> overwrites the keypad's entire keymap and macro table. Be sure to recreate all desired keys and macros inside ZDD Lab before downloading. Your modifier-delay level is only overwritten if you explicitly change it in Settings.
</details>

<details>
<summary><strong>ZDD Lab isn't detecting my keypad. How can I fix it?</strong></summary>
<br>
<ul>
  <li>Try plugging the keypad directly into a rear motherboard USB port rather than an unpowered hub.</li>
  <li>Disconnect any other identical CH552 keypads while configuring so there is no device collision.</li>
  <li>Open Windows <strong>Device Manager</strong>, locate the keypad's <em>USB Composite Device</em>, uninstall it, and unplug/replug the cable to clear a stuck Windows HID handle.</li>
</ul>
</details>

<details>
<summary><strong>Why did my keypad briefly disconnect after running for 24 hours?</strong></summary>
<br>
This is normal hardware behavior. The CH552 keypad firmware triggers an automatic watchdog self-restart after 24 hours of continuous power. ZDD Lab will briefly show its connection screen and automatically reconnect within seconds.
</details>

<details>
<summary><strong>Can I change individual RGB colors or animations?</strong></summary>
<br>
Not yet. The keypad's firmware protocol only exposes a global RGB On/Off switch—specific colors and lighting patterns are determined internally by the keypad's firmware.
</details>

<details>
<summary><strong>Is it safe to flash my keypad with ZDD Lab?</strong></summary>
<br>
ZDD Lab follows the exact flashing sequence used by the original factory software, though it has only been verified on an AliExpress 2-key CH552 keyboard so far. Make sure you <strong>do not unplug the USB cable</strong> while a download is actively writing to DataFlash.
</details>

---

## 🔒 Privacy & Terms of Use

* **Zero Data Collection:** ZDD Lab runs 100% locally on your computer. It never creates an account, never logs your key mappings, and never transmits personal data. *(When online, the app may fetch a standard UI font file on startup; your theme setting is stored strictly locally).*
* **License & Terms:** ZDD Lab v1.0 is free to install and use on your own computers for personal or internal use, and may be redistributed unchanged for the same purposes. Selling the software or removing ownership notices is prohibited. View the complete Terms of Use at [zddlab.freedev.app](https://zddlab.freedev.app/?i=1).

<details>
<summary><strong>View Full Terms of Use (v1.0)</strong></summary>
<br>

```text
ZDD LAB - TERMS OF USE
Version 1.0

Please read these terms carefully. By clicking "I accept" you agree to them. If you do not agree, click Cancel and the app will not be installed.

1. WHAT THIS SOFTWARE DOES
ZDD Lab ("the Software") lets you change which keys, mouse buttons and media functions your compatible ZDD USB keypad sends, and switch its RGB lighting on or off. It talks to the keypad over a standard USB connection.

2. LICENSE
You may install and use the Software on your own computers for personal or internal use, and copy it unchanged to other people for the same purposes. You may not sell it, claim it as your own, or remove these terms or any ownership notices.

3. USE AT YOUR OWN RISK - YOUR KEYPAD
Sending a configuration to your keypad replaces the key settings stored in it. Do not unplug the keypad while a download is in progress. The Developer mode of the Software can send raw commands to the keypad; use it only if you know what you are doing. Although the Software is designed to be safe, you are responsible for what you send to your device, and the makers cannot guarantee that a keypad will never need to be reset or reconfigured.

4. NO WARRANTY
The Software is provided "as is" and "as available", without warranty of any kind, whether express or implied, including fitness for a particular purpose, reliability, or that it will work with every keypad or computer.

5. LIMITATION OF LIABILITY
To the fullest extent allowed by law, the makers of the Software are not liable for any loss, damage or inconvenience arising from installing or using it, including loss of data, a keypad that stops responding, or lost time.

6. PRIVACY
The Software runs on your computer. It does not create an account, and it does not collect or send your key settings or any personal information. When you are online it may download a font file for its appearance, which is a normal web request that your internet provider and the font host can see. Your theme choice is stored on your computer only.

7. UPDATES AND CHANGES
The Software may be updated from time to time. We may change these terms for new versions; the terms shown during an installation apply to that version.

8. ENDING THESE TERMS
You can stop at any time by uninstalling the Software from Windows Settings, then Apps. These terms end if you break them.

9. TRADEMARKS
ZDD and ZDD Lab and their logos belong to their owners. Other names mentioned belong to their respective owners.

By clicking "I accept" you confirm that you have read and agree to these terms.
```

</details>
