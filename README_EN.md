# plumOS_XU_MINI_M

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/plumOS_XU_MINI_M.png" width="480">  

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/MagicX_logo.png" width="240">  <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc01.jpg" width="240">   

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc02.jpg" width="240">  <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc03.jpg" width="240">  


## Acknowledgements 
- Thanks and respect to the MagicX XU_MINI_M and AmberELEC development teams.

## Features 
StockOS for MagicX XU MINI M This is a modified CFW of (AmberELEC).

## Download 
[You can download the file from "Releases". ](https://github.com/game-de-it/XU_MINI_M/releases/tag/plumOS_XU_MINI_M_0.1)

## Beta 0.2 update information 
- [NEW] Portmaster now works
- [FIX] Emulationstation Changed each item in "GAME SETTINGS"->"DEFAULT GLOBAL SETTINGS" to AUTO
- [FIX] Prevented the "ports_scripts" directory from being generated in SD2


## Basic Information
- Important! Since it will not work properly with only SD1, be sure to use SD2 formatted with FAT32 or exFAT
(SD2 used with StockOS can be used as is)  
- Various settings of Emulationstation are possible
- Menu with Retroarch and Drastic It is possible to display and freely configure it.
- It is possible to connect to the network using a USB Wifi dongle.
  - Supported drivers: RTL815x 8812AU 8821AU 8821CU 88x2BU
  - Samba connection (Guest) and SSH (root user, password is "amberelec ") can be used to connect.
- [NEW] Portmaster is automatically installed in the "ports" directory of SD2 when the OS starts.
  - If the "ports_scripts" directory exists in SD2, delete it.
  - ports You can launch Portmaster from the section
  - After installing ports games using Portmaster, refresh the games list

## Known issues
- In Retroarch 64bit, if you set the video driver to the gl driver, the menu screen will rotate 90 degrees, so the OS is set to "sdl2" when shipped. If you rarely use menu operations, you should set it to "gl", which has better performance than "sdl2". We recommend changing the driver.
- To use the PCSX_ReARMed core, we use Retroarch32bit included in StockOS.
As a result, menu operations are limited  
(press the "G" button to display the menu)

## Automatic creation of roms directory 
- When you start the OS with a formatted SD2 connected, the ROM directory will be automatically generated.

## Retroarch specifications 
- Save files (srm) and state save files are It will be created in the same directory as the ROM file (can be changed)

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
| SELECT+Y | Show/Hide FPS |

---

- ​​Drastic (can be changed freely)

| Button Combo | Action |
|:-----------|------------:|
| G button | Display menu |
| Right stick | Mouse operation |
| R3 | Mouse click |

---

End
