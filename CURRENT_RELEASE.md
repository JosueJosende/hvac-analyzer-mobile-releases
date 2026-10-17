# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.16.0 (build 27)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.16.0/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,160,214 bytes
- SHA-256: `22c1e8f14b8db0c92fdba57997cc760689803b4d1dbde70345702f43d5636671`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

A feature release. A new installation must be activated with an installation code before the app
opens: instead of the interface it shows a code screen with the support address. The code is ten
characters — Crockford base32, no ambiguous letters — case-insensitive and tolerant of the hyphens
people type, and it is redeemed once and never re-checked, so an activated unit starts with no
network call at all and keeps working on the equipment's own Wi-Fi, which has no internet. The gate
wraps the header, the navigation and the router view, so a blocked installation reaches no screen
and the runtime — update check, local network binding and the polling loop — does not start; the
missing record *is* the blocked state, so it asks again after closing and reopening. A code is
granted to one device: the server grant is a single conditional `UPDATE` and only its
`rowsAffected` authorizes, so two phones cannot spend the same code. Reinstalling and clearing app
data are indistinguishable to the system, and both reactivate with the same code because the local
record carries the `ANDROID_ID` it was issued for; that same field stops a restored Android backup
from bypassing activation on a different phone. The support address covers only what the phone
cannot solve alone: a code in use on another device, a new phone, or a factory reset. **An
installation that already exists has no activation record and will ask for a code after this
update** — that is the intended behaviour, not a fault — and that first boot needs the phone to
reach the activation service. Once accepted the app never asks again. The catalogs, alarms,
monitoring, Modbus behaviour, export formats, cloud upload, diagnosis flow and the `apiKey` are
unchanged, as is the local configuration.

## Migration

The signing certificate is byte-equal to the 1.12.4 through 1.15.1 releases, so this is an ordinary in-place update and the local configuration is kept. The updated installation will ask for an installation code on the first launch after the update, and that launch needs internet. An installation signed with a different certificate — for example a debug build — cannot be updated in place; Android rejects it with `INSTALL_FAILED_UPDATE_INCOMPATIBLE` and no flag avoids that. Uninstall first, after exporting a configuration backup, or rebuild with the release key.
