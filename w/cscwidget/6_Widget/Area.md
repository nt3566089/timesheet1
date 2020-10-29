[Area](../abstractwidgetcontents)
======

機能
---------

-   概要

> アプリケーション画面の、を適用しないグレイ色のエリアを描画する。

-   機能

> 指定された範囲に対して、グレイ色のテクスチャを適用する。
>
> 指定範囲の上端には、テーマカラーに依存したセパレーターラインを描画する。
>
> Areaに配置されたcscwidgetに対し、Areaに配置されていることを示すコンテキストを提供する。つまり、本Widgetはコンテナとして、上に配置される部品にを背景に持つことを考慮した色彩を適用する。

-   操作

> なし

-   音

> なし

-   レイアウト

> テクスチャは、テーマカラーがDarkGrayのときのみDarkGray色のものを、それ以外の場合は、Gray色のものを適用する。上端のセパレーターラインの色は、適用されているテーマカラーに従って決定される。
>
> **全体レイアウト**
>
> **各種スタイル定義**

<table>
<thead>
<tr class="header">
<th>height</th>
<th>width</th>
<th>セパレーターライン　border-width</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>自動/アプリ指定</td>
<td>パネル幅と同等</td>
<td><p>1pxを2本。Areaの高さは、ラインの2pxを含む。</p>
<p>Paddingは、下側のラインを含む。</p></td>
</tr>
</tbody>
</table>

> Areaは、その内部に対して、デフォルトで以下のマージンを持つものとする。
>
> **Area内のマージン定義**

<table>
<thead>
<tr class="header">
<th></th>
<th>top</th>
<th>bottom</th>
<th>left</th>
<th>right</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>5inch</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>10inch</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

> &lt;RTL表記でのレイアウトについて&gt;
>
> Areaは、機能を持たないのでRTL表記であるかLTR表記であるかを関知しない。

API Documentation
---------

-   オブジェクト名

> Area

-   コンストラクタ

> $.cscwArea (\[options\])
> :Areaを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | <br>&lt;div id=”Area”&gt;<br><br>Areaに配置する要素<br><br>&lt;/div&gt;<br><br> |
| Script | $(“#Area).cscwArea(height: 450); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| height | Integer | <br>Areaの高さをpixel数で指定する。<br><br>指定がない場合は、スタイルシートの記述に従う。<br><br>スタイルシートの指定もない場合は、Areaに含まれる要素とAreaのマージン値から、ブラウザによって計算される。<br><br>負の値もしくは0が指定された場合はエラーを返す。<br><br> |  |

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> コンストラクタをコールする要素に対して、heightを指定することで、Areaの高さが指定できる。
>
> Example:　　\#gray\_field{ height:400px;}
>
> Areaの持つPaddingを変更したい場合も、直接paddingを指定することで対応できる。
>
> 特に、Areaの高さを自動計算させる場合、topとbottomのpaddingには注意が必要である。

-   メソッド

> Widget共通定義メソッドのみ。

-   イベント

> GrayFiledは、独自のイベントを持たない。