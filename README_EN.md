# plumOS_XU_MINI_M
[Click here for the English version of the explanation page](https://github.com/game-de-it/XU_MINI_M/blob/main/README_EN.md)

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/plumOS_XU_MINI_M.png" width="480">

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/MagicX_logo.png" width="240"> <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc01.jpg" width="240">

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc02.jpg" width="240"> <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc03.jpg" width="240">

## Features
This is a CFW modified from the StockOS_20240811 (AmberELEC) of the MagicX XU MINI M.

## Download
[You can download the files from "Releases".](https://github.com/game-de-it/XU_MINI_M/releases/tag/plumOS_XU_MINI_M_0.6)

## Acknowledgments
- We express our gratitude and respect to the development teams of MagicX XU_MINI_M and AmberELEC, as well as to the community members who love the XU MINI M.
- Contributors (in no particular order)
  - fishku, Ry, snake, shauninman, Gamma, and All Retro Handhelds community members!

## Beta 0.6 Update Information
- [FIX] The process of automatically generating ROM directories has been revised, and unnecessary directories like "wii" have been removed.
- [FIX] Various settings in Emulationstation's `DEFAULT GLOBAL SETTINGS` and `ADVANCED SYSTEM OPTIONS` have been revised.
- [FIX] Additions/fixes related to Retroarch:
    - Some default settings have been changed.
    - Several shaders have been added.
    - Several overlay filters have been added.
    - Scrolling processes in SNES9X have been made smoother.
- [NEW] Added support for volume control on more USB-DAC devices.
- [NEW] A feature to automatically install themes for Emulationstation has been added (usage is explained later).

## Basic Information
- You can connect to the network using a USB Wifi dongle.
  - Supported drivers: RTL815x 8812AU 8821AU 8821CU 88x2BU
  - Connection is possible via samba (`Guest` user) and SSH (`root` user, password is `amberelec`).
- Portmaster is automatically installed in the `ports` directory of the SD card upon OS startup.
  - If the `ports_scripts` directory exists on the SD card, please delete that directory.
  - You can start Portmaster from the ports section.
  - After installing a ports game using Portmaster, please update the game list.
- The CPU frequency will automatically increase or decrease between 400MHz and 1500MHz depending on the load.
  - However, if you press the SELECT button on the ROM selection screen and set ENABLE MAX PERFORMANCE in ADVANCED SYSTEM OPTIONS to ON, it will always run at 1500MHz.
  - To run it at 1500MHz on all emulators, set GAME SETTINGS -> ENABLE MAX PERFORMANCE to ON in Emulationstation.

---

## Known Issues
> [!CAUTION]  
> Do not enable `system settings->ENABLE OVERCLOCK`, as it may cause the OS to enter a reboot loop.

---

## Automatic Creation of ROM Directories
- If you boot the OS with an SD2 formatted in FAT32 connected, ROM directories will be automatically generated.
- By executing `Create_ROMdir_SD` in the `ports` section, ROM directories will be created on both SD1 and SD2.

## Procedure to Switch Between SD1 and SD2
- You can switch the partition containing the ROM directories for SD1 and SD2 using the feature in Emulationstation's `TF CARD MANAGEMENT`.

> [!TIP]
> The advantage of using SD2 is that you won't need to prepare ROM files every time you update the OS.

## How to Use USB-DAC and Bluetooth AUDIO
### Specifications
- Bluetooth AUDIO dongles confirmed to work:
  - Creative BT-W2
  - GuliKit Route Air  
- To revert back to the internal speakers, execute `Switch_USB-AUDIO` again.
- If you reboot the OS with the USB-DAC or Bluetooth AUDIO disconnected from the USB port, it will automatically switch back to the internal speakers.
- If the device does not switch after running `Switch_USB-AUDIO`, try unplugging the device from the USB port and plugging it back in.

### Usage
1. After connecting the device to the USB port, execute `Switch_USB-AUDIO` in the `ports` section.
2. For Bluetooth devices, perform pairing.
3. Start a game and confirm that sound is output.
> [!WARNING]
> It is not guaranteed that all USB-DAC and Bluetooth AUDIO devices will work.  
> Some devices may have issues with volume control, leading to very loud audio.  
> Depending on the emulator, sound may cut out or operation may become unstable.

## Automatic Installation of Themes in Emulationstation
1. Copy the theme file (.zip) for Emulationstation to the `ports/themes` directory on the SD card.
2. Execute `Install_Themes` in the ports section of Emulationstation.
3. You can select the installed theme from `UI SETTINGS`->`THEME SET`.

## How to Play PICO-8
1. First, purchase a PICO-8 license from the following site and download the `Raspberry Pi` zip file:
   https://www.lexaloffle.com/pico-8.php
2. After unzipping the file, copy `pico8_64` and `pico8.dat` to the `pico-8` directory on the SD card.
3. If you want to start the native PICO-8, boot plumOS, then execute `Splore.p8` in the `PICO-8` section of Emulationstation or `Start Pico-8` in the `ports` section.
   - If `Splore.p8` and `Start Pico-8` are missing, they should be automatically created upon rebooting the OS.

## How to Play ScummVM
1. Create a `game1` directory within the `scummvm` directory on the SD card.
    - If you want to play multiple games, add directories like `game2`, `game3`, etc.
2. Copy the files extracted from the game's zip file into the game1 directory.  
Example) Directory structure for Beneath a Steel Sky - Freeware Floppy Version:

```
scummvm/
`-- game1
    |-- readme.txt
    |-- sky.dnr
    `-- sky.dsk
```


3. Execute `_Scan ScummVM Games` in the `ports` section of Emulationstation, and a file to start the game will be created in the `ScummVM` section.
   - If `_Scan ScummVM Games` is missing, it should be automatically created upon rebooting the OS.
4. Execute `Beneath a Steel Sky (sky)` in the `ScummVM` section to start the game.

## Retroarch Specifications
- Save files (srm) and state save files are created in the same directory as the ROM file (this can be changed).

## Hotkey List
  - Retroarch (can be freely changed)
  
| Button Combo | Action | 
|:-----------|------------:|
| L3+R3       |        Show Menu |
| SELECT+G Button       |        Show Menu |
| SELECT+START+L+R       |        Quit |
| SELECT+R     |      Save State |
| SELECT+L     |      Load State |
| SELECT+R2     |      Fast forward (2x speed) |
| SELECT+L2     |      Slow motion (1.5x slower) |
| SELECT+X     |      Screenshot |
| SELECT+Y     |      Toggle FPS display |

---

  - Drastic (can be freely changed)

| Button Combo | Action | 
|:-----------|------------:|
| G Button       |        Show Menu |
| Right Stick       |        Mouse Operation |
| R3       |        Mouse Click |

---

That's all.

