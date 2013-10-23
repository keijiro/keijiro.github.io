---
layout: post
title: サスティンペダル MIDI 変換器 (Arduino)
category: posts
---

![photo 1](/images/2013-09-24-1.jpg)

サスティンペダルから MIDI 信号を出力するための変換器を Arduino で作成した。事の経緯は[こちら](http://keijiro.github.io/posts/iphone_sustain_pedal/)にある通り。つまるところ microKORG にサスティンペダルを繋げたかったというだけの話だ。

Arduino と各種パーツの接続はこんな感じ。抵抗は 220Ω を使う。

![circuit](/images/2013-09-24-2.png)

実際にはこれをバニラシールド基板の上に配線するかたちにした。0.1 インチピッチに合うオーディオジャックと DIN ジャックを持ち合わせていなかったので、適当な基板接続用の端子を使ってケーブルと接続している。

プログラムは [GitHub に上げてある](https://github.com/keijiro/sustain-pedal-midi/blob/master/sustain_pedal_midi.ino)。サスティンペダルは単なるスイッチでしかないので、その状態変化に応じてシリアルからサスティンペダルの MIDI 信号を出力するだけという、非常にシンプルなプログラムだ。

これを Apple TV の空き箱に入れて使うことにした。Arduino を使った製作物を入れるにはちょうどいいサイズかもしれない。

![photo 2](/images/2013-09-24-3.jpg)

また次に暇があれば、放置時に省電力モードに入るような仕組みを考えてみたい。