---
layout: post
title: Icosphere
category: posts
---

Unity でいわゆる icosphere を動的に生成するためのライブラリを作成した。

![Icospheres](/images/2013-10-08-1.png)

Unity に標準で備わっている sphere メッシュは、いわゆる UV sphere というやつで、極付近と赤道付近とで密度に大きな偏りがある。また、分割数の設定も変更できない。これは球体を変形させて使おうという場合には大きな弱点になる。

![UV sphere](/images/2013-10-08-2.png)

Icosphere なら密度が均一だからキレイに変形ができるし、分割数を自由に設定できるのも表現の幅になりえる。下のアニメーションのように敢えて荒い分割数でいじくるのも面白い。

<div class="videoframe"><iframe src="//player.vimeo.com/video/76109906" width="600" height="338" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div>

このアニメーションは今回の icosphere と [Perlin noise](https://github.com/keijiro/unity-perlin) の組み合わせで作成した。

---

この icosphere を生成するライブラリは、将来的に他の形状を生成する機能も含めていくことで、よりライブラリらしいものにまとめていこうと考えている。

[github.com/keijiro/unity-emgen](https://github.com/keijiro/unity-emgen)
