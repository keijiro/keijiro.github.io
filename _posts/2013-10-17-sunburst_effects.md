---
layout: post
title: Sunburst effects (Unity, C#)
category: posts
---

<div class="video frame"><iframe src="//player.vimeo.com/video/76949095" width="600" height="338" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div>

[github.com/keijiro/unity-sunburst-effects](https://github.com/keijiro/unity-sunburst-effects)

光源から後光がピカーっと差すような感じのエフェクトを作成した。この手のエフェクトに呼び方は色々ある。ここではとりあえず [Sunburst](http://en.wikipedia.org/wiki/Sunburst) という名前を付けておくことにした。

フラットな絵作りに合うよう作ったものなので、恐らく、普通の絵作りにはマッチしない。

上の動画にあるように、動きを制御するいくつかのパラメーターを持っている。これらのパラメーターと transform の動きを組み合わせることによって、色々と面白い効果を与えることができる。

