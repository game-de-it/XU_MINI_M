# plumOS_XU_MINI_M

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/plumOS_XU_MINI_M.png" width="480">  

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/MagicX_logo.png" width="240">  <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc01.jpg" width="240">   

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc02.jpg" width="240">  <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc03.jpg" width="240">  


## Acknowledgements 
- Thanks and respect to the MagicX XU_MINI_M and AmberELEC development teams.

## Features 
StockOS for MagicX XU MINI M This is a modified CFW of (AmberELEC).

## Download 
[You can download the file from "Releases". ](https://github.com/game-de-it/XU_MINI_M/releases/tag/plumOS_XU_MINI_M_0.3)

## Beta 0.3 Update Information
- [FIX] It is now possible to switch between SD1 and SD2 ROM partitions


## Basic Information
- IMPORTANT! Do not enable "systemc settings"->"ENABLE OVERCLOCK" as this will cause the OS to enter a reboot loop.
- Various settings of Emulationstation are possible
- Menu with Retroarch and Drastic It is possible to display and freely configure it.
- It is possible to connect to the network using a USB Wifi dongle.
  - Supported drivers: RTL815x 8812AU 8821AU 8821CU 88x2BU
  - Samba connection (Guest) and SSH (root user, password is "amberelec ") can be used to connect.
- Portmaster is automatically installed in the "ports" directory of SD2 when the OS starts.
  - If the "ports_scripts" directory exists in SD2, delete it.
  - ports You can launch Portmaster from the section
  - After installing ports games using Portmaster, refresh the games list

## Steps to switch between SD1 and SD2
- Run "Switch_SD" in the "ports" section of Emulationstation
  - If the ROM file does not appear even after updating the game list, restart the OS.


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
