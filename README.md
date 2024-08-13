# plumOS_XU_MINI_M
[Click here for the English version of the explanation page](https://github.com/game-de-it/XU_MINI_M/blob/main/README_EN.md)  

<img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/plumOS_XU_MINI_M.png" width="480">   

  <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/MagicX_logo.png" width="240">    <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc01.jpg" width="240">   
  
  <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc02.jpg" width="240">   <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/sc03.jpg" width="240">   




## 謝辞
- MagicX XU_MINI_MおよびAmberELECの開発チーム、XU MINI Mを愛するコミュニティーメンバーに感謝と敬意を表します。

## 特徴
MagicX XU MINI MのStockOS_20240811(AmberELEC)を改修したCFWです。 

## ダウンロード
[「Releases」からファイルをダウンロードできます。](https://github.com/game-de-it/XU_MINI_M/releases/tag/plumOS_XU_MINI_M_0.5)  

## Beta 0.5更新情報
- [FIX] 不必要になったportsファイルを削除しました
- [NEW] StockOS_20240811がベースになりました
- [NEW] CPUクロックの可動範囲が400MHz~1500MHzに変更されました
  - 変更前の可動域は1000MHz~1300MHz
  - これは実験的な機能なのでなんらかの問題が生じる可能性があります
  - コミュニティの皆さんに感謝します！
- [NEW] USB-DACおよびBluetooth AUDIOに対応しました
> [!WARNING]
> 全てのUSB-DACおよびBluetooth AUDIOで動作することは保証しません。    
> 音量調整できない機器があるため大音量で音が流れる可能性があります。  
> 初めて利用する場合はイヤホンを耳に装着せずに音を鳴らしてください。  
> スピーカーに接続する場合は、スピーカー側の音量をあらかじめ小さくしてから音を鳴らしてください。  
> エミュレーターによっては音が途切れたり、動作が不安定になる場合があります。  


## 基本情報
- USB Wifiドングルでネットワークへの接続が可能
  - 対応ドライバ : RTL815x 8812AU 8821AU 8821CU 88x2BU
  - samba接続(`Guest`ユーザ)およびSSH(`root`ユーザ、パスワードは`amberelec`)で接続可能です
- PortmasterはOS起動時に自動的にSDの`ports`ディレクトリへインストールされます
  - SDカードに`ports_scripts`ディレクトリが存在する場合は、そのディレクトリを削除してください
  - portsセクションからPortmasterを起動できます
  - Portmasterを利用してportsゲームをインストールした後はゲームリストを更新してください

---

## 既知の問題
> [!CAUTION]  
> OSが再起動ループをしてしまうため、`system settings->ENABLE OVERCLOCK`を有効にしないでください

---


## ROMディレクトリの自動作成
- FAT32でフォーマットされたSD2を接続した状態でOSを起動すると、自動的にROMディレクトリを生成してくれます


## SD1とSD2を切り替える手順
- Emulationstationの`TF CARD MANAGEMENT`にある機能を使うと、SD1とSD2のROMディレクトリがあるパーティションを切り替えることができます

> [!TIP]
> SD2を利用するメリットは、OSのアップデートをするたびにROMファイルを準備する必要がなくなることです。


## USB-DACおよびBluetooth AUDIOの使い方
1. USBポートに機器を接続した後に、`ports`セクションにある`Switch_USB-AUDIO`を実行します
    - 自動的に内部スピーカーへは切り替わらないので、内部スピーカーに戻したい時はもう一度`Switch_USB-AUDIO`を実行します
3. Bluetooth機器の場合はペアリングをします
    - 動作確認済みの型番 `GuliKit Route Air`
4. ゲームを起動して音が出ることを確認します
> [!WARNING]
> 全てのUSB-DACおよびBluetooth AUDIOで動作することは保証しません。    
> 音量調整できない機器があるため大音量で音が流れる可能性があります。  
> 初めて利用する場合はイヤホンを耳に装着せずに音を鳴らしてください。  
> スピーカーに接続する場合は、スピーカー側の音量をあらかじめ小さくしてから音を鳴らしてください。  
> エミュレーターによっては音が途切れたり、動作が不安定になる場合があります。  

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
