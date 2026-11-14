[Project overview and downloads](../README.md)

<div align="center">

<h1>StereoShutter — 3D gaming, video and photos</h1>

**3D games, 3D films, Blu-ray 3D and 3D photos with your NVIDIA 3D Vision glasses, and now with Samsung SSG-5100GB TV glasses too (experimental).<br>OLED at 240 / 360 Hz with optional HDR output; 3D Vision monitors with LightBoost, including NVIDIA Surround.**

[![StereoShutter](https://img.shields.io/badge/StereoShutter-0.18.111.209-2ea44f)](#documentation-and-licence)
[![Player](https://img.shields.io/badge/Player-1.0.4-2ea44f)](#stereoshutter-player)
[![Photos](https://img.shields.io/badge/Photos-1.0.3-2ea44f)](#stereoshutter-photos)
![Windows](https://img.shields.io/badge/Windows-10%20%7C%2011-31363B?logo=windows&logoColor=76B900)
![GPU](https://img.shields.io/badge/GPU-NVIDIA-76B900?logo=nvidia&logoColor=white)
![OLED](https://img.shields.io/badge/OLED-240%20%2F%20360%20Hz-76B900)
![HDR](https://img.shields.io/badge/HDR-scRGB%20%C2%B7%20HDR10-76B900)
![3D Vision](https://img.shields.io/badge/3D%20Vision-LightBoost%20%C2%B7%20Surround-76B900)

![Licence](https://img.shields.io/badge/licence-freeware-31363B)

### [⬇️ Download StereoShutter 0.18.111.209](https://github.com/murdavs/StereoShutter/releases/latest/download/StereoShutter.zip)

[Release details](https://github.com/murdavs/StereoShutter/releases/latest) · [Changelog](../CHANGELOG.md) · [Discord community](https://discord.gg/J6dgWXhAPy) — optional help and discussion; no Discord account is needed to download.

**StereoShutter Manager 0.1.116 is available in its own ZIP.** It finds games, installs compatible fixes and configures supported 3D outputs. [Download Manager](https://github.com/murdavs/StereoShutter/releases/latest/download/StereoShutterManager.zip) · [Project overview](../README.md)

[Highlights](#highlights) · [🧩 Manager](#stereoshutter-manager) · [🎮 Games](#games) · [⚠️ Multiplayer safety](#multiplayer-and-anti-cheat) · [Quick start](#quick-start) · [📺 Samsung glasses](#samsung-ssg-5100gb-glasses) · [Tools](#the-tools) · [🎬 Player](#stereoshutter-player) · [📷 Photos](#stereoshutter-photos) · [📸 3D photos of games](#3d-photos-of-games) · [Monitors](#monitors) · [Display modes](#display-modes) · [Stability](#game-pacing-and-automatic-stability) · [HDR](#hdr-input-and-output) · [Reporting a problem](#reporting-a-problem) · [FAQ](#faq) · [Credits](#acknowledgements) · [📖 Manuals](#documentation-and-licence)

</div>

---

**Bring your legacy NVIDIA 3D Vision glasses back to life.** StereoShutter shows stereoscopic images and synchronizes the shutter glasses with the monitor. It uses NVIDIA's emitter USB driver and works alongside the installed NVIDIA graphics driver, without the discontinued 3D Vision graphics driver. It also drives **Samsung SSG-5100GB** TV glasses over Bluetooth, with a TP-Link UB500 USB adapter and no NVIDIA emitter (experimental). It is an independent application that complements existing 3D communities and game fixes.

For games, a 3D fix supplies the left and right views: a community **geo-11 fix** from HelixMod in DirectX 11 games, or a **StereoShutter Engine fix** in DirectX 12 games, in geometric 3D with each eye rendered from its own camera. **StereoShutter Manager**, a separate download, installs both kinds and sets up the glasses. Engine fixes are separate game-specific downloads, not included in this ZIP. **StereoShutter Player 1.0.4** brings 3D films, unencrypted Blu-ray 3D and 3D videos playing in a browser to the same glasses, and **StereoShutter Photos 1.0.3** shows 3D photos, both with **HDR output to make them brighter through the glasses**. StereoShutter handles the presentation, the timing and the glasses' values. It does not turn 2D pictures into 3D.

> 🎮 **Start with the manual geo-11 installation:** first install your game’s **geo-11 fix** from [HelixMod](https://helixmod.blogspot.com/search/label/geo-11), following that game’s instructions, **then** add StereoShutter to the same game folder and run **StereoShutter_geo-11_Setup**. StereoShutter does not make arbitrary games 3D. [Manager](#stereoshutter-manager) offers an integrated workflow. [Games](#games) · Player and Photos do not need game fixes.

StereoShutter, the Player and Photos each come with an **illustrated manual in English and Spanish** (PDF); the StereoShutter manual has a chapter on the Manager, whose full guide is included in its separate download.

> ⚠️ **Single-player recommended — multiplayer / anti-cheat risk**
>
> 3D layers and fixes get into the game (DLL files and hooks). Anti-cheat systems may block them or impose account sanctions, including permanent bans, even when they are used only for 3D. **This setup is not recommended for online multiplayer or for games protected by anti-cheat.** Read the [safety guidance](#multiplayer-and-anti-cheat) before installing anything in a game.

### ✨ New since 0.18.83

- 🧩 **StereoShutter Manager (separate download):** a separate application for game discovery, 3D fix installation and updates, glasses and output setup, and opening Player and Photos. It has its own ZIP. [More](#stereoshutter-manager)
- 📺 **Samsung SSG-5100GB glasses (experimental):** over Bluetooth with a TP-Link UB500 USB adapter, on an OLED monitor at 240 or 360 Hz, with no NVIDIA emitter; one general glasses profile for every game. [More](#samsung-ssg-5100gb-glasses)
- 🎮 **DirectX 12 games in geometric 3D:** StereoShutter Engine fixes, with ray tracing, DLSS Super Resolution and DLSS Frame Generation in both eyes. Game fixes, starting with The Witcher 3, have separate releases and are not part of this ZIP. [More](#directx-12-stereoshutter-engine)
- 🕶️ **Steadier glasses:** after a hitch of the computer, or when another window comes in front, a short neutral moment instead of a picture in the wrong eye; a refresh that Windows counts twice no longer restarts the glasses' timing; less work for the graphics card at 60 cycles a second. [More](#game-pacing-and-automatic-stability)
- 🛡️ **Hardware-accelerated GPU scheduling (HAGS) works:** StereoShutter asks Windows for administrator rights for a small helper that keeps its images first on the graphics card. [More](#2-nvidia-and-windows-settings)
- 🎯 **The automatic queue goes up without restarting the picture, and comes down again** after 10 minutes of calm play.
- ☀️ **Bright-area limit for OLED monitors** with HDR and the black refresh: large very bright areas no longer make the monitor's own brightness limiter flicker (**Ctrl+Alt+End**, **Ctrl+Alt+Home**). [More](#hdr-input-and-output)
- 📸 **3D photos of games:** **Ctrl+Alt+P** saves the game's picture as a side-by-side JPG, an HDR JPEG XR or a red-cyan anaglyph. [More](#3d-photos-of-games)
- 🎮 **32-bit games:** DirectX 11 games of 32 bits work with geo-11 too, through the new **StereoShutter_host32.dll**; the geo-11 setup chooses the right DLL, and sets up fixes made for 3DMigoto Loader.
- 🖥️ **More refresh rates:** 300 Hz at 75 cycles a second, 371–555 Hz (480 Hz at 80 cycles), and 3D Vision monitors at a refresh rate their NVIDIA table does not have, from 198 Hz.
- 🎬 **Player 1.0.4** plays a video again after its end; **StereoShutter_Feedback 0.18.79** prepares the file even when the game did not open.
- 🔐 **Update the host DLLs too:** StereoShutter 0.18.111.209 works only with the StereoShutter_host.dll and StereoShutter_host32.dll of its own download (0.18.32), which also give the Samsung glasses the picture of geo-11 games.

All the changes are in the [changelog](../CHANGELOG.md).

## Highlights

<table>
<tr>
<td width="50%" valign="top">

<img src="icons/play.png" width="64" alt="">

### ☀️ Stereoscopic gaming with native HDR

**240 / 360 Hz, with a black refresh between the eyes.**

Play HDR games in stereoscopic 3D on a high-refresh OLED. For SDR games, HDR output works as a separate brightness boost through the glasses: **3× Windows' SDR white** by default, adjustable with **Ctrl+Alt+Page Up / Page Down**, never above the monitor's peak.

HDR10 and scRGB game pictures are recognized; an HDR panel adjusts brightness, contrast, colour and highlights with the mouse, in both eyes.

</td>
<td width="50%" valign="top">

<img src="icons/stereoshutter.png" width="64" alt="">
<img src="icons/surround-setup.png" width="64" alt="">

### 💡 3D Vision + LightBoost

**One NVIDIA-certified 3D Vision monitor, or three in NVIDIA Surround.**

Recognized modes use NVIDIA's glasses and display timing table, with LightBoost switched on for the session and restored at the end.

For an **NVIDIA Surround** grid, dedicated setup and undo tools prepare the monitors' LightBoost timings. On-screen texts stay on the middle monitor.

</td>
</tr>
<tr>
<td width="50%" valign="top">

<img src="icons/player.png" width="64" alt="">

### 🎬 3D video player

**3D films, Blu-ray 3D and browser video, brighter through the glasses.**

Half or full side-by-side and top/bottom videos, unencrypted Blu-ray 3D at **1920 × 1080 per eye**, or a browser's 3D video through window capture. A 3D menu with the mouse, subtitles at their own depth, **seven languages**.

[More](#stereoshutter-player) · [English PDF](StereoShutter_Player_Manual_EN.pdf) · [PDF en español](StereoShutter_Player_Manual_ES.pdf)

</td>
<td width="50%" valign="top">

<img src="icons/photos.png" width="64" alt="">

### 📷 3D photo viewer

**Photos of 3D cameras, JPS and side-by-side pictures.**

MPO files of 3D cameras, JPS and PNS, side-by-side and top/bottom pictures and 2D photos: a whole folder with the arrow keys or as a slideshow, full screen or in a window, with zoom and depth.

[More](#stereoshutter-photos) · [English PDF](StereoShutter_Photos_Manual_EN.pdf) · [PDF en español](StereoShutter_Photos_Manual_ES.pdf)

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🎯 Automatic stability

**The supplied settings adapt to the game by themselves.**

The output margin grows when the graphics card is late, on the same picture, and comes down again after 10 minutes of calm play; it is remembered for that game. StereoShutter's GPU priority rises only while its images are about to be late. For a game that fills the graphics card, StereoShutter keeps a part of it for its images. The game's frames are paced to the glasses' cycles. After a hitch of the computer or a change of the window in front, a short neutral moment instead of a picture in the wrong eye.

[Pacing and automatic stability](#game-pacing-and-automatic-stability)

</td>
<td width="50%" valign="top">

### 📖 Manuals and help

**Illustrated PDF manuals, in English and Spanish.**

Step by step: the NVIDIA and Windows settings, setting up the glasses, games with geo-11, HDR, the messages on the screen and what to do about them.

When something goes wrong, **StereoShutter_Feedback** records one game session into a single file of at most 5 MB, ready to send by e-mail.

[StereoShutter manual (EN)](StereoShutter_Manual_EN.pdf) · [Manual de StereoShutter (ES)](StereoShutter_Manual_ES.pdf)

</td>
</tr>
</table>

- 🧩 **StereoShutter Manager (separate download):** games, fixes, glasses and 3D output in one program, released separately.
- 🕶️ **Two kinds of glasses:** NVIDIA 3D Vision with their USB emitter, and Samsung SSG-5100GB over Bluetooth (experimental).
- 🎮 **Game integration:** DirectX 11 games, 64-bit and 32-bit, through geo-11 and StereoShutter's host DLLs, connected by a setup tool with undo; fixes made for 3DMigoto Loader too. DirectX 12 games through StereoShutter Engine fixes.
- 🎯 **Pacing:** the game's frames in step with the glasses: **60 cycles a second at 360 Hz** (90 for games that keep 90), **60 at 240 Hz**, **75 at 300 Hz**.
- 📸 **3D photos of games:** one key saves the game's picture as a side-by-side JPG for 3D photo programs, VR viewers and StereoShutter Photos, in HDR too, or as a red-cyan anaglyph.
- 🧭 **Glasses setup:** a guided assistant, and a quick setup inside a paused game; the values are shared by every game folder.
- ⌨️ **While playing:** turn the 3D off and on, swap the eyes, change the HDR brightness and look, and the settings for each game, in panels with the mouse.
- 🚨 **Safety nets:** messages on the screen that say what to change, and an independent stop watcher that switches the emitter off even if the picture is stuck.

## StereoShutter Manager

**StereoShutter Manager 0.1.116** is supplied in its own ZIP alongside the standalone StereoShutter ZIP. It brings games, compatible fixes and glasses together, and downloads components when requested. Game fixes remain separate downloads. Use the workflow below or [Quick start](#quick-start) for manual installation.

- 🔎 **It finds your installed games** and shows which ones have a 3D fix: community **geo-11 fixes published on HelixMod**, with each author's instructions and credits, and **StereoShutter Engine fixes** for DirectX 12 games.
- 📦 **It installs, updates and removes a fix,** and keeps a copy of what it changes, so that the game can go back to how it was.
- 🕶️ **Glasses:** one general profile for every game, NVIDIA 3D Vision or Samsung SSG-5100GB (experimental), with the test bars and the calibration. A game can keep a profile of its own.
- 🖥️ **3D output of the Engine fixes:** shutter glasses through StereoShutter, native Leia SR, side-by-side and top-bottom for 3D TVs and projectors, anaglyph, interlaced, checkerboard and Katanga.
- 🎬 **Photos & video:** it downloads, updates and opens StereoShutter Player and StereoShutter Photos.
- 🔐 **Checked downloads:** what the Manager downloads is signed and checked before it is installed. HelixMod fixes come from their authors' own pages.
- 🆓 **No account for what is free:** free fixes, the glasses, the Player and Photos need no sign-in. Signing in is only for the early access of Ko-fi members to new Engine fixes, which are free for everyone a few days later.
- 🌍 **Seven languages:** English, Spanish, Italian, French, German, Portuguese and Russian.

**How to use Manager**

1. **Start it.** Extract the Manager's ZIP to a folder where you can write and run **StereoShutterManager.exe**. Windows 10 or 11, 64-bit. It looks for its own updates and asks before it restarts to apply one.
2. **Library.** It lists the installed games it has found (Steam, Epic, Ubisoft Connect, GOG, EA and other launchers) and shows which ones have a 3D fix. **Scan again** looks again after you install or move a game, **Add game** lets you choose a game's executable yourself, and **Search games** (Ctrl+F) filters the list.
3. **Install a fix.** Open the game (**View details**), read the author's instructions and press **Install fix**, with the game closed. For a geo-11 fix from HelixMod, choose **StereoShutter** as its output when the Manager asks. It keeps a copy of what it changes.
4. **Glasses.** **Glasses**, at the top, holds the general profile that every game uses: choose **NVIDIA 3D Vision 2** or **Samsung 3D (Bluetooth)**, save, and press **Test glasses** to adjust them with the two bars. A game that needs other values keeps its own: on its page, **Use own settings**; **Use general profile** goes back.
5. **Play.** **Play** starts the game once its fix is ready.
6. **Take a fix out.** On the game's page, **Uninstall fix**, with the game closed: the Manager puts back the files it kept. **Repair fix** restores a fix's damaged or missing files, and **Backup history** brings back earlier saved settings.
7. **Photos & video** downloads, updates and opens StereoShutter Player and StereoShutter Photos.

The Manager's full user guide and its privacy notes are included in its separate download (`docs\USER_GUIDE.md`, `PRIVACY.txt`). ⚠️ Read [Multiplayer and anti-cheat](#multiplayer-and-anti-cheat) before installing a fix.

## Games

A game needs a **3D fix** that supplies the left and right views. These fixes are distributed separately from this StereoShutter ZIP. Manager manages both kinds:

| | DirectX 11 games | DirectX 12 games |
|---|---|---|
| **The fix** | A community **geo-11** fix from [HelixMod](https://helixmod.blogspot.com/search/label/geo-11), the work of its author | A **StereoShutter Engine** fix, made game by game |
| **How it gets in** | Manager, or by hand as described below | A separate Engine fix, installed through Manager |
| **Glasses** | NVIDIA 3D Vision and Samsung SSG-5100GB (experimental), through StereoShutter | NVIDIA 3D Vision and Samsung SSG-5100GB (experimental), through StereoShutter; other 3D outputs without glasses software |

### DirectX 11: start with HelixMod

**The game's geo-11 fix comes first.** Find your exact game on [HelixMod's geo-11 pages](https://helixmod.blogspot.com/search/label/geo-11), download its fix and follow its installation instructions, including the required game version, DirectX/API mode and game settings. Check that the fix supports your version of the game before continuing.

The fix supplies the stereoscopic views. StereoShutter displays those views and synchronizes the glasses; **it does not supply the game fix or turn an arbitrary game into 3D**. The fix has to be made for geo-11: a 3Dmigoto fix made for 3D Vision does not work as it is. **64-bit and 32-bit games both work:** a 32-bit game uses the 32-bit geo-11 and fix, and StereoShutter's **StereoShutter_host32.dll** (the setup chooses it). After installing the fix, copy **the contents of the ZIP's StereoShutter folder** beside the game's executable and the installed fix, run **StereoShutter_geo-11_Setup.exe** there with the game closed, and then launch the game. Follow the [numbered connection steps](#4-connect-a-game) after setting up your glasses.

This setup by hand is for **DirectX 11 / geo-11**. **Player and Photos do not need HelixMod or geo-11 fixes**; they use your video and photo files.

### DirectX 12: StereoShutter Engine

**StereoShutter Engine** is the project's own engine for DirectX 12 games in **geometric 3D**: each eye is rendered from its own camera through the game's own rendering, not made from a depth map. Its fixes are made and tested game by game.

- **Ray tracing, DLSS Super Resolution and DLSS Frame Generation in both eyes,** where the game has them.
- **Separate game-fix releases.** Each fix includes the Engine version it needs. These packages are not included in this StereoShutter ZIP; Manager downloads and installs them separately.
- **The Witcher 3 (DirectX 12)** is the first supported Engine title. **Marvel’s Guardians of the Galaxy** is next, and **Star Wars Outlaws** is in development. Game-fix availability and updates are announced separately.
- **New fixes reach Ko-fi members (Beta and Priority) a few days early,** and are then free for everyone.
- **3D outputs:** shutter glasses through StereoShutter (NVIDIA 3D Vision, and Samsung SSG-5100GB (experimental)), native Leia SR, side-by-side and top-bottom (half or full) for 3D TVs and projectors, anaglyph, interlaced, checkerboard and Katanga.

## Multiplayer and anti-cheat

Prefer **single-player games that permit these modifications**. Single-player or offline mode alone does not guarantee that anti-cheat is absent or that a game's rules allow the integration. Compatibility and enforcement depend on the game and its publisher; StereoShutter cannot guarantee that an account is safe from sanctions.

**Turning 3D off or closing StereoShutter does not remove what is installed in the game's folder.** Before returning to protected online play, follow the removal steps for StereoShutter **and** for the game's 3D fix, and restore a clean game installation. Never bypass or disable anti-cheat protections.

Check the publisher's current rules and ask for explicit confirmation if support is unclear. For examples of game-specific restrictions, see [Valve's Trusted Mode guidance](https://help.steampowered.com/en/faqs/view/09A0-4879-4353-EF95) and [VAC information](https://help.steampowered.com/en/faqs/view/571A-97DA-70E9-FF74); these are not a compatibility approval for StereoShutter or for other games.

## Quick start

**Use the steps below with this download.** Manager offers glasses setup and fix installation from its own pages; it is not required for the manual geo-11 workflow.

### 1. Check the requirements

- Windows 10 or 11, 64-bit, an NVIDIA graphics card ([which one](#which-graphics-card)), NVIDIA 3D Vision glasses and their USB emitter. Some 3D Vision monitors have the emitter built in, and its signal comes through the video cable, not through USB. StereoShutter cannot use that emitter: with those monitors, the separate USB emitter is needed.
- NVIDIA's emitter USB driver installed: Device Manager shows **NVIDIA Stereoscopic 3D USB controller**. The driver is available from [NVIDIA](https://www.nvidia.com/en-us/drivers/nv3dvisionusb/390_41/nv3dvisionusb-dch-driver/) and is not part of the download.
- A compatible PC monitor that meets the [panel-response and strobing requirements](#monitors), with a supported [display mode](#display-modes) selected in Windows before starting.
- For games, install the game's **geo-11 fix from [HelixMod](https://helixmod.blogspot.com/search/label/geo-11) first**, following its instructions and required game version and DirectX/API mode. See [Games](#games). For films and photos, see the [Player](#stereoshutter-player) and [Photos](#stereoshutter-photos); no game fix is needed.
- **With Samsung SSG-5100GB glasses** the NVIDIA emitter and its driver are not needed: see [Samsung SSG-5100GB glasses](#samsung-ssg-5100gb-glasses).

Only one program should drive the emitter. Close other glasses software and VR sessions first.

### 2. NVIDIA and Windows settings

**Three settings.** StereoShutter checks them at the start and says on screen if something is missing.

1. **Hardware-accelerated GPU scheduling (HAGS): on or off.** Settings → System → Display → Graphics settings. Games' frame generation needs it on. With it on, the game in front goes first on the graphics card, so each time StereoShutter starts it asks Windows for **administrator rights for a small helper** of its own, which keeps StereoShutter in the graphics card's realtime class while it runs: **answer yes**. With no, StereoShutter runs all the same and its images may come late (flicker). `[Output] hags_realtime = no` never asks. After switching HAGS, restart Windows.
2. **Global Low Latency Mode: On or Off, never Ultra.** NVIDIA Control Panel → Manage 3D settings → Global Settings. Ultra in a single game's profile is fine.
3. **G-SYNC off on the glasses' monitor** (Fixed Refresh). 3D Vision monitors have no G-SYNC.

At every start StereoShutter keeps **its own NVIDIA profile, for StereoShutter.exe only** (no low latency for it, no FPS limit, its own vertical sync, maximum performance). **Global settings and game profiles stay as they are.** `[Output] nvidia_profile = no` turns this off.

In the game: vertical sync off. While playing, keep the game in front and close what keeps drawing: browsers, videos, chat programs, the game's launcher.

### 3. Download and set up the glasses

Download **StereoShutter-0.18.111.209.zip** from [Releases](https://github.com/murdavs/StereoShutter/releases/latest) and compare its SHA-256 with the one published there. The current programs are unsigned, so Windows may warn or block them; read the [digital-signature FAQ](#faq) before running them. Extract it to a folder where you can write. It has three folders:

| Folder | What it is |
|---|---|
| **StereoShutter** | StereoShutter for games, its tools, the manual and the user guide |
| **StereoShutter Player** | The 3D video player, with its own copy of StereoShutter |
| **StereoShutter Photos** | The 3D photo viewer, with its own copy of StereoShutter and three sample photos |

Set Windows to the refresh rate you will play at and run **StereoShutter_Setup.exe** in the StereoShutter folder. This adjusts NVIDIA 3D Vision glasses (for the Samsung ones see [Samsung SSG-5100GB glasses](#samsung-ssg-5100gb-glasses)); **StereoShutter_geo-11_Setup.exe** is the separate tool that connects each game in step 4.

| Step | What you see | What to do |
|---|---|---|
| Ghost | Crosstalk bars | Close one eye; use ← / → to adjust the phase. Your eye’s bar should be clear, while the other bar stays faint, not white. Check the other eye. |
| Eyes | A rectangle with depth | It should float in front of the screen. S swaps the eyes, then Enter. |
| Brightness | Crosstalk bars | ↑ opens the lenses longer; use ↓ if the other bar becomes too bright. Keep the other eye’s bar faint rather than trying to make it disappear completely. |
| Save | The values | Enter saves. |

It is done once for each monitor and refresh rate, and works for every game, the player and the viewer. 3D Vision monitors use NVIDIA's values in the modes of their table. On an HDR monitor the assistant offers **H** for the HDR output; then run it again with HDR.

### 4. Connect a game

⚠️ Read [Multiplayer and anti-cheat](#multiplayer-and-anti-cheat) first.

**DirectX 11 / geo-11 — follow this order:**

1. **Install the game's fix first.** Find and download its geo-11 fix from [HelixMod](https://helixmod.blogspot.com/search/label/geo-11). Follow the game's instructions, including its required game version, DirectX/API mode and settings. StereoShutter does not install this fix.
2. **Copy the contents, not the enclosing folder.** With the game closed, open the extracted ZIP's **StereoShutter** folder and copy its contents into the folder containing the actual game .exe and the installed HelixMod fix. **StereoShutter.exe and StereoShutter_geo-11_Setup.exe must sit beside the game's executable, not inside an extra StereoShutter subfolder.** Follow the fix's game-specific folder instructions; do not use the launcher's folder. Player and Photos stay separate. If updating an existing installation, back it up, keep that game's StereoShutter.ini (it holds its saved settings) and **replace StereoShutter_host.dll too** (StereoShutter_host32.dll in a 32-bit game): StereoShutter 0.18.111.209 works only with the host DLLs of its own download.
3. **Connect the installed fix.** Run **StereoShutter_geo-11_Setup.exe** from that same game folder. Read the changes it proposes and press Enter to apply them. This is the game-integration setup, not the glasses assistant.
4. **Launch the game and wait for the window to settle.** Games often change resolution or switch between windowed and fullscreen modes during startup. StereoShutter waits for those changes to finish: **3D activates automatically 5–10 seconds after the game window and resolution become stable**, not 5–10 seconds after launching the game. This delay avoids activating 3D during the startup display transitions.

The setup connects geo-11 with these settings:

~~~ini
; d3dx.ini
[System]
proxy_d3d11 = StereoShutter_host.dll   ; StereoShutter_host32.dll in a 32-bit game

; d3dxdm.ini
[Device]
direct_mode = katanga_vr
~~~

It also gets the fix ready: `full_screen = 0` and `create_profile = 0` where the fix sets something else (exclusive full screen hides the 3D, and fixes adapted from 3D Vision ones may write a 3D Vision profile), `[Host] geo11_load_redirect = yes` where geo-11's `load_library_redirect` is on, and, in two known versions of geo-11, a fix for a fault of its d3d11.dll that now and then closes the game when the 3D starts. It keeps a copy of every file it changes, asks for REPLACE before removing another chained DLL, and offers **UNDO** when run again. It does not install the game's 3D fix.

**StereoShutter_Play** starts StereoShutter by hand for an already configured game.

**A fix made for 3DMigoto Loader** (its instructions start the game with 3DMigoto Loader.exe, from a folder of its own): leave the fix as it is, copy StereoShutter's files into that folder and run the geo-11 setup there; it sets the folder up and says so. To play, open **StereoShutter_Play** first, then the game with 3DMigoto Loader. StereoShutter then shows geo-11's picture in a window of its own over the game, without the doorman: give the game its own FPS limit (60, or 90 with 90 cycles). If the folder holds neither the game nor the loader, the setup says where the files go and changes nothing.

### 5. The keys

| Keys | What they do |
|---|---|
| Ctrl+T | Turn the 3D off and on |
| Ctrl+Alt+S | Swap the eyes |
| Ctrl+Alt+K | The keys, then the settings for this game, then the quick setup (pause the game first) |
| Ctrl+Alt+Enter | Save the glasses' values, the HDR settings and the FPS counter for this game |
| Ctrl+Alt+← / → | The glasses' phase, 10 µs a press (with Shift, 100 µs) |
| Ctrl+Alt+↑ / ↓ | How long the lenses stay open, 10 µs a press (with Shift, 100 µs) |
| Ctrl+Alt+G | Lock the glasses again |
| Ctrl+Alt+Page Up / Page Down | HDR brightness |
| Alt+Shift+F10 | The HDR panel (while it is open: Ctrl+Alt+I / M the control, Ctrl+Alt+J / L its value, Ctrl+Alt+Backspace reset) |
| Ctrl+Alt+H | The game's picture read as Auto or HDR10, this session only |
| Ctrl+Alt+End | The bright-area limit on and off (with `hdr_bfi_limit = static` or `scene`) |
| Ctrl+Alt+Home | The bright-area limit's level: 100, 85, 70, 55 % |
| Ctrl+Alt+F | The FPS counter |
| Ctrl+Alt+P | A 3D photo of the game ([3D photos of games](#3d-photos-of-games)) |
| Ctrl+Alt+Shift+P | What the 3D photo saves (the photo menu) |
| Ctrl+Alt+R | The monitor's ELMB strobing off and on again, through DDC/CI (only with `[Monitor] relatch_elmb = yes`) |
| Ctrl+Alt+F9 | Mark a moment, while StereoShutter_Feedback records a session |
| Ctrl+Alt+F12 | Stop StereoShutter and switch the emitter off; the game goes on |

Keys without Alt, such as Ctrl+T, are taken only while the game or StereoShutter is in front, so other programs keep them. Every key can be changed in `[Keys]` of StereoShutter.ini.

## Samsung SSG-5100GB glasses

Support is experimental and limited to the glasses, adapter and monitor modes below. Results depend on the setup; NVIDIA 3D Vision support is unchanged.

StereoShutter also drives **Samsung SSG-5100GB** active 3D glasses, the ones made for Samsung's 3D TVs. They are Bluetooth glasses: there is no NVIDIA emitter, and NVIDIA 3D Vision glasses go on working as before.

**What it needs**

- **Samsung SSG-5100GB** glasses.
- A **TP-Link UB500** USB Bluetooth adapter with [TP-Link's official driver](https://www.tp-link.com/es/support/download/ub500/v3/) installed. While the 3D runs, the adapter works only for the glasses: its other Bluetooth connections come back when StereoShutter closes.
- An **OLED monitor at 240 Hz or 360 Hz**. Both give 60 cycles a second, that is, up to 60 images a second for each eye: at 240 Hz each eye gets an image and a black refresh, at 360 Hz the image twice and a black refresh, which is brighter.

**Setting them up with this download**

1. Connect the UB500 and install its driver. Keep the glasses close to the adapter, and the TV they were used with off.
2. Run `StereoShutter.exe --settings` in the StereoShutter folder. In its glasses window (in Spanish for now), choose **Gafas** → **Samsung 3D (Bluetooth)**, select **Pantalla** (the monitor), and confirm **La pantalla seleccionada es OLED** (the selected screen is an OLED).
3. Use **Guardar** (save) and **Probar gafas** (test glasses). Answer yes when Windows asks for administrator rights: StereoShutter prepares the adapter for the glasses and puts its driver back at the end.
4. Wait for the countdown on the screen, then press the button of the glasses briefly. The first time, or after the glasses were used with a TV, hold the button for about two seconds so that they join StereoShutter. Do not add them in Windows’ Bluetooth settings.
5. Close one eye, then the other: **Ctrl+Alt+← / →** adjusts the phase and **Ctrl+Alt+↑ / ↓** how long the lenses stay open (with Shift, ten times the step). Each eye’s own bar should be clear; the other bar should remain faint, not white. Do not try to make the faint bar disappear completely. **Ctrl+Alt+F12** ends the test. Keep the saved calibration for the monitor and display mode you will use.

The glasses window saves the choices in that folder’s StereoShutter.ini. They can also be written there by hand: `[Emitter] backend = bluetooth` and the `[Bluetooth]` section, as [the settings file](../StereoShutter.ini) explains.

**Manager integration:** its Glasses page manages a general profile shared by games, with the option for an individual game to keep its own values. The Manager is not needed for the setup above.

**In games**

- **StereoShutter Engine fixes** work with these glasses as with NVIDIA's.
- **Games with geo-11 need StereoShutter_host.dll 0.18.32 or later** next to StereoShutter.exe (StereoShutter_host32.dll in a 32-bit game), the ones of this download: they hand the game's picture to StereoShutter as complete pairs, which these glasses need.
- **Ctrl+Alt+K** in the game shows the keys, then the settings, then the two bars for a quick adjustment.

**Good to know**

- A longer open time is brighter, but lets more of the other eye's picture through. On some monitors a little of it remains and changes with the viewing angle.
- Only one StereoShutter at a time. If the adapter is left without its driver after an interruption, open StereoShutter's own glasses window (`StereoShutter.exe --settings`, in Spanish for now) and press **Recuperar USB** (recover USB).
- The adapter's firmware is taken from TP-Link's installed driver. It is not part of the download.
- Other Samsung models, other Bluetooth 3D glasses and other adapters are not supported.

## The tools

Each tool is a small program with its own icon, in the StereoShutter folder.

| Tool | What it does |
|---|---|
| <img src="icons/setup.png" width="40" alt=""><br>**StereoShutter_Setup** | The assistant to set up NVIDIA 3D Vision glasses. |
| <img src="icons/test.png" width="40" alt=""><br>**StereoShutter_Test** | The test pattern for ten minutes, with the setup keys and a report. |
| <img src="icons/play.png" width="40" alt=""><br>**StereoShutter_Play** | Starts StereoShutter by hand for a game. |
| <img src="icons/geo11-setup.png" width="40" alt=""><br>**StereoShutter_geo-11_Setup** | Connects StereoShutter to geo-11 in a game's folder and gets the fix ready, or undoes it. |
| <img src="icons/undo-lightboost.png" width="40" alt=""><br>**StereoShutter_Undo_LightBoost** | Puts a monitor's previous signal back if LightBoost was left on. |
| <img src="icons/surround-setup.png" width="40" alt=""><br>**StereoShutter_LightBoost_Surround_Setup** | Prepares LightBoost on an NVIDIA Surround grid, once. |
| <img src="icons/surround-undo.png" width="40" alt=""><br>**StereoShutter_LightBoost_Surround_Undo** | Removes it. |
| <img src="icons/feedback.png" width="40" alt=""><br>**StereoShutter_Feedback** | Records your next game session to [report a problem](#reporting-a-problem). |

## StereoShutter Player

<a href="player-menu.png"><img src="player-menu.png" alt="StereoShutter Player's menu: picture, sound and subtitles, and StereoShutter's HDR brightness and colour" width="100%"></a>

*The Player's menu, from its manual. "HDR brightness and colour" opens StereoShutter's HDR panel.*

**StereoShutter Player 1.0.4** is a separate video player that shows its pictures through StereoShutter. On an HDR monitor, **StereoShutter's HDR output makes SDR 3D films brighter through the glasses**. It starts StereoShutter by itself and closes it when it closes.

| Source | What it plays |
|---|---|
| Video files | Half or full **side-by-side (SBS)**, half or full **top/bottom (TAB / OU)**, and **2D**. The format comes from the file, its name or its size; the menu chooses another. |
| Blu-ray 3D | **Unencrypted ISO images and BDMV folders**, at **1920 × 1080 per eye**, with pause, seeking and sound tracks. |
| A window | A 3D video playing in a browser or another program, through window capture. Protected video shows black. |

Drag a video, an ISO image or a Blu-ray folder onto **StereoShutter_Player.exe**, or open it and choose. Right-click or **Enter** opens the menu; **Space** pauses, and after the end plays the video again; **O** opens another video; **W** shows a window; **Esc** closes. For a browser video, put it **full screen on another monitor**, then choose it with W.

- 🖼️ **Framing:** black bars found and left out, crop, proportions, fit, zoom, fill or stretch.
- 🕶️ **3D:** depth, swap eyes, one eye in both (to check). 2D videos stay 2D.
- 🔊 **Sound:** volume, mute, sound track and delay.
- 💬 **Subtitles:** text and PGS tracks of Matroska files, and SRT, ASS or SSA files beside the film, at their own depth and size.
- 🌍 **Seven languages:** English, Spanish, Italian, French, German, Portuguese and Russian.

**It needs:** Windows 10 or 11, 64-bit, a DirectX 12 graphics card, the glasses set up, and **VLC media player 3, 64-bit**, installed separately for files and Blu-rays ([VideoLAN](https://www.videolan.org/vlc/); VLC is not included, VLC 4 is not supported). Window capture needs Windows 10 version 1903 or later. Its folder in the download includes StereoShutter 0.18.111.209 with settings for films.

**Not supported:** a film's own HDR (HDR films are shown as normal pictures, which StereoShutter's HDR output then brightens), encrypted Blu-rays, disc menus and disc subtitles, MVC 3D inside MKV files, subtitles of other containers and VobSub.

📖 [Player manual — English PDF](StereoShutter_Player_Manual_EN.pdf) · [Manual del reproductor — PDF en español](StereoShutter_Player_Manual_ES.pdf)

## StereoShutter Photos

**StereoShutter Photos 1.0.3** shows 3D photos through StereoShutter, as the Player shows films, with the same HDR output, menu and pointer in front of the screen.

- 📷 **Formats:** photos of 3D cameras (**MPO**), **JPS** and **PNS** files, side-by-side and top/bottom pictures (named by a 3D tag, or found by comparing their halves) and 2D photos. Keys 1–4 and 0 choose another format.
- 🗂️ **A whole folder:** the arrow keys, Home and End, or a slideshow; the next photo is read ahead.
- 🔍 **Zoom and depth:** the mouse wheel zooms in around the pointer, a large photo is dragged with the mouse, and the depth of the whole photo moves forward or back.
- 🪟 **Full screen or in a window** (F, F11, Alt+Enter or a double click). Full screen is the safe choice for the glasses.
- 🎨 **Colours:** EXIF orientation, and colour profiles (Display P3, Adobe RGB) made sRGB.

Drag a photo or a folder onto **StereoShutter_Photos.exe**. Three sample photos come in its **Samples** folder. Photos are read by Windows itself: HEIC, WebP and AVIF need their Windows image extensions.

📖 [Photos manual — English PDF](StereoShutter_Photos_Manual_EN.pdf) · [Manual de Photos — PDF en español](StereoShutter_Photos_Manual_ES.pdf)

## 3D photos of games

**Ctrl+Alt+P** takes a 3D photo of the game at once, from the game's own picture: without StereoShutter's texts or the FPS counter, and with the game's light, not the extra brightness for the glasses. The photos go to **Pictures\StereoShutter**, named after the game, the date and the time. **Ctrl+Alt+Shift+P** opens the settings for this game at what the photo saves; several can be ticked, and they all come from the same moment.

| Photo | File | For |
|---|---|---|
| **SBS 3D** (ticked as standard) | 3840×1080 JPG: both eyes side by side, 1920×1080 each, the left eye on the left | 3D photo programs that read full side-by-side, VR viewers, [StereoShutter Photos](#stereoshutter-photos) |
| **SBS 3D HDR** | 3840×1080 JPEG XR with the game's HDR light | HDR screens, with an HDR image viewer (the format of Windows' HDR screenshots). Games with HDR only; in others the JPG is saved instead |
| **Red-cyan anaglyph** | 1920×1080 JPG with Dubois' colours | Red-cyan glasses: the colours kept best, the least ghost image |

Each eye fits whole into its 1920×1080 without being stretched: a 21:9 game gets black bars above and below, a 4:3 game at the sides. `[Photo] folder` in StereoShutter.ini changes the folder. If Windows' **Controlled folder access** is on, it may not let StereoShutter write into Pictures: allow StereoShutter.exe in Windows Security, or choose another folder.

## Monitors

**For the cleanest 3D, choose an OLED at 240 / 360 Hz or an NVIDIA 3D Vision monitor with LightBoost.** Refresh rate alone is not enough: the panel must complete its pixel transitions while the other eye is hidden.

The matrix separates **practical tests** from **expected results**. Cells marked **tested** report an observed result; all other assessments are expectations based on panel response, not confirmation that every model works equally well. For the supported refresh-rate ranges and presentation sequences, see [Display modes](#display-modes). The same panel classes apply at 300 Hz (75 cycles a second) and at 371–555 Hz (each eye's image twice, then black), which have not been tried on a real monitor yet.

| Windows refresh rate and display mode | Stereo cycles/s | OLED: <0.1 ms | Fast LCD: ≈1 ms | LCD: 2–4 ms | Slow LCD: >4 ms |
|---|---|---|---|---|---|
| **360 Hz · black refreshes between eyes** | **60** as supplied; **90** optional | ✅ Clean **(tested)** | ⚠️ Mild ghosting | ⚠️ Visible ghosting | ❌ Heavy ghosting |
| **240 Hz · black refreshes between eyes** | **60** | ✅ Clean | ✅ Clean | ⚠️ Visible ghosting | ❌ Heavy ghosting |
| **100–185 Hz · monitor strobing enabled** (e.g. ULMB / ELMB / DyAc) | Half the refresh rate | ✅ Clean **(tested at 180 Hz)** | ✅ Clean | ⚠️ Depends on strobing | ⚠️ Depends on strobing |
| **100–185 Hz · no monitor strobing** | Half the refresh rate | ❌ Heavy ghosting **(tested)** | ❌ Heavy ghosting | ❌ Heavy ghosting | ❌ Heavy ghosting |
| **NVIDIA 3D Vision · LightBoost**, in a recognized mode | Half the refresh rate | — | ✅ Clean **(tested)** | — | — |

**Key:** ✅ Clean or nearly clean 3D. ⚠️ Works with ghosting; its extent depends on the panel and, where noted, the monitor's strobing. ❌ Not recommended because of heavy ghosting. A ❌ result describes picture quality; it does not mean that StereoShutter refuses to start at that refresh rate.

### Why panel response and strobing matter

At **360 Hz**, one black refresh lasts approximately **2.8 ms**; at **240 Hz**, approximately **4.2 ms**. There is one black refresh between the left and right eyes' images, giving the pixels time to complete their transition before the next eye opens. Slow transitions leave some of the previous eye's image visible as ghosting.

The response-time columns refer to **real pixel response**, preferably measured independently. An advertised **“1 ms” grey-to-grey** figure, often obtained with aggressive overdrive, does not establish how quickly the panel completes a transition to full black and back. Those transitions can take longer.

At **100–185 Hz**, StereoShutter presents one refresh per eye without inserting the black refresh used at higher rates. The monitor's **own strobing must be enabled** for the clean results in the strobing row; the no-strobing row shows why even a fast OLED can produce heavy ghosting in that mode. NVIDIA 3D Vision monitors use **LightBoost**, with NVIDIA's timing in recognized modes.

### Display modes

**StereoShutter chooses the presentation mode from the monitor and the refresh rate selected in Windows. It never changes the refresh rate.** Select the required Windows mode before starting. The table is for NVIDIA 3D Vision glasses.

| Mode | Windows refresh rate | Presentation | Stereo cycles/s | Practical testing |
|---|---|---|---|---|
| **NVIDIA 3D Vision** | Only **refresh-rate and resolution combinations listed in NVIDIA's timing table**, for example 120 or 144 Hz | One refresh per eye, with **LightBoost** | **Half** the refresh rate: 120 Hz → **60** | **Tested at 120 Hz**, including **NVIDIA Surround** |
| **One refresh per eye** | **99–185 Hz**, including 100, 120, 144, 165 and 180 Hz | The monitor's own strobing, such as **ULMB / ELMB**, separates the eyes; without it, ghosting remains | **Half** the refresh rate: 144 Hz → **72**; 180 Hz → **90** | **Tested at 180 Hz on OLED with its own strobing** |
| **NVIDIA 3D Vision outside its table** | **198 Hz or more**, at a refresh rate NVIDIA's table does not have (for example 240 Hz) | Black refreshes, as on other monitors, **without LightBoost** | As on other monitors: 240 Hz → **60** | Not yet tried |
| **Two refreshes per eye** | **198–370 Hz**, including 200, 240, 280, 300 and 360 Hz | **Image · Black** for each eye | **One quarter** of the refresh rate: 240 Hz → **60**; 300 Hz → **75**; 360 Hz → **90** | **Tested at 360 Hz on OLED** |
| **Three refreshes per eye — default at 360–370 Hz** | **360–370 Hz** | **Image · Image · Black** for each eye | **One sixth** of the refresh rate: 360 Hz → **60** | **Tested at 360 Hz on OLED** |
| **Three refreshes per eye — always at 371–555 Hz** | **371–555 Hz**, including 380, 480 and 540 Hz | **Image · Image · Black** for each eye | **One sixth** of the refresh rate: 380 Hz → **63**; 480 Hz → **80**; 540 Hz → **90** | Not yet tried |
| **Unsupported refresh rates** | **Below 99 Hz, 186–197 Hz or above 555 Hz** | The glasses do not start | — | — |

At **360–370 Hz**, three refreshes per eye are the default; below 360 Hz StereoShutter uses two (300 Hz → 75 cycles). To choose two at 360 Hz, open **Per-game settings → Glasses cycles**, or set `refreshes_per_eye = 2` in the `[BFI]` section of StereoShutter.ini. The [360 Hz comparison below](#360-hz-60-or-90-cycles) shows both sequences and their trade-off.

**With Samsung SSG-5100GB glasses** the modes are an OLED monitor at **240 Hz** (two refreshes per eye) or **360 Hz** (three), both at 60 cycles a second: see [Samsung SSG-5100GB glasses](#samsung-ssg-5100gb-glasses).

**Other refresh rates within the supported ranges work by design, but have not been tested on a real monitor.** The tested entries above identify the practical observations; they are not a test of every rate or monitor in a range.

Timing support does not guarantee clean 3D. Use the [monitor compatibility matrix](#monitors) to assess panel response and strobing. NVIDIA Surround requires the dedicated [LightBoost setup](#lightboost-in-nvidia-surround).

Use a **PC monitor** at the actual selected refresh rate and resolution; televisions are not supported. A monitor's maximum advertised refresh rate does not validate every mode or guarantee low ghosting. **371–555 Hz, 480 Hz included, work by design but have not been tried on a real monitor yet.**

The setup balances lens-open time against ghosting: **a shorter opening reduces ghosting but makes the picture darker**. Calibrate each monitor and refresh rate, then choose the balance that works for your display.

### 360 Hz: 60 or 90 cycles

| Mode | Repeating sequence | Glasses | What it gives |
|---|---|---|---|
| **60 cycles/s** (as supplied) | Left · Left · Black · Right · Right · Black | **120 Hz** | The steadier: each eye's image shown longer, and 60 frames a second are enough for the game |
| **90 cycles/s** | Left · Black · Right · Black | **180 Hz** | Smoother motion when the game keeps 90 frames a second |

The monitor stays at **360 Hz** in both. Choose it for each game in the settings panel (Ctrl+Alt+K twice → Glasses cycles), save, and start again, or for every game with `refreshes_per_eye = 2` in the `[BFI]` section of StereoShutter.ini; the glasses' values are saved apart for each. Some people notice a slight flicker at 60 cycles.

### Which graphics card

In 3D the game draws each frame for both eyes, so it asks more of the graphics card than in 2D. The recommended card for high settings in most games with 3D:

| Monitor | 60 cycles a second | 90 cycles a second |
|---|---|---|
| 1920×1080 (3D Vision monitors too) | RTX 3070, 4060 Ti, 5060 or better | RTX 4070 Super, 5070 or better |
| 2560×1440 | RTX 3080 Ti, 4070 Super, 5070 or better | RTX 4090, 5080 or better |
| 3440×1440 | RTX 4070 Ti Super, 5070 Ti or better | RTX 4090\*, 5090 |
| 3840×2160 | RTX 4090, 5090 | — |

- 60 cycles: compatible monitors at 120, 240 and 360 Hz (as supplied). 90 cycles: at 180 Hz, or at 360 Hz when chosen. At 144, 165, 300 and 480 Hz (72, 82.5, 75 and 80 cycles), in between. At 100–185 Hz, follow the [strobing and panel guidance](#monitors); refresh rate alone does not ensure a clean picture.
- A somewhat smaller card also works with lower settings; the newest, heaviest games can need more. At 3840×2160, no card gives 90 cycles with room to spare.
- \* With the RTX 4090, most games hold 90; some dip in their heaviest scenes.
- Tested with an RTX 4090; the other cards are estimated from published benchmarks. Films and photos need much less.

### How black frames help

The monitor draws each image from top to bottom. While it does, part of the previous eye's image can still be on screen. A black refresh between the eyes gives the glasses a dark moment to switch.

<img src="black-frames.png" alt="Black-frame sequence: left image, black, right image, black" width="100%">

The setup balances how long each lens stays open against crosstalk. On 3D Vision monitors, LightBoost strobes the backlight in step with the glasses.

### LightBoost in NVIDIA Surround

<img src="icons/surround-setup.png" width="80" align="right" alt="">

Set up NVIDIA Surround at a resolution and refresh rate of the monitors' NVIDIA table, usually 120 or 144 Hz. Save your work and close games, then run **StereoShutter_LightBoost_Surround_Setup**: it explains the operation and waits for **YES**. It separates the grid for a moment, saves each monitor's timing, puts the grid back and checks it. With `[Monitor] lightboost_surround = auto`, the timing is used while playing and the previous signal is put back at the end. **StereoShutter_LightBoost_Surround_Undo** removes it.

These tools change the display configuration through NVIDIA's driver: the screen can go black for a moment, and a failed change can hang or restart the computer.

## Game pacing and automatic stability

**The doorman:** StereoShutter asks the game's layer, or its host DLL with geo-11, for one game frame per cycle of the glasses, in step with them. With the supplied settings it lets one frame per cycle through while the game keeps up, one every two cycles when it keeps up with half of them, and steps aside when it cannot even do that. A late frame is never held back. Without the host DLL, give the game its own FPS limit to match the selected stereo cycle rate (for example, 60; or 90 at 360 Hz with 90 cycles).

The supplied `StereoShutter.ini` has the automatic modes on:

| Setting | What it does |
|---|---|
| `[Output] queue = auto` | Starts with 3 images prepared ahead and adds one each time the graphics card does not have StereoShutter's images in time (up to 6), on the same picture: the 3D goes on. It says so on screen and remembers it for that game; after 10 minutes of calm play at a raised level, that game's next start is one level lower. |
| `[Output] gpu_priority_absolute = auto` | StereoShutter's images at the priority of the game in front, and above it only while one is about to be late. |
| `[Output] engine = auto` | For a game that fills the graphics card and makes very few frames a second, or whose hitches hold the graphics card: StereoShutter keeps a part of the graphics card for its images for the rest of the session and says so; once that has held for 2 minutes, it remembers it for that game. This helps reduce flicker; the game remains slow. |
| `[Output] present_hold = auto` | With three refreshes per eye (image, image, black): each eye image is presented once for its two refreshes, and the black comes from a buffer that already holds it. Fewer GPU jobs for StereoShutter’s presentation, with the same output on screen; this is not a threefold reduction in the game’s rendering cost. |

After a hitch of the whole computer, or while another window comes in front or goes, StereoShutter shows neutral images for a moment (the left eye's picture in both eyes, or black) instead of letting an image reach the other eye, and the 3D comes back by itself. With hardware-accelerated GPU scheduling, its images go first on the graphics card through the realtime class ([step 2](#2-nvidia-and-windows-settings)).

More margin adds a little latency; the automatic modes take it only when needed. They cannot make up for a graphics card that is completely overloaded: lower the game's graphics (in 3D it draws everything twice) or give it an FPS limit.

## HDR input and output

| Setting | Meaning |
|---|---|
| `[Output] hdr = yes` | StereoShutter's HDR output on an HDR monitor: brighter pictures through the glasses. Windows HDR is switched on for the session if it was off. |
| `[Input] picture = auto` | What the game's picture is, from its colour space and format. |
| `[Input] picture = sdr / hdr10 / scrgb` | Set by hand, only when the colours come out wrong. |

HDR output makes an SDR game brighter through the glasses; it does not give it the detail of a real HDR picture. A game's own HDR is shown as HDR when the game and its 3D layer hand it over. **Ctrl+Alt+H** reads the game's picture as Auto or HDR10 for the session, for a game that sends HDR10 without saying so.

With HDR output on, **Alt+Shift+F10** opens the HDR panel: brightness, exposure, midtones, contrast, shadows, saturation, highlights, the gain of each colour, paper white and peak, with the mouse or the keys. **Ctrl+Alt+Enter** saves; separate profiles keep the look for SDR games and for games in HDR.

<details>
<summary>🖼️ The HDR panel — both pages</summary>

<img src="hdr-panel-page1.png" alt="HDR panel page 1: brightness, exposure, midtones, contrast, shadows, saturation and SDR gamma" width="100%">

<img src="hdr-panel-page2.png" alt="HDR panel page 2: highlight compression, highlights, colour gains, paper white and peak" width="100%">

Pause the game before adjusting. SDR gamma does not apply to a game's own HDR. Reset puts the selected control back; Save keeps the current profile.

</details>

**Bright-area limit (OLED, HDR output with the black refresh):** a large very bright area (sky, sand, snow), lit and black at every eye, can make an OLED's own brightness limiter flicker, even without the glasses. `[Output] hdr_bfi_limit = scene` lowers only the bright part of each stereo pair, as much as that pair needs to keep its mean light at the monitor's full-screen luminance; darker parts never change, pictures already below it are untouched, and both eyes get the same. `static` lowers the bright part by a fixed gain. Off as standard; **Ctrl+Alt+End** turns it on and off and **Ctrl+Alt+Home** steps its level, for the session.

StereoShutter switches Windows HDR on before the game makes its picture, and puts the previous state back at the end. Started after a geo-11 game is already running, it does not switch it.

### Fullscreen

In geo-11 games, the geo-11 setup turns geo-11's own exclusive full screen off in the fix: it hides StereoShutter's picture. Some games turn their own HDR on only in Fullscreen: `[Host] fullscreen_compat = yes` gives them a borderless window over the monitor instead (64-bit games only).

## Reporting a problem

**StereoShutter_Feedback** prepares one file with what is needed to find the cause of a problem:

1. Open **StereoShutter_Feedback** (next to StereoShutter.exe, in the game's folder), press **Record the next game session** and then **OK, close this window**.
2. Start the game as usual and play until the problem shows. The screen says that the session is being recorded.
3. When you see the problem, press **Ctrl+Alt+F9**: that moment is marked and its detail kept. You can mark more than one.
4. Close the game. A window opens with the ZIP file ready, **at most 5 MB**: send it by e-mail to **info@stereoshutter.com**, saying what you saw and when.

If the game did not open, or its 3D did not start, open StereoShutter_Feedback again and press **The 3D did not start: prepare the file**. If your e-mail program answers that the e-mail was cancelled, the window says so and shows the file in its folder, to attach it from your usual e-mail.

It records only that session, and sends nothing by itself. Review the ZIP before sending it; use e-mail for full diagnostic reports, not a public issue or shared Discord channel. The manual lists what the file holds.

## FAQ

**Do I need StereoShutter Manager?**
No. Manual installation in a game with a geo-11 fix, Player and Photos work independently. Manager is supplied in a separate ZIP and brings these operations and Engine fix installation into one window. It is not included in this ZIP.

**Do I need an account or a subscription?**
No. This StereoShutter download, Player, Photos and HelixMod’s geo-11 fixes are free and need no sign-in. Public Engine fixes are also free; their releases are separate from this ZIP. Manager uses sign-in only for Ko-fi Beta and Priority early access to new Engine fixes, which become free for everyone a few days later.

**Are the downloads digitally signed?**
No. Current downloads are unsigned. Download from this repository's Releases and compare the published SHA-256. ZIP Properties → Unblock does not sign the files or guarantee that Windows or antivirus warnings disappear. If a download is blocked, review the warning and verify the source; do not disable protections just to run it.

**Does StereoShutter make any game stereoscopic?**
No: the game needs a 3D fix that supplies left and right views, a geo-11 fix in DirectX 11 games or a StereoShutter Engine fix in DirectX 12 games. StereoShutter shows them and drives the glasses. The Player and Photos likewise need 3D sources; they do not turn 2D into 3D.

**The depth looks reversed.**
Ctrl+Alt+S, then Ctrl+Alt+Enter to save. Over a game and with HDR the values are saved apart from the test pattern's.

**The picture flickers or shows the other eye for a moment.**
Check the [three settings](#2-nvidia-and-windows-settings), keep the game in front, close the game's launcher and programs that draw (browsers, videos), and follow the messages on the screen. **Do not change global V-Sync or add a global FPS limit for StereoShutter.** If it goes on, [report it](#reporting-a-problem).

**Windows asks for administrator rights each time StereoShutter starts.**
That is hardware-accelerated GPU scheduling (HAGS) on: StereoShutter's helper keeps it in the graphics card's realtime class while it runs, so that its images are not held behind the game's frames. Answer yes. Not to be asked: turn HAGS off (Windows Settings → System → Display → Graphics settings, then restart Windows), or write `[Output] hags_realtime = no` (with HAGS on, the glasses may then flicker).

**After updating, the 3D does not start in a game.**
Replace StereoShutter_host.dll in that game's folder too (StereoShutter_host32.dll in a 32-bit game) with the one of the same download: StereoShutter does not connect to the host DLL of an older version.

**A large bright sky or sand flickers on my OLED, even without the glasses.**
With HDR output and the black refresh between the eyes, try `[Output] hdr_bfi_limit = scene` in that game's StereoShutter.ini ([HDR](#hdr-input-and-output)). Turning off the monitor's dynamic brightness boost helps too.

**The program calls itself "0.18.111 V2 Samsung RC9".**
That is this version, StereoShutter 0.18.111.209: the name inside the program is the one of the build that added the Samsung glasses.

**The Samsung glasses do not start.**
Check that the TP-Link UB500 is connected with TP-Link's own driver, that no other StereoShutter is running, that the monitor is an OLED at 240 or 360 Hz, and that the glasses are on and close to the adapter: a short press of their button once the picture is ready, about two seconds the first time. In a geo-11 game, StereoShutter_host.dll must be the 0.18.32 of this download. If the adapter is left without its driver, open `StereoShutter.exe --settings` and press **Recuperar USB** (recover USB).

**Can I use other Bluetooth 3D glasses, or another adapter?**
Not for now: the experimental support is for Samsung SSG-5100GB glasses with a TP-Link UB500 adapter.

**A game closes with the host DLL.**
Try `[Host] pace_hook = no` in its StereoShutter.ini and give the game its own FPS limit.

**How do I stop or remove it?**
Ctrl+Alt+F12 stops StereoShutter without closing the game. For this manual installation, undo the Surround timings if you prepared them, run the geo-11 setup and choose UNDO, then delete StereoShutter’s files from the game’s folder. Manager provides uninstall and backup restoration for fixes it installs. StereoShutter leaves nothing running after it closes.

**Is it open source?**
No. StereoShutter, the Manager, the Player and Photos are free of charge under the licences included in each program's folder; the source code is not published. See the [StereoShutter licence](../StereoShutter_LICENSE.txt) for StereoShutter's terms. Keep each program's licence and its applicable third-party notices with any copies permitted by that licence. The notices for [StereoShutter](../StereoShutter_THIRD_PARTY.txt) and [Player](../StereoShutter_Player_THIRD_PARTY.txt) are also available here.

## Acknowledgements

Thank you to the developers and communities whose work supports StereoShutter and stereoscopic 3D:

- **The [HelixMod community](https://helixmod.blogspot.com/search/label/geo-11)**, for the game fixes and instructions that make the games setup possible; **[geo-11 by davegl1234](https://helixmod.blogspot.com/2022/06/announcing-new-geo-11-3d-driver.html)** and the **3Dmigoto community**, whose work provides geo-11's hooking and shader foundation. These are external game integrations, installed separately.
- **MinHook by Tsuda Kageyu**, including **HDE32/HDE64 by Vyacheslav Patkov**, used in StereoShutter's host DLL.
- **[edge264](https://github.com/tvlabs/edge264) by Thibault Raffaillac**, with copyright held by Celticom / TVLabs and Thibault Raffaillac, built into StereoShutter Player for H.264/MVC decoding.
- **[VideoLAN](https://www.videolan.org)**, for VLC and libvlc, which Player uses from a separate VLC installation.
- **[NVIDIA's NVAPI SDK](https://github.com/NVIDIA/nvapi)**, for the API declarations used with the installed NVIDIA driver, and NVIDIA's 3D Vision timing data, read from the USB emitter driver's registry entries.
- **3DVisionActivator**, **libnvstusb**, **nv3d-vision-restoration**, **NVIDIA's CustomTiming sample** and **Kodi's pull request 26096**, for technical references used to understand the emitter, LightBoost and HDR. Their code is not included in StereoShutter.

See the third-party notices for [StereoShutter](../StereoShutter_THIRD_PARTY.txt) and [Player](../StereoShutter_Player_THIRD_PARTY.txt) for the exact use and applicable licences. These acknowledgements do not imply affiliation, sponsorship or endorsement.

## Documentation and licence

| | English | Español |
|---|---|---|
| **StereoShutter 0.18.111.209** | [Manual (PDF)](StereoShutter_Manual_EN.pdf) | [Manual (PDF)](StereoShutter_Manual_ES.pdf) |
| **StereoShutter Player 1.0.4** | [Manual (PDF)](StereoShutter_Player_Manual_EN.pdf) | [Manual (PDF)](StereoShutter_Player_Manual_ES.pdf) |
| **StereoShutter Photos 1.0.3** | [Manual (PDF)](StereoShutter_Photos_Manual_EN.pdf) | [Manual (PDF)](StereoShutter_Photos_Manual_ES.pdf) |
| **StereoShutter Manager** (separate download) | [How to use it](#stereoshutter-manager) · full user guide in its download (`docs\USER_GUIDE.md`) | Capítulo 14 del manual de StereoShutter · guía completa (en inglés) en su descarga |

[What's new](../WHATS_NEW.md) · [User guide (text)](../StereoShutter_README.txt) · [The settings file](../StereoShutter.ini) · [Release notes](../RELEASE_NOTES.md) · [Changes](../CHANGELOG.md)

Copyright (C) 2026 murdavs. All rights reserved. StereoShutter is not made, supported or endorsed by NVIDIA, Samsung, TP-Link or the makers of the games. NVIDIA, 3D Vision, LightBoost and DLSS are trademarks of NVIDIA Corporation; Samsung, TP-Link, Leia and the names of the games are trademarks of their owners.

The programs are provided without warranty under the included licences. Brightness and HDR output can increase display wear: keep the monitor's care features on and do not leave a bright still picture running.

---

[🌐 Official website](https://www.stereoshutter.com) · <a href="https://discord.gg/J6dgWXhAPy"><img src="https://raw.githubusercontent.com/murdavs/StereoShutter/main/docs/icons/discord.svg" height="18" alt=""> Discord</a> · <a href="https://ko-fi.com/stereoshutter"><img src="https://raw.githubusercontent.com/murdavs/StereoShutter/main/docs/icons/kofi.png" height="18" alt=""> Ko-fi</a>
