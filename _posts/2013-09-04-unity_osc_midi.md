---
layout: post
title: Unity と OSC, MIDI
category: posts
---

Unity 上で OSC と MIDI を使用するためのいくつかのプラグインを開発しました。

## 開発の目的

Unity と音楽の同期を実現することが目的です。そのため、これらのプラグインは OSC や MIDI の信号を受信あるいは再生することに特化しています。OSC や MIDI の送信側になることは考慮していません。

## プラグイン群

以下のプラグインを開発しました。

### unity-osc

UDP 経由で送信された OSC を受信するためのプラグイン (C#)

- [keijiro/unity-osc](https://github.com/keijiro/unity-osc)

### unity-midi-receiver

MIDI インタフェースから入力された MIDI 信号を受信するためのプラグイン (native)

- [keijiro/unity-midi-receiver](https://github.com/keijiro/unity-midi-receiver)
- [keijiro/unity-midi-receiver-windows](https://github.com/keijiro/unity-midi-receiver-windows)

### smflite

SMF (Standard MIDI File) からタイミング情報を取得（再生）するためのプラグイン (C#)

- [keijiro/smflite](https://github.com/keijiro/smflite)

## 何ができるのか

unity-osc を使えば、例えば TouchOSC のような OSC コントローラーから遠隔操作が可能になります -- [TouchOSC の使用例](https://vine.co/v/hbwuvZx2Ybd)

また、Duration のような OSC ベースのソフトウェアとの連携も容易に実現できます -- [Duration の使用例](https://vine.co/v/hhqtAuWXMZz)

unity-midi-receiver を使用すると、一般的な MIDI 機器を入力に用いることが可能になります。例えば、鍵盤でピアノを弾きつつ、それに合わせてリアルタイムにアニメーションを生成する、などということも簡単にできます -- [MIDI 鍵盤の使用例](http://vimeo.com/72337792)

リアルタイムではない、録音された音源との連携には smflite が適しています。SMF ファイル（mid ファイル）からノート情報を取り出し、それと Unity の同期を実現します -- [ピアノ演奏との連携例](http://keijiro.github.io/unity-smf-test/piano.html)
