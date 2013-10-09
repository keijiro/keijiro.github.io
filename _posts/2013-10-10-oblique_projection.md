---
layout: post
title: Oblique Projection (Unity, C#)
category: posts
---

![Oblique projection](/images/2013-10-10-1.png)

[Oblique projection](http://en.wikipedia.org/wiki/Oblique_projection) （斜投影）は平行投影の一種だ。同じく平行投影の一種である Orthographic projection （正投影）と似ているけれど、ちょっと違う。上の図のように、正面は正投影っぽい見た目になりつつ、奥行きは斜めに傾いた軸として表現される。

Orthographic projection でいいじゃん、と思われるかもしれないけれど、2.5D 的な表現を用いたい場合に oblique projection の方が適している場合もある。

例えば、Orthographic projection で上と同じような絵を作ろうとすると、下のようになる。

![Orthographic projection](/images/2013-10-10-2.png)

2D 的な平面感を強調したい場合に、横軸が傾いているのは都合が悪いこともある。だからと言って横軸の傾きをなくすと、奥行きが垂直の線になってしまい、厚みの表現が弱くなってしまう。

![Orthographic projection (2)](/images/2013-10-10-3.png)

平面感と厚みの表現を両立したい場合に斜投影を用いるのは理にかなっている。昔の 2D ゲームなどでも、この表現方法が効果的に用いられている。

![2D games](/images/2013-10-10-4.png)

というわけで、Unity で斜投影を行うためのスクリプトを実装してみた。簡単なスクリプトだけれど、専用のインスペクタなども用意して、そこそこに使いやすくしてある。

[github.com/keijiro/unity-oblique-projection](https://github.com/keijiro/unity-oblique-projection)
