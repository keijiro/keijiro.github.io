---
layout: post
title: Unity から Eclipse プロジェクトを出力する
category: posts
---

Unity 4.0 では Unity から Eclipse プロジェクトを出力する機能が正式に用意されています（裏技的なものは以前から存在しましたが、正式な機能ではありませんでした）。

## Build ダイアログから

- Build Settings ダイアログにある "Create Eclipse Project Layout" を on にする。
- Export ボタンを押す。

## スクリプトから

（以下は Unity 4.0 の時点での仕様です。将来的に変更される可能性もあります。）

スクリプトからビルド時に Eclipse 出力を行うには、BuildPlayer の引数として BuildOptions.AcceptExternalModificationsToPlayer を指定します。何故？と思われるかもしれませんが、まあなんでかこういう仕様になっています……

以下の例は、フォルダ選択ダイアログを表示して、そのフォルダの中に Eclipse プロジェクトを出力するというものです。

```
@MenuItem("Custom/Export Eclipse Project")
static function CustomBuildMenu() {
  var dest = EditorUtility.SaveFolderPanel("Export Eclipse project", "", "");
  BuildPipeline.BuildPlayer(null, dest, BuildTarget.Android, BuildOptions.AcceptExternalModificationsToPlayer);
}
```
