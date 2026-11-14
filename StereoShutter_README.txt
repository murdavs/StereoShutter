StereoShutter - User guide
StereoShutter 0.18.111.209, with StereoShutter Player 1.0.4 and StereoShutter Photos 1.0.3
NVIDIA 3D Vision shutter glasses; Samsung SSG-5100GB glasses (experimental)
Copyright (C) 2026 murdavs. All rights reserved.

StereoShutter shows the separate left and right images that a game's 3D fix
supplies, and synchronizes the shutter glasses with the monitor: NVIDIA 3D
Vision glasses with their USB emitter, or, as experimental support, Samsung
SSG-5100GB glasses over Bluetooth (section 14). High-refresh OLED and LCD
monitors use a black refresh between the eyes. Recognized 3D Vision monitors
use NVIDIA's timing values and LightBoost.

StereoShutter Manager, a separate download, finds the installed games,
installs their 3D fixes and sets up the glasses: section 15 says how to use
it. The rest of this guide is for StereoShutter installed by hand.

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
 14. Samsung SSG-5100GB glasses (experimental)
 15. StereoShutter Manager and DirectX 12 games
 16. Display care and licence

1. REQUIREMENTS AND THE DOWNLOAD

  - Windows 10 or 11, 64-bit, and an NVIDIA graphics card (for games, see
    "Graphics card for games" below).
  - NVIDIA 3D Vision glasses and their USB emitter (for Samsung SSG-5100GB
    glasses, see section 14 instead of this point and the next). Some 3D
    Vision monitors have the emitter built in, and its signal comes through
    the video cable, not through USB. StereoShutter cannot use that emitter:
    with those monitors, the separate USB emitter is needed.
  - NVIDIA's emitter USB driver. Device Manager should show "NVIDIA
    Stereoscopic 3D USB controller". NVIDIA's discontinued 3D Vision graphics
    driver is not needed.
  - A supported display mode, selected in Windows before starting.
  - For games, a 3D fix that supplies both eye images: a geo-11 fix in
    DirectX 11 games (section 4), or a StereoShutter Engine fix in DirectX
    12 games (section 15).

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
    Other OLED/LCD monitors at 198-555 Hz:
      Up to 370 Hz, two refreshes per eye: left image, black, right image,
      black. At 240 Hz that is 60 stereo cycles a second; at 300 Hz, 75.
      At 360-370 Hz, as supplied, three refreshes per eye: each eye's image
      twice, then black. At 360 Hz that gives 60 cycles a second, the
      steadier; two refreshes per eye give 90. See section 7.
      At 371-555 Hz, always three refreshes per eye: at 480 Hz, 80 cycles a
      second; at 540 Hz, 90. Not yet tried on such a monitor.
    Other monitors at 99-185 Hz:
      One refresh per eye. At 120 Hz that is 60 cycles a second.
      IMPORTANT: turn on the monitor's own strobing (ELMB, ULMB, DyAc or
      "motion blur reduction", depending on the brand) in its menu. Without
      it there will be a ghost image at the top or the bottom, or a darker
      picture. If the monitor does not have it and reaches 240 Hz or more,
      use that rate: from 198 Hz StereoShutter puts a black refresh between
      the eyes itself, and the monitor's strobing stays off. The panel's
      response decides the rest of the crosstalk.
    Recognized NVIDIA 3D Vision monitors:
      A mode of NVIDIA's table, with its resolution and refresh rate.
      LightBoost uses the table's timing. At a refresh rate the table does
      not have, from 198 Hz (a 240 Hz monitor at 240 Hz), the black refresh
      of other monitors, without LightBoost. Not yet tried.
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
  chosen. At 144, 165, 300 and 480 Hz (72, 82, 75 and 80 cycles), in
  between. A somewhat smaller card also works with lower settings; the
  newest, heaviest games can need more. At 3840x2160, no card gives 90
  cycles with room to spare.
  (*) With the RTX 4090, most games hold 90; some dip in their heaviest
  scenes. Tested with an RTX 4090; the other cards are estimated from
  published benchmarks. Films and photos need much less.

