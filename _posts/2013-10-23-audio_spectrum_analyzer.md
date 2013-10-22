---
layout: post
title: スペクトルアナライザー (Xcode, Objective-C)
category: posts
---

<div class="videoframe"><iframe src="//player.vimeo.com/video/77549498" width="600" height="337" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div>

[先日作成した Unity 用のスペクトルアナライザー](http://keijiro.github.io/posts/unity_audio_spectrum/)は、Unity の内部で鳴らしている音源を分析するもので、外部入力には対応していない。実際の VJ 的な応用を考えると、外部入力への対応は必須だ。ただ残念なことに、現状の Unity は外部からのオーディオ入力の処理にとても弱い。

この弱点を補うには、オーディオ入力部分をネイティブプラグインとして自作する必要がある。そのための準備として、まずは Cocoa ベースでスペクトルアナライザーを作成してみることにした。

ソースコードはここに公開してある。

[github.com/keijiro/AudioSpectrum](https://github.com/keijiro/AudioSpectrum)

このスペクトルアナライザーでは、オーディオ入力に [HAL Output Audio Unit (AUHAL)](https://developer.apple.com/library/mac/technotes/tn2091/_index.html) を、スペクトル分析 (FFT) に Accelerate Framework の一部である [vDSP](https://developer.apple.com/library/mac/documentation/Performance/Conceptual/vDSP_Programming_Guide/Introduction/Introduction.html#//apple_ref/doc/uid/TP40005147) を使用した。

当初はオーディオ入力に [Audio Queue](https://developer.apple.com/library/mac/documentation/MusicAudio/Conceptual/AudioQueueProgrammingGuide/Introduction/Introduction.html) を使用していたが、レイテンシーの問題を解決することができず、最終的に AUHAL への移行を余儀なくされた。Audio Queue は非常に簡便な API で実装を楽に進めることができる反面、高レベルオーディオ API の宿命とも言えるレイテンシーの問題から逃れることができない。この辺りは今回得た大きな教訓のひとつだと思う。
