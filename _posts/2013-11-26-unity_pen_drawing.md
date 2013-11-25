---
layout: post
title: ペン描風エフェクトの実験 (Unity)
category: posts
---

![Screenshot](/images/2013-11-26-1.png)

シンプルな[ランダムウォーク](http://en.wikipedia.org/wiki/Random_walk)でペン描風のエフェクトを作れないか試したもの。[Sobel filter](http://en.wikipedia.org/wiki/Sobel_operator) で抽出した輪郭線の上をランダムウォークさせるだけのごく簡単なアルゴリズムだけど、雰囲気はそれなりに出ていると思う。

<div class="videoframe"><iframe class="vine-embed" src="https://vine.co/v/hFrrElErvzU/embed/simple" width="480" height="480" frameborder="0"></iframe><script async src="//platform.vine.co/static/scripts/embed.js" charset="utf-8"></script></div>

ソースはこちら。

[github.com/keijiro/unity-randomwalker](https://github.com/keijiro/unity-randomwalker)
