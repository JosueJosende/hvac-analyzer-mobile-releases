# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.12.9 (build 18)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.12.9/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,133,542 bytes
- SHA-256: `f272079b7564d90906c22c6e1d387d6ef9210b9479304ed9e3b5ebdf50824906`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

This release fixes a defect that stopped the app from working for anyone using a VPN. The app deliberately sent the version check and the cellular diagnosis over the mobile data network; when a VPN is connected that network is no longer the phone's default route, and Android forbids an application from binding its traffic outside the VPN. The app could therefore not check for updates — it answered "No se pudo buscar actualizaciones" — and the cellular diagnosis failed as well. It now detects that refusal, steps aside and continues over the phone's normal route, which respects the VPN, while still preferring mobile data when it is available. Anyone with a VPN was affected, including Tailscale, WireGuard, a corporate profile or Android's own VPN. Monitoring, alarming and configuration are unchanged.

**Update scope:** this is the second update performed by the fixed update flow introduced in 1.12.7, so the installer should open by itself when the download completes, without closing and reopening the app. Updating from 1.12.6 or earlier is still performed by that older build and may need one restart.

**Known limits:** a request can still fail for the genuine reasons — no available mobile data network, both name resolvers failing, a timeout, a connection failure or an HTTP error. The name resolution falls back only when the mobile-data resolver throws. When there is no mobile data route at all, the diagnosis shows its error screen with a retry and does not keep the previous result on screen.

**Verified on a real phone with the VPN connected:** the check answered "Estás al día" instead of the error, and the device log proved the mechanism, not just the message — the app logged the refusal once, continued over the default route and completed the request with HTTP 200, for both the automatic check on launch and the manual one. No automated test in this project can catch this class of defect.

The signing certificate is unchanged from 1.12.4 onwards, so installations can be updated in place without uninstalling and without losing configuration.
