# What's new since StereoShutter 0.18.83

The highlights. Every change, version by version, is in the [changelog](CHANGELOG.md).

## 🕶️ StereoShutter 0.18.111.209

- **Works with HAGS** (hardware-accelerated GPU scheduling), the Windows setting that frame generation needs.
- **Steadier glasses:** after a hitch of the PC, a short flat moment instead of a picture in the wrong eye.
- **Less GPU presentation work in the image–image–black mode**, with the same picture on screen. This reduces StereoShutter’s output work, not the game’s rendering cost by a factor of three.
- **Bright-area limit for OLED monitors with HDR**, against the flicker of large bright areas such as sky, sand or snow (Ctrl+Alt+End).
- **3D photos of your games** with Ctrl+Alt+P: side-by-side, HDR and anaglyph.
- **32-bit DirectX 11 games**, and more refresh rates (300 Hz and 371–555 Hz, not yet tried on such monitors).

## 📺 Samsung 3D TV glasses (experimental)

- **Samsung SSG-5100GB glasses over Bluetooth** with a TP-Link UB500 USB adapter on an OLED monitor at 240 or 360 Hz: no NVIDIA emitter needed. 60 stereo pairs a second; support is still being refined.
- **One general glasses profile** for every game, in StereoShutter Engine fixes and in geo-11 games. NVIDIA 3D Vision glasses work as before.

## 🧩 StereoShutter Manager 0.1.116

[Download Manager](https://github.com/murdavs/StereoShutter/releases/latest/download/StereoShutterManager.zip), the recommended free application for getting started. It is supplied in its own ZIP alongside standalone StereoShutter.

- **One program for everything:** it finds your installed games and installs, updates and removes their 3D fixes, with backups to go back.
- **HelixMod (geo-11) fixes and StereoShutter Engine fixes** in one library, with each author's instructions and credits.
- **Glasses, 3D output and game settings** set up from the same place. Free fixes need no account or sign-in; Ko-fi members get early access.

**New in 0.1.116:** concise fix release notes in the interface language, seven translations, reviewed English/Spanish Witcher 3 instructions and clearer layout without duplicated languages. [Manager notes](MANAGER_RELEASE_NOTES.md).

## 🎮 StereoShutter Engine: DirectX 12 in geometric 3D

Engine game fixes are separate releases, not part of this StereoShutter ZIP. Availability is announced with each fix.

- **Each eye is rendered from its own camera**, not converted from a depth map.
- **Ray tracing, DLSS Super Resolution and DLSS Frame Generation in both eyes.**
- **Outputs:** 3D Vision glasses (and Samsung ones, experimental) through StereoShutter, native Leia SR, side-by-side and top-bottom (half or full), anaglyph, interlaced, checkerboard and Katanga.

## 🐺 Games

- **The Witcher 3 (DirectX 12)** is the first Engine title. Work on its separate fix includes steadier automatic convergence in conversations, name labels at the depth of their characters (on horseback too), and terrain and hair corrections. Its version and download are announced separately.
- **Marvel's Guardians of the Galaxy** is next, and **Star Wars Outlaws** is in development.

Copyright (C) 2026 murdavs. NVIDIA, 3D Vision, DLSS and the names of the games and other products are trademarks of their owners; StereoShutter is not made, supported or endorsed by them.
