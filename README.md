# plumOS_XU_MINI_M
[Click here for the English version of the explanation page](https://github.com/game-de-it/XU_MINI_M/blob/main/README_EN.md)  

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/plumOS_XU_MINI_M.png" width="480">   

  <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/MagicX_logo.png" width="240">    <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc01.jpg" width="240">   
  
  <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc02.jpg" width="240">   <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc03.jpg" width="240">   




## 謝辞
- MagicX XU_MINI_MおよびAmberELECの開発チーム、XU MINI Mを愛するコミュニティーメンバーに感謝と敬意を表します。

## 特徴
MagicX XU MINI MのStockOS(AmberELEC)を改修したCFWです。 

## ダウンロード
[「Releases」からファイルをダウンロードできます。](https://github.com/game-de-it/XU_MINI_M/releases/tag/plumOS_XU_MINI_M_0.4)  

## Beta 0.4更新情報
- [NEW] ネイティブのPICO-8が起動可能になり、ネットワークを使ってゲームをDLすることが可能になりました
- [NEW] ScummVMスタンドアローンが起動できるようになりました

## 基本情報
> [!CAUTION]  
> OSが再起動ループをしてしまうため、`system settings->ENABLE OVERCLOCK`を有効にしないでください

- Emulationstationの各種設定が可能
- RetroarchとDrasticでメニュー表示が可能になり、設定を自由にすることが可能
- USB Wifiドングルでネットワークへの接続が可能
  - 対応ドライバ : RTL815x 8812AU 8821AU 8821CU 88x2BU
  - samba接続(`Guest`ユーザ)およびSSH(`root`ユーザ、パスワードは`amberelec`)で接続可能です
- PortmasterはOS起動時に自動的にSDの`ports`ディレクトリへインストールされます
  - SD2に`ports_scripts`ディレクトリが存在する場合は、そのディレクトリを削除してください
  - portsセクションからPortmasterを起動できます
  - Portmasterを利用してportsゲームをインストールした後はゲームリストを更新してください


## SD1とSD2を切り替える手順
- Emulationstationの`ports`セクションにある`Switch_SD`を実行します
  - ゲームリストをアップデートしてもROMファイルが表示されない場合は、OSの再起動をしてください
 
## PICO-8の遊び方
1. まず初めに下記サイトからPICO-8のライセンスを購入して、`Raspberry Pi`のzipファイルをダウンロードします
https://www.lexaloffle.com/pico-8.php

2. zipファイルを解凍したら`pico8_64`と`pico8.dat`を、SDカードの`pico-8`ディレクトリにコピーします
3. ネイティブのPICO-8を起動したい場合はplumOSを起動した後、Emulationstationの`PICO-8`セクションにある`Splore.p8`を実行するか、`ports`セクションにある`Start Pico-8`を実行してください
   - `Splore.p8`と`Start Pico-8`がない場合はOSを再起動すると自動的に作成されるはずです

## ScummVMの遊び方
1. SDカード内の`scummvm`ディレクトリ内に`game1`ディレクトリを作成します  
    - 複数のゲームを遊びたい場合は`game2` `game3`などのディレクトリを追加してください
    
2. game1ディレクトリ内にゲームのzipファイルを解凍してできたファイルをコピーします  
例) Beneath a Steel Sky - Freeware Floppy Versionのディレクトリ構成  

```
scummvm/
`-- game1
    |-- readme.txt
    |-- sky.dnr
    `-- sky.dsk
```

3. Emulationstationの`ports`セクションにある`_Scan ScummVM Games`を実行すると、`ScummVM`セクションにゲームを起動するためのファイルが作成されます
   - `_Scan ScummVM Games`がない場合はOSを再起動すると自動的に作成されるはずです
4. `ScummVM`セクションの`Beneath a Steel Sky (sky)`を実行するとゲームが開始します

## 既知の問題
> [!CAUTION]  
> OSが再起動ループをしてしまうため、`system settings->ENABLE OVERCLOCK`を有効にしないでください

- Retroarch64bitではビデオドライバをglドライバにするとメニュー画面が90度回転してしまうため、OS出荷時には`sdl2`に設定してあります
メニュー操作をほとんどしない方は、`sdl2`よりもパフォーマンスがよい`gl`ドライバへの変更をお勧めします  
- PCSX_ReARMedコアを利用するために、StockOSに内包されているRetroarch32bitを利用します  
そのためメニュー操作が限られます（メニューを表示するには`Gボタン`を押してください）

## romsディレクトリの自動作成
- フォーマットされたSD2を接続した状態でOSを起動すると、自動的にROMディレクトリを生成してくれます  

## Retroarch仕様
- セーブファイル(srm)およびステートセーブファイルは、ROMファイルと同じディレクトリ内に作成されます(変更可能)

## ホットキー一覧
  - Retroarch(自由に変更可能)
  
| Button Combo | Action | 
|:-----------|------------:|
| L3+R3       |        メニュー表示 |
| SELECT+Gボタン       |        メニュー表示 |
| SELECT+START+L+R       |        終了 |
| SELECT+R     |      ステートセーブ |
| SELECT+L     |      ステートロード |
| SELECT+R2     |      fastforward(2倍速) |
| SELECT+L2     |      スローモーション(1.5倍遅くなる) |
| SELECT+X     |      スクリーンショット |
| SELECT+Y     |      FPS表示/非表示 |

---

  - Drastic(自由に変更可能)

| Button Combo | Action | 
|:-----------|------------:|
| Gボタン       |        メニュー表示 |
| 右スティック       |        マウス操作 |
| R3       |        マウスクリック |

---

以上
