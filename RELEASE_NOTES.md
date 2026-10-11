# StereoShutter 0.18.83

🕶️ **Bring legacy NVIDIA 3D Vision glasses back to life on modern NVIDIA systems: 3D games, 3D films and 3D photos.** One download with three programs:

| Folder | Program |
|---|---|
| **StereoShutter** | **StereoShutter 0.18.83**, for games, with its tools: the glasses setup assistant, the pattern test, the geo-11 setup, the LightBoost tools and **StereoShutter_Feedback** to report a problem. |
| **StereoShutter Player** | **StereoShutter Player 1.0.2**, the 3D video player: SBS and top/bottom videos, unencrypted Blu-ray 3D and browser video. |
| **StereoShutter Photos** | **StereoShutter Photos 1.0.2**, the 3D photo viewer: 3D camera photos (MPO), JPS, side-by-side pictures, with three sample photos. |

Each one comes with its **illustrated manual in English and Spanish** (PDF).

## Highlights

- ☀️ **OLED at 240 / 360 Hz** with a black refresh between the eyes: 60 or 90 cycles a second at 360 Hz, 60 at 240 Hz. **HDR output** makes the picture brighter through the glasses; games in HDR are shown in HDR.
- 💡 **3D Vision monitors with LightBoost**, also three of them in **NVIDIA Surround**, with NVIDIA's own timing values.
- 🎮 **Games:** DirectX 11 through geo-11, connected and made ready by **StereoShutter_geo-11_Setup** (with undo); DirectX 12 through the SLT12 Output layer, which has not been publicly released yet.
- 🎯 **Stability that adapts by itself:** more output margin when the graphics card is late (remembered for each game), StereoShutter's GPU priority raised only when its images are about to be late, and, for a game that fills the graphics card, a part of it kept for StereoShutter's images. The game's frames are paced to the glasses.
- 🩺 **Reporting a problem:** StereoShutter_Feedback records one game session into a single file of **at most 5 MB**, ready to send by e-mail.
- 🎬 **StereoShutter Player** and 📷 **StereoShutter Photos** show films and photos through the same glasses, with StereoShutter's HDR output, a 3D menu with the mouse and seven languages.

## Included in this first public release

StereoShutter 0.18.83 includes the following applications, tools and capabilities:

- **StereoShutter Photos 1.0.2**, the 3D photo viewer, and **StereoShutter Player 1.0.2**, with error handling for damaged media and subtitle pictures. Blu-ray 3D playback starts at the film, not a looping menu background; the timeline, seeking and external subtitles follow the 3D picture's playback position.
- **The manual**: StereoShutter's own illustrated manual, in English and Spanish, with the troubleshooting tips found while testing games.
- **StereoShutter_Feedback 0.18.77**: records one game session in a ZIP of at most 5 MB, with Windows 10-compatible report dialogs. Choose to record the next session, confirm **OK, close this window**, then play. Ctrl+Alt+F9 marks a problem; after closing the game, review and e-mail the report yourself. Nothing is sent automatically.
- **The supplied settings** turn the automatic modes on: `queue = auto`, `gpu_priority_absolute = auto` and `engine = auto`, which reserves GPU capacity for StereoShutter's output under heavy game load to reduce flicker. This does not guarantee flicker-free output on every setup. At 360 Hz they give 60 cycles a second, the steadier (`refreshes_per_eye = 3`; 2 gives 90). Reports are off; `StereoShutter_Feedback` records one session when needed.
- **Starting over a game**: StereoShutter waits for the game's picture (black until it comes) and for the window the game really draws in, and follows it when the game makes a new one.
- **The geo-11 setup** also turns off exclusive full screen and the 3D Vision profile of fixes made for 3D Vision, sets what some games need for geo-11's library loading, and fixes a fault of two known geo-11 versions that now and then closed the game when the 3D started.
- **StereoShutter_host.dll 0.18.29** hooks the game's colour space call the way it hooks Present, so it works alongside overlays that hook the same call (a game's own HDR through geo-11).
- **The keys**: a key without Alt (Ctrl+T) is taken only while the game or StereoShutter is in front. Messages say when a value is kept for that game's next starts.
- **StereoShutter_Play** is the manual game launcher, identified by its game-controller icon.

## Install

1. Download **StereoShutter-0.18.83.zip** and check its SHA-256 (below).
2. Extract the ZIP into a folder where you can write. The programs are unsigned: if Windows or an antivirus blocks a file, review the warning and verify its source. ZIP Properties → Unblock does not sign files or guarantee that warnings disappear; do not disable protections just to run them.
3. The three NVIDIA and Windows settings: hardware-accelerated GPU scheduling **off** (restart Windows), NVIDIA's global low latency mode **On or Off, never Ultra**, and **G-SYNC off** on the glasses' monitor.
4. Run **StereoShutter_Setup.exe** in the StereoShutter folder to adjust the glasses.
5. **For games, install the game's 3D fix first.** Find its compatible geo-11 fix on [HelixMod](https://helixmod.blogspot.com/search/label/geo-11), download it and follow that game's instructions.
6. With the game closed, copy **the contents of the ZIP's StereoShutter folder** beside the actual game .exe and the installed fix. Do not leave the files inside an extra StereoShutter subfolder or put them in the launcher's folder. Player and Photos stay separate.
7. Run **StereoShutter_geo-11_Setup.exe** from that game folder and apply its proposed changes. This connects the fix; it is not the glasses assistant.
8. **Launch the game and let its window settle.** Resolution and window-mode changes during startup are normal. StereoShutter activates 3D automatically **5–10 seconds after the window and resolution become stable**, not after launching the game, to avoid starting 3D during those transitions.

StereoShutter does not include game fixes or create stereoscopic views by itself. Player and Photos do not need game fixes. When updating an existing game installation, back it up and preserve its StereoShutter.ini.

The manual explains each step: `StereoShutter/StereoShutter_Manual_EN.pdf` (in Spanish: `StereoShutter_Manual_ES.pdf`).

## Before you install

> ⚠️ **Not recommended for online multiplayer or games protected by anti-cheat.** 3D layers and fixes get into the game (DLL files and hooks), and anti-cheat systems may block them or sanction the account. Closing StereoShutter does not remove what is installed in the game's folder.

- Needs Windows 10 or 11, 64-bit, an NVIDIA graphics card ([which one](https://github.com/murdavs/StereoShutter#which-graphics-card)), NVIDIA 3D Vision glasses and their USB emitter with NVIDIA's emitter driver (not included).
- Games need their own 3D fix or layer. The Player needs **VLC media player 3, 64-bit**, installed (not included; VLC 4 is not supported).
- The programs are not digitally signed.
- OLED monitors wear with brightness and time: keep the monitor's care features on and do not leave a bright still picture running.

## Files

`StereoShutter-0.18.83.zip` — SHA-256 `72ab865ac010c3f48a0187377daa0268fc71fb8723b2d5db457299bf056492c7`

Copyright (C) 2026 murdavs. All rights reserved. Free of charge under the licences in each folder. NVIDIA, 3D Vision and LightBoost are trademarks of NVIDIA Corporation; StereoShutter is not made, supported or endorsed by NVIDIA.

---

[🌐 Official website](https://www.stereoshutter.com) · <a href="https://discord.gg/J6dgWXhAPy"><img src="https://raw.githubusercontent.com/murdavs/StereoShutter/main/docs/icons/discord.svg" height="18" alt=""> Discord</a> · <a href="https://ko-fi.com/stereoshutter"><img src="https://raw.githubusercontent.com/murdavs/StereoShutter/main/docs/icons/kofi.png" height="18" alt=""> Ko-fi</a>
