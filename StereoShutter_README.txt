StereoShutter - User guide
StereoShutter 0.18.83, with StereoShutter Player 1.0.2 and StereoShutter Photos 1.0.2
NVIDIA 3D Vision shutter glasses on modern NVIDIA systems
Copyright (C) 2026 murdavs. All rights reserved.

StereoShutter shows the separate left and right images that a game's 3D fix or
layer supplies, and synchronizes NVIDIA 3D Vision glasses with the monitor.
High-refresh OLED and LCD monitors use a black refresh between the eyes.
Recognized 3D Vision monitors use NVIDIA's timing values and LightBoost.

The illustrated manual, with everything in this guide and more:
  StereoShutter_Manual_EN.pdf (in Spanish: StereoShutter_Manual_ES.pdf),
  next to this file.

IMPORTANT: MULTIPLAYER / ANTI-CHEAT RISK

  This setup is not recommended for online multiplayer or for games protected
  by anti-cheat. 3D layers and fixes get into the game (DLL files and hooks),
  and anti-cheat systems may block them or impose account sanctions,
  including permanent bans, even when used only for 3D.

  Prefer single-player games that permit these modifications. Single-player or
  offline mode alone does not guarantee that anti-cheat is absent or that the
  integration is allowed. Check the publisher's current rules; StereoShutter
  cannot guarantee protection from account sanctions.

  Turning 3D off or closing StereoShutter does not remove what is installed in
  the game's folder. Before protected online play, follow the removal steps for
  BOTH StereoShutter and the game's 3D fix, and restore a clean game
  installation. Never bypass or disable anti-cheat protections.

CONTENTS
  1. Requirements and the download
  2. NVIDIA and Windows settings
  3. Set up the glasses
  4. Connect a game
  5. Films and photos: StereoShutter Player and StereoShutter Photos
  6. Controls
  7. Cycles, pacing and stability
  8. HDR input and output
  9. Fullscreen compatibility
 10. LightBoost and NVIDIA Surround
 11. Settings and saved values
 12. Reporting a problem, and troubleshooting
 13. Exit, recovery and removal
 14. Display care and licence

1. REQUIREMENTS AND THE DOWNLOAD

  - Windows 10 or 11, 64-bit, and an NVIDIA graphics card (for games, see
    "Graphics card for games" below).
  - NVIDIA 3D Vision glasses and their USB emitter. Some 3D Vision monitors
    have the emitter built in, and its signal comes through the video cable,
    not through USB. StereoShutter cannot use that emitter: with those
    monitors, the separate USB emitter is needed.
  - NVIDIA's emitter USB driver. Device Manager should show "NVIDIA
    Stereoscopic 3D USB controller". NVIDIA's discontinued 3D Vision graphics
    driver is not needed.
  - A supported display mode, selected in Windows before starting.
  - For games, a 3D fix or layer that supplies both eye images.

  NVIDIA's emitter driver is not included: get it from NVIDIA. If its
  installer does not suit, extract its package and use Device Manager >
  Update driver > Browse my computer for drivers, with the extracted
  NV3DVisionUSB.Driver folder.

  The download has three folders:
    StereoShutter          this folder: StereoShutter for games, its tools,
                           this guide and the manual.
    StereoShutter Player   the 3D video player, with its own copy of
                           StereoShutter.exe and of StereoShutter.ini.
    StereoShutter Photos   the 3D photo viewer, the same way.
  Extract it to a folder where you can write. The programs are not signed.
  Download from the official GitHub Releases and compare the published
  SHA-256. If Windows or an antivirus blocks a file, review the warning and
  verify its source; do not disable protections just to run it. ZIP
  Properties > Unblock does not sign files or guarantee warnings disappear.

  Display modes:
    Other OLED/LCD monitors at 198-370 Hz:
      Two refreshes per eye: left image, black, right image, black.
      At 240 Hz that is 60 stereo cycles a second.
      At 297-370 Hz, as supplied, three refreshes per eye: each eye's image
      twice, then black. At 360 Hz that gives 60 cycles a second, the
      steadier; two refreshes per eye give 90. See section 7.
    Other monitors at 99-185 Hz:
      One refresh per eye. At 120 Hz that is 60 cycles a second. The panel's
      response and any strobing of its own (ELMB, ULMB) decide the crosstalk.
    Recognized NVIDIA 3D Vision monitors:
      A mode of NVIDIA's table, with its resolution and refresh rate.
      LightBoost uses the table's timing.
    Other refresh rates:
      "Unsupported display mode"; the glasses do not start.

  A supported refresh rate does not guarantee a given image quality: the
  panel, its scanout, its response time and the glasses' values all matter.
  Only one program should control the emitter at a time.

  Graphics card for games: in 3D the game draws each frame for both eyes, so
  it asks more of the graphics card than in 2D. Recommended for high
  settings in most games with 3D:
    Monitor     60 cycles a second             90 cycles a second
    1920x1080   RTX 3070, 4060 Ti, 5060        RTX 4070 Super, 5070
    2560x1440   RTX 3080 Ti, 4070 Super, 5070  RTX 4090, 5080
    3440x1440   RTX 4070 Ti Super, 5070 Ti     RTX 4090 (*), 5090
    3840x2160   RTX 4090, 5090                 -
  Or better. 1920x1080 includes 3D Vision monitors. 60 cycles: monitors at
  120, 240 and 360 Hz (as supplied). 90 cycles: at 180 Hz, or at 360 Hz when
  chosen. At 144 and 165 Hz (72 and 82 cycles), in between. A somewhat
  smaller card also works with lower settings; the newest, heaviest games
  can need more. At 3840x2160, no card gives 90 cycles with room to spare.
  (*) With the RTX 4090, most games hold 90; some dip in their heaviest
  scenes. Tested with an RTX 4090; the other cards are estimated from
  published benchmarks. Films and photos need much less.

