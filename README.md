# plumOS_XU_MINI_M
[Click here for the English version of the explanation page](https://github.com/game-de-it/XU_MINI_M/blob/main/README_EN.md)  

  <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/plumOS_XU_MINI_M.png" width="480">  <img src="https://github.com/game-de-it/XU_MINI_M/blob/main/assets/MagicX_logo.png" width="240">  

## 謝辞
- MagicX XU_MINI_MおよびAmberELECの開発チームに感謝と敬意を表します。

## 特徴
MagicX XU MINI MのStockOS(AmberELEC)を改修したCFWです。 

## ダウンロード
[「Releases」からファイルをダウンロードできます。](https://github.com/game-de-it/XU_MINI_M/releases/tag/plumOS_XU_MINI_M_0.1)  

## 更新情報
- [NEW] β版 Ver 0.1をリリース！  

## 基本情報
- 重要！　SD1のみでは正常に動作しないため、必ずFAT32およびexFATでフォーマットされたSD2を利用してください  
(StockOSで利用していたSD2はそのまま利用可能です)
- Emulationstationの各種設定が可能
- RetroarchとDrasticでメニュー表示が可能になり、設定を自由にすることが可能
- USB Wifiドングルでネットワークへの接続が可能
  - 対応ドライバ : RTL815x 8812AU 8821AU 8821CU 88x2BU
  - samba接続(Guest)およびSSH(rootユーザ、パスワードは"amberelec")で接続可能です

## 既知の問題
- Retroarch64bitではビデオドライバをglドライバにするとメニュー画面が90度回転してしまうため、OS出荷時には"sdl2"に設定してあります  
メニュー操作をほとんどしない方は、"sdl2"よりもパフォーマンスがよい"gl"ドライバへの変更をお勧めします  
- PCSX_ReARMedコアを利用するために、StockOSに内包されているRetroarch32bitを利用します  
そのためメニュー操作が限られます（メニューを表示するには"Gボタン"を押してください）

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
