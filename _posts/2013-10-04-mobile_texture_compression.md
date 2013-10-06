---
layout: post
title: Unity iOS/Android におけるテクスチャ画質の改善
category: posts
---

![Animation](/images/2013-10-04-1.png)

iOS/Android においてテクスチャ圧縮は必須ですが、画質の著しい劣化を招く可能性があり、嫌われる傾向にあります。特に厳しいのはアルファチャンネルを使う場合です。どうしてもこの劣化を受け入れることができず、泣く泣く 32 bit true color を使っているケースも少なくないのではないかと思います。

ただ、多くのケースにおいては、ちょっとした工夫を行うことにより、これらの問題の改善が可能です。その代表的な３つの手法を文書にまとめてみました。

- [github.com/keijiro/unity-dither4444](https://github.com/keijiro/unity-dither4444)

16 bit 減色を行う際にディザリングを適用することによって画質の改善を図る。

- [github.com/keijiro/unity-pvr-cleaner](https://github.com/keijiro/unity-pvr-cleaner)

アルファが 0% の領域をクリアすることによって PVRTC の画質の改善を図る。

- [github.com/keijiro/unity-alphamask](https://github.com/keijiro/unity-alphamask)

アルファチャンネルをマスクとして別テクスチャへ分離することにより画質の改善を図る。

---

OpenGL ES 3.0 では [ETC2](http://en.wikipedia.org/wiki/Ericsson_Texture_Compression) が対応必須になっているらしいので、これで状況は若干まともになるのではないかと思います。個人的には [ASTC](http://en.wikipedia.org/wiki/Adaptive_Scalable_Texture_Compression) の義務化に期待したいところですが。