2. NVIDIA AND WINDOWS SETTINGS

  Only three things are needed. StereoShutter checks them at the start and
  warns on screen if one is missing:

    1. Windows: hardware-accelerated GPU scheduling (HAGS) off. Settings >
       System > Display > Graphics settings, then restart Windows. With HAGS
       on, the glasses do not start; StereoShutter does not change it itself.
    2. NVIDIA Control Panel > Manage 3D settings > Global Settings: Low
       Latency Mode "On" or "Off", never "Ultra" globally. "Ultra" in a single
       game's profile is fine.
    3. NVIDIA: G-SYNC off on the glasses' monitor (Fixed Refresh). The glasses
       need a fixed refresh rate. A monitor without G-SYNC needs nothing.

  StereoShutter does the rest: at every start it keeps a small program profile
  in NVIDIA's driver for StereoShutter.exe only (no low latency for it, no FPS
  limit, its own vertical sync, maximum performance), so that the global
  settings do not get in its way. Global settings and game profiles are not
  changed. [Output] nvidia_profile = no turns this off.

  In the game: vertical sync off, and borderless full screen or windowed.

  While playing: keep the game in front (with another window in front,
  Windows composes the screen and the 3D can flicker). Close or minimize what
  keeps drawing (browsers, videos, chat or AI programs), the game's launcher
  and other windows left behind it, and programs that get into games
  (overlays, recorders, FPS counters). StereoShutter names the programs it
  sees using the graphics card.

3. SET UP THE GLASSES

  Set Windows to the refresh rate you will play at and run
  StereoShutter_Setup. It is done once for each monitor and refresh rate,
  and works for every game. 3D Vision monitors use NVIDIA's values; other
  monitors need the assistant.

  Ghost:
    Close one eye and use Left/Right until the faint bar disappears.
    Check the other eye.
  Eyes:
    The light rectangle should float in front of the screen. S swaps the
    eyes if it is behind; Enter goes on.
  Brightness:
    Up opens the lenses longer (more light); Down shortens it if the faint
    bar comes back.
  Save:
    Enter saves. L changes the language of the texts.

  The values are saved for the monitor, resolution, refresh rate and cycles,
  and apart for StereoShutter's own window, over a game, and each of them with
  HDR. If the depth is reversed in a game, Ctrl+Alt+S and Ctrl+Alt+Enter there.

  Quick setup in a game:
    Pause the game. Ctrl+Alt+K shows the keys; the next press opens "Settings
    for this game", and the next the quick setup. Ctrl+Alt+Left/Right moves
    the phase, Ctrl+Alt+Up/Down the open time. Ctrl+Alt+K goes back to the
    game; Ctrl+Alt+Enter saves.

  StereoShutter_Test runs the test pattern for ten minutes and writes a
  report.

