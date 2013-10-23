---
layout: post
title: 生成的なアニメーション表現 (Unity, C#)
category: posts
---

[![ropelike-physics](/images/2013-09-09-1.jpg)](http://keijiro.github.io/unity-ropelike-physics/)

[unity-ropelike-physics](http://keijiro.github.io/unity-ropelike-physics/) ([source code](https://github.com/keijiro/unity-ropelike-physics))

『[ジェネラティブ・アート](http://www.bnn.co.jp/books/title_index/web/processing.html)』を読んで色々と考えるところあって、自分でも生成的な何らかを作ってみようと思い立った。

道具はなんでもいいのだけれど、とりあえずは Unity を使うのが手軽だろう。 Unity を使うという前提のもとで考えた場合、最も手軽に生成的なアプローチができるのは何だろう？ そこでまず考えたのは、物理挙動を生成的なアニメーションに用いるというアイデアだった。

物理挙動を使ってアニメーションを作る方法はいくつかある。単純な加速や衝突を用いるのは最もシンプルな方法だけれど、若干味気ない動きに落ち着くきらいがある。複雑かつ有機的な動きを作るには、ジョイントを用いるのが手軽でいい。ジョイントを使って複数の物体間に拘束条件を与えて、単体の運動では作り出せない複雑性を生み出すのだ。

このデモでは Configurable Joint を使ってロープ状の連結したシステムを構築している。そこにランダムな力を与えるだけで、複雑かつ予測のできない動きをしてくれる。
