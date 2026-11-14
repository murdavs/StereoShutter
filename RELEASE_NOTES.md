# StereoShutter 0.18.111.209 + Manager 0.1.116

**Start with [StereoShutter Manager](https://github.com/murdavs/StereoShutter/releases/latest/download/StereoShutterManager.zip)**, or choose the [standalone StereoShutter package](https://github.com/murdavs/StereoShutter/releases/latest/download/StereoShutter.zip). This release provides two independent ZIPs; game fixes download separately.

🕶️ **3D games, 3D films and 3D photos with NVIDIA 3D Vision glasses, and now with Samsung SSG-5100GB TV glasses too (experimental).** This version brings **Samsung glasses support**, **steadier glasses in games**, **hardware-accelerated GPU scheduling (HAGS)**, **3D photos of games**, **32-bit games** and **more refresh rates**, and supports integration with **StereoShutter Manager 0.1.116** and separate **DirectX 12 fixes**. The standalone StereoShutter ZIP contains three programs:

| Folder | Program |
|---|---|
| **StereoShutter** | **StereoShutter 0.18.111.209**, for games, with its tools: the glasses setup assistant, the pattern test, the geo-11 setup, the LightBoost tools and **StereoShutter_Feedback** to report a problem. |
| **StereoShutter Player** | **StereoShutter Player 1.0.4**, the 3D video player: SBS and top/bottom videos, unencrypted Blu-ray 3D and browser video. |
| **StereoShutter Photos** | **StereoShutter Photos 1.0.3**, the 3D photo viewer: 3D camera photos (MPO), JPS, side-by-side pictures, with three sample photos. |

Each one comes with its **illustrated manual in English and Spanish** (PDF).

**StereoShutter Manager 0.1.116 is included as a separate release asset.** It is not inside the standalone StereoShutter ZIP. See the [getting-started guide](https://github.com/murdavs/StereoShutter#get-started-with-manager) or use the manual installation below.

## New since 0.18.83

### 📺 Samsung SSG-5100GB glasses (experimental)

StereoShutter now also drives **Samsung SSG-5100GB** active 3D TV glasses, over Bluetooth, with a **TP-Link UB500** USB adapter and its official TP-Link driver: no NVIDIA emitter. Support is still being refined and applies only to these glasses and this adapter. NVIDIA 3D Vision glasses work as before.

- **On an OLED monitor at 240 Hz or 360 Hz,** at 60 cycles a second (up to 60 images a second for each eye). At 360 Hz each eye's image is shown twice before its black refresh, which is brighter.
- **Setting them up with this download:** use StereoShutter's own glasses window (`StereoShutter.exe --settings`, in Spanish for now). Choose Samsung 3D (Bluetooth) and the monitor, test the glasses, answer yes to Windows' administrator prompt, wait for the countdown and press the button of the glasses (about two seconds the first time). Adjust the bars with Ctrl+Alt and the arrow keys: each eye’s own bar should be clear and the other bar faint, not white; do not try to make the faint bar disappear completely. The glasses are not added in Windows' Bluetooth settings.
- **One general glasses profile for every game,** kept in your Windows user (`%LOCALAPPDATA%\StereoShutter\glasses.ini`); a game can keep its own (`[Glasses] profile = game`).
- **In games:** StereoShutter Engine fixes, and games with geo-11 through the new **StereoShutter_host.dll 0.18.32** (StereoShutter_host32.dll in 32-bit games), which hands the game's picture to StereoShutter as complete pairs.
- While the 3D runs, the adapter works only for the glasses; StereoShutter puts its driver back when it closes.

### 🧩 StereoShutter Manager 0.1.116

Manager brings games, compatible fixes and glasses into one free application. Its own ZIP is the recommended starting point; components and game fixes download when requested. It includes:

- **It finds your installed games** and shows which ones have a 3D fix: the community's **geo-11 fixes published on HelixMod**, with each author's instructions and credits, and **StereoShutter Engine fixes** for DirectX 12 games.
- **It installs, updates and removes a fix** and keeps a copy of what it changes, so that the game can go back to how it was.
- **Glasses:** one general profile for every game (NVIDIA 3D Vision, or Samsung SSG-5100GB as experimental support), with the test bars and the calibration; a game can keep a profile of its own.
- **3D output of the Engine fixes:** shutter glasses through StereoShutter, native Leia SR, side-by-side and top-bottom, anaglyph, interlaced, checkerboard and Katanga.
- **Photos & video:** it downloads, updates and opens StereoShutter Player and StereoShutter Photos.
- **Checked downloads, and no account for what is free.** Signing in is only for the early access of Ko-fi members to new Engine fixes.

**New in 0.1.116:** concise game-fix notes in the selected interface language, seven translations, reviewed English and Spanish instructions for The Witcher 3 DX12 fix 0.1.4, and a clearer layout without repeated languages. These changes concern the Manager’s presentation; they do not rewrite the fix archive or its shaders. [Full Manager notes](https://github.com/murdavs/StereoShutter/blob/main/MANAGER_RELEASE_NOTES.md).

### 🎮 DirectX 12 games in geometric 3D

**StereoShutter Engine** fixes render each eye from its own camera through the game's own rendering, with **ray tracing, DLSS Super Resolution and DLSS Frame Generation in both eyes** where the game has them. They are separate game-specific releases, not included in this ZIP; Manager installs them as separate downloads. **The Witcher 3 (DirectX 12)** is the first supported Engine title; **Marvel's Guardians of the Galaxy** is next and **Star Wars Outlaws** is in development. New fixes reach Ko-fi members a few days early and are then free for everyone.

### 🕶️ Steadier glasses in games

- **Hardware-accelerated GPU scheduling (HAGS) works now**, the Windows setting that games' frame generation needs. Before, the glasses did not start with it on. With HAGS, the game in front goes before other programs on the graphics card, and StereoShutter's images could wait behind its frames. So each time StereoShutter starts with HAGS on (over a game, the Player or Photos), Windows asks for administrator rights for a small helper of StereoShutter's own: it keeps StereoShutter in the graphics card's **realtime class** while it runs, so that its very short eye images go first. **Answer yes.** With no, StereoShutter runs all the same and says that its images may come late. `[Output] hags_realtime = no` never asks. Without HAGS nothing is asked and nothing changes.
- **After a hitch of the computer: a short dark or flat moment instead of a picture in the wrong eye.** When the whole computer stops for longer than StereoShutter's queue (the game froze, a driver call held everything up), the images that may reach the screen late go out without eyes (the left eye's picture in both eyes, or black) until Windows' statistics show that the screen has caught up. An eye image whose Present came back after its refresh had begun is replaced by the black after it. The same guard also starts when the screen keeps taking the images later than planned for a while.
- **Another window in front, or back to the game.** At that moment Windows starts or stops composing StereoShutter's picture, and the screen moves by two refreshes for about a quarter of a second. StereoShutter now sees the change with the very next image and shows neutral images (no 3D for a moment) until the new timing is confirmed, then the 3D comes back: no burst of swapped eyes.
- **A refresh counted twice by Windows** (one refresh that lasted two periods): the glasses' clock renumbers the refreshes and carries on. Before, it started again, and that restart (a pause of the eye commands and the emitter set up again) was a visible blink.
- **The black right after each image.** An eye's black refresh, and its second image, go to the screen right after the image, with nothing in between that could wait on Windows.
- **Less work for the graphics card at 60 cycles a second** (three refreshes per eye: image, image, black): each eye image is presented once for its two refreshes, and the black comes from a buffer that already holds black (checked now and then on the graphics card). Two jobs a cycle instead of six; on the screen, exactly the same. `[Output] present_hold = auto`, the default.
- **No longer stuck at 30 fps** after a loading screen or a menu: a game held at half the cycles tries one frame per cycle again once it has been waiting long enough.
- **No swapped eyes after a hitch** that left the screen a refresh or two ahead of StereoShutter's plan: the plan follows the screen again at once.
- **The automatic queue** (`queue = auto`, the default) **also comes down**: after 10 minutes of play at a raised level with nothing missing for want of margin, counted over several sessions too, the game's next start begins one level lower (5.6 ms less delay a level at 90 cycles a second, 8.3 ms at 60); if that level flickers, it goes back up at once. **Going up no longer restarts StereoShutter's picture**: it happens on the same picture, from the next eye. And a stall of the whole computer is no longer taken for a slow graphics card.
- **The automatic output engine and GPU priority** (`engine = auto`, `gpu_priority_absolute = auto`) act sooner where they help and stay out where they cost: a hitch of the game that holds the graphics card calls for the copy engine at once, but copy is kept for the game's next starts only after it has held for 120 s; priority 17, which interrupts the game's work on the card, only when 16 is not enough.
- **Fewer waits on NVIDIA's driver:** the display's HDR state is read during play only when the game's picture does not say its colours itself (a slow read held StereoShutter's images up to tens of milliseconds), and with the report off (the standard) nothing wakes at every refresh only for the report.

### ☀️ Bright-area limit for OLED monitors

With HDR output and the black refresh between the eyes, a large very bright area (sky, sand, snow) can make an OLED's own brightness limiter flicker, even without the glasses. `[Output] hdr_bfi_limit = scene` lowers only the bright part of each stereo pair, as much as that pair needs to keep its mean panel load at the monitor's full-screen luminance: pictures already below it are untouched, the darker parts never change, and both eyes get the same. `static` lowers the bright part by a fixed gain. Off by default. **Ctrl+Alt+End** turns it on and off and **Ctrl+Alt+Home** steps its level (100, 85, 70, 55 %), for the session.

### 📸 3D photos of games

**Ctrl+Alt+P** saves the game's picture at once in **Pictures\StereoShutter**: a 3840×1080 side-by-side JPG (both eyes, 1920×1080 each) for 3D photo programs, VR viewers and StereoShutter Photos, a side-by-side JPEG XR with the game's HDR light, and a red-cyan anaglyph, whichever are ticked. Each eye fits whole without being stretched, and the photo has neither StereoShutter's texts nor the extra brightness for the glasses. **Ctrl+Alt+Shift+P** chooses what the photo saves, for each game.

### 🎮 32-bit games

DirectX 11 games of 32 bits work with their 32-bit geo-11 fix through the new **StereoShutter_host32.dll**, as 64-bit games do with StereoShutter_host.dll. **StereoShutter_geo-11_Setup** tells which one the game needs from geo-11's d3d11.dll, and changes nothing if geo-11 and the game do not match.

### 🖥️ More refresh rates

**300 Hz at 75 cycles a second**; **371 to 555 Hz** with each eye's image twice and then black (**80 cycles at 480 Hz**); and **3D Vision monitors at a refresh rate their NVIDIA table does not have**, from 198 Hz, with the black refresh of other monitors instead of LightBoost. These new rates work by design and have not been tried on such monitors yet.

### 🧰 Tools and the other programs

- **One update for every piece.** When StereoShutter connects to StereoShutter_host.dll, the Player or Photos, it now checks with a challenge and an answer that the other side is a genuine part of StereoShutter. **Update StereoShutter_host.dll (and StereoShutter_host32.dll in 32-bit games) together with StereoShutter.exe** in each game folder: StereoShutter 0.18.111.209 does not work with the host DLLs of 0.18.83. The new ones are 0.18.32.
- **StereoShutter_geo-11_Setup and 3DMigoto Loader.** A fix made to be started with 3DMigoto Loader is set up too, and the setup says how to play it: open **StereoShutter_Play** first, then the game with the loader. In a folder with neither the game nor the loader, it says where the files go and changes nothing.
- **StereoShutter_Setup** opens the assistant for NVIDIA 3D Vision glasses, as before. For the Samsung glasses see their section above.
- **StereoShutter Player 1.0.4**: after the end of a video, Space, the timeline or the arrow keys play it again (before, nothing happened).
- **StereoShutter_Feedback 0.18.79**: the file can be prepared even when the game did not open, it says which programs of the game's folder are 32-bit or 64-bit, and when the e-mail program answers that the e-mail was cancelled, the window says so and shows the file in its folder.
- **The FPS counter** is off at the start in the supplied StereoShutter.ini; **Ctrl+Alt+F** shows it, and over a game **Ctrl+Alt+Enter** keeps it that way for that game.
- **The report** (when turned on) is saved also when the game is closed without Ctrl+Alt+F12.

### 📖 Manuals

In English and Spanish, with all of it: the Manager and the Samsung glasses, HAGS, the new keys, the bright-area limit, 3D photos, 32-bit games, the new refresh rates, fixes made for 3DMigoto Loader, and the monitor's own strobing at 99–185 Hz made very clear (without it there is a ghost image).

The [changelog](https://github.com/murdavs/StereoShutter/blob/main/CHANGELOG.md) has every change, version by version.

## Updating from 0.18.83

**For an installation managed by Manager, use the game’s update action.** To update a standalone installation manually, follow the steps below.

1. Close the game and StereoShutter.
2. In each game folder, replace StereoShutter's program files with those of the new **StereoShutter** folder, **StereoShutter_host.dll included** (and StereoShutter_host32.dll in a 32-bit game), and **keep that game's StereoShutter.ini**: it holds its saved settings. A StereoShutter.ini of 0.18.83 works as it is; what it lacks takes the standard values. It says `fps_counter = yes`, so the FPS counter keeps showing from the start there; write `no` for the new standard.
3. Replace the **StereoShutter Player** and **StereoShutter Photos** folders with the new ones, keeping their StereoShutter_Player.ini and StereoShutter_Photos.ini if you changed them.
4. The glasses' values (%LOCALAPPDATA%\StereoShutter\monitors.json) stay as they were: no new setup is needed at the same monitor and refresh rate.

For a **32-bit game**, install its 32-bit geo-11 fix, copy the contents of the StereoShutter folder next to the game's .exe, and run **StereoShutter_geo-11_Setup.exe** there: it connects StereoShutter_host32.dll.

## Install

**Recommended:** follow [Get started with Manager](https://github.com/murdavs/StereoShutter#get-started-with-manager). For the standalone package, use the manual steps below.

1. Download **StereoShutter-0.18.111.209.zip** and check its SHA-256 (below).
2. Extract the ZIP into a folder where you can write. The programs are unsigned: if Windows or an antivirus blocks a file, review the warning and verify its source. ZIP Properties → Unblock does not sign files or guarantee that warnings disappear; do not disable protections just to run them.
3. The NVIDIA and Windows settings: NVIDIA's global low latency mode **On or Off, never Ultra**, and **G-SYNC off** on the glasses' monitor. Hardware-accelerated GPU scheduling may be on or off; with it on, answer **yes** when Windows asks for administrator rights for StereoShutter.
4. Run **StereoShutter_Setup.exe** in the StereoShutter folder to adjust NVIDIA 3D Vision glasses.
5. **For games, install the game's 3D fix first.** Find its compatible geo-11 fix on [HelixMod](https://helixmod.blogspot.com/search/label/geo-11), download it and follow that game's instructions.
6. With the game closed, copy **the contents of the ZIP's StereoShutter folder** beside the actual game .exe and the installed fix. Do not leave the files inside an extra StereoShutter subfolder or put them in the launcher's folder. Player and Photos stay separate.
7. Run **StereoShutter_geo-11_Setup.exe** from that game folder and apply its proposed changes. This connects the fix; it is not the glasses assistant.
8. **Launch the game and let its window settle.** Resolution and window-mode changes during startup are normal. StereoShutter activates 3D automatically **5–10 seconds after the window and resolution become stable**, not after launching the game, to avoid starting 3D during those transitions.

The StereoShutter ZIP does not include game fixes, and StereoShutter does not create stereoscopic views by itself. Player and Photos do not need game fixes. When updating an existing game installation, back it up and preserve its StereoShutter.ini.

The manual explains each step: `StereoShutter/StereoShutter_Manual_EN.pdf` (in Spanish: `StereoShutter_Manual_ES.pdf`).

## Before you install

> ⚠️ **Not recommended for online multiplayer or games protected by anti-cheat.** 3D fixes get into the game (DLL files and hooks), and anti-cheat systems may block them or sanction the account. Closing StereoShutter does not remove what is installed in the game's folder.

- Needs Windows 10 or 11, 64-bit, an NVIDIA graphics card ([which one](https://github.com/murdavs/StereoShutter#which-graphics-card)), and NVIDIA 3D Vision glasses with their USB emitter and NVIDIA's emitter driver (not included), or Samsung SSG-5100GB glasses with a TP-Link UB500 adapter and TP-Link's driver (not included) on an OLED monitor at 240 or 360 Hz.
- Games need their own 3D fix. The Player needs **VLC media player 3, 64-bit**, installed (not included; VLC 4 is not supported).
- At 99–185 Hz, turn on the monitor's own strobing (ELMB, ULMB, DyAc…): without it there is a ghost image. From 198 Hz StereoShutter puts the black refresh between the eyes itself.
- The programs are not digitally signed.
- OLED monitors wear with brightness and time: keep the monitor's care features on and do not leave a bright still picture running.

## Files

`StereoShutterManager-0.1.116.zip` — SHA-256 `29d67ad8c677c741e3ea5bcbd5ff3e3816de2e1d2931df421bafe50995d5770e`

`StereoShutterManager.zip` is the same Manager package under the fixed name used by the main download link. Manager and standalone StereoShutter are independent packages.

`StereoShutter-0.18.111.209.zip` — SHA-256 `0e6d2454181995dd2c9a88b79b0b746468210ea3545ae8a08fb14d5fffa2969e`

`StereoShutter.zip` is the same file under a fixed name, for the website's download link.

Copyright (C) 2026 murdavs. All rights reserved. Free of charge under the licences in each folder. NVIDIA, 3D Vision, LightBoost and DLSS are trademarks of NVIDIA Corporation; Samsung, TP-Link, Leia and the names of the games are trademarks of their owners. StereoShutter is not made, supported or endorsed by any of them.

---

[🌐 Official website](https://www.stereoshutter.com) · <a href="https://discord.gg/J6dgWXhAPy"><img src="https://raw.githubusercontent.com/murdavs/StereoShutter/main/docs/icons/discord.svg" height="18" alt=""> Discord</a> · <a href="https://ko-fi.com/stereoshutter"><img src="https://raw.githubusercontent.com/murdavs/StereoShutter/main/docs/icons/kofi.png" height="18" alt=""> Ko-fi</a>
