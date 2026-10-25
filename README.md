# Hajj Sonar 🕋

**Private, end-to-end-encrypted messaging built for Hajj and Ummah.** No accounts, no phone numbers — your identity is a cryptographic key that never leaves your phone. Talk, coordinate, and pay without handing your data to anyone.

This is your direct-to-phone build (v0.1-alpha.15.9, arm64-v8a / armeabi-v7a). Arabic-first on fresh installs; English and Arabic fully supported.

## Download

⬇️ **[Download the latest APK (v0.1-alpha.15.9)](https://github.com/omar-for-beginners/hajj-sonar/releases/latest)**

[Direct download — hajj-sonar-v0.1-alpha.15.9-release.apk](https://github.com/omar-for-beginners/hajj-sonar/releases/download/v0.1-alpha.15.9/hajj-sonar-v0.1-alpha.15.9-release.apk) — sideload: enable "Install unknown apps" for your browser/file manager, open the APK, install. No Google account required.

> The release APK is signed with a local build signature, not a store key. After installing, verify the SHA-256 from the release notes matches what you received.

## Features

**Private messaging**
- End-to-end encrypted one-to-one chats and groups
- **Bluetooth mesh transport** — talk when the network doesn't: messages hop device-to-device (BLE peer discovery + GATT), with internet transport as the fallback
- Local-first: everything you read and send lives on your phone; your key never leaves the device
- Voice notes, photos, videos, files, and stickers
- Audio and video calls with always-dark, high-contrast call screen

**Built for the pilgrim journey**
- **Nearby radar** — find people around you via Bluetooth, grouped to a neighborhood→country geohash scale you choose
- **Location channels** — local channels for where you actually are (neighborhood, site, country)
- **Safety verification** — compare security numbers face-to-face or on a call to confirm nobody is in the middle
- Arabic-first launch, full right-to-left layouts, technical values (keys, sats amounts) always render left-to-right
- Font scaling to 200%, TalkBack labels, per-locale app language

**Finding and joining**
- Search across chats, channels, and people
- Group invites via QR code, `sonar://` links, and shareable join links
- Share content into Sonar from other apps via the Android share sheet
- Channel, group, and contact screens with verification, mute, and leave with honest confirmation copy

**Payments**
- Send and receive Lightning payments (sats) — scan destination QR, review before confirming; no money moves without your explicit confirm tap
- Wallet activity with signed amounts, pending states that never guess, mint status
- Runs on the Breez SDK (Liquid) — bring your own Breez API key to activate the wallet
- In this release the wallet and payment entry points are hidden in the app. Balances, settlement, and receipts keep working in the background and nothing is deleted; the hiding is a single switch and will be turned back off.

**Reliability and privacy**
- Encrypted auto-backup on mobile/Wi-Fi rules you set; restore flow with honest scope copy and no destructive surprises
- Push notifications for messages and wallet events; app lock with device-credential unlock
- Relay status diagnostics with a truthfulness contract — the app never claims more uptime or privacy than it has
- No contact upload, no analytics, no third-party SDKs in the message path

## Tech snapshot

- Kotlin Multiplatform + Compose (Android phone app), Rust core (`sonar-core`) via UniFFI
- Nostr-style key identity, BLE mesh + internet relay routing, SQLite local store
- Full test suite: 920 Android unit tests, catalog-driven i18n (1,357 translation keys, EN/AR at full parity)

## Status

Alpha. Behaviors may still change; data formats are stabilized but treat backups as important to verify. Desktop/Apple surfaces are not in this build yet.

## Repository

Source code: [omar-for-beginners/hajj-sonar-mobile](https://github.com/omar-for-beginners/hajj-sonar-mobile) (`apps/sonar` is the Android phone app; `core/` holds the Rust engine; `scripts/i18n/` holds the translation pipeline). This repository hosts the signed release builds.
