# plumOS_XU_MINI_M

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/plumOS_XU_MINI_M.png" width="480">   

  <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/MagicX_logo.png" width="240">    <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc01.jpg" width="240">   
  
  <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc02.jpg" width="240">   <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc03.jpg" width="240">   




## Acknowledgments
- We express our gratitude and respect to the development teams of MagicX XU_MINI_M and AmberELEC, and to the community members who love XU MINI M.

## Features
This is a custom firmware (CFW) modified from the StockOS_20240811 (AmberELEC) of MagicX XU MINI M.

## Download
[You can download the files from the "Releases" section.](https://github.com/game-de-it/XU_MINI_M/releases/tag/plumOS_XU_MINI_M_0.5)

## Beta 0.5 Update Information
- [FIX] Removed unnecessary ports files.
- [NEW] Based on StockOS_20240811.
- [NEW] CPU clock range changed to 400MHz~1500MHz.
  - The previous range was 1000MHz~1300MHz
  - This is an experimental feature, so there may be some issues.
  - Thanks to the community!
- [NEW] Support for USB-DAC and Bluetooth AUDIO.
> [!WARNING]
> We do not guarantee that all USB-DACs and Bluetooth AUDIO devices will work.  
> Some devices may not allow volume adjustment, resulting in potentially loud audio output.  
> When using for the first time, please play the audio without wearing headphones.  
> If connecting to speakers, reduce the volume on the speaker before playing audio.  
> In some emulators, sound may cut out or the operation may become unstable.

## Basic Information
- Network connection is possible via USB Wi-Fi dongle.
  - Supported drivers: RTL815x, 8812AU, 8821AU, 8821CU, 88x2BU.
  - Connection is possible via samba (`Guest` user) and SSH (`root` user, password: `amberelec`).
- Portmaster will be automatically installed into the `ports` directory on the SD card when the OS boots up.
  - If the `ports_scripts` directory exists on the SD card, please delete it.
  - You can start Portmaster from the ports section.
  - After installing ports games using Portmaster, please refresh the game list.

---

## Known Issues
> [!CAUTION]  
> Do not enable `system settings->ENABLE OVERCLOCK` as it may cause the OS to enter a reboot loop.

---

## Automatic ROM Directory Creation
- When you start the OS with SD2 formatted in FAT32 connected, ROM directories will be automatically generated.

## Procedure for Switching Between SD1 and SD2
- You can switch SD cards from Emulationstation's `TF CARD MANAGEMENT`.

## How to Use USB-DAC and Bluetooth AUDIO
1. After connecting the device to the USB port, run `Switch_USB-AUDIO` in the `ports` section.
    - It will not automatically switch to the internal speaker, so if you want to switch back to the internal speaker, run `Switch_USB-AUDIO` again.
2. For Bluetooth devices, pair them.
    - - Operation-confirmed model number `GuliKit Route Air`
3. Start a game and confirm that audio is playing.
> [!WARNING]
> We do not guarantee that all USB-DACs and Bluetooth AUDIO devices will work.  
> Some devices may not allow volume adjustment, resulting in potentially loud audio output.  
> When using for the first time, please play the audio without wearing headphones.  
> If connecting to speakers, reduce the volume on the speaker before playing audio.  
> In some emulators, sound may cut out or the operation may become unstable.

## How to Play PICO-8
1. First, purchase a PICO-8 license from the site below and download the `Raspberry Pi` zip file.  
https://www.lexaloffle.com/pico-8.php

2. After unzipping the file, copy `pico8_64` and `pico8.dat` to the `pico-8` directory on your SD card.
3. If you want to launch the native PICO-8, start plumOS and then either run `Splore.p8` in the `PICO-8` section of Emulationstation, or run `Start Pico-8` in the `ports` section.
   - If `Splore.p8` and `Start Pico-8` are not available, they should be created automatically after restarting the OS.

## How to Play ScummVM
1. Create a `game1` directory within the `scummvm` directory on your SD card.  
    - If you want to play multiple games, add directories like `game2`, `game3`, etc.
    
2. Copy the files extracted from the game's zip file into the `game1` directory.  
Example) Beneath a Steel Sky - Freeware Floppy Version directory structure

```
scummvm/
`-- game1
    |-- readme.txt
    |-- sky.dnr
    `-- sky.dsk
```

3. Run `_Scan ScummVM Games` in the `ports` section of Emulationstation to create files for starting the game in the `ScummVM` section.
   - If `_Scan ScummVM Games` is not available, it should be created automatically after restarting the OS.
4. Start `Beneath a Steel Sky (sky)` in the `ScummVM` section to begin the game.

## Retroarch Specifications
- Save files (.srm) and state save files are created in the same directory as the ROM files (this can be changed).

## Hotkey List
  - Retroarch (freely customizable)
  
| Button Combo | Action | 
|:-----------|------------:|
| L3+R3       |        Display menu |
| SELECT+G button       |        Display menu |
| SELECT+START+L+R       |        Exit |
| SELECT+R     |      Save state |
| SELECT+L     |      Load state |
| SELECT+R2     |      Fast forward (2x speed) |
| SELECT+L2     |      Slow motion (1.5x slower) |
| SELECT+X     |      Screenshot |
| SELECT+Y     |      Show/hide FPS |

---

  - Drastic (freely customizable)

| Button Combo | Action | 
|:-----------|------------:|
| G button       |        Display menu |
| Right stick       |        Mouse operation |
| R3       |        Mouse click |

---

That's all.
