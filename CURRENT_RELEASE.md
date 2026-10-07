# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.13.1 (build 20)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.13.1/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,146,234 bytes
- SHA-256: `9cedf0dc5fed557318cb37992c2a27d2a6935d7b9483ce6ecf8c3676327eb120`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

A maintenance release. The app now shows its name as "HVAC Analyzer Mobile" in the installer, the launcher and the download notification, with the package and the signing key unchanged so the update lands in place and keeps the local configuration. Two field defects are fixed: the gateway's own Wi-Fi now works with mobile data enabled — its traffic used to leave over mobile data, because a Wi-Fi without internet is never the system's default network, so the gateway one hop away never answered — and the update check now uses whichever network reaches the internet, the Wi-Fi when it has one and mobile data when it does not. Mobile data is now held only while an upload needs it, and a binding failure names its reason in the interface language instead of leaving only a socket error that reads like a network fault. The equipment catalogs, alarms, monitoring and the remote diagnosis are unchanged.
