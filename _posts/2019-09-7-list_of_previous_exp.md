---
title: "Experimental list (May ~ Jun)"
header:
  overlay_image: /assets/images/experiment_5_6/exp_0628_1.jpeg
  overlay_filter: rgba(255, 255, 255, 0.2)
  teaser: /assets/images/experiment_5_6/exp_0628_1.jpeg
toc: true
toc_sticky: true
categories:
  - blog
tags:
  - CICP2019
  - NAIST
  - Robotics
author_profile: true
---
<div class="row">

<div class="medium-12  columns" markdown="1">
## はじめに
このホームページは2019年8月26日に公開したのですが，UUVプロジェクト自体は5月頃から色々と活動を行ってきました．

そこで，UUVプロジェクトの活動の中で今まで行ってきた実験を紹介したいと思います．ただし，全ての実験を書くと内容が多くなってしまうので，今回の記事では**5~6月**に行った実験を紹介します！

## 2019年5月16日 カメラテスト
この実験では，BuleROV2に搭載されているカメラからの映像をROS (Robot Operating System)へ通信し，ノートPC上で再生・保存するテストを行いました．
結果として，**水中ドローンからの映像をノートPC上にリアルタイムでストリーミング**できました．以下の写真は，水槽上からの実験の様子です．
![fig1]({{ "/assets/images/experiment_5_6/exp_0516.jpeg" | relative_url }})


## 2019年6月11日 水中モーキャプテスト
この実験では，水中用のモーションキャプチャを試してみました．というのも奈良先端大では，水中モーキャプが使えるとのことで，専用ソフトの「Motive」と「ROS」で試してみました．なぜ「ROS」で扱いたいかと言うと，**水中ドローンのシステムはROSというフレームワークを使用**しているので，モーキャプもROSで扱えると色々便利な訳です．

水中で使う前に，陸上で試してみた様子がこんな感じです．
![fig2]({{ "/assets/images/experiment_5_6/exp_0611_1.jpeg" | relative_url }})

陸上でモーションを撮ってみたところ，それっぽいカメラ姿勢と，物体の位置情報が出せたので，実際に水槽に沈めてみました．
この時，Motive単体ではもちろん，**ROSでも物体の3次元座標をトピック通信**できました．実際に沈めた様子がこちらです．防水仕様とは分かっていながらも．沈める時はドキドキしました笑

![fig3]({{ "/assets/images/experiment_5_6/exp_0611_2.jpeg" | relative_url }})

本来は，水槽のすみに4つ並べないとキャリブレーションが難しいのですが，安全確保の問題から安全柵が設置されているところのみで設置しています．本音としては4つでもキツイのに一方向に3つだけとか．．．はい．

キャリブレーションワンドを使って，こんな感じでキャリブレーションをしましたが，結果は全くダメでした．原因は言うまでもないですね．
![fig4]({{ "/assets/images/experiment_5_6/exp_0611.gif" | relative_url }})

## 2019年6月14日 ゴミ収集実験1
この実験では，**初めてゴミの回収**を試しました．この時，ゴミを集める簡単な機構を取り付け，ペットボトルや缶を水槽に浮かせました．
![fig5]({{ "/assets/images/experiment_5_6/exp_0614_1.jpeg" | relative_url }})

この機構の収集アイデアは，ロボットの上の囲いにゴミが入るよう，ロボットを水面で前進させるというものです．

![fig6]({{ "/assets/images/experiment_5_6/exp_0614_2.jpeg" | relative_url }})

水面のゴミを集められるか試してみましたが，結果として完全に失敗でした．ですが，ロボットの動きや水流の影響など，たくさんの学びが得られました．
![fig7]({{ "/assets/images/experiment_5_6/exp_0614.gif" | relative_url }})

## 2019年6月18日 ゴミ収集実験2
この実験では，前回の失敗を活かして，ゴミ収集機構を２つ用意しました．
- 前回の機構に袋をつけて再チャレンジ
- **水中から上昇し，ゴミを囲いに入れる新機構**
![fig8]({{ "/assets/images/experiment_5_6/exp_0618_1.jpeg" | relative_url }})

![fig9]({{ "/assets/images/experiment_5_6/exp_0618_2.jpeg" | relative_url }})

結果として，前回の機構はやはりゴミを集めることは厳しかったです．理由はロボットの接近と同時にゴミが水流で逃げてしまうからです．
一方で，新機構は以下のgifのように，**成功率は低いもののゴミを収集することはできました．**ただし，機構的な問題はたくさん残っています．~~簡単に言うとちゃっちい?~~

![fig10]({{ "/assets/images/experiment_5_6/exp_0618.gif" | relative_url }})

## 2019年6月28日 データセット集め
この実験では，回収に関しては一旦お休みして，**ゴミの画像をたくさん撮ること**が目的です．というのも，ゴミの認識に近年流行りの機械学習を用いるため，たくさんのデータセットが必要でした．この時，水中ロボットには**GoProを設置**して写真や動画を撮影しました．ここで，アクリルの板は今後，ロボットに様々なパーツが取り付けられるように，設置しています．
![fig11]({{ "/assets/images/experiment_5_6/exp_0628_1.jpeg" | relative_url }})

以下は，gifを作成過程で少し荒くなってしまいましたが実際の様子です．(俯瞰視点，GoPro視点)

![fig12]({{ "/assets/images/experiment_5_6/exp_0628_1.gif" | relative_url }})

![fig13]({{ "/assets/images/experiment_5_6/exp_0628_2.gif" | relative_url }})
