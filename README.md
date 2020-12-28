This is a port of dxx-rebirth (open-source engine for Descent 1/2) to Nintendo Switch. It's a homebrew app, so you need to be running custom firmware for it to work.


[1] BUILDING
------------

If you're targeting Nintendo Switch, make sure you're using the `switch` branch. The `master` branch contains changes which are not specific to Switch and could be used on other platforms.

You will need to install the [devkitPro](https://devkitpro.org/) toolchain. Make sure to include the following packages:

    libnx switch-sdl2_image switch-sdl2_mixer switch-mesa switch-physfs

You'll need to build and install two additional libraries, [GLU](https://github.com/ptitSeb/GLU) and [GLAD](https://glad.dav1d.de/).
For GLAD, I have used OpenGL 2.1 compatibility profile.

Then follow the usual steps to build dxx-rebirth.

If you don't intend to do any coding and just want to play, grab the latest [release](https://github.com/dimag0g/dxx-rebirth/releases) instead.


[2] SETUP
---------

You will need a copy of the official game to run this port. If you don't own the game, you can get the shareware game contents
[here](https://www.dxx-rebirth.com/game-content/), which will let you have a first impression.

dxx-rebirth root directory is hardcoded as `/switch/d1x-rebirth` and `/switch/d2x-rebirth` for Descent 1 and 2, respectively.
Put the release files there, then add the files from your copy of the game or the shareware files.
The release already includes addons from  [dxx-rebirth](https://www.dxx-rebirth.com/addons/): the high resolution pack for D1 and OGG music for both D1 and D2.

If you want to watch demos, copy the `*.dem` files into `DEMOS` folder inside `/switch/d1x-rebirth` and `/switch/d2x-rebirth`.

⚠ For Descent 2, you may want to skip `INTRO.MLV`: if you copy it, the game will play the intro which is currently impossible to skip.

Mods are supported in principle, but I obviously didn't try all of them.


[3] RUNNING
-----------

This build of dxx-rebirth was tested on 10.2.0|AMS 0.14.4|S (FAT32). exFAT is not recommended.
Alternative controllers (keyboards, mouses, etc.) might work but weren't tested.

Both games run at solid 60fps with currently enabled effect (transparency and dynamic lighting).
More effects (like anisotropic filtering) are available in the video settings. Some combinations of settings may have an impact of the framerate.

Game controls can be changed in the game options. Default configuration mimics the layout used by [Sublevel Zero](http://www.sigtrapgames.com/sublevelzero/)
(not that I recommend that game, but it's the only zero-G shooter on Switch that I know and the layout it has seems reasonable):

- L-stick - Accelerate/reverse and strafe left/right
- L-stick push - Afterburner (D2 only)
- R-stick - Look around
- R-stick push - Toggle headlight (D2 only)
- R/L - strafe up/down
- Y/B - bank left/right (CCW/CW)
- ⊖ - Open map
- ⊕ - Menu
- ZL/ZR - Fire primary/secondary
- A - Fire flare
- X - Rear view
- D-pad down - Convert energy to shield (D2 only)
- D-pad left/right - Cycle primary/secondary weapon

[4] TODO
--------

Here's a list of known bugs / missing features, approximately in order of priority. Don't bother reporting those as issues.

- cutscenes/briefings cannot be skipped
- impossible to change HUD parameters accessible via hotkeys only
- no network play
- no gyro aim
- no full HD resolution when docked
