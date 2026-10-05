# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.12.7 (build 16)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.12.7/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,133,030 bytes
- SHA-256: `c91e40fcb6364b903efd575aac870457de63c95881d7d9a5b97d7762edd07054`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

This release makes the in-app update reliable on Android 14 and later, including Android 16. The completion signal from the Android download manager was no longer being delivered, so the update button could stay on "Descargando..." indefinitely even though the file had already arrived, and the install only started when the app was closed and reopened. The signal is delivered again and the app no longer depends on it: it checks the real download status itself, opens the installer when the file is complete, bounds the wait at fifteen minutes, reports an indeterminate wait instead of claiming the update is ready, keeps the pending update across a cancelled installer dialog so it can be retried in the same session, and removes the downloaded file only when the installed version and build match the target and the installer was launched from the app. Installing from the system notification instead of from inside the app is never cleaned up automatically. Monitoring, alarming and configuration behaviour are unchanged.

The signing certificate is unchanged from 1.12.4 onwards, so installations can be updated in place without uninstalling and without losing configuration.
