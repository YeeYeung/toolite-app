# TooLite

[English](README.md) | [简体中文](README.zh-CN.md)

A native iOS pack-weight app for hikers and backpackers. Build gear lists and see base weight, worn weight and consumables for every trip. Bring a LighterPack list over with one link, and share a list as a QR-code image. No account, no ads, no subscription.

<p>
  <a href="https://toolite.win"><img src="badges/website-en.svg" height="48" alt="Visit the website: toolite.win"></a>
</p>

## Stack

| | |
|---|---|
| Language | Swift 6 |
| UI | SwiftUI, iOS 17+ |
| Data | SwiftData; iCloud sync through the user's own private CloudKit database |
| Purchases | StoreKit 2: one-time purchase, no subscription |
| Sharing | Core Image to draw the QR code, Vision to read it back from a saved photo |
| Weather | WeatherKit trip forecast |
| Languages | English, Simplified Chinese |

## Engineering highlights

- A whole list travels inside the QR code: compact binary, zlib, base64url in the URL fragment. A 31-item list is about 780 characters, and nothing is uploaded.
- The share image survives messaging-app recompression: the QR code is drawn at a size and error-correction level tested against WeChat's image compression.
- Weight rules follow LighterPack: base weight is total minus worn minus consumables, and a worn item counts once whatever its quantity. Totals match what you see on the web.
- LighterPack import from a share link or CSV, and export back to the same CSV format.

## Privacy

- No account, no analytics, no ads.
- Lists stay on the device, or in the user's own private iCloud database with sync on.
- [Privacy policy](https://toolite.win/privacy/)
