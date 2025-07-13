# Android FRP Bypass Vulnerability on Pixel 6 – Security Disclosure by Derek Morris

**Author:** Derek Morris  
**Reported to:** Google Android Security Rewards Program  
**Date Reported:** June 2024  
**Status:** Won’t Fix (Intended Behavior)  
**Reward:** Issued by Google  
**Affected Platform:** Android 14 (June Security Patch)  
**Device Used:** Google Pixel 6  
**Build Fingerprint:** `google/oriole/oriole:14/AP2A.240605.024/11860263:user/release-keys`

---

## Overview

This report outlines a critical security flaw discovered on a Google Pixel 6 device running Android 14. The vulnerability allows an individual to bypass Factory Reset Protection (FRP), even when the bootloader is locked and USB debugging is disabled. The bypass is achieved through the use of officially released OTA images and the Android Debug Bridge (ADB) sideload feature.

The vulnerability was submitted to Google under the Android Security Rewards Program. While a reward was granted, Google classified the behavior as "Won’t Fix (Intended Behavior)," meaning it will not be addressed through a security patch.

---

## Exploit Impact

This vulnerability can be exploited by anyone with physical access to the device and basic knowledge of ADB tools. A successful attack enables:

- Full bypass of FRP lock and PIN-protection
- Access to personal data stored on the device (if not wiped)
- Re-enrollment of the device using a different Google account
- Enabling of developer options and bootloader unlocking
- Installation of custom or unauthorized firmware

This undermines Android’s built-in theft protection and potentially allows stolen or lost devices to be reused without authorization.

---

## Exploit Method

This vulnerability was tested and confirmed on a Pixel 6 running the June 2024 Android 14 release with all security updates installed.

**Tools Required:**
- Android Platform Tools (ADB)
- Pixel Flasher Tool (latest version)
- Android 15 Beta 3.1 OTA Image

**Steps:**

1. Boot the device into recovery mode and perform a factory reset.
2. Go through device setup, add a Google account, and set a PIN.
3. Confirm that the OEM unlock option is disabled and USB debugging is turned off.
4. Reboot the device back into recovery mode and select “Apply update from ADB.”
5. Connect the device to a computer via USB using a data-capable cable.
6. Open Pixel Flasher and detect the device in sideload mode.
7. Load the Android 15 Beta OTA image into the tool and initiate a full OTA flash.
8. After flashing is complete, reboot the device.

Upon reboot, the device no longer displays the lock icon or prompts for previous Google account credentials. Developer options and OEM unlocking become available. The attacker now has full administrative control over the device.

---

## Technical Cause

The bypass appears to stem from a failure to revalidate FRP enforcement following an OTA sideload. Even though FRP was correctly set and USB debugging was off, the Android system permits a sideload of a beta OTA image that resets the device state, allowing reconfiguration without authentication.

---

## Google’s Response

Google acknowledged the issue and provided a monetary reward. However, the final determination was that the behavior is consistent with intended system design, and a fix is not planned.

> "Thank you for your submission. After analysis, this behavior is considered intended and will not be addressed. However, we are issuing a reward under the Android Security Rewards program."

---

## Disclosure Notes

- This issue was reported to Google through their official Android Security Rewards process.
- A financial reward was granted, confirming the issue’s significance.
- The issue remains unpatched due to being classified as intended behavior.
- This public documentation serves to validate the finding and recognize the responsible disclosure.

**Public credit requested under the name:** Derek Morris

---

## Search Keywords

android frp bypass, pixel 6 security vulnerability, android 14 frp exploit, adb sideload bug, pixel flasher frp bypass, google pixel factory reset protection flaw, android 15 beta bypass, android bug bounty 2024, derek morris android vulnerability, won't fix intended behavior android security
