---
layout: post
title: Unity から glLineWidth を呼ぶ
category: posts
---

![Lines](/images/2013-11-25-1.png)

Unity から <code>glLineWidth</code> を呼び出すサンプルプログラムを組んでみた。

[github.com/keijiro/unity-linewidth-plugin](https://github.com/keijiro/unity-linewidth-plugin)

<code>MeshTopology.Lines</code> 等と組み合わせて任意の太さのラインを描画できる。アンチエイリアスをかけた状態で 1 より細い線を描画することも可能になる。

---

仕組みを少し解説する。Unity の描画パイプラインに任意の処理を差し挟むには [low-level native plugin interface](http://docs.unity3d.com/Documentation/Manual/NativePluginInterface.html) を用いる必要がある。

正確に言うと、マルチスレッドレンダラーが動作する環境においては、この仕組みを用いて描画スレッド側からコールバックをかけてもらわなくてはならない。少なくともデスクトッププラットフォームにおいてはデフォルトでマルチスレッドレンダラーが動作するようになっているので、この仕組みを使う必要がある。

この low-level native plugin interface には若干使いづらいところがあって、複数のプラグインを共存させることが難しい。そのため今回のコードは汎用的に使えるプラグインという形にまでは整理せず、あえて中途半端なサンプルプログラムというレベルにとどめておくことにした。