4. CONNECT A GAME

  StereoShutter does not make a game 3D by itself. First install the game's
  compatible geo-11 fix from https://helixmod.blogspot.com/search/label/geo-11
  following that game's guide; the fix is not part of this download.

  Copy the CONTENTS of the extracted ZIP's StereoShutter folder beside the
  actual game's .exe and the installed fix. Do not leave those files inside
  an extra StereoShutter subfolder or use the launcher's folder. Player and
  Photos stay separate. Follow the fix's game-specific folder instructions.
  When updating, back up the existing installation and keep that game's
  StereoShutter.ini, which holds its saved settings.

  DirectX 11 with geo-11:
    1. Close the game.
    2. Copy the files next to the game's .exe and geo-11's d3d11.dll,
       d3dx.ini and d3dxdm.ini.
    3. Run StereoShutter_geo-11_Setup.exe from that folder. It says what it
       will change and waits for Enter. This connects the game;
       StereoShutter_Setup.exe is the separate glasses-adjustment assistant.
    4. Start the game as usual and wait for its window and resolution to
       settle. Games often change resolution or window mode during startup.
       StereoShutter activates 3D automatically 5-10 seconds AFTER the
       window and resolution become stable, not after launching the game.
       This delay avoids activating 3D during startup display transitions.

  What the setup changes:
    d3dx.ini, [System]:   proxy_d3d11 = StereoShutter_host.dll
    d3dxdm.ini, [Device]: direct_mode = katanga_vr
    and it gets the fix ready:
    - full_screen = 0 in d3dx.ini and d3dxdm.ini, where the fix sets another
      value (exclusive full screen hides StereoShutter's picture);
    - create_profile = 0 in d3dx.ini, where the fix sets another value (fixes
      made for 3D Vision write 3D Vision settings into the game's NVIDIA
      profile);
    - [Host] geo11_load_redirect = yes in StereoShutter.ini while geo-11's
      load_library_redirect is on (geo-11 turns it off once a DLL is chained
      after it, and some games need it);
    - in two known versions of geo-11, a fix of a fault of its d3d11.dll that
      now and then closes the game when the 3D starts.
  It keeps a copy of each file before changing it (....before-StereoShutter).
  If that would remove another DLL chained after geo-11, it asks for REPLACE.
  Run again, it offers UNDO, which puts everything back as it was. It does
  not install the game's 3D fix.

  StereoShutter_host.dll starts StereoShutter with the game, before the game
  makes its picture, so that Windows HDR is ready first. It puts StereoShutter's
  picture inside the game's window, tells StereoShutter when the game puts its
  picture in HDR, and paces the game's frames. It passes the game's calls to
  Windows unchanged. [Host] autostart = no turns the automatic start off.

  DirectX 12 / SLT12 Output:
    StereoShutter works with the SLT12 Output layer, including full screen.
    SLT12 Output has not been publicly released and is not part of this
    download. The layer starts StereoShutter by itself.

  Starting by hand:
    StereoShutter_Play waits up to 10 minutes for a game. Without the host
    DLL, StereoShutter shows geo-11's picture in a window of its own over the
    game's; there is then no pacing: give the game its own FPS limit.
    [Input] game_window names the game's window if another one is taken.
    For a geo-11 game that needs Windows HDR, start StereoShutter before the
    game: started after it, it does not switch Windows HDR on.

  Keep StereoShutter_host.dll under its name and connect it only through the
  setup. Do not use it to replace a game's own graphics proxy.

5. FILMS AND PHOTOS: STEREOSHUTTER PLAYER AND STEREOSHUTTER PHOTOS

  Two separate programs show films and photos through the same glasses, with
  StereoShutter's HDR output to make them brighter through the glasses. To
  StereoShutter each of them is a game: it starts StereoShutter by itself and
  closes it when it closes. Set up the glasses first (section 3): the values
  are shared.

  StereoShutter Player 1.0.2 (folder "StereoShutter Player"):
    Half or full side-by-side and top/bottom videos, 2D videos, unprotected
    Blu-ray 3D (an .iso image or a copied disc folder, 1920x1080 per eye),
    and the window of another program (a 3D video in a web browser). Drop a
    video on StereoShutter_Player.exe, or open it and choose. Right-click or
    Enter: the menu; Space: pause; Esc: close.
    It needs VLC media player 3, 64-bit, installed (videolan.org) for files
    and Blu-rays; VLC is not included and VLC 4 is not supported. Window
    capture needs Windows 10 version 1903 or later. HDR films are shown as
    normal pictures. Protected Blu-rays, disc menus and disc subtitles are not
    supported.

  StereoShutter Photos 1.0.2 (folder "StereoShutter Photos"):
    Photos of 3D cameras (MPO), JPS and PNS files, side-by-side and top/bottom
    pictures, and 2D photos; the photos of a folder one after another or as a
    slideshow, full screen or in a window. Drop a photo or a folder on
    StereoShutter_Photos.exe. Three sample photos are in its Samples folder.

  Each folder has its README.txt and its manual in English and Spanish
  (StereoShutter_Player_Manual_EN.pdf, StereoShutter_Photos_Manual_EN.pdf...).
  Their StereoShutter.ini is the one for games with the player always paced
  and no keys page or FPS counter over the picture.

6. CONTROLS

  Ctrl+T                       Turn the 3D off and on.
  Ctrl+Alt+S                   Swap the eyes.
  Ctrl+Alt+G                   Lock the glasses again.
  Ctrl+Alt+K                   Keys / settings for this game / quick setup.
  Ctrl+Alt+Left / Right        Phase.
  Ctrl+Alt+Up / Down           Open time.
  Ctrl+Alt+PageUp / PageDown   HDR brightness.
  Alt+Shift+F10                The HDR panel.
  Ctrl+Alt+H                   The game's picture read as Auto or HDR10, this
                               session only.
  Ctrl+Alt+Enter               Save the glasses' values and the HDR settings.
  Ctrl+Alt+F                   The FPS counter.
  Ctrl+Alt+F12                 Stop StereoShutter; the game goes on.

  The phase and open time keys repeat while held; Shift moves ten times as
  much. A key without Alt (Ctrl+T) is taken only while the game or
  StereoShutter is in front, so other programs keep it. [Keys] in
  StereoShutter.ini changes the keys; empty or none turns one off. The stop
  key is also watched apart from the drawing.

  "Settings for this game" (Ctrl+Alt+K, twice) has the glasses' cycles, the
  HDR output, the FPS counter, the keys page at the start, the depth of the
  panels, the eyes in geo-11 games, covering the other monitors, the language
  and the monitor's brightness. It works with the mouse and the keyboard, and
  saves into that game's StereoShutter.ini.

7. CYCLES, PACING AND STABILITY

  A cycle shows both eyes once. The usual rates:
    360 Hz, three refreshes per eye: 60 cycles a second (glasses at 120 Hz),
                                     as supplied.
    360 Hz, two refreshes per eye:   90 cycles a second (glasses at 180 Hz).
    240 Hz, image and black:         60 cycles a second.
    120 Hz, one refresh per eye:     60 cycles a second.
  At 360 Hz, 60 cycles are the steadier: each eye's image is shown longer,
  and the game needs 60 frames a second. 90 cycles move more smoothly when
  the game keeps 90 frames a second. Some people notice a slight flicker at
  60. The monitor stays at 360 Hz. "Settings for this game" > Glasses
  cycles changes it for that game ([BFI] refreshes_per_eye = 2 for 90); the
  glasses' values for 60 and for 90 cycles are saved apart (with nothing
  saved for 60, those of 90 are carried over).

  The doorman: StereoShutter asks the game's layer, or StereoShutter_host.dll,
  for one game frame per cycle, in step with the glasses. With [Input]
  pace_game = auto (as supplied), it lets one frame per cycle through while the
  game keeps up, one every two cycles when it keeps up with half of them, and
  steps aside when it cannot even do that; a late frame is never held back.
  pace_lead_auto = yes follows when the game's frames come. Without the host
  DLL there is no doorman: give the game its own FPS limit (60; 90 at 360 Hz
  with 90 cycles). A game slower than the cycles is less smooth; the glasses
  do not lose their step for that.

  The supplied StereoShutter.ini has the automatic modes on:
    [Output] queue = auto: starts with 3 images prepared ahead and adds one
      each time the graphics card does not have StereoShutter's images ready
      in time (up to 6). It says so in red, and writes queue_auto_start into
      that game's StereoShutter.ini for its next starts (delete the line to
      start at 3 again). A number (queue = 3) keeps the queue fixed.
    [Output] gpu_priority_absolute = auto: StereoShutter's work at priority
      16, the level of the game in front, and at 17 only while an image of
      its own is about to be late.
    [Output] engine = auto: for a game that fills the graphics card and makes
      very few frames a second, so that even the largest queue is not enough.
      StereoShutter then keeps a part of the graphics card for its images
      (copy) for the rest of the session and says so in red; the game stays
      as slow, without flicker. It writes engine_auto_start = copy for that
      game's next starts (delete the line to start with draw again).
  If flicker remains, lower the game's graphics (in 3D it draws everything
  twice), give it an FPS limit, and close what uses the graphics card.

