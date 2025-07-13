# Android FRP Bypass Vulnerability on Google Pixel 6 – Security Report by Derek Morris

**Discovered By:** Derek Morris  
**Reported To:** Google Android Security Rewards Program  
**Date Reported:** June 2024  
**Status:** Won’t Fix (Intended Behavior)  
**Reward:** Issued  
**Affected Version:** Android 14 (June SPL)  
**Test Device:** Google Pixel 6  
**Build Fingerprint:** `google/oriole/oriole:14/AP2A.240605.024/11860263:user/release-keys`

---

## 🔐 Android 14 FRP Bypass Vulnerability Overview

This security report documents a serious vulnerability in **Android 14** on the **Google Pixel 6** that allows attackers to **bypass Factory Reset Protection (FRP)** — even with a locked bootloader and USB debugging disabled. The flaw can be exploited using publicly available tools and an OTA image from the **Android 15 Beta** program.

Although the issue was responsibly disclosed to Google and a reward was issued, the Android Security team classified it as "**Won’t Fix (Intended Behavior)**".

---

## 🎯 What an Attacker Can Do

Anyone with physical access to a vulnerable device and basic computer skills can:

- Completely bypass **FRP lock and PIN protection**
- Access or wipe sensitive user data (emails, photos, files)
- Unlock developer settings and bootloader
- Install custom or factory ROMs
- Repurpose or resell stolen Pixel devices anonymously

---

## 🧪 Step-by-Step: How the FRP Bypass Works on Pixel 6

This Android FRP exploit was tested on a **Pixel 6 running Android 14** with the June 2024 security patch. Here's how it can be reproduced:

### 🔧 Requirements
- Google Pixel 6 with Android 14 (locked bootloader, FRP enabled, USB debugging disabled)
- [Android Platform Tools (ADB)](https://developer.android.com/tools/releases/platform-tools)
- [Pixel Flasher Tool](https://github.com/bkerler/pixel-flasher)
- Android 15 Beta 3.1 OTA image

### 🛠️ Exploit Process

1. Boot into **Recovery Mode** → Factory reset the device
2. Go through initial setup → Add a Google account + lock PIN
3. Confirm **FRP is active** and **USB debugging is off**
4. Reboot → Enter **Recovery Mode** again
5. Choose **Apply update from ADB**
6. Connect device via USB cable to your computer
7. Open Pixel Flasher → Load OTA image → Start full OTA flash
8. Let the process complete → Reboot the device

### 🎉 Post-Flash Result

- Device boots **without FRP lock**
- Setup bypasses previous Google account
- Developer options and **OEM unlocking** are now enabled
- Full control of the device is restored

---

## 🧩 Why This Vulnerability Exists

The flaw lies in **Android's handling of ADB sideloaded OTA updates**. Even with full protection mechanisms (locked bootloader, no debugging, active FRP), the system fails to revalidate the original device state after sideloading a beta image — effectively **nullifying FRP**.

---

## 📬 Google’s Response (ASR)

> “Thank you for your submission. This behavior is considered **intended** and will not be addressed. However, we are issuing a reward under the Android Security Rewards program.”

While no patch will be issued, the reward from Google validates the security relevance and potential misuse of this behavior.

---

## 🧑‍💻 About the Researcher – Derek Morris

I’m a cybersecurity researcher focused on mobile device security, Android OS internals, and ethical vulnerability disclosure.

This FRP bypass on Android 14 is an example of how even systems designed for theft protection can be circumvented when implementation leaves edge cases open to manipulation.

- GitHub: [https://github.com/yourusername](https://github.com/yourusername)
- LinkedIn: [https://linkedin.com/in/yourname](https://linkedin.com/in/yourname)

---

## ✅ Disclosure & Recognition

- This issue was privately reported to Google under ASR.
- The vulnerability is now publicly documented here to ensure proper **research credit**, **transparency**, and **awareness**.
- A bounty was awarded; however, **the vulnerability remains unpatched**.

📝 **Public Credit** requested under: **Derek Morris**

---

## 📌 Keywords (for search indexing)
`android 14 frp bypass`, `google pixel vulnerability`, `frp bypass won't fix`, `pixel flasher exploit`, `adb sideload bug`, `android bug bounty`, `android 15 beta sideload`, `pixel 6 security issue`, `frp lock bypass 2024`, `android security researcher Derek Morris`

---

*© 2025 Derek Morris — This write-up follows responsible disclosure policies and is for educational awareness only.*

