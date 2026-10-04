# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.12.5 (build 14)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.12.5/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,124,102 bytes
- SHA-256: `976437e0daa04f17a8b98f86609ce1dd30e1d58a770c2299d1d07dbbe42286d3`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

This release adds an automatic install step for Android update downloads: when a download finishes, the app opens the system installer and the user confirms. If the app is in the background, the installer cannot be opened, or the "install unknown apps" allowance is missing, the download remains available for manual installation. Updates from 1.12.4 or earlier remain manual.