8. HDR INPUT AND OUTPUT

  Output and input are separate:

    [Output] hdr = yes
      StereoShutter's HDR output on an HDR monitor: brighter pictures through
      the glasses. If Windows HDR is off for that monitor, StereoShutter
      switches it on while it runs and off at the end. The setup assistant
      offers it (H) on an HDR monitor; then run the assistant again with HDR.
      hdr_brightness: the pictures' white in times Windows' SDR white (1 to
      8, usually 3), never above the monitor's peak.

    [Input] picture = auto
      What the game's picture is, from the game's colour space and its format.
      sdr, hdr10 or scrgb by hand only when the colours come out wrong.

  HDR output makes a normal game brighter through the glasses; it does not
  give it the detail of a real HDR picture. A game's own HDR is shown as HDR
  when the game and its 3D layer hand it over. A 10-bit picture, stronger
  colours or more brightness are not proof of HDR.

  Ctrl+Alt+H reads the game's picture as Auto or HDR10 for this session: for
  a game that sends HDR10 without saying so. It does not switch the game's
  HDR, Windows HDR or the output, and it is not saved.

  Ctrl+Alt+PageUp/PageDown change the HDR brightness; Ctrl+Alt+Enter saves
  it. For a game's own HDR, a lower value leaves more room for its bright
  parts. A game's own HDR usually looks darker than its SDR picture, with
  brighter highlights: that is how HDR games are made. To lighten it, raise
  Midtones in the HDR panel.

  The HDR panel (Alt+Shift+F10): brightness, exposure, midtones, contrast,
  shadows, saturation, gamma, highlights, the gain of each colour, paper
  white and peak, in both eyes in front of the screen, with the mouse or
  the keys (Ctrl+Alt+I / M choose, Ctrl+Alt+J / L change, Ctrl+Alt+Backspace
  resets). Ctrl+Alt+Enter or its Save button saves; closing it does not.
  [HDR.SDR] keeps the look for games without HDR, [HDR.Native] for games in
  HDR.

  At the start, Windows HDR is switched on before the game makes its picture
  (with StereoShutter_host.dll or the layer starting StereoShutter). Started
  after a geo-11 game is already running, StereoShutter does not switch it.
  Windows HDR is not switched in NVIDIA Surround.

