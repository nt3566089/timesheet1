[Carousel](../abstractwidgetcontents)
======

機能
--------

-   概要

> carouselは、与えられた複数の要素(carousel
> itemと呼ぶことにする)の並びをエンドレスにあるいは有限の範囲でスクロール表示する機能を提供する。
>
> 縦に回転(スクロール)するcarouselを例に概念を説明する。Carouselは、carousel
> itemの載るbodyの位置を表示窓に対して移動すると共に、body上のcarousel
> itemの表示位置を入れ替え移動することでスクロールを実現する。
>
> **カルーセルの仕組み**

-   機能

> スクロール位置に従いスクロールバーを表示する。スクロールバーの表示/非表示を選択できる。
>
> スクロール位置に合わせた影表示をする。影の表示/非表示を選択できる。
>
> 所定位置にtransitionあり/なしでスクロールする。
>
> 利用者のジェスチャー操作(ドラッグ、フリップ) に従う/無視する
> を指定する。
>
> スクロール位置を所定単位(グリッド)に合わせる。
>
> スクロールの開始、進行、終了をコールバック関数にて通知する。

-   操作

> ドラッグによりスクロールする。
>
> フリックによりスクロールする。

-   音

> なし

-   レイアウト

> **カルーセル全体図**
>
> min, gridOffset,
> gridを設定し、最初のグリッド位置の収まっている時の配置を示す。gridOffsetには負の値、minにはgridOffsetより小さい値、gridはitem
> の幅と同じ値を設定したとする。gridOffset,
> minに負の値を設定したのでbodyに対して0の位置にあるitem
> 1より左はitemが表示されず空白となる。
>
> **前図の状態から右へスクロールして次のグリッド位置に収まった図**
>
> **左端までドラッグしている時の位置**
>
> minにgridOffsetより小さな値を設定した場合、最初のグリッド位置よりさらに左までドラッグ可能となる。またこの説明では、gridを指定しているのでリリースすると最初のグリッド位置に戻る。
>
> **maxとvirtualTotalSizeを指定した場合に、最右端へスクロールした状態**
>
> carousel
> のitemは、0からvirtualTotalSizeまでの範囲で表示され、virtualTotalSizeより右は空白となる。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> Carouselのレイアウトは、RTL表記であってもLTR表記と同じとする。
> RTL表記であってもitemは左から右に配置され、最初のitemは表示窓の左端に来る。

API Documentation
--------

-   オブジェクト名

> Carousel

-   コンストラクタ

> $.cscwCarousel(\[options\]) :carouselを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | <br>&lt;div id=”Carousel” &gt;<br>&lt;div id=”item1”&gt;&lt;/div&gt;<br>&lt;div id=”item2”&gt;&lt;/div&gt;<br>&lt;/div&gt;<br><br> |
| Script | $(“#Carousel”).cscwCarousel ({height:400,width:800}); |

-   オプション

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| direction | string | <br>回転方向<br><br>下記以外の値を指定しないこと<br><br>"vertical"：縦回転<br><br>"horizontal"：横回転<br><br> | "vertical" |
| grid | Integer | <br>スクロール位置を、指定値の倍数に制限する場合の指定値<br><br>指定のない場合はスクロール位置を制限しない<br><br>例 ) grid:100を指定する。170pxの位置へスクロールした場合、200pxの位置へ移動する。<br><br> | null |
| gridOffset | integer | <br>gridの指定がある場合に作用する。<br><br>gridオプションによって制限するスクロール位置を、"gridの倍数+gridOffset"にずらす<br><br> | 0 |
| initRefresh | Boolean | <br>widget生成時のrefresh有無<br><br>true：refreshを行う<br><br>false：refreshを行わない<br><br> | true |
| showScrollBar | Boolean | <br>スクロールバーの表示/非表示<br><br>true：表示する。 min/maxの両方が指定されている必要がある。<br><br>false：表示しない<br><br> | false |
| width | Integer | Carouselの外形の幅 | 必須 |
| height | Integer | Carouselの外形の高さ | 必須 |
| position | Integer | <br>初期スクロール位置<br><br>grid(およびgridOffset)が指定されている場合、positionに指定した値に最も近いスクロール制限位置を初期位置とする。<br><br>省略(nullを指定)した場合は、0を初期スクロール位置とする。<br><br> | null |
| min | Integer | <br>スクロール左端/上端位置<br><br>指定なき場合は、左/上へ制限なくスクロールし、スクロールに従ってcarousel itemが入れ替わり表示される。<br><br>指定された場合、指定位置までスクロールするがcarousel itemの表示はposition 0 までとなり、それより左/上は余白として表示される。<br><br> | null |
| max | Integer | <br>スクロール右端/下端位置<br><br>指定なき場合は、右/下へ制限なくスクロールし、スクロールに従ってcarousel itemが入れ替わり表示される。<br><br>指定された場合、指定位置までスクロールできるが、carousel itemの表示はvirtualTotalSizeまでとなり、それより右/下は余白として表示される。<br><br> | null |
| virtualTotalSize | Integer | <br>有限の範囲でスクロールする場合に、carousel itemが仮想的に埋め尽くす範囲の幅(横回転)/高さ(縦回転)<br><br>指定なき場合は、refresh時の全carousel itemの幅(横回転)/高さ(縦回転)<br><br> | null |
| onScroll | function() | スクロール中に随時呼ばれるコールバック関数 | null |
| onStart | function() | <br>スクロール開始時に呼ばれるコールバック関数<br><br>関数は、引数なし。戻り値なし。<br><br>onStartは、onStopを挟まずに、複数回呼ばれることがある。アプリケーションはこのコールバックを動き始めを示唆するヒント情報として扱う必要がある。<br><br> | null |
| onStop | function(pos) | <br>スクロール終了時、および位置移動が確定した時に呼ばれるコールバック関数<br><br>関数の引数は(bodyの)スクロール位置。戻り値は、なし。<br><br>スクロール終了時以外にも、位置移動が確定したときに呼ばれる。アプリケーションはこのコールバックを位置確定を示唆するヒント情報として扱う必要がある。<br><br>たとえば、scroll(0, null)はtransitionなしでposition=0に移動するが、onStartは呼ばれないが、onStopは呼ばれる。<br><br> | null |
| inertial | Boolean | <br>スクロールのスタイルを規定する。<br><br>true：フリックでは、フリック速度に応じた量をスクロールする。グリッドが指定されている場合、最も近いグリッド位置に合わせる。<br><br>false：フリック、ドラッグとも最終移動方向で直近のグリッド位置へ移動する。(グリッド指定が必須)<br><br> | true |

