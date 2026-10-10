# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.13.3 (build 22)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.13.3/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,151,194 bytes
- SHA-256: `5de874b3fffd265284fc4c7c3cd80348556f9d47e96f2817fef074813a4133c9`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

A reliability release. Exporting a session used to discard the captured measurements before the
result was known, so a failed cloud upload — no API key, no data, no coverage, a rejected key —
closed the dialog and lost the capture, which on site means repeating a visit. The session is now
kept until the result is confirmed, the dialog reopens with the concrete reason, a Retry button
repeats the export that failed, and the session can be written to the phone as CSV or JSON with no
internet at all. Discarding is now deliberate: it happens only after a confirmed success or when
the operator chooses to, and in the transition dialog the analysis no longer starts until the
export is resolved. Recording again no longer wipes an unresolved session, and a failure while
stopping the recording can no longer leave the export flow permanently blocked. The package, the
signing key, the equipment catalogs, alarms, monitoring and every Modbus behaviour are unchanged.

## Migration

The signing certificate is byte-equal to the 1.12.4 through 1.13.2 releases, so this is an ordinary in-place update and the local configuration is kept. An installation signed with a different certificate — for example a debug build — cannot be updated in place; Android rejects it with `INSTALL_FAILED_UPDATE_INCOMPATIBLE` and no flag avoids that. Uninstall first, after exporting a configuration backup, or rebuild with the release key.
