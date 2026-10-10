# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.15.1 (build 26)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.15.1/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,156,582 bytes
- SHA-256: `c5406a570cbc7f3c4c9d40487a067a30e7a73cfb36e93726d35c835f033de00e`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

A patch release. Startup spent about twelve seconds on a blank screen when the phone had no
internet, because `index.html` loaded two font families from Google Fonts: a stylesheet is
render-blocking, and on the equipment's own Wi-Fi — which has no internet — the request hangs until
it times out. Neither family was ever applied, since every `font-family` in the code uses the
system stack, `monospace` or the self-hosted Oxanium that already ships in the APK. Measured on the
same phone with no connectivity, the interface went from sixteen blank captures before appearing to
two. The app now ships everything it needs inside the APK; the only remote calls left are the
deliberate, asynchronous ones — update check, cloud upload and remote diagnosis. Nothing visual
changed, and the package, the signing key, the catalogs, alarms, monitoring, the export formats and
every Modbus behaviour are unchanged.

## Migration

The signing certificate is byte-equal to the 1.12.4 through 1.15.0 releases, so this is an ordinary in-place update and the local configuration is kept. An installation signed with a different certificate — for example a debug build — cannot be updated in place; Android rejects it with `INSTALL_FAILED_UPDATE_INCOMPATIBLE` and no flag avoids that. Uninstall first, after exporting a configuration backup, or rebuild with the release key.
