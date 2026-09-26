<p align="center">
  <img src="Biddabari/Assets.xcassets/AppIcon.appiconset/icon-1024.png" width="120" alt="Biddabari icon">
</p>

# Biddabari for iOS

A lightweight native iOS wrapper for [biddabari.com](https://biddabari.com). It opens the site full screen in a web view, so it feels like an app while always showing the latest version of the site.

## Features

- **Full-screen web view** of biddabari.com with swipe back and forward
- **Loading bar** at the top while pages load
- **Pull to refresh**
- **Keeps you in the app on biddabari.com.** Links to other sites (YouTube, Facebook, Play Store…) open in their own apps or in Safari.
- **`tel:`, `mailto:`, `sms:` and FaceTime links** open the matching system app
- **Popups and `target="_blank"` links** open inside the app when they point to biddabari.com
- iPhone and iPad, portrait and landscape

## Requirements

- Xcode 16 or later
- iOS 16.0 or later
- [XcodeGen](https://github.com/yonaskolb/XcodeGen) (`brew install xcodegen`)

## Getting started

The Xcode project is generated from `project.yml` and is not committed.

```bash
git clone https://github.com/MachangDoniel/Biddabari.git
cd Biddabari
xcodegen generate
open Biddabari.xcodeproj
```

Choose a simulator or your device and press **Run**. To install on a real device, set your team under **Signing & Capabilities**, or set `DEVELOPMENT_TEAM` in `project.yml`.

## Project structure

```
Biddabari/
├── BiddabariApp.swift     App entry point
├── ContentView.swift      Loading bar + web view
├── WebView.swift          WKWebView wrapper: navigation rules, refresh, popups
└── Assets.xcassets        App icon and accent color
project.yml                XcodeGen project definition
```

## Customizing

- **Site URL:** `siteURL` in [`ContentView.swift`](Biddabari/ContentView.swift)
- **Domains that stay in the app:** `onSiteHosts` in [`WebView.swift`](Biddabari/WebView.swift)
- **App name, bundle ID and version:** [`project.yml`](project.yml), then run `xcodegen generate` again
