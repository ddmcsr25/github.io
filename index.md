# Android Factory Reset Protection (FRP) Security Research — Pixel 6

**Researcher:** Derek Morris  
**Disclosure Program:** Google Android & Devices Vulnerability Reward Program (ASR / VRP)  
**Date Reported:** June 2024  
**Status:** Won’t Fix (Classified as Intended Behavior)  
**Recognition:** Reward issued by Google  
**Affected Platform:** Android 14  
**Device:** Google Pixel 6  

---

## Overview

This page provides **public attribution** for security research I reported to Google involving
Android Factory Reset Protection (FRP) behavior on Google Pixel devices.

The research was submitted through Google’s official Android Security Rewards Program,
acknowledged by Google, and resulted in a reward.  
Google classified the behavior as **“Intended Behavior / Won’t Fix”** under their threat model.

This document is intentionally **non-operational** and does **not** include exploit steps,
tools, or reproduction instructions.

---

## Public Reference

- **Issue Tracker ID:** 352333773  
- **Reporter:** Derek Morris  
- **Program:** Android & Devices VRP / Android Security Rewards  
- **Outcome:** Reward issued  
- **Disposition:** Intended behavior (no patch planned)

---

## Security Impact (High-Level)

The research examined how FRP enforcement behaves under certain
**physical-access conditions** and system update states.

Key observations evaluated by Google included:
- Device state transitions during system updates
- Ownership verification expectations
- Residual risk when a device is in attacker possession

The behavior was determined to fall within Google’s accepted security model,
despite having real-world implications for lost or stolen devices.

---

## Why “Intended Behavior” Can Still Be Security-Relevant

Some security findings are not patched because:
- They require physical access
- They do not scale remotely
- They align with platform design tradeoffs

Documenting these behaviors improves transparency and helps users,
defenders, and researchers better understand Android’s security boundaries.

---

## Defensive Guidance (Non-Operational)

- Keep devices updated to the latest Android security patch level
- Use strong device authentication and account security (2FA)
- Enterprises should use MDM controls for inventory and device recovery
- Always complete official ownership transfer steps when buying used devices

---

## Disclosure Timeline

- **Reported:** June 2024  
- **Reviewed by:** Google Android Security team  
- **Resolution:** Intended behavior / Won’t fix  
- **Recognition:** Monetary reward issued

---

## Attribution

This page exists to provide a **stable public reference**
confirming that the research was submitted by:

**Derek Morris**  
GitHub: https://github.com/ddmcsr25

---

## Disclaimer

This content is published for **defensive security awareness and attribution only**.
No instructions, tools, or methods for bypassing device protections are provided.
