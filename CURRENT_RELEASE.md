# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.15.0 (build 25)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.15.0/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,156,730 bytes
- SHA-256: `7c8e09f433e05f7163ffbc1ca430ca37602226fe847fafeac3268cad2d0fa6cd`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

A feature release. Saving a stopped session could fail and leave only a warning: the saved session
might be incomplete, and there was nothing to do about it. Inicio now offers a retry beside that
warning and reports whether it worked. While a recording runs the flush timer already retried on
every tick, so the uncovered case was a session that had already stopped whose final flush failed.
The retry goes through the same per-session write queue behind a synchronous guard, so two
simultaneous retries cannot write the same points twice, not even when the first fails and returns
the tail to the buffer; and with nothing pending it does not touch storage at all. The package, the
signing key, the catalogs, alarms, monitoring, the export formats and every Modbus behaviour are
unchanged.

## Migration

The signing certificate is byte-equal to the 1.12.4 through 1.14.1 releases, so this is an ordinary in-place update and the local configuration is kept. An installation signed with a different certificate — for example a debug build — cannot be updated in place; Android rejects it with `INSTALL_FAILED_UPDATE_INCOMPATIBLE` and no flag avoids that. Uninstall first, after exporting a configuration backup, or rebuild with the release key.
