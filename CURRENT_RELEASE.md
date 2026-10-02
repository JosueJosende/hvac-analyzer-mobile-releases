# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.12.4 (build 13)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.12.4/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,117,850 bytes
- SHA-256: `60015a38dde097697fc09074efcd577cdf09667afded7a8e90c6216bd059c09a`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

The release signing certificate differs from the debug certificate used by earlier development builds, so Android cannot update a debug-signed installation directly. Export and verify a configuration backup before any manual migration; exported JSON contains the API key in plaintext and must be kept private. Data preservation during manual migration is not guaranteed.
