---
layout: post
title: ビジュアライザ向けオーディオスペクトル分析 (Unity, C#)
category: posts
---

![Screenshot](/images/2013-10-16-1.png)

[github.com/keijiro/unity-audio-spectrum](https://github.com/keijiro/unity-audio-spectrum)

Unity でオーディオスペクトルを分析するための簡単なライブラリを作成した。この手のライブラリは以前にも作ったことがあったけれど、それはあまりビジュアライザに適したものではなかった。今回の実装は、より一般的なオーディオビジュアライザの挙動に沿ったものとなっている。

作成にあたって、主にこの辺りの資料を参考にした。

- [blog.leeburrows.com/2011/01/creating-an-audio-visualiser](http://blog.leeburrows.com/2011/01/creating-an-audio-visualiser/)
- [apmr.matelys.com/Standards/OctaveBands.html](http://apmr.matelys.com/Standards/OctaveBands.html)

このライブラリは前の [VJ システムの実験](http://localhost:4000/posts/generative_vj/)で実際に使用している。自分で使ってみた結果、次のような感想を持った。

- 4 バンドから 31 バンドまで様々なバンドタイプに対応したものの、アニメーションの入力として用いる場合には、もっぱら 4 バンドのものを使うことになるだろうと思う。それ以上の細かいやつは要らないかも……
- オーディオコンポなどでよく見られるフォールダウンタイプのピークレベルを取得できるようにしたものの、これはあまり使い出がない気がする。
- Inspector 上でスペクトルを見られるようにしたものの、更新頻度が低すぎてあまり役に立たない気がする。
- Mean level という形で「動きの滑らかなスペクトル」を取得できるようにした。これはアニメーションの入力として使うにはとても便利だった。

以上の感想をフィードバックして、また改良していこうと考えている。