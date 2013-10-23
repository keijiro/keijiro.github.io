---
layout: post
title: プリミティブな skybox シェーダー (Unity)
category: posts
---

![Horizontal Skybox](/images/2013-09-25-1.png)

Unity でテストプログラムを書くとき、たいてい背景は単色にしている。多くの場合それで十分なのだけれど、たまにシンプルなグラデーションぐらいは欲しいかな、と思うことがある。

そこで、シンプルなグラデーションを生成する skybox シェーダーを作成した。

- [github.com/keijiro/unity-skybox-shaders](https://github.com/keijiro/unity-skybox-shaders)

## Horizontal Skybox

上のスクリーンショットで使用しているシェーダー。Top, horizon, bottom の３つの色を指定することができる。このシェーダーは、その３つの色を、上から地平線、地平線から下へと補間する。例えば上のスクリーンショットでは、top を薄い灰色、horizon と bottom を白色にしている。

デモは[こちら](http://keijiro.github.io/unity-skybox-shaders/horizontal.html)。

## Gradient Skybox

![Gradient Skybox](/images/2013-09-25-2.png)

こちらは更にシンプルで、top と bottom の２つの色のみを指定することができる。与えられた２つの色を、単純に上から下へと補間する。

このシェーダーでは回転を与えることができる。斜めに傾いたグラデーションを作り出したい場合にこれを使う。

![Custom Inspector](/images/2013-09-25-3.png)

デモは[こちら](http://keijiro.github.io/unity-skybox-shaders/gradient.html)。