2. NVIDIA AND WINDOWS SETTINGS

  Three things to check. StereoShutter checks them at the start and warns on
  screen:

    1. Windows: hardware-accelerated GPU scheduling (HAGS), on or off. With
       HAGS on (a game's frame generation needs it), StereoShutter asks
       Windows for administrator rights each time it starts over a game, the
       player or the viewer, for a small helper of its own that keeps
       StereoShutter in the graphics card's realtime class while it runs, so
       that its images go before the game's frames: answer yes. With no, it
       runs all the same, but its images may come late and the glasses
       flicker. [Output] hags_realtime = no never asks. StereoShutter does not
       change HAGS itself; after switching it, restart Windows.
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

  In the game: vertical sync off.

  While playing: keep the game in front (with another window in front,
  Windows composes the screen and the 3D can flicker). Close or minimize what
  keeps drawing (browsers, videos, chat or AI programs), the game's launcher
  and other windows left behind it, and programs that get into games
  (overlays, recorders, FPS counters). StereoShutter names the programs it
  sees using the graphics card.

3. SET UP THE GLASSES

  This is for NVIDIA 3D Vision glasses; the Samsung ones are in section 14.

  Set Windows to the refresh rate you will play at and run
  StereoShutter_Setup. It is done once for each monitor and refresh rate,
  and works for every game. 3D Vision monitors use NVIDIA's values at the
  modes of their table; other monitors, and other modes, need the
  assistant.

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

  The fix has to be made for geo-11: a 3Dmigoto fix made for 3D Vision does
  not work as it is. 64-bit and 32-bit games both work: a 32-bit game has the
  32-bit geo-11 and fix, and the setup connects StereoShutter_host32.dll
  instead of StereoShutter_host.dll.

  Copy the CONTENTS of the extracted ZIP's StereoShutter folder beside the
  actual game's .exe and the installed fix. Do not leave those files inside
  an extra StereoShutter subfolder or use the launcher's folder. Player and
  Photos stay separate. Follow the fix's game-specific folder instructions.
  When updating, back up the existing installation, keep that game's
  StereoShutter.ini, which holds its saved settings, and replace
  StereoShutter_host.dll too (StereoShutter_host32.dll in a 32-bit game):
  StereoShutter works only with the host DLLs of its own download.

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
                          (StereoShutter_host32.dll in a 32-bit game: it
                          tells which from geo-11's d3d11.dll, and stops if
                          geo-11 and the game are not of the same kind)
    d3dxdm.ini, [Device]: direct_mode = katanga_vr
    and it gets the fix ready:
    - full_screen = 0 in d3dx.ini and d3dxdm.ini, where the fix sets another
      value (exclusive full screen hides StereoShutter's picture);
    - create_profile = 0 in d3dx.ini, where the fix sets another value (fixes
      adapted from 3D Vision ones may still write 3D Vision settings into the
      game's NVIDIA profile);
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
  StereoShutter_host32.dll does the same in 32-bit games, except [Host]
  fullscreen_compat and nvapi_hdr_route (64-bit games only).

  A fix made for 3DMigoto Loader (its guide starts the game with
  3DMigoto Loader.exe, from a folder of its own):
    Leave the fix as it is, copy StereoShutter's files into that folder and
    run StereoShutter_geo-11_Setup there: it sets the folder up and says so.
    To play, open StereoShutter_Play first, then the game with 3DMigoto
    Loader. StereoShutter shows geo-11's picture in a window of its own over
    the game, without the doorman: give the game its own FPS limit. In a
    folder with neither the game nor the loader, the setup says where the
    files go and changes nothing.

  Starting by hand:
    StereoShutter_Play waits up to 10 minutes for a game. Without the host
    DLL, StereoShutter shows geo-11's picture in a window of its own over the
    game's; there is then no pacing: give the game its own FPS limit.
    [Input] game_window names the game's window if another one is taken.
    For a geo-11 game that needs Windows HDR, start StereoShutter before the
    game: started after it, it does not switch Windows HDR on.

  Keep StereoShutter_host.dll and StereoShutter_host32.dll under their names
  and connect them only through the setup. Do not use them to replace a game's
  own graphics proxy.

5. FILMS AND PHOTOS: STEREOSHUTTER PLAYER AND STEREOSHUTTER PHOTOS

  Two separate programs show films and photos through the same glasses, with
  StereoShutter's HDR output to make them brighter through the glasses. To
  StereoShutter each of them is a game: it starts StereoShutter by itself and
  closes it when it closes. Set up the glasses first (section 3): the values
  are shared.

  StereoShutter Player 1.0.4 (folder "StereoShutter Player"):
    Half or full side-by-side and top/bottom videos, 2D videos, unprotected
    Blu-ray 3D (an .iso image or a copied disc folder, 1920x1080 per eye),
    and the window of another program (a 3D video in a web browser). Drop a
    video on StereoShutter_Player.exe, or open it and choose. Right-click or
    Enter: the menu; Space: pause, and after the end, play again; Esc: close.
    It needs VLC media player 3, 64-bit, installed (videolan.org) for files
    and Blu-rays; VLC is not included and VLC 4 is not supported. Window
    capture needs Windows 10 version 1903 or later. HDR films are shown as
    normal pictures. Protected Blu-rays, disc menus and disc subtitles are not
    supported.

  StereoShutter Photos 1.0.3 (folder "StereoShutter Photos"):
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
  Ctrl+Alt+End                 The bright-area limit on and off (only with
                               [Output] hdr_bfi_limit = static or scene).
  Ctrl+Alt+Home                The bright-area limit's level: 100, 85, 70,
                               55 %. Both for this session only.
  Ctrl+Alt+Enter               Save the glasses' values and the HDR settings,
                               and the FPS counter as Ctrl+Alt+F left it.
  Ctrl+Alt+F                   The FPS counter.
  Ctrl+Alt+P                   A 3D photo of the game.
  Ctrl+Alt+Shift+P             What the 3D photo saves (the photo menu).
  Ctrl+Alt+R                   The monitor's ELMB off and on again (only with
                               [Monitor] relatch_elmb = yes).
  Ctrl+Alt+F9                  Mark a moment while StereoShutter_Feedback
                               records a game session.
  Ctrl+Alt+F12                 Stop StereoShutter; the game goes on.

  The phase and open time keys repeat while held; Shift moves ten times as
  much. A key without Alt (Ctrl+T) is taken only while the game or
  StereoShutter is in front, so other programs keep it. [Keys] in
  StereoShutter.ini changes the keys; empty or none turns one off. The stop
  key is also watched apart from the drawing.

  "Settings for this game" (Ctrl+Alt+K, twice) has the glasses' cycles, the
  HDR output, the FPS counter, the keys page at the start, the depth of the
  panels, the eyes in geo-11 games, covering the other monitors, the language,
  the monitor's brightness and what the 3D photo saves. It works with the
  mouse and the keyboard, and saves into that game's StereoShutter.ini.

  3D photos: Ctrl+Alt+P takes a 3D photo of the game at once, from the game's
  own picture (without StereoShutter's texts or the FPS counter, and with the
  game's light, not the extra brightness for the glasses), into
  Pictures\StereoShutter, named after the game, the date and the time.
  Ctrl+Alt+Shift+P opens "Settings for this game" at what it saves; several
  can be ticked, all from the same moment:
    SBS 3D (ticked as standard)  3840x1080 JPG, both eyes side by side
                                 (1920x1080 each, the left eye on the left):
                                 3D photo programs that read full
                                 side-by-side, VR viewers, StereoShutter
                                 Photos.
    SBS 3D HDR                   The same in JPEG XR with the game's HDR
                                 light (the format of Windows' HDR
                                 screenshots; an HDR image viewer shows it
                                 in HDR). Games with HDR only; in others
                                 the JPG is saved instead.
    Red-cyan anaglyph            1920x1080 JPG for red-cyan glasses, with
                                 Dubois' colours (the least ghost image).
  Each eye fits whole into its 1920x1080 without being stretched: a 21:9 game
  gets black bars above and below. [Photo] folder in StereoShutter.ini
  changes the folder. If Windows' Controlled folder access is on, it may not
  let StereoShutter write into Pictures: allow StereoShutter.exe in Windows
  Security, or choose another folder.

7. CYCLES, PACING AND STABILITY

  A cycle shows both eyes once. The usual rates:
    360 Hz, three refreshes per eye: 60 cycles a second (glasses at 120 Hz),
                                     as supplied.
    360 Hz, two refreshes per eye:   90 cycles a second (glasses at 180 Hz).
    240 Hz, image and black:         60 cycles a second.
    120 Hz, one refresh per eye:     60 cycles a second.
    300 Hz, image and black:         75 cycles a second.
    480 Hz, three refreshes per eye: 80 cycles a second (glasses at 160 Hz).
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
      in time (up to 6), on the same picture: the 3D goes on ([Output]
      queue_raise). It says so in red, and writes queue_auto_start into
      that game's StereoShutter.ini for its next starts (delete the line to
      start at 3 again). After 10 minutes of play at a raised level with
      nothing missing for want of margin, counted over several sessions too
      (queue_auto_calm), the next start begins one level lower; if that level
      flickers, it goes back up at once. A stall of the whole computer is not
      counted as a slow graphics card. A number (queue = 3) keeps the queue
      fixed.
    [Output] gpu_priority_absolute = auto: StereoShutter's work at priority
      16, the level of the game in front, and at 17 only while an image of
      its own is about to be late.
    [Output] engine = auto: for a game that fills the graphics card and makes
      very few frames a second, so that even the largest queue is not enough.
      StereoShutter then keeps a part of the graphics card for its images
      (copy) for the rest of the session and says so in red; the game stays
      as slow, without flicker. A hitch of the game that holds the graphics
      card longer than the whole queue calls for copy too. Once copy has held
      for 2 minutes, it writes engine_auto_start = copy for that game's next
      starts (delete the line to start with draw again); if copy misses
      before that, draw again for the session.
    [Output] present_hold = auto: with three refreshes per eye (image, image,
      black), each eye image is presented once for its two refreshes and the
      black comes from a buffer that already holds it: a third of the work
      for the graphics card, the same on the screen.
  After a hitch of the whole computer, or while another window comes in
  front or goes, StereoShutter shows neutral images for a moment (the left
  eye's picture in both eyes, or black) instead of letting an image reach the
  other eye, and the 3D comes back by itself.
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

  The bright-area limit, only with HDR output and the black refresh between
  the eyes: on an OLED, a large very bright area (sky, sand, snow) lit and
  black at every eye can make the monitor's own brightness limiter flicker,
  even without the glasses. [Output] hdr_bfi_limit = scene lowers only the
  bright part of each stereo pair, as much as that pair needs to keep its
  mean light at the monitor's full-screen luminance (hdr_bfi_limit_nits);
  darker parts never change, and both eyes get the same. static lowers the
  bright part by a fixed gain (hdr_bfi_limit_gain). Off as supplied.
  Ctrl+Alt+End turns it on and off and Ctrl+Alt+Home steps its level, for
  the session.

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

  In geo-11 games, the geo-11 setup sets the fix's full_screen = 0: geo-11's
  own exclusive full screen hides StereoShutter's picture. Some fixes set
  full_screen in an .ini file of their
  ShaderFixes folder that d3dx.ini includes, which the setup does not read:
  set it to 0 there.

  Some games turn their own HDR on only in Fullscreen. [Host]
  fullscreen_compat = yes gives such a game a borderless window over the
  monitor when it asks for exclusive full screen, with DXGI kept windowed. It
  is off by default; turn it on only for a game that needs it (64-bit games
  only).

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

  The general glasses profile (which glasses, which monitor, the refreshes
  per eye), written by StereoShutter Manager and shared by every game:
    %LOCALAPPDATA%\StereoShutter\glasses.ini
  A game follows it unless its own StereoShutter.ini says
  [Glasses] profile = game. Without that file, each StereoShutter.ini decides
  for itself, as before.

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
    If the game did not open, or its 3D did not start, open
    StereoShutter_Feedback again and press "The 3D did not start: prepare
    the file". If the e-mail program answers that the e-mail was cancelled,
    the window says so and shows the file in its folder: send it as an
    attachment from your usual e-mail.
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
    Choose a supported refresh rate (section 1); for a 3D Vision monitor, a
    mode of its table, or 198 Hz or more.
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
  "HAGS is on and StereoShutter could not get the graphics card's realtime
  class" at the start:
    Answer yes when Windows asks for administrator rights as StereoShutter
    starts, or turn HAGS off in Windows and restart Windows (section 2).
  The 3D does not start after an update:
    Replace StereoShutter_host.dll (StereoShutter_host32.dll in a 32-bit
    game) with the one of the same download: StereoShutter does not connect
    to the host DLL of an older version.
  A large bright sky or sand flickers on an OLED, even without the glasses:
    With HDR output: [Output] hdr_bfi_limit = scene (section 8). Turning off
    the monitor's dynamic brightness boost helps too.
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
       are all called StereoShutter...).
    5. Delete %LOCALAPPDATA%\StereoShutter if no game needs the glasses'
       values any more.
  StereoShutter installs nothing in Windows and leaves nothing running.

14. SAMSUNG SSG-5100GB GLASSES (EXPERIMENTAL)

  StereoShutter also drives Samsung SSG-5100GB active 3D glasses, the ones
  made for Samsung's 3D TVs, over Bluetooth. There is no NVIDIA emitter.
  NVIDIA 3D Vision glasses go on working as before, and stay the standard.

  This support is experimental: it is new in this version and still being
  refined. It is only for the glasses, the adapter and the kind of monitor
  named here, and how well it works can change from one setup to another.

  What it needs:
    - Samsung SSG-5100GB glasses.
    - A TP-Link UB500 USB Bluetooth adapter with TP-Link's official driver
      installed. While the 3D runs, the adapter works only for the glasses;
      StereoShutter puts its driver back when it closes.
    - An OLED monitor at 240 Hz (two refreshes per eye) or at 360 Hz (three
      refreshes per eye). Both give 60 cycles a second.

  Setting them up, in StereoShutter Manager (section 15):
    1. Connect the UB500 and install its driver. Keep the glasses close to
       the adapter, and the TV they were used with off.
    2. In the Manager open Glasses, choose "Samsung 3D (Bluetooth)", choose
       the monitor, confirm that it is an OLED and save.
    3. Press "Test glasses" and answer yes when Windows asks for
       administrator rights: StereoShutter prepares the adapter for the
       glasses and puts its driver back at the end.
    4. Wait for the countdown on the screen, then press the button of the
       glasses briefly. The first time, or after the glasses were used with
       a TV, hold the button for about two seconds so that they join
       StereoShutter. Do not add the glasses in Windows' Bluetooth settings.
    5. Close one eye, then the other: Ctrl+Alt+Left/Right moves the phase
       and Ctrl+Alt+Up/Down the open time, until each eye sees only its own
       bar (with Shift, ten times the step). Ctrl+Alt+F12 ends the test;
       back in the Manager, save the adjustment it brings back.
  From then on every game uses this general profile, also when it is started
  outside the Manager.

  In games:
    - StereoShutter Engine fixes work with these glasses as with NVIDIA's.
    - A game with geo-11 needs StereoShutter_host.dll 0.18.32 or later next
      to StereoShutter.exe (StereoShutter_host32.dll in a 32-bit game), the
      ones of this download: they hand the game's picture to StereoShutter
      as complete pairs, which these glasses need. [Host] pairs = no in the
      game's StereoShutter.ini turns that off.
    - Ctrl+Alt+K in the game shows the keys, then the settings, then the two
      bars for a quick adjustment; Ctrl+Alt+Enter saves it for that game.

  Without the Manager, in a game's StereoShutter.ini:
    [Glasses]
    profile = game          this game keeps its own choice of glasses
    [Emitter]
    backend = bluetooth     nvidia = NVIDIA 3D Vision, the standard
    [Bluetooth]
    glasses_model = samsung
    display_mode = monitor
    oled_confirmed = yes    only for an OLED monitor
    refreshes_per_eye = 3   3 at 360 Hz, 2 at 240 Hz
  StereoShutter.exe --settings opens StereoShutter's own window to choose
  the glasses and the monitor and to test them (in Spanish for now). Its
  "Recuperar USB" button puts the adapter's driver back if an interruption
  left the adapter without it.

  Good to know:
    - A longer open time is brighter, but lets more of the other eye's
      picture through. On some monitors a little of it remains and changes
      with the viewing angle.
    - Only one StereoShutter at a time.
    - The adapter's firmware is taken from TP-Link's installed driver. It is
      not part of the download.
    - Other Samsung models, other Bluetooth 3D glasses and other adapters
      are not supported.

15. STEREOSHUTTER MANAGER AND DIRECTX 12 GAMES

  StereoShutter Manager is a separate download, published on its own and
  with its own versions: it is not in this ZIP. It finds the installed games
  and shows the 3D fixes there are for them: the community's geo-11 fixes
  published on HelixMod, with their authors' instructions and credits, and
  StereoShutter Engine fixes for DirectX 12 games. It installs, updates and
  removes a fix with a copy of what it changes, sets up the glasses (a
  general profile for every game, or one for a game), chooses the 3D output
  of the Engine fixes, and downloads and opens StereoShutter Player and
  StereoShutter Photos. It downloads StereoShutter by itself: with the
  Manager, nothing of this folder has to be copied by hand. Free fixes, the
  glasses, the Player and Photos need no account.

  How to use it:
    1. Extract the Manager's ZIP into a folder where you can write and run
       StereoShutterManager.exe. Windows 10 or 11, 64-bit. It looks for its
       own updates and asks before it restarts to apply one.
    2. Library lists the installed games it has found (Steam, Epic, Ubisoft
       Connect, GOG, EA and other launchers) and shows which ones have a 3D
       fix. "Scan again" looks again after you install or move a game, "Add
       game" lets you choose a game's executable yourself, and "Search
       games" (Ctrl+F) filters the list.
    3. To install a fix, open the game ("View details"), read the author's
       instructions and press "Install fix", with the game closed. For a
       geo-11 fix from HelixMod, choose StereoShutter as its output when the
       Manager asks. It keeps a copy of what it changes.
    4. Glasses, at the top, holds the general profile that every game uses:
       choose "NVIDIA 3D Vision 2" or "Samsung 3D (Bluetooth)", save, and
       press "Test glasses" to adjust them with the two bars. A game that
       needs other values keeps its own: on its page, "Use own settings";
       "Use general profile" goes back.
    5. "Play" starts the game once its fix is ready.
    6. To take a fix out: on the game's page, "Uninstall fix", with the game
       closed. The Manager puts back the files it kept. "Repair fix"
       restores a fix's damaged or missing files, and "Backup history"
       brings back earlier saved settings.
    7. "Photos & video" downloads, updates and opens StereoShutter Player
       and StereoShutter Photos.
  The Manager's full user guide is inside its own download
  (docs\USER_GUIDE.md). Read the multiplayer and anti-cheat warning at the
  top of this guide before installing a fix.

  StereoShutter Engine fixes bring DirectX 12 games in geometric 3D: each
  eye is rendered from its own camera through the game's own rendering,
  with ray tracing, DLSS Super Resolution and DLSS Frame Generation in both
  eyes where the game has them. They come complete from the Manager. With
  shutter glasses their picture goes through StereoShutter; they also have
  outputs of their own (native Leia SR, side-by-side, top-bottom, anaglyph,
  interlaced, checkerboard and Katanga).

16. DISPLAY CARE AND LICENCE

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
  NVIDIA, 3D Vision, LightBoost, GeForce, G-SYNC, Reflex and DLSS are
  trademarks of NVIDIA Corporation; Samsung, TP-Link and Leia are trademarks
  of their owners. StereoShutter is not made, supported or endorsed by any
  of them.
