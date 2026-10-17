# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.16.1 (build 28)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.16.1/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,160,150 bytes
- SHA-256: `cfc6742584a5a1ad4f0689a2826a940764976904ca8d8d28e58e13973e57ed38`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

A patch release: installation-code redemption now records the app version and Android build instead
of leaving those descriptive fields empty. Version lookup failures never block activation.
Existing activated installations remain activated after updating; no fresh code is required.
Previous server rows are not automatically backfilled: metadata is recorded on activation or
reactivation. Connections, alarms, monitoring, Modbus, API keys and export formats are unchanged.

## Activation

A fresh installation needs a ten-character installation code and internet access for its first
activation. Codes are case-insensitive and accept a hyphen between groups of five. Once activated,
the app starts without rechecking the server and works offline. Reinstalling or clearing data can
reactivate with the same code on the same phone. For a code in use on another device or a changed
device identity, contact josuejosende@gmail.com.

## Migration

The release uses the same signing certificate as 1.12.4 through 1.16.0, so an in-place update keeps
local configuration and existing activation. A debug-signed installation cannot be updated with a
release-signed APK: Android rejects mismatched signatures. Do not uninstall without first exporting
and verifying a configuration backup; uninstalling deletes local data.
