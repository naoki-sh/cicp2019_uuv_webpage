---
title: "Develop ROS wrapper of screw, gripper and sonar"
header:
  overlay_image: /assets/images/ROS_wrapper/ROSicon.png
  overlay_filter: rgba(255, 255, 255, 0.2)
  teaser: /assets/images/ROS_wrapper/ROSicon.png
toc: true
toc_sticky: true
categories:
  - blog
tags:
  - ROS
  - screw
  - gripper
  - sonar
  - BlueRobotics
author_profile: true
---
<div class="row">

<div class="medium-12  columns" markdown="1">
## はじめに
 [前回の記事](https://naoki-sh.github.io/cicp2019_uuv_webpage/blog/Circuit-configuration-change/)で水中ドローンに新たにスクリュー，グリッパ，ソナーの回路を配線し，動作テストを行ったのですが，今回はその続きでROS (Robot Operating System)で実装を紹介したいと思います！
  ちなみに，タイトルにある**wrapper(ラッパー)**は，あるプログラム言語で書かれているライブラリやモジュール等を別のプログラミング言語，あるいはフレームワーク等で実装したものを指します．
 そもそも，pythonスクリプトで動作テストができたなら，なんでわざわざROSに実装する必要があるの？の感じた人もいると思うので，わざわざROSで実装する理由を挙げると，(個人的な意見)

- システム開発が容易 (ROSの恩恵を享受できる)
- 水中ドローンとスクリューやグリッパ，ソナーを通信可能

ということです．
 ここで更に，ROSの恩恵って何やねん！と思った方もいると思うのですが，その恩恵は沢山ありすぎてここでは説明しきれないので，今度の記事にさせてください．．．
ROSで実装する理由を簡単な言葉で言い換えると，**一人で遊んでいたスクリュー君をロボットクラブに勧誘して，ドローン君とスクリュー君を一緒に遊ばせてあげたい** 訳です．

## 目的と準備
 はいということで，**ドローン君とスクリュー君を一緒に遊ばせてあげること** が目的です．
ここで，もう１つ確認しなければならないポイントがあります．それは，**ドローン君はノートPC**，**スクリュー君はraspberryPi**にそれぞれ接続されているということです．
ROSは複数のロボットやPC間で分散システムの構築が可能です．ドローン君からスクリュー君を制御するためには，raspi上にROSのワークスペースが必要になります．
raspi上にROSの環境構築をする場合，

- Rasbian上にROSをインストール
- Ubuntu上にROSをインストール

の2つの方法があります．大きな違いはないのですが，筆者は前者で実装しています．
長い前置きになりましたが，準備としてraspiにROSをインストールして，ワークスペースを作成することが必要となります．

## 手順
さて，長い前置きになってしまいましたが，手順は以下のレポジトリをクローンするだけです．[詳しくは，Readmeを見て下さい.](https://github.com/kumahika/GPIO_output)
```vb
$ cd ~/your_ws/src
$ gitclone https://github.com/kumahika/GPIO_output
```


## 実験
実際の水槽でROSを利用してスクリュー，グリッパーを動かしてみました．
少々見づらいのですが，よく見るとスクリューが水中で回転しているのが見えるかと思います．

![fig1]({{ "/assets/images/ROS_wrapper/screw.gif" | relative_url }})

グリッパーもぜひ！
![fig2]({{ "/assets/images/ROS_wrapper/gripper.gif" | relative_url }})

今回の実装で，新しく設置したスクリュー，グリッパー，ソナーを**ROSで簡単に操作できるようになりました!**

## まとめ
この記事の情報量だけで，同様なことができるかと言えば，難しいところがあるかもしれません．かっこよく言えばノウハウになるのですが，単純に書き漏らしてる内容もあるかと思います．具体的に質問がある方はメールかgithubでお願いします．
