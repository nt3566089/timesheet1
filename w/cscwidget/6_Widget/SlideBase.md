[Slide Base](../abstractwidgetcontents)
======

機能
---------

-   概要

> SlidePaneのtransitionを補完するためウィジェット

-   機能

> SlidePaneおよび、SlidePaneによって画される画面要素の共通の親要素として生成され、SlidePaneと協調動作することによりSlidePaneのtransitionをよりStyleGuideに準拠したものとする
>
> オプション指定によりtransition時のpaddingを表示できる（詳細はレイアウト図とAPIを参照）。

-   操作

> なし

-   音

> なし

-   レイアウト

> レイアウトは、以下のとおり。
>
> **全体レイアウト**

| Display Size | <br>padding<br><br>(inside)<br><br> |
|:------------ |:----------------------------------- |
| 5inch |  |
| 10inch |  |

-   popup内にSlieBaseとSlidePaneを適用した例

    -   popupはHeaderなしで生成する

    -   slideBaseは、popupのbodyとして、width:100%; height:100%;で配置

    -   slideBaseの子要素として

        -   beforeの画面を作成

        -   afterの画面をSlidePane（type="container"）で作成

        -   afterのslidePaneのtargetをbeforeの画面とする

-   ListにSlideBase/SlidePaneを適用した例

<!-- -->

-   上にSlideBaseを配置する

-   slideBaseの子要素として

    -   beforeのListを作成

    -   SlidePane（type="container"）を作成して、その中にafterのListを作成

    -   上記SlidePaneのtargetにbeforeのListを指定する

API Documentation
----------

-   オブジェクト名

> slideBase

-   コンストラクタ

> $.cscwSlideBase(\[options\]) :SlideBaseを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | <br>&lt;div id=”slideBase”&gt;<br>&lt;div id=”Table”&gt;<br>….<br>&lt;div&gt;<br>&lt;div id="slidePane&gt;<br>&lt;div class="body"&gt;<br>&lt;/div&gt;<br>&lt;/div&gt;<br>&lt;/div&gt;<br><br> |
| Script | <br>$(“#slideBase”).cscwSlideBase({<br>borderAtTransition: true,<br>});<br>$("#slidePane").cscwSlidePane({<br>type: "container",<br>target: $("#Table"),<br>});<br><br> |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description	| Default |
|:-------- |:---- |:----------- |:------- |
| borderAtTransition | Boolean	| 内部のslidePaneがtransitionする際にborderを表示する	| false |
| hasPadding | Boolean | 内部のslidePaneがtransitionする際にpadding要素を表示する	| false |
| paddingLayer | Integer | padding用のdivのレイヤ | 1000 |
| width | Integer/String | 幅（Stringの場合はcssの値） | null |
| height | Integer/String	| 高さ（Stringの場合はcssの値）	| null |

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> width、height

-   メソッド

> なし