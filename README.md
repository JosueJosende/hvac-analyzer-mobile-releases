<p align="center">
  <img src="assets/logo.png" width="120" alt="HVAC Analyzer Mobile snowflake and circuit logo">
</p>

<h1 align="center">HVAC Analyzer Mobile</h1>

<p align="center">Connect to compatible HVAC controllers, monitor live registers, and review operating information from an Android phone.</p>

<p align="center">
  <a href="https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/latest/download/hvac-analyzer-mobile.apk">Download latest APK</a> ·
  <a href="https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases/latest">Latest release</a> ·
  <a href="https://github.com/JosueJosende/hvac-analyzer-mobile-releases/releases">Release history</a> ·
  <a href="CURRENT_RELEASE.md">Current release details</a>
</p>

HVAC Analyzer Mobile is a field tool for technicians and controls integrators who need a mobile view of equipment data exposed through Modbus. Connect over a reachable local network, inspect mapped values, follow trends and alarms, and export telemetry for later review.

## Is it a fit?

**A good fit if you** work with an HVAC controller that exposes Modbus TCP, can configure its network connection and register addressing, and want a portable way to inspect and record operating data.

**Not a fit if you need** automatic discovery of any HVAC brand, direct USB or Bluetooth access to a serial controller, a replacement for controller safety systems, or guaranteed remote/24-hour monitoring.

| Equipment or connection | What to expect |
| --- | --- |
| Controller with Modbus TCP | Connect from Android using the controller's reachable IP address, TCP port, and unit ID. |
| Serial Modbus controller | Use a compatible TCP-to-serial/network gateway. The app does not connect directly by USB or Bluetooth. |
| Built-in model profile | Select a profile only when it matches the equipment. Profiles cover selected models; they do not imply support for every model from a manufacturer. |
| Proprietary or unmapped controller | Compatibility depends on a usable Modbus interface and correct register mapping; proprietary protocols are not universal plug-and-play support. |

The phone must be able to reach the controller or gateway over the network. Network routing, firewall rules, controller settings, and correct register addresses can affect the connection and displayed data.

## What you can do

| Capability | Practical use | Important boundary |
| --- | --- | --- |
| Modbus register views | Inspect coils, holding registers, input registers, and discrete inputs. | Values and meanings depend on the equipment's register map and configuration. |
| HVAC status and measurements | View available circuit, status, pressure, temperature, and performance indications. | Only information exposed by correctly mapped live registers can be shown. |
| Trends and telemetry export | Choose variables to trend, record telemetry, and export it for review. | Exported data reflects the readings available during the recorded session. |
| Alarms and history | Review available alarms, alarm history, and connected communication logs. | Alarm reset is available only when a supported reset register is configured. |
| Operator-controlled writes | Write supported coils or holding registers when the controller permits them. | Writes can change equipment operation; use only authorized, documented values. They are not automatic repairs. |
| Local configuration and display | Adjust connection, polling, and display options; use full-screen or keep-screen-on preferences. | Keep exported configuration files private; see Privacy and safe use below. |

## Connect and monitor

1. **Check the interface.** Confirm the controller provides Modbus TCP, or connect a serial controller through a compatible network-to-serial gateway. Obtain the correct register documentation.
2. **Make the network reachable.** Connect the Android phone to a network that can reach the controller or gateway. Confirm the configured address, port, and any required network access rules.
3. **Configure the device.** Enter the IP address, TCP port, and unit ID, or choose a matching built-in model profile. A profile is not automatic equipment detection.
4. **Connect and inspect.** Open the register views or available HVAC status screens. Check that values and units agree with the controller documentation before relying on them.
5. **Follow the data.** Select variables for trends, review alarms and communication history, and export telemetry when useful. Use writes or alarm reset only when the exact supported register and value are known and authorized.

## Local connection and optional cloud services

Basic controller connection and local monitoring do not require a cloud API key. Keep the phone's network path to the controller available while monitoring.

Optional service-backed diagnosis or cloud export is separate from local monitoring. It requires applicable service access and an API key, cellular availability, and suitable live operating readings. Some diagnosis requests are gated on the reported compressor operating state. Measurements and related context are sent to the service when using these cloud features; the app does not keep all data exclusively on the phone in that case.

Version checks use cellular connectivity. APK downloads are handled by Android Download Manager and may use mobile data; download connectivity is not guaranteed to be cellular-only.

## Preferences and languages

The interface is available in **English, Spanish, and Catalan**. Settings include connection and polling options, display preferences such as full-screen and keep-screen-on, and JSON configuration backup/import with confirmation.

## Privacy and safe use

- A JSON configuration backup can contain the API key in **plaintext**. Store it securely, share it only with authorized people, and remove copies you no longer need.
- Cloud diagnosis and export send measurements and context to the service. Use them only when authorized and when the network and service requirements are met.
- Verify equipment, register mapping, units, and values against the controller documentation. Incorrect mappings or writes can lead to misleading displays or affect equipment operation.
- Treat the app as a monitoring and operator tool, not a safety system, automatic repair service, or guarantee of diagnosis accuracy or continuous background monitoring.

## Releases

Download the APK and browse release history from the links above. The current release document contains the version-specific APK details, verification values, signing information, and migration caution: [CURRENT_RELEASE.md](CURRENT_RELEASE.md). Read its migration notes before manually moving an installation between signing certificates.

This repository distributes public Android APK releases and release information; APK files can be inspected. It is not the application source repository.
