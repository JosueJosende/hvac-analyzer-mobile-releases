# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.14.0 (build 23)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.14.0/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,155,874 bytes
- SHA-256: `393e25abc0671224ddb9a2764fbf31c9411e87e65fefa5fc3250c30c16eeba43`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

A reliability release. An analysis session used to exist only while the app stayed alive, so
closing it — or the system killing it — lost the capture and meant repeating a visit. Sessions are
now flushed to the phone's own database while recording, a session interrupted by a hard kill is
recovered on the next launch, and the saved sessions are listed at the bottom of Inicio with
per-session export (CSV, JSON or cloud) and discard. The unflushed window is a preference in
Ajustes, between 10 and 60 seconds, defaulting to 60. A damaged session now fails loudly instead of
being exported as a silent truncated prefix. The HMI lost its own recovery button, so there is one
path to a saved session rather than two. The package, the signing key, the equipment catalogs,
alarms, monitoring, the export formats and every Modbus behaviour are unchanged.

## Migration

The signing certificate is byte-equal to the 1.12.4 through 1.13.3 releases, so this is an ordinary in-place update and the local configuration is kept. An installation signed with a different certificate — for example a debug build — cannot be updated in place; Android rejects it with `INSTALL_FAILED_UPDATE_INCOMPATIBLE` and no flag avoids that. Uninstall first, after exporting a configuration backup, or rebuild with the release key.
