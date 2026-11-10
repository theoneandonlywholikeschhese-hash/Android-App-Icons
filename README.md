# Android-App-Icons
collection of app icons from Android
# Android 1.6 App Icons

PNG launcher icons from the system apps of the Android-x86 1.6 and 1.6.1 live CDs (ISO builds).

## Contents

28 PNG files, one per launchable app, named after the app's label (for example `Calendar.png`, `Dialer.png`, `Snake on a Phone.png`). Most are 48×48 px, a few are 36, 64, or other sizes, depending on what each app shipped.

Apps included: Alarm Clock, AndAppStore, Browser, Calendar, Camera, ConnectBot, Contacts, Dev Tools, Dialer, Email, Global Time, Google Search, Home, JetBoy, LIME, Lunar Lander, Messaging, Music, Note Pad, OI File Manager, Pinyin IME, RSS Reader, RockOn, Settings, Snake on a Phone, Sound Recorder, Spare Parts, Terminal Emulator.

## How they were extracted

1. Read the ISO's `system.sfs` (SquashFS), which contains `system.img` (ext2).
2. Pulled the APKs from `/app` and `/framework/framework-res.apk` with `debugfs`.
3. For each app, read the icon reference from its manifest and resources (`resources.arsc` and binary XML) with [androguard](https://github.com/androguard/androguard), then saved the PNG.
4. Where an app declares no icon (RSS Reader and Snake on a Phone), used the framework's default app icon, `sym_def_app_icon.png`, which is what Android would display.

Only the lowest-density (mdpi/hdpi) icon resources are included, since that is what Android 1.6 used.

## Licensing and credits

These icons were not created by this project. They belong to their original authors.

- Most come from AOSP (Android Open Source Project) apps, which are generally released under the Apache License 2.0. Google and the Android Open Source Project retain rights to their artwork and trademarks; the Apache license covers the code, and icon artwork and trademarks may be handled differently.
- Some come from third-party apps bundled in the image (AndAppStore, LIME, RockOn, and possibly others). Their licenses may differ. Check each project before reusing its icon.
- Android, Google, and related names and logos are trademarks of their owners.

This repository is an archive for reference and personal use. It is not affiliated with Google, the Android Open Source Project, or the Android-x86 project. If you are a copyright holder and want an icon removed, open an issue and it will be removed.

## Source builds

- Android-x86 1.6 (`android-x86-1_6.iso`)
- Android-x86 1.6.1 (`android-x86-1_6_1.iso`)

Both builds contained the same set of system APKs.