9. FULLSCREEN COMPATIBILITY

  In geo-11 games, use the game's borderless full screen or window: exclusive
  full screen hides StereoShutter's picture (the geo-11 setup sets the fix's
  full_screen = 0). Some fixes set full_screen in an .ini file of their
  ShaderFixes folder that d3dx.ini includes, which the setup does not read:
  set it to 0 there.

  Some games turn their own HDR on only in Fullscreen. [Host]
  fullscreen_compat = yes gives such a game a borderless window over the
  monitor when it asks for exclusive full screen, with DXGI kept windowed. It
  is off by default; turn it on only for a game that needs it.

  With SLT12 Output (DirectX 12), the game's Fullscreen works too, including
  HDR where the game has it; fullscreen_compat is not used there.

  If a game changes the refresh rate, set it back before playing.

10. LIGHTBOOST AND NVIDIA SURROUND

  One 3D Vision monitor:
    [Monitor] lightboost = yes switches the table's LightBoost timing on for
    the session and puts the previous one back at the end. lightboost = no
    leaves the monitor's timing alone.

  NVIDIA's table is read from the emitter driver's registry entries; it is
  not changed and not part of this download. An optional JSON copy next to
  the program ([Monitor] nvidia_table) adds only monitors the registry
  lacks. The glasses' values you save win over the table's.

  NVIDIA Surround of three 3D Vision monitors:
    1. Set up the grid in NVIDIA Control Panel, at a mode of the monitors'
       table (usually 120 or 144 Hz).
    2. Save your work and close games and programs.
    3. Run StereoShutter_LightBoost_Surround_Setup, read it and type YES.
  It separates the grid for a moment, saves each monitor's timing as a
  custom resolution, puts the grid back and checks it. With [Monitor]
  lightboost_surround = auto, the timing is used while playing and the
  previous signal is put back at the end. StereoShutter_LightBoost_Surround_
  Undo removes the timings (keep StereoShutter_lightboost_surround.json until
  it says it finished).

  These tools change the display configuration through NVIDIA's driver: the
  screen can go black for a moment, and a failed change can hang or restart
  the computer. lightboost_surround = try is not recommended for that reason.

