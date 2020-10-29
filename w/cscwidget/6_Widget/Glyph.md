[Glyph](../abstractwidgetcontents)
======

機能
-----

-   概要

> テキストのエイリアス

-   機能

> 実装上の実体はテキストと同じであるが、グリフを指定された領域の上下左右中央に配置しやすいようにデフォルトのパラメータが調整される

-   操作

> なし

-   音

> なし

API Documentation
-----

-   オブジェクト名

> glyph

-   コンストラクタ

> $.cscwGlyph (\[options\]) :テキストボックスを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”glyph”&gt;&lt;/div&gt; |
| Scripts | $(“#glyph”).cscwGlyph(); |

> &lt;注意事項&gt;
>
> GlyphはTextのエイリアスであり、コンストラクタパラメータやメソッドなどは同じパラメータをとる。ただしGlyphは指定された領域内に上下左右中央に配置されることが多いので、コンストラクタパラメータのデフォルト値が調整されている。

-   オプション

> Textとの差分と、それに関連する箇所のみを記述する。

| **Property** | **Type** | **Description** | **Default** |
|:------------ |:-------- |:--------------- |:----------- |
| isGlyph | boolean | Text isGlyphを参照。Textとはデフォルト値のみ異なる。 | true |
| hAlign | String | Text hAlignを参照。Textとはデフォルト値のみ異なる。 | center |

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> 　　なし

## Glyphウィジェットのレイアウト

> GlyphウィジェットはTextウィジェットのエイリアスであり、同じパラメータをとり、同じメソッドを持つ。ただし、生成時のパラメータのデフォルト値は、Glyphのユースケースに合うように設定される。

-   単純ケース

> Glyphウィジェットでは、最頻ユースケースを、width/heightを指定でglyphをその領域の上下左右中央に配置するケースと想定している。この使い方では最適化も適用される。
>
> <img src="./media/CSCWidget仕様書_3/media/image1.png" style="width:6.03056in;height:2.53125in" />

-   フォントサイズ

> <img src="./media/CSCWidget仕様書_3/media/image2.png" style="width:6.03056in;height:2.53125in" />