[Scroll Pane](../abstractwidgetcontents)
======

機能
-----------

-   概要

> スクロール機能を実現し、必要に応じてスクロールバーを表示する

-   機能

> 表示項目が表示領域の高さ/幅を超える場合には、スクロールバーを表示し、項目を表示可能とする。
>
> 本クラスが単体で描画可能な項目が無いため、単体で使用されることはない。
>
> スクロールアウトした部分の存在を示すため、その辺に上位プログラムで指定されたスタイルの影を表示する。

-   操作

> フリック・ドラッグ操作によるスクロールが可能。

-   音

> なし

-   レイアウト

> 以下にレイアウトを示す。

Scroll Pane

> **各種スタイル定義**

| Display Size | scroll bar 幅 | offset | vMargin | hMargin | Scroll barのborder-radius |
|:------------ |:------------- |:------ |:------- |:------- |:------------------------- |
| 5inch / 10inch |  |  |  |  |  |

> Scroll barは、常にopacity で表示される。
>
> Scroll bar の色、および影の色はスタイルガイドに従う。
>
> <span class="underline">＜影＞</span>
>
> スクロールアウトした部分があることを示すため、scroll
> paneはスクロールアウトした部分のある辺にbox-shadowで影をつける。box-shadowは４辺が独立にスタイルを指定でき、動的に変更できる。
>
> 影の色はテーマに従うが、Headerに隣接する部分の影はHeaderに合わせた影の色を用いる。box-shadowの詳細はStyle
> GuideのScrollとHeaderを参照。box-shadowはデフォルトでテーマに従った標準の影の色が適用される。また、あらかじめ用意されたclass名を用いることでテーマに従ったHeaderの影の色、あるいはカスタマイズモードのの影の色を指定できる。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> Scroll Paneはミラーリングをサポートしない。
>
> LTR表記であっても、縦スクロールインジケータは常に右端に表示されることに変更なし。初期位置が、横スクロールにおいては左端であることに変更なし。

API Documentation
-----------

-   オブジェクト名

> scrollPane

-   コンストラクタ

> $.cscwScrollPane (\[options\]) :
> スクロール領域を生成するコンストラクタ。
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | <br>&lt;div id=”ScrollPane”&gt;<br>&lt;div id=”ScrollPaneBody”&gt;<br>&lt;/div&gt;<br>&lt;/div&gt; |
| Script | <br>$(“#ScrollPaneBody”).outerHeight(適切な値);<br>$(“#ScrollPane”).cscwScrollPane({});<br><br> |

> ScrollPaneBodyは、scrollPaneウィジェットにスクロールさせる対象となる要素。scrollPaneは自身の大きさと、ScrollPaneBodyの大きさを比較して、ScrollBarを出すか出さないかを決定する。ScrollPaneの大きさに変更があった場合は、scrollPaneのrefreshを呼ぶ必要がある。

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| width | Integer | 表示可能な領域の幅(pixel)　nullの場合、親要素の幅に合わさる | null |
| height | Integer | 表示可能な領域の高さ(pixel)　 | 必須 |
| direction | String | <br>スクロール可能な方向<br><br>vertical/horizontal以外の値を指定しないこと<br><br>vertical 　縦方向<br><br>horizontal 横方向<br><br>both　　縦/横方向の双方<br><br>none　　スクロール不可<br><br> | vertical |
| showScrollBar | Boolean | <br>スクロールバーを表示するか否か<br><br>true　スクロールバーを表示する<br><br>false　スクロールバーを表示しない<br><br> | true |

-   オプション相当情報のCSSによる指定

> コンストラクタをコールする要素に対して、widthとheightを指定することで、サイズを指定できる。

Example：　　\#scrollPane { width:500px; height:500px;}

-   メソッド

| .cscwCall(“refresh”) |
|:-------------------- |
| <br>スクロール領域の表示更新を行う。<br><br>スクロール領域内に表示されるコンテント全体の大きさが変更された場合は、本メソッドをコールすること。<br><br> |

| .cscwCall(“gesture”, value) |   |   | 　|
|:--------------------------- |:--- |:--- |:---|
| 利用者のタッチ操作に対する<br>スクロールの振る舞いを切り替える。 |  |  | |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| value | Boolean | タッチ操作によるスクロール可否 |  |
|  |  | true | タッチ操作に従いスクロールを行う |
|  |  | false | タッチ操作を無視する |

| .cscwCall(“gesture”) |   |   |　　|
|:-------------------- |:--- |:--- |:--- |
| 利用者のタッチ操作に対する<br>スクロールの設定を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
| | boolean | タッチ操作によるスクロール可否 | |
| | | true |タッチ操作に従いスクロールを行う|
| | | false |タッチ操作を無視する|

| .cscwCall(“height”, value) |   |   |
|:-------------------------- |:--- |:--- |
| 高さを変更し、ScrollPaneを更新する。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| value | Integer | ScrollPaneの高さ。 |

| .cscwCall(“height”) |   |   |
|:------------------- |:--- |:--- |
| ScrollPaneの高さを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | ScrollPaneの高さ。 |

| .cscwCall(“scrollPosition”, x, y, duration[, cb]) |   |   |
|:----------------------------------------------- |:--- |:--- |
| スクロール位置を変更する |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| x | Integer | 水平位置 |
| y | Integer | 垂直位置 |
| duration | Integer | スクロールにかける時間 (ms) |
| cb | function | スクロール終了後に呼び返すコールバック関数 省略可能 |

| .cscwCall(“scrollPosition”) |   |   |
|:--------------------------- |:--- |:--- |
| スクロール位置を取得する  |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
| x | Integer | 水平位置 |
| y | Integer | 垂直位置 |

| .cscwCall(“maxX”) |   |   |
|:----------------- |:--- |:--- |
| 水平方向の最大スクロール位置 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | 水平位置 |

| .cscwCall(“maxY”) |   |   |
|:----------------- |:--- |:--- |
| 垂直方向の最大スクロール位置を取得する |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | 垂直位置 |

| .cscwCall(“onScroll”, func) |   |   |
|:--------------------------- |:--- |:--- |
| スクロール時に通知を受けるためのコールバック関数を登録する。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| func | function | コールバック関数 |

| .cscwCall(“offScroll”, func) |   |   |
|:---------------------------- |:--- |:--- |
| スクロール時に通知を受けるためのコールバック関数の登録を削除する。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| func | function | コールバック関数 |

| .cscwCall(“width”, value) |   |   |
|:------------------------- |:--- |:--- |
| 幅を変更し、ScrollPaneを更新する。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| value | Integer | ScrollPaneの幅 |

| .cscwCall(“width”) |   |   |
|:------------------ |:--- |:--- |
| ScrollPaneの幅を取得する |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
|  | Integer | ScrollPaneの幅 |

-   イベント

> なし