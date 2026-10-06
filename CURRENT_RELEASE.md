# HVAC Analyzer Mobile releases

This repository distributes public Android APK releases and release metadata; it does not publish the application source. APK downloads are public and can be inspected.

## Current release: 1.12.8 (build 17)

- App: HVAC Analyzer Mobile (`com.hvacmodbus.app`)
- APK: [Download hvac-analyzer-mobile.apk](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/download/v1.12.8/hvac-analyzer-mobile.apk)
- [All releases](https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases)
- Size: 6,133,102 bytes
- SHA-256: `c81a9b3f69ab6556478f10a71db088b1f708df71f542c75401fd7a95cac15a0c`
- Signing certificate SHA-256: `c1f91c52b1b75bd57fa1d7b2619110f78351a9c51a08a3fd35821eee4e698d8f`
- Signature: one RSA-4096 signer, APK Signature Scheme v2; non-debuggable

This release fixes the recovery action when the cellular diagnosis cannot run. When a diagnosis fails for lack of a mobile data route and needs a manual retry, the retry now appears inside the diagnosis panel next to the last result, so the previous diagnosis stays visible while you can act on the failure, and a "no mobile data" failure is reported as such instead of being rewritten as a generic network error. Exactly one retry is offered in every state. The rest of the release clears the project's accumulated test debt: 20 long-standing failing tests were triaged, 18 were tests left behind by deliberate product changes and now assert today's behaviour, and 2 contained no assertion at all. The suite passes completely, with more tests than before and no behavioural change. Monitoring, alarming and configuration are unchanged.

**Update scope:** this is the **first update performed by the fixed update flow** introduced in 1.12.7, so the installer should open by itself when the download completes, without closing and reopening the app. Updating from 1.12.6 or earlier is still performed by that older build and may need one restart, as the 1.12.7 notes describe.

**Known limit:** when there is no cellular route at all, the app shows the diagnosis error screen with its retry and does not keep the previous result on screen. The retry is visible in that case.

The signing certificate is unchanged from 1.12.4 onwards, so installations can be updated in place without uninstalling and without losing configuration.
