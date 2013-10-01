---
layout: post
title: Perlin noise (Unity, C#)
category: posts
---

![Animation](/images/2013-10-02-1.gif)

１年ぐらい前に書いた Perlin noise のコードをオーバーホールした。特になんの変哲もないコードで、1D/2D/3D の Perlin noise と、いわゆる [fBm](http://en.wikipedia.org/wiki/Fractional_Brownian_motion) の関数を備えている。

[github.com/keijiro/unity-perlin](https://github.com/keijiro/unity-perlin)

有機的な形や動きを作るのに便利。特殊な高速化は施していないので、特に速いということはないけども、特に重いということもない。プロトタイピングには便利だと思う。
