---
layout: post
title: MIDI Input プラグイン (Unity, C#)
category: posts
---

<div  class="videoframe"><iframe src="//player.vimeo.com/video/78024247" width="600" height="337" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div>

[github.com/keijiro/unity-midi-input](https://github.com/keijiro/unity-midi-input)

Unity で外部 MIDI デバイスからの入力を扱うためのプラグインを作成した。ネイティブコード部分は [Unity MIDI Receiver](https://github.com/keijiro/unity-midi-receiver) からの流用で、Unity 側のインタフェースを使いやすく簡便化した形になっている。

CC として入力されたコントローラーの値を好きなタイミングで使えるようにしてあるうえ、この値にローパスフィルターをかけることができるようになっている。というのも、MIDI コントローラーの CC の値は 128 段階しかないため、細かな動きをした場合にその値をそのまま使うと、階段状にガクガクとした動きになってしまう恐れがある。これを避けるためにローパスフィルターが必要になる。

とはいえ、あまりきつくフィルターをかけると即応性が下がってしまうので善し悪しだ。このプラグインでは、フィルターをかけていないリアルタイムな値、軽いフィルターをかけた値、重くフィルターをかけた値の３種類を使い分けられるようにした。

---

追記：ノート情報も受け取れるようにした。ホイールとアフタータッチにはまだ対応していない。アフタータッチはともかく、ホイールぐらいはサクっと対応しておくべきかも。
