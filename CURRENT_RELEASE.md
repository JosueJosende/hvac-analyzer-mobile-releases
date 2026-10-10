# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.14.1 (build 24)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.14.1/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,156,330 bytes
- SHA-256: `298e4e5be194c6baaab02818cc7a1216cdf765a9f4b1977f27938096b8f2ad5a`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

A patch release. The export dialog opened anchored to the bottom of the Home page with its buttons
out of reach, because the section it was rendered in carries `backdrop-filter`, which makes that
element the containing block for fixed-position descendants; the dialog is now rendered through a
teleport to the document body, so no ancestor can trap it, and its height is bounded with internal
scrolling so a short screen can always reach its actions. A successful export also stayed
successful: export and cleanup used to share one error path, so a failed deletion after a written
file was reported as an export failure and offered a retry that would have uploaded a second copy.
They are now separate, and a failed flush — previously recorded but invisible — shows a discreet
warning in Inicio saying the saved session may be incomplete. The package, the signing key, the
catalogs, alarms, monitoring, the export formats and every Modbus behaviour are unchanged.

## Migration

The signing certificate is byte-equal to the 1.12.4 through 1.14.0 releases, so this is an ordinary in-place update and the local configuration is kept. An installation signed with a different certificate — for example a debug build — cannot be updated in place; Android rejects it with `INSTALL_FAILED_UPDATE_INCOMPATIBLE` and no flag avoids that. Uninstall first, after exporting a configuration backup, or rebuild with the release key.
