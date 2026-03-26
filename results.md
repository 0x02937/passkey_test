# Passkey -8 (Ed25519) Compatibility Matrix

## Registration (Create)

| Device / Platform | Authenticator | alg -8 (Ed25519) | alg -7 (ES256) | Notes |
|---|---|---|---|---|
| Windows / Chrome | Windows Hello | ❌ |✅ | stalls after PIN |
| Windows / Edge | Windows Hello |❌ | | |
| Windows / Firefox | Windows Hello |❌ | | |
| iPhone / Safari | iCloud Keychain | ✅ | | |
| iPhone / Chrome | iCloud Keychain | | | |
| Android / Chrome | Google Password Manager | | | |
| Android / Samsung | Samsung Pass | | | |
| macOS / Safari | Touch ID / iCloud Keychain | | | |
| macOS / Chrome | Touch ID | | | |
| YubiKey 5 (USB) | Hardware key | | | |

## Authentication (Check)

| Initiator (browser) | Authenticator (where key lives) | Flow | alg -8 | Notes |
|---|---|---|---|---|
| Windows Chrome | iCloud Keychain (iPhone) | QR code | ✅ | register on iPhone first |
| Windows Chrome | Windows Hello | platform | ❌ | no -8 key to use |
| Windows Chrome | iCloud Keychain (iPhone) | QR code |❌ | |
| iPhone Safari | iCloud Keychain | platform | ✅ | |
| macOS Safari | iCloud Keychain | platform |✅ | |
| macOS Chrome | Touch ID | platform |❌ | |
| Android Chrome | Google Password Manager | platform | | |

## Cross-Device (QR / Hybrid) Registration

| Desktop browser | Phone scanned QR | alg -8 | Notes |
|---|---|---|---|
| Windows Chrome | iPhone | ❌ | "something is wrong" — CTAP2 hybrid rejects -8 |
| Windows Chrome | Android | | |
| macOS Chrome | iPhone | | |
| macOS Chrome | Android | | |
