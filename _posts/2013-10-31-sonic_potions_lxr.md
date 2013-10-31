---
layout: post
title: Sonic Potions LXR
category: posts
---

![LXR](/images/2013-10-31-1.jpg)

[Sonic Potions](http://www.sonic-potions.com) のドラムマシン [LXR](http://www.sonic-potions.com/lxr) のキットを購入して組み立てた。[Mutable Instruments](http://mutable-instruments.net) の [Shruthi-1](http://mutable-instruments.net/shruthi1) に続いて、シンセ自作キットの２つ目のチャレンジになる。

組み立ての難易度はそれほど高くなかった。組み立ての必要な部分のほとんどは制御用のデジタル回路となるため、やたらとたくさんタクトスイッチやら LED やら IC ソケットの足やらをハンダ付けしたような気がするけれど、値の異なる素子を間違えないよう細かくハンダ付けしなければならないアナログ回路と比較すると、間違いが生じにくく難易度としては低くなるように思える。最も複雑な中枢部であるところのメイン基盤（ARM Cortex-M4 を搭載している）は組み立て済みで付属されているので、最後に仕上げとしてぶっ挿すだけで OK だ。

<div class="videoframe"><iframe src="//player.vimeo.com/video/77891588" width="600" height="337" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div>

LXR の出音の方は、アナログモデリングを基本としつつ、あまりアナログにはこだわらない方向性でまとめられている。オシレーターと env mod で基本の音作りをしつつ、短サンプルによるアタック音の付加や、シンプルな FM 変調、フィルターやディストーション等々で細かな味付けを行う。また、ハイハット用の音源では FM が２重にかけられるようになっていたり、スネア用の音源ではノイズ側のみフィルターがかかるようになっていたり、ドラムならではの特殊な設計も盛り込まれている。

インタフェースもよく設計されている。基本的なエディットを行う "Voice" モード、演奏中の操作に特化した "Performance" モード、ステップ単位でのエディットに特化した "Step" モードの、各種の作業内容に合わせたモードが用意されており、基本的な操作はすべてリアルタイムに行えるのはもちろん、これらのモード間の切り替えも演奏を止めずに行えるようになっている。

出力は４系統のパラアウトが可能。上の動画のように外部エフェクターと組み合わせて遊ぶのも面白いと思う。これ１台で様々な遊び方を楽しめる機材だ。シンセの自作キットに挑戦してみたいという人にお勧めの１台だと思う。