11. SETTINGS AND SAVED VALUES

  StereoShutter.ini, next to StereoShutter.exe, keeps the settings, each with
  its explanation above it. Edit it with StereoShutter closed. A missing line
  takes the program's standard value. Each game folder has its own
  StereoShutter.ini; StereoShutter writes into it what is saved, and what
  queue = auto and engine = auto learn for that game (keeping a copy of the
  ini first).

  The glasses' values:
    %LOCALAPPDATA%\StereoShutter\monitors.json (shared by every game folder)
    %LOCALAPPDATA%\StereoShutter\monitors.json.previous (the one before)

  A section can have a version for one monitor or refresh rate:
    [Output @ 120 Hz]
    [Output @ DISPLAY2]
    [Input @ DISPLAY2 360 Hz]
  The last matching one wins; the command line wins over them. They do not
  work for what is needed before the monitor is known (see the end of
  StereoShutter.ini).

  StereoShutter.exe --help lists the command-line options; --version gives
  the version.

12. REPORTING A PROBLEM, AND TROUBLESHOOTING

  Reporting a problem:
    StereoShutter_Feedback records the next game session with everything
    needed to find the cause, in one ZIP file of at most 5 MB, ready to send
    by e-mail to info@stereoshutter.com:
      1. Open StereoShutter_Feedback (next to StereoShutter.exe, in the
         game's folder), press "Record the next game session" and then
         "OK, close this window".
      2. Start the game and play until the problem shows. The message on the
         screen says that the session is being recorded.
      3. When you see the problem, press Ctrl+Alt+F9: that moment is marked
         and its detail kept. You can mark more than one.
      4. Close the game. A window opens with the file ready: send it by
         e-mail, saying what you saw and when.
    It records only that session and sends nothing by itself. The manual
    ("Reporting a problem") lists what the file holds.

  Reports: [Report] enabled = yes writes a report of each session in
  StereoShutter_reports and StereoShutter_host.log next to the DLL. The setup
  assistant and the pattern test always write theirs. Reports can hold local
  paths and game names: look at them before sharing.

  No emitter:
    Check its USB connection, NVIDIA's USB driver, and that no other program
    uses the glasses.
  Unsupported display mode:
    Choose a supported refresh rate; for a 3D Vision monitor, a mode of the
    table.
  Depth reversed:
    Ctrl+Alt+S, then Ctrl+Alt+Enter, in the situation where it happens.
  A ghost image that stays:
    Set the phase and open time again (section 3). The panel's response
    limits what can be reached.
  Flicker, or an eye shown in the other:
    Check the three settings of section 2, close the game's launcher and the
    programs that draw, keep the game in front, and follow the messages on
    the screen. queue = auto and engine = auto act by themselves (section 7).
  Flicker once a second in heavy scenes:
    For a game that does not turn its HDR on through NVIDIA's driver, [Input]
    nvapi_hdr = no in its StereoShutter.ini.
  "independent flip no" for most of a report:
    [Host] visible_game_strip = 0 (the supplied value).
  Small stutters the first time through a place, with a 3D fix just
  installed or changed:
    Normal: geo-11 prepares each effect the first time the game uses it. The
    eyes do not cross.
  A grey picture, like a depth map:
    The fix's .ini files are not of the same version as the geo-11 d3d11.dll
    next to them: keep all the files of one fix together.
  The depth keeps changing by itself:
    The automatic convergence some fixes have; the fix says its key.
  The game closes when its own HDR is turned on (geo-11):
    Try [System] allow_platform_update = 2 in the fix's ini (d3dx.ini, or an
    .ini file of its ShaderFixes folder), for that game only. If something
    else fails with 2, put it back and play with the game's HDR off.
  A game closes during its first frames with the host DLL:
    [Host] pace_hook = no (then give the game its own FPS limit).
  Wrong colours:
    Check [Input] picture against what the game sends (section 8).
  "HAGS" at the start:
    Turn HAGS off in Windows and restart Windows (section 2).
  LightBoost left on after an interruption:
    Section 13.

