# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.13.2 (build 21)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.13.2/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,149,422 bytes
- SHA-256: `12fbc1ba1404a9e6c6701643380d8efd0a78ebc66ab93f3e6545f5c235305775`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

A feature release. Analysis sessions can now be exported to CSV and JSON from the HMI, in the shape the desktop analyzer accepts for its mobile-test upload — one shared time axis, one series per variable with its display name, original key, unit and line style, plus the alarm history — and the file is written through a native plugin. The previous export built a `blob:` link that the Android WebView does not handle, so it reported success while writing nothing. The HMI panel also stops showing a full grid of `--` when there is no connection, or when a connection has not delivered a reading yet, and shows a single message instead. Dead export code and dead dialog CSS were removed, and the README now names the real APK path and documents the signature-mismatch case. The package, the signing key, the equipment catalogs, alarms, monitoring and every Modbus behaviour are unchanged.

## Migration

The signing certificate is byte-equal to the 1.12.4 through 1.13.1 releases, so this is an ordinary in-place update and the local configuration is kept. An installation signed with a different certificate — for example a debug build — cannot be updated in place; Android rejects it with `INSTALL_FAILED_UPDATE_INCOMPATIBLE` and no flag avoids that. Uninstall first, after exporting a configuration backup, or rebuild with the release key.
