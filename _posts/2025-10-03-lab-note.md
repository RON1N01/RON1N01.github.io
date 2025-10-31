---
title: "Intune and Entra ID Rollout – License Pathing and Enrollment Troubleshooting"
date: 2025-10-03
tags: [intune, entra-id, windows, sysadmin, endpoint-management]
---

### Objective
Establish production-grade device onboarding using **Microsoft Entra ID** and **Intune**, ensuring compliance, license alignment.

### Activities
- **Device Enrollment**
  - Began onboarding two new laptops.
  - Verified automatic MDM enrollment prerequisites; confirmed **Premium Entra ID** licensing required for auto-enroll.
  - Proceeded with manual enrollment for testing.

- **Windows Edition Upgrade**
  - Identified one device running **Windows 11 Home**.
  - Attempted in-place edition upgrade to **Pro** using both generic key and purchased license.
  - Encountered error `0xc004f050` → determined cause: edition mismatch / invalid key injection.
  - Documented correct path: deploy Pro image or use digital license tied to MS account before tenant join.

- **Tenant Join / Intune Link**
  - Confirmed successful Entra ID join on one device with valid license.
  - Confirmed Intune enrollment with baseline compliance policies active.
  - Confirmed Company Portal access and sync verification.

### Findings
- Automatic MDM enrollment fails without **Entra ID Premium P1/P2**.
- Licensing status directly affects policy propagation and compliance visibility.
- Using consistent Pro image from the start eliminates activation friction.

### Lessons / Best Practices
- Maintain a **golden image** with Windows 11 Pro pre-licensed and all corporate certificates.
- Validate **hardware hash** collection early for Autopilot readiness.
---

**Status:** Production pilot live — first endpoint successfully managed through Entra ID + Intune stack.

