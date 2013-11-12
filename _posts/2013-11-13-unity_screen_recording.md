---
layout: post
title: Unity から連番ビットマップを出力する
category: posts
---

<div class="videoframe"><iframe src="//player.vimeo.com/video/79190321" width="600" height="337" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div>

Unity から連番ビットマップを出力して Final Cut で動画にするまでのワークフローを整理した。上の映像はそのテスト。このプロジェクトは実機でもリアルタイムに動作するけれど、動画を出力しながらの実行では流石に処理落ちする。このような処理落ちを回避したい場合に、このテクニックは便利だ。

Unity からの出力
----------------

Unity の画面をキャプチャーするには [<code>Application.CaptureScreenshot</code>](http://docs.unity3d.com/Documentation/ScriptReference/Application.CaptureScreenshot.html) を使う。ただし、この関数を使って毎フレームキャプチャーを行うと、当然処理落ちする。処理落ちをそのままにキャプチャーを続けるとフレームの欠落が生じてしまう。

このようなフレームの欠落を防ぐには [<code>Time.captureFramerate</code>](http://docs.unity3d.com/Documentation/ScriptReference/Time-captureFramerate.html) が使える。これにフレームレートを設定すると、Unity は実時間の進行を無視して、固定の <code>deltaTime</code> で進行するようになる。

これらの機能を使って連番でフレームを出力するようなスクリプトを組めばいい。例えば[こんな感じ](https://gist.github.com/keijiro/7429201)でいいと思う。

あとは、出力の前に Game ビューの大きさを調整しておく必要がある。画面が狭い場合は <code>CaptureScreenshot</code> の <code>superSize</code> 引数との組み合わせ技を使うといいかもしれない。例えば 720p の映像を作りたいなら、下図のように Game ビューの大きさを半分の 360 に設定しておいて、<code>superSize</code> には 2 を設定する。

![Game View Setting](/images/2013-11-13-1.png)

Final Cut への入力
------------------

Final Cut 側では、普通に Media Import 画面を経由して連番ビットマップを取り込むことができる。

![Media Import](/images/2013-11-13-2.png)

取り込んだ連番をタイムライン上に配置し、メニューの Modify から Change Duration を選択する。

![Change Duration](/images/2013-11-13-3.png)

ここで 1 を入力することにより、各静止画クリップの長さを 1 フレームに縮めることができる。若干分かりにくいのだけれど、画面中央のインジケーターが入力可能状態になっているので、"1" と入れたあとにリターンキーを押すだけでいい。

![Changing Clip Length](/images/2013-11-13-4.png)

あとは好きなフォーマットで出力するだけ。凝った編集を行いたい場合は、一旦 QuickTime 形式で出力してから、それを別プロジェクトに取り込むようにするといいかもしれない。
