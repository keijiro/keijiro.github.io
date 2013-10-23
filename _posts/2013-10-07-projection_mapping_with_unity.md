---
layout: post
title: プロジェクションマッピング実験 (Unity)
category: posts
---

<div class="videoframe"><iframe class="vine-embed" src="https://vine.co/v/hgPaQ5nqjAZ/embed/simple" width="320" height="320" frameborder="0"></iframe><script async src="//platform.vine.co/static/scripts/embed.js" charset="utf-8"></script></div>

先週一週間、ちょくちょく隙間の時間を見つけては、Unity を使ったプロジェクションマッピングの実験を行っていた。それなりに成果を得られたので、これをチュートリアルという形で文書にまとめた。

[Unity によるプロジェクションマッピング入門](https://github.com/keijiro/unity-pm-tutorial)

Unity でプロジェクションマッピングを行うのは難しくない、要は実世界と同じシーンを構築して、プロジェクターの位置にカメラを置くだけ。無料版の Unity でも相当に遊べる。プロジェクターもごく普通のもので構わない。

そこから先、何を表現するかによって、難易度は変化していく。錯視的効果を得たければ render texture （Unity Pro の機能）が必要になるし、中規模以上のプロジェクションになればレーザー距離計のような機材も必要になってくる。プロジェクターも光量の大きなものが必要になるかもしれない。

ただ、よほど欲張らない限りは、ごく普通の機材と、ごく簡単な技術の組み合わせで、色々と遊べる分野であると、実際に試した結果そのように感じられた。