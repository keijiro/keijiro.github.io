---
layout: post
title: パーティクルエフェクトの外部制御 (Unity)
category: posts
---

<div class="videoframe"><iframe src="//player.vimeo.com/video/80048661" width="600" height="338" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div>

Unity のパーティクルエフェクトをスクリプトから制御する方法について実験したもの。

Unity のパーティクルエフェクトシステムでは、スクリプトから個々のパーティクルへアクセスする手段として [GetParticles](http://docs.unity3d.com/Documentation/ScriptReference/ParticleSystem.GetParticles.html)/[SetParticles](http://docs.unity3d.com/Documentation/ScriptReference/ParticleSystem.SetParticles.html) が用意されている。[提供されているプロパティ](http://docs.unity3d.com/Documentation/ScriptReference/ParticleSystem.Particle.html)はそれほど多くないものの、直接アクセスすることで標準機能では不可能な動きを作り出すことができる。

上の映像では、特定のオブジェクトに吸い寄せられるような動きと、そこから反発するような動きを試してみている。ソースコードは次のような感じ。

[ExternalControl.cs](https://github.com/keijiro/unity-particle-animations/blob/master/Assets/Scripts/ExternalControl.cs)

C# から逐次処理を行っているため、それなりの負荷が発生することは避けられない。ただ、個々のパーティクルを GameObject として実装する方法と比較すれば、負荷は遥かに低くて済む。見た目の数を稼ぎたいときには有効な方法だと思う。
