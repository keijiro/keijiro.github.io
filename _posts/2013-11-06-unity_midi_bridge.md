---
layout: post
title: Unity MIDI Bridge (Unity, C#, Cocoa, Objective-C)
category: posts
---

![MIDI Bridge](/images/2013-11-06-1.png)

Unity-MIDI 連携の最終形として、無料の Unity Basic でも使える Unity MIDI ブリッジを作成した。

ライブラリはこちら。

[github.com/keijiro/unity-midi-bridge](https://github.com/keijiro/unity-midi-bridge)

この中にあるブリッジソフトウェア (midi-bridge-osx.zip) を起動しておくことによって、Unity から MIDI デバイスへのアクセスが可能になる、という仕組み。

[MIDI Input](http://keijiro.github.io/posts/midi_input_unity/) のように MIDI デバイスからの入力が可能になるのはもちろん、今回は MIDI デバイスへの出力にも対応している。

<div class="videoframe"><iframe class="vine-embed" src="https://vine.co/v/hjEFp2dVU1n/embed/postcard" width="320" height="320" frameborder="0"></iframe><script async src="//platform.vine.co/static/scripts/embed.js" charset="utf-8"></script></div>

ブリッジソフトウェアのソースコードはこちら。

[github.com/keijiro/midi-bridge-osx](https://github.com/keijiro/midi-bridge-osx)

---

今後の課題は以下の通り。

- Windows 版ブリッジソフトウェアの作成
- ドキュメントの整備

---

Unity Basic でこの手の機能拡張を行う方法について補足。Unity におけるネイティブコード連携 ([native code plug-in](http://docs.unity3d.com/Documentation/Manual/Plugins.html)) は、本来、Pro 版およびモバイルプラットフォームのみの機能として制限されている。

この制限を迂回するには、今回の用意したブリッジソフトウェアのように、必要な機能を外部プロセスとして実装しておいて、プロセス間通信によって Unity との連携を図るようにしなければならない。

とても実装が面倒なうえメンテナンスも困難になるので、自家製の one-off ものを作成するのにこのような手法を用いるのはおすすめできない。どうしても Basic ライセンスで動かす必要がある、という場合に、まあいちおうこういう手段もありますよ……というレベルの話。
