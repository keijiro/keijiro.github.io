---
layout: post
title: 外部オーディオ処理プラグイン AudioBridge (Unity)
category: posts
---

![AudioBridge](/images/2013-10-28-1.jpg)

[先日作成したスペクトルアナライザー](http://keijiro.github.io/posts/audio_spectrum_analyzer/)を転用する形で、外部オーディオ処理を行う Unity プラグインを作成した。任意のオーディオインタフェースを通して入力された音声を、リアルタイムにスペクトル分析することができる。

[github.com/keijiro/unity-audiobridge](https://github.com/keijiro/unity-audiobridge)

---

Unity には外部オーディオを録音する機能として [Microphone クラス](http://docs.unity3d.com/Documentation/ScriptReference/Microphone.html) が用意されている。ただ、残念なことにこのクラスはリアルタイムでの入力に対応していない。細かく時分割して擬似的にリアルタイム性を出すというテクニックもあるのだけれど、これでリアルタイムなスペクトル分析を行うのにはかなりの無理がある。

この AudioBridge プラグインでは、Core Audio と vDSP framework を使用することにより、低レイテンシかつ低負荷なオーディオ処理を実現している。分析されたスペクトルは適当なオクターブバンドにまとめられ、各バンドのデシベル値が Unity 側へ返されるようになっている。

---

今回のプラグインは Mac OS X 版だけしか用意していない。Windows 版も用意したかったのだけれど、Windows における低レイテンシオーディオのトレンドがよく分かっていないというのと、Windows における vDSP の代替物を探すのが面倒くさい、という理由で投げ出している。