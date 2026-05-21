# macOS Microsoft Defender for Endpoint — MDM Configuration Profiles

Apple MDM configuration profiles (.mobileconfig) for deploying **Microsoft Defender for Endpoint (MDE)** on macOS via an MDM solution (Intune, Jamf, Mosyle, etc.).

## Profiles

| File | Purpose |
|------|---------|
| `fulldisk.mobileconfig` | Full Disk Access (TCC) for `com.microsoft.wdav`, `com.microsoft.wdav.epsext`, and `com.microsoft.dlp.daemon` |
| `accessibility.mobileconfig` | Accessibility / Privacy Preferences Policy Control |
| `bluetooth.mobileconfig` | Bluetooth usage privacy preference |
| `background_services.mobileconfig` | Background Service Management — allows MDE daemons to run persistently |
| `kext.mobileconfig` | Approved Kernel Extensions (for older macOS versions) |
| `netfilter.mobileconfig` | Network Content Filter — required for Network Protection |
| `notif.mobileconfig` | Notification permissions for MDE alerts |
| `sysext.mobileconfig` | System Extension approval for the Endpoint Security extension |

## Usage

Deploy these profiles through your MDM solution **before** installing the MDE agent to ensure all required permissions are pre-approved. Deploying after installation may require the user to manually grant permissions.

### Recommended deployment order

1. `kext.mobileconfig`
2. `sysext.mobileconfig`
3. `fulldisk.mobileconfig`
4. `accessibility.mobileconfig`
5. `bluetooth.mobileconfig`
6. `background_services.mobileconfig`
7. `netfilter.mobileconfig`
8. `notif.mobileconfig`

## References

- [Microsoft Defender for Endpoint on Mac — Microsoft Docs](https://learn.microsoft.com/en-us/defender-endpoint/microsoft-defender-endpoint-mac)
- [Set up Microsoft Defender for Endpoint on macOS with Jamf](https://learn.microsoft.com/en-us/defender-endpoint/mac-install-with-jamf)
- [Set up Microsoft Defender for Endpoint on macOS with Intune](https://learn.microsoft.com/en-us/defender-endpoint/mac-install-with-intune)
