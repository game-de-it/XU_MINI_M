# plumOS Developer Information
This page explains the modifications made to stockOS to create plumOS.

## Boot Sequence
As shown in the image below, the processes are executed in order from top to bottom. The final process, `amberelec.target`, triggers the execution of `amberelec-autostart.service`, which then runs `/storage/.config/custom_start.sh`.  
<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/bootseq.svg" width="480">   

## About custom_start.sh

Towards the end of `/storage/.config/custom_start.sh`, the following lines are included:

```
# Any commands that you want to run after the frontend has started goes here
  /storage/bin/Create_ROMdir_SD.sh
  /storage/bin/portsfile.sh
  /storage/bin/pico8.sh
  /storage/bin/portmaster_install.sh
  /storage/bin/Startup_USB-AUDIO.sh
  /storage/bin/overlay.sh
  /storage/bin/TurboMode.sh &   <-(Ver0.8では"&"をつけ忘れたため、0.9で修正されます)
  sync
    exit 0
```


The roles of each script are as follows:

| Script | Action | 
|:-----------|------------:|
| /storage/bin/Create_ROMdir_SD.sh       |  Creates ROM directories on SD1 and SD2. |
| /storage/bin/portsfile.sh       |  Copies several executable files to the /storage/roms/ports directory. |
| /storage/bin/pico8.sh      |        Copies the necessary files for PICO-8. |
| /storage/bin/portmaster_install.sh     |  Installs Portmaster on SD1 and SD2. |
| /storage/bin/Startup_USB-AUDIO.sh     |  Configures USB-AUDIO settings. |
| /storage/bin/overlay.sh     |   Applies an overlay to the /usr/bin/ directory. |
| /storage/bin/TurboMode.sh     |   Sets MAX performance according to the governor status. |

## CPU, GPU, MEM Frequencies
Improvements were initiated by Gamma and shauninman, and are now being led by Gamma.

The modified `KERNEL` and `rk3562-magicx-linux.dtb` files he worked on are copied over the existing ones in the `/flash/` directory.  
The command to remount `/flash/` with write access is as follows:  
`mount -o remount,rw /dev/mmcblk0p1 /flash`

## Overlay File System
In stockOS, the overlay file system is used to gain write access to directories stored in read-only squashfs, such as `/usr/lib/libretro`.  
In plumOS, an overlay script is executed during OS startup to allow writing to the `/usr/bin` directory.

## USB-AUDIO Volume Adjustment
The stockOS kernel is built to support USB-AUDIO, and to enable its use, `/storage/bin/Startup_USB-AUDIO.sh` and `/storage/roms/ports/Switch_USB-AUDIO.sh` are used.  
These scripts ensure that if a USB-AUDIO device is connected to a USB port, `/storage/bin/vol.py` will continuously run in the background.  
`/storage/bin/vol.py` detects when the device's volume buttons are pressed and invokes the `/storage/bin/vol` script to adjust the volume.

---

End


---



# plumOS開発者情報
これはstockOSにどのような変更を加えてplumOSが出来上がっているのかを説明するページです。




## 起動シーケンス
下記の画像のように上から順番にプロセスが実行され、一番最後の`amberelec.target`によって`amberelec-autostart.service`が実行されて`/storage/.config/custom_start.sh`が実行されます。  
<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/bootseq.svg" width="480">   

## custom_start.shについて

`/storage/.config/custom_start.sh`の最後の方の行に下記のように記述されています。  

```
# Any commands that you want to run after the frontend has started goes here
  /storage/bin/Create_ROMdir_SD.sh
  /storage/bin/portsfile.sh
  /storage/bin/pico8.sh
  /storage/bin/portmaster_install.sh
  /storage/bin/Startup_USB-AUDIO.sh
  /storage/bin/overlay.sh
  /storage/bin/TurboMode.sh &   <-(Ver0.8では"&"をつけ忘れたため、0.9で修正されます)
  sync
    exit 0
```

各スクリプトの役割は下記のとおりです。  

| script | Action | 
|:-----------|------------:|
| /storage/bin/Create_ROMdir_SD.sh       |  SD1とSD2にROMディレクトリを生成します。 |
| /storage/bin/portsfile.sh       |  /storage/roms/portsディレクトリに幾つかの実行ファイルをコピーします |
| /storage/bin/pico8.sh      |        PICO-8に必要なファイルをコピーします |
| /storage/bin/portmaster_install.sh     |  SD1とSD2にPortmasterをインストールします |
| /storage/bin/Startup_USB-AUDIO.sh     |  USB-AUDIOの設定を実行します |
| /storage/bin/overlay.sh     |   /usr/bin/ディレクトリにオーバレイを設定します |
| /storage/bin/TurboMode.sh     |   ガバナーの状態に応じてMAXパフォーマンスを設定します |

## CPU,GPU,MEMの周波数について
Gamma氏とshauninman氏によって改善が開始され、現在はGamma氏が主導で改善を行ってくれています。  

彼が修正した`KERNEL`と`rk3562-magicx-linux.dtb`ファイルは`/flash/`ディレクトリに上書きコピーされています。  
`/flash/`を書き込みできるように再マウントするコマンドは下記のとおりです。  
`mount -o remount,rw /dev/mmcblk0p1 /flash`

## オーバレイfsについて
stockOSでは`/usr/lib/libretro`などの書き込み禁止のsquashfs内に保存されているディレクトリへの書き込み権限を得るために、オーバーレイfsを利用しています。  
plumOSでは`/usr/bin`ディレクトリを書き込み可能にするためのオーバレイスクリプトがOS起動時に実行されています。  

## USB-AUDIOの音量調整について
StockOSのKernelはUSB-AUDIOが利用できるようにビルドされており、それを実際に使えるようにするために`/storage/bin/Startup_USB-AUDIO.sh`と`/storage/roms/ports/Switch_USB-AUDIO.sh`が利用されます。  
これらのスクリプトによってUSB-AUDIOデバイスがUSBポートに接続されている場合、`/storage/bin/vol.py`がバックグラウンドで起動し続けるようにします。  
`/storage/bin/vol.py`は本体のボリュームボタンが押されたことを検知して`/storage/bin/vol`スクリプトを呼び出して音量を調整しています。  

---

以上










