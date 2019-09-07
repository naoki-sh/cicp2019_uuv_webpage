---
title: "New actuators are installed on UUV."
header:
  overlay_image: /assets/images/circuit/IMG_7381.JPG
  overlay_filter: rgba(255, 255, 255, 0.2)
  teaser: /assets/images/circuit/IMG_7381.JPG
toc: true
toc_sticky: true
categories:
  - blog
tags:
  - BlueROV2
  - Screw
  - Gripper
  - Sonar
author_profile: true
---
<div class="row">

<div class="medium-12  columns" markdown="1">
## 目的：水中ドローンにスクリューを搭載
本HP初めての記事は，水中ドローン (BlueROV2) の回路の換装です！

このドローンには，標準で防水仕様のスクリューが8個，LEDが4個搭載されているのですが，今回は新たに**スクリュー，ソナー，グリッパ**を追加したいと思います．
![fig2]({{ "/assets/images/circuit/Bluerov2.jpeg" | relative_url }})

<a href="https://underwaterdrone.stores.jp/items/5cfe3a0e5aa9386d2f394020">水中ドローンのスペック</a>

## 準備：なぜ回路を換装しなければならないか？
BlueROVの回路部品は，写真のように防水仕様でアクリルカプセルの中に収納されています．
![fig2]({{ "/assets/images/circuit/IMG_7371.JPG" | relative_url }})
このようにして回路部品は防水されるのですが，「アクリルの中の電子部品」を「アクリルの外のスクリュー等」に接続するために，このような特殊なエンドキャップとケーブルが使用されています．
![fig3]({{ "/assets/images/circuit/IMG_7370.JPG" | relative_url }})
ここで問題なのは，エンドキャップには，ケーブル穴が元々14個しかなく，スクリュー，ソナー，グリッパ用のケーブルを通そうとすると，穴の数が足りないということになります．そこで今回は，ケーブル穴が18個のエンドキャップを購入し，エンドキャップの取り替えに伴う回路の換装を行った次第です．

## 作業：ボトルの取り外しと回路構築
ネジをいくつか回して，そーっとアクリルボトルを取り外すとこんな感じになります．
![fig4]({{ "/assets/images/circuit/IMG_7372.JPG" | relative_url }})
ここから，どんどんバラして，，，
![fig5]({{ "/assets/images/circuit/IMG_7374.JPG" | relative_url }})
最終的にこんな感じに配線になります．(雑)
![fig7]({{ "/assets/images/circuit/IMG_7376.JPG" | relative_url }})
ここで，ワイヤ線を間違えないようにしながら，左のエンドキャップに付け替えていきます．この時，写真でも感じるかもしれませんが，下の表のようにワイヤが多くて大変です．配線を間違えないように細心の注意が必要です．

| ワイヤ線   | 本数            |
| ----: | --------------- |
| スクリュー   | 3本 ×　9個 = 27本  |
| グリッパ   | 3本 |
| ソナー   | 3本 |
| LED   | 3本 |
| 電源    | 1本|
| 通信    | 10本  |
| 合計    | 47本  |

## 動作テスト：スクリュー，グリッパ
回路の換装の最後は，バキュームポンプを使って，ボトル内部の圧力をチェックします．
![fig9]({{ "/assets/images/circuit/IMG_7384.JPG" | relative_url }})
RaspiのGPIOにスクリューとグリッパを配線して，pytohnでPWMを出力する簡単なコードを書いて動作確認をします．
{% include video id="QXPXQSdtots" provider="youtube" %}
次は，このコードをROS(Robot Operating System)で実装したいと思います.
