# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.12.6 (build 15)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.12.6/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,124,706 bytes
- SHA-256: `e9cd9e6071d5d205bd08d461ab0bad05a076dc472a90c066d03d95d8f4ef8cf9`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

This release adds an opt-in compact mobile view that hides onboarding and helper content on phone widths only; tablet and desktop layouts are unchanged. Alarm reset now sits under the active-alarms badge, appears only with a working reset variable, and stays disabled until an alarm is active. The reset configuration card disappears when a working variable is associated and remains available to repair a broken association. Active alarms and history share a row on larger screens and keep stacking on phones.
