[Separator Line](../abstractwidgetcontents)
======

機能
--------------

-   概要

> 区切り線

-   機能

> 指定された長さの区切り線（水平方向 / 垂直方向）を描画する。

-   操作

> なし

-   音

> なし

-   レイアウト

**全体レイアウト（水平方向/垂直方向）**

> **各種スタイル定義**

|   | width | height | darkStroke位置 | lightStroke位置 |
|:--- |:----- |:------ |:------------- |:--------------- |
| 水平方向 |  |  |  |  |
| 垂直方向 |  |  |  |  |

> darkstrokeおよびlightStrokeの色彩は、適用されたAplicacion
> themeおよびContainer themeに従って決定される。 Container theme
> がblack　の場合は、darkStrokeを持たないため、darkStrokeに相当する領域は透明で描画される。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> Separator
> Lineは、RTL表記/ミラーリングを関知しない。RTL/LTRに関わらずレイアウトは一定。

API Documentation
--------------

-   オブジェクト名

> separatorLine

-   コンストラクタ

> なし。

| Example |   |
|:------- |:--- |
| Markup | <br>&lt;div id=”line1” class=”cscw-horizontalSepLine”&gt;&lt;/div&gt;<br><br>&lt;div id=”line2” class=”cscw-verticalSepLine”&gt;&lt;/div&gt;<br><br> |
| Script |  |
| CSS | <br>#line1{ width:400px; }<br><br>#line1{ height:100px; }<br><br> |

> オプションクラスでは以下を使用する。

| CSS class name | description |
|:-------------- |:----------- |
| cscw-horizontalSepLine | 区切り線（横）を表示するCSSクラス |
| cscw-verticalSepLine | 区切り線（縦）を表示するCSSクラス |

-   オプション

-   イベント

-   メソッド

> なし