# plumOS_XU_MINI_M

  <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/plumOS_XU_MINI_M.png" width="480">    <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc01.jpg" width="480">  
  <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/MagicX_logo.png" width="240">  

## Acknowledgements
- We would like to express our gratitude and respect to the development team of MagicX XU_MINI_M and AmberELEC.

## Features
This is a CFW that modifies StockOS (AmberELEC) for MagicX XU MINI M.

## Download
[You can download the file from "Releases".](https://github.com/game-de-it/XU_MINI_M/releases/tag/plumOS_XU_MINI_M_0.1)

## Update Information
- [NEW] Beta version 0.1 released!

## Basic Information
- Important! Since SD1 alone will not work properly, please make sure to use SD2 formatted with FAT32 or exFAT.   
(SD2 used with StockOS can be used as is)
- Various settings of Emulationstation are possible
- Menu display is possible with Retroarch and Drastic, and settings can be freely configured
- Network connection is possible with USB Wifi dongle
  - Supported drivers: RTL815x 8812AU 8821AU 8821CU 88x2BU
  - Connection is possible with samba connection (Guest) and SSH (root user, password is "amberelec")

## Known issues
- In Retroarch 64bit, if the video driver is set to the gl driver, the menu screen will rotate 90 degrees, 
so it is set to "sdl2" when shipped with the OS. If you rarely operate the menu, we recommend changing to the "gl" driver, which has better performance than "sdl2".
- To use the PCSX_ReARMed core, use Retroarch 32bit included in StockOS.
Therefore, menu operations are limited (press the "G button" to display the menu)

## Automatic creation of roms directory
- When you start the OS with a formatted SD2 connected, it will automatically generate a ROM directory

## Retroarch specifications
- Save files (srm) and state save files are created in the same directory as the ROM file (can be changed)

## List of hotkeys
- Retroarch (can be changed freely)

| Button Combo | Action |
|:-----------|------------:|
| L3+R3 | Display menu |
| SELECT+G button | Display menu |
| SELECT+START+L+R | Exit |
| SELECT+R | Save state |
| SELECT+L | Load state |
| SELECT+R2 | Fastforward (2x speed) |
| SELECT+L2 | Slow motion (1.5x slower) |
| SELECT+X | Screenshot |
| SELECT+Y | Show/hide FPS |

---

- Drastic (can be changed freely)

| Button Combo | Action |
|:-----------|------------:|
| G button | Show menu |
| Right stick | Mouse operation |
| R3 | Mouse click |

---

The end