| function(pos, nextPosition) |   |   |
|:--------------------------- |:--- |:--- |
| onScroll で用いるコールバック関数 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| pos | Integer | スクロール位置 |
| nextPositions | Array(Integer) | それぞれのcarousel itemのbody内での左端(横回転)/上端(縦回転) の位置 |

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> なし

-   メソッド

| .cscwCall(“gesture”, value) |   |   |
|:--------------------------- |:--- |:--- |
| 利用者のタッチ操作に対するスクロールの振る舞いを切り替える。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| value | Boolean | <br>true　タッチ操作に従いスクロールを行う。<br><br>false　タッチ操作を無視する。<br><br> |

| .cscwCall(“gesture”) |   |   |
|:-------------------- |:--- |:--- |
| 利用者のタッチ操作に対するスクロールの設定を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Boolean | <br>true　タッチ操作に従いスクロールを行う。<br><br>false　タッチ操作を無視する。<br><br> |

| .cscwCall(“body”) |   |   |
|:----------------- |:--- |:--- |
| Carousel itemを載せてスクロールするcarousel itemの親要素 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | jQueryObject |  |

| .cscwCall(“stop”)  |
|:------------------ |
| スクロールを現在位置で止める。 |

| .cscwCall(“position”, pos[, transition])  |   |   |
|:--------------------------------------- |:--- |:--- |
| (Bodyの)スクロール位置を設定する |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| pos | Integer | スクロール位置 |
| transition | Integer | <br>Transitionを⾏う時間( ミリ秒 )<br><br>指定なき場合は、transitionなし。<br><br> |

| .cscwCall(“position”) |   |   |
|:--------------------- |:--- |:--- |
| (Bodyの)スクロール位置を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | 位置 |

| .cscwCall(“refresh”)  |
|:--------------------- |
| <br>表示更新を行う。<br><br>carousel itemの増減および大きさの変更が行われた場合は、本メソッドをコールすること。<br><br> |

| .cscwCall("totalSize")  |
|:--------------------- |
| 全CarouselItemの合計高さ/幅を取得する。<br>direction: "vertical"の場合は高さを、direction: "horizontal"の場合は幅を取得する。<br>本メソッドで取得できる値は各Item間のマージン(2px)を含んだ値である。(最後のItemの下/右にもマージンがあるものとする) |

| .cscwCall(“range”, params)  |   |   |
|:--------------------------- |:--- |:--- |
| スクロール可能範囲を変更する |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| params | Object | スクロール可能範囲の変更内容を指定するオブジェクト。 |

> params で用いるオブジェクト

| Property | Type | Description |
|:-------- |:---- |:----------- |
| min | Integer | <br>スクロール範囲左端/上端位置。<br><br>指定なき場合は、制限なくスクロールする。<br>showScrollBarがtrueの場合、同時にmaxも指定する必要がある。<br><br> |
| max | Integer | <br>スクロール範囲右端/下端位置。<br><br>指定なき場合は、制限なくスクロールする。<br>showScrollBarがtrueの場合、同時にminも指定する必要がある。<br><br> |
| virtualTotalSize | Integer | <br>有限の範囲でスクロールする場合に、carousel itemが仮想的に埋め尽くす範囲の幅(横回転)/高さ(縦回転)。<br><br>指定なき場合は、全carousel itemの幅(横回転)/高さ(縦回転)。<br><br> |
| position | Integer | <br>スクロール位置<br><br>指定なき場合は、現在の位置のまま。<br><br> |

-   イベント

> なし