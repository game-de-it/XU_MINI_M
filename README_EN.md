# plumOS_XU_MINI_M

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/plumOS_XU_MINI_M.png" width="480">

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/MagicX_logo.png" width="240"> <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc01.jpg" width="240">

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc02.jpg" width="240"> <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc03.jpg" width="240">

## Acknowledgments
- We express our gratitude and respect to the MagicX XU_MINI_M and AmberELEC development teams, as well as to the community members who love XU MINI M.

## Features
This is a custom firmware (CFW) that has been modified from the StockOS (AmberELEC) of MagicX XU MINI M.

## Download
[You can download the files from the "Releases" section.](https://github.com/game-de-it/XU_MINI_M/releases/tag/plumOS_XU_MINI_M_0.4)

## Beta 0.4 Update Information
- [NEW] Native PICO-8 can now be launched, and games can be downloaded using the network.
- [NEW] ScummVM standalone can now be launched.

## Basic Information
> [!CAUTION]  
> Please do not enable `system settings->ENABLE OVERCLOCK` as it may cause the OS to enter a reboot loop.

- Various settings of Emulationstation can be configured.
- Menus can now be displayed in Retroarch and Drastic, allowing for customization of settings.
- Network connection is possible with a USB Wi-Fi dongle.
  - Supported drivers: RTL815x, 8812AU, 8821AU, 8821CU, 88x2BU
  - Connection is possible via samba (`Guest` user) and SSH (`root` user, password is `amberelec`).
- Portmaster will be automatically installed into the ports directory of SD2 when the OS starts.
  - If the `ports_scripts` directory exists on SD, please delete that directory.
  - You can launch Portmaster from the ports section.
  - After installing ports games using Portmaster, please update the game list.

## Switching between SD1 and SD2
- Run `Switch_SD` in the `ports` section of Emulationstation.
  - If ROM files do not appear even after updating the game list, please restart the OS.

## How to Play PICO-8
1. First, purchase a PICO-8 license from the following site and download the `Raspberry Pi` zip file.  
https://www.lexaloffle.com/pico-8.php

2. After unzipping the file, copy `pico8_64` and `pico8.dat` to the `pico-8` directory on the SD card.
3. To launch native PICO-8, start plumOS, then run `Splore.p8` in the `PICO-8` section of Emulationstation or run `Start Pico-8` in the `ports` section.
   - If `Splore.p8` and `Start Pico-8` are not available, they should be created automatically upon restarting the OS.

## How to Play ScummVM
1. Create a `game1` directory within the `scummvm` directory on the SD card.
   - If you want to play multiple games, add directories like `game2`, `game3`, etc.

2. Copy the files extracted from the game's zip file into the game1 directory.  
Example: Directory structure for Beneath a Steel Sky - Freeware Floppy Version  

```
scummvm/
`-- game1
    |-- readme.txt
    |-- sky.dnr
    `-- sky.dsk
```

3. Run `_Scan ScummVM Games` in the `ports` section of Emulationstation to create files for launching the game in the `ScummVM` section.
   - If `_Scan ScummVM Games` is not available, it should be created automatically upon restarting the OS.
4. Run `Beneath a Steel Sky (sky)` in the `ScummVM` section to start the game.

## Known Issues
> [!CAUTION]  
> Please do not enable `system settings->ENABLE OVERCLOCK` as it may cause the OS to enter a reboot loop.

- In Retroarch64bit, if the video driver is set to gl, the menu screen will rotate 90 degrees, so it is set to `sdl2` by default. If you do not use the menu much, we recommend changing to the `gl` driver, which offers better performance than `sdl2`.
- To use the PCSX_ReARMed core, the 32-bit Retroarch included in the StockOS is used. As a result, menu operations are limited (press the `G button` to display the menu).

## Automatic Creation of roms Directory
- When a formatted SD2 is connected, the OS will automatically generate the ROM directory upon startup.

## Retroarch Specifications
- Save files (srm) and state save files are created in the same directory as the ROM files (modifiable).

## Hotkey List
  - Retroarch (customizable)
  
| Button Combo | Action |
|:-----------|------------:|
| L3+R3       |        Display menu |
| SELECT+Gボタン       |        Display menu |
| SELECT+START+L+R       |        Exit |
| SELECT+R     |      Save state |
| SELECT+L     |      Load state |
| SELECT+R2     |      Fast forward (2x speed) |
| SELECT+L2     |      Slow motion (1.5x slower) |
| SELECT+X     |      Screenshot |
| SELECT+Y     |      Show/hide FPS |

---

  - Drastic (customizable)

| Button Combo | Action |
|:-----------|------------:|
| G button       |        Display menu |
| Right stick       |        Mouse operation |
| R3       |        Mouse click |

---

