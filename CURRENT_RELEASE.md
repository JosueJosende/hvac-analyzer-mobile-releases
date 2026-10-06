# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.13.0 (build 19)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.13.0/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,134,970 bytes
- SHA-256: `ee18153c3c2e003284b96867fdfb5d55b4a3b0902a39af09e2962cbef4a25b29`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

This release adds the VERNE equipment profile, selectable in Connections under both BAXI and HITECSA as `verne/91-1201`. Built from a partial HITECSA listing, it exposes 56 registers so an engineer can open a connection and confirm that the unit answers over Modbus; diagnosis is deliberately not enabled for these units. The listing states no units or scaling factor, so the `0.1` resolution applied to temperatures and liquid pressure must be confirmed against the hardware. This is not a complete unit map. Monitoring, alarming and configuration for every existing equipment, and the existing catalogs, are unchanged.