13. EXIT, RECOVERY AND REMOVAL

  Ctrl+Alt+F12 stops StereoShutter and leaves the game running. The stop key
  and the game's end are watched apart from the drawing, so that the emitter
  is switched off even if the picture is stuck ([Emitter] disable_on_exit =
  yes). Loading screens do not stop it. If a driver itself is stuck, unplug
  the emitter and plug it in again.

  At the end StereoShutter puts back the monitor's brightness, Windows HDR
  (if it switched it on) and LightBoost. If StereoShutter closes suddenly (a
  crash), they can stay as they were while it ran: set the brightness back
  in the monitor's menu, switch HDR off in Windows display settings if
  StereoShutter switched it on, and change the refresh rate, or run
  StereoShutter_Undo_LightBoost (keep StereoShutter_lightboost_pending.json
  until it has finished). For Surround, StereoShutter_LightBoost_Surround_Undo.

  Removal:
    1. Close the game and StereoShutter.
    2. If you used LightBoost in Surround, run
       StereoShutter_LightBoost_Surround_Undo.
    3. In geo-11 games, run StereoShutter_geo-11_Setup and choose UNDO.
    4. Delete StereoShutter's files and folders in each game folder (they
       are all called StereoShutter...; in a game with SLT12 Output,
       StereoShutter_output.ini and StereoShutter_output.log belong to the
       layer: keep them).
    5. Delete %LOCALAPPDATA%\StereoShutter if no game needs the glasses'
       values any more.
  StereoShutter installs nothing in Windows and leaves nothing running.

14. DISPLAY CARE AND LICENCE

  While it runs, StereoShutter sets the monitor's brightness to maximum
  ([Monitor] brightness = keep leaves it alone) and, with the HDR output,
  makes its pictures brighter than the desktop. The monitor keeps its own
  limits and protections. An OLED screen wears with brightness and time, and
  something bright that stays in the same place can leave a mark. Keep the
  monitor's care features on, lower the HDR brightness if in doubt, and do
  not leave a still picture running. You use it at your own risk.

  StereoShutter is free for everyone under StereoShutter_LICENSE.txt. It may
  be passed on free of charge, as the complete, unchanged download, with its
  licence and StereoShutter_THIRD_PARTY.txt. The source code is not
  published. No warranty: the licence has the full terms.

  Copyright (C) 2026 murdavs. All rights reserved.
  NVIDIA, 3D Vision, LightBoost, GeForce, G-SYNC and Reflex are trademarks of
  NVIDIA Corporation. StereoShutter is not made, supported or endorsed by
  NVIDIA.
