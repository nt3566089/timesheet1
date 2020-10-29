[Grid](../abstractwidgetcontents)
======

機能
----

-   概要

> グリッド（全体）。

-   機能

> 内部に配置された複数のグリッドアイテムをまとめて、グリッド全体としての見た目や挙動の整合をとる。

-   操作

> フリック（内部にスクロールが適用された場合のみ）
>
> 他の操作は、内部に配置されたグリッドアイテムが受け付ける。

-   種類

> グリッドはスクロール可能なものと不可能なものがあり以下に分類される。
>
> 固定グリッド：内容に関わらずスクロールしないもの。
>
> カルーセルグリッド：必要に応じてスクロールするもの。（この場合、かならずカルーセルが適用される）

-   音

> なし

-   レイアウト

> <span
> class="underline">＜グリッドの最大高さ（maxHeight）および高さ（Height）の指定有無による描画内容の違い＞</span>
>
> <span class="underline">いずれも指定しない場合</span>
>
> グリッドとしては何も描画しない。
>
> 高さは、中に入ったGridItemの大きさ/数によって決定され、外形はGridItemの外形線で構築される。
>
> <span class="underline">maxHeightのみを指定した場合</span>
>
> グリッドは、中に入ったGridItemの大きさ/数によって決定される高さと、maxHeightにて指定された高さのうち値が小さい方に従って、外形線を描画する。さらに、中にGridItemがひとつもない場合には、アプリケーションが指定した文字列が、Grid内(1行目のGridItem相当エリア内)に、センタリング表示される。
>
> <span class="underline">heightのみを指定した場合</span>
>
> <span class="underline"> </span>
> グリッドは、heightで指定された高さに従って、外形線を描画する。
>
> 中に入ったGridItemの大きさ/数によって決定される高さが、heightで指定された値よりも小さい場合には、外形線が透過()で描画される。さらに、中にGridItemがひとつもない場合には、アプリケーションが指定した文字列が、Grid上部(1行目相当エリア内)に、センタリング表示される。
>
> **グリッドの高さもしくは最大高さが規定される場合のスタイル定義（上段:5inch/下段:10inch）**

| width | max-width | maxHeight | border-width | border-radius | border-color |
|:----- |:--------- |:--------- |:------------ |:------------- |:------------ |
| アプリ指定 |  | <br>アプリ指定<br><br>(任意)<br><br> |  |  | テーマカラーに依存。*1 |

> \*1　適用されているApplication / Container
> themaにおける、Buttonの外形線の色に従う。
>
> **内部にGridItemがひとつもない場合の表示例**
>
> <span class="underline">＜角丸(border-radius)の適用＞</span>
>
> 複数のInteractive GridItemおよびReadOnlyGrid
> Itemを、Gridとしてまとめた際、一番上に配置されたGridItemに対して、左上、右上の角に対して、border-radius　の規定値を適用する。同様に、一番下に配置されたGridItemに対しては、左下、右下の角に対して、border-radiusの規定値を適用する。さらに、一番下に配置されたGridItemについては、通常存在しない下辺に対して、上辺と同じスタイルを適用して描画する。

-   カルーセルの適用について

> Grid内に表示すべきデータ数が非常に多い場合、データ数に対応した数のGridItemを作成するのではなく、内部にカルーセルを適用するとともに、一度に表示される行数＋α　のGridItemを使いまわす方法を用いることが望ましい。
>
> カルーセルを用いた場合の仕組みについて記載する。
>
> **カルーセルを利用した場合の仕組み**
>
> 　アプリケーションは、必要な数のGridItemを作成し、Grid配下に配置する。
>
> カルーセルをスクロールすると、見えている範囲が変化するため、GridItem内に表示する内容の変更が必要となる。Gridは、その旨をコールバックにてアプリケーションに伝える。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> 内部にGridItemが一つもないことを示す文字列: empty caption
> は、CSCWidgetのデフォルト設定に従いtrlまたはltrで表示される。(センタリング表示は変わらない)
>
> RTL表記であっても、スクロールインジケータは右端に表示する。

-   制限事項

<!-- -->

-   gray, color,black以外のコンテナ色には対応していない。

API Documentation
----

-   オブジェクト名

> grid

-   コンストラクタ

> $.cscwGrid (\[options\]) :グリッドを生成するコンストラクタ。
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”Grid”&gt;&lt;/div&gt; |
| Script | $("#Grid").cscwGrid(); |

-   CarouselGridに関する注意事項

> 生成後にnItemsを呼ぶことで、onUpdateが呼び出され、最初の表示の準備が行なわれる。
>
> 状態管理、status=on/offおよびenable=true/falseの状態はGrid側では管理しない。ただし、action:altのgridではstatus=on/offはgrid側で管理し、seletedメソッドでget/setできる。
>
> onUpdateで非同期処理する場合は、最新のassignStart/assignEndをアプリ側でトラックする必要がある。

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| onUpdate | Function | <br>Gridウィジェットは、本パラメータがnullでない場合にカルーセルを適用する。<br><br>内部に表示されるGridItemの更新用コールバック関数。<br><br> | null |
| width | Integer | <br>グリッド全体の幅。<br><br>指定がなければエラーになる。<br><br> | 必須 |
| maxHeight | Integer | <br>グリッド全体の高さの最大値。<br>中に配置されたアイテムの高さの合計が、指定した値を超える場合は、スクロールが適用される。<br><br>カルーセルの場合のみ有効。<br><br> | null |
| height | Integer | <br>グリッド全体の高さ。<br>中に配置されたアイテムの高さの合計が、指定した値を超える場合は、スクロールが適用される。<br><br>カルーセルの場合のみ有効。<br><br> | null |
| nColumns | Integer | グリッドの列数。<br><br>数値が指定されていなければエラーになる。 | 1 |
| itemHeight | Integer | <br>内部に表示されるGridItemの高さ。*1<br><br>GridItemのnormalレイアウト時の高さ。<br><br> | null |
| emptyCaption | String | <br>Grid内部にGridItemがひとつも存在しなかったときに表示される文字列。<br>複数の改行を含んではならない。<br><br>カルーセルの場合のみ有効。<br><br> | null |
| action | String | <br>各GridItemの動作種類。<br><br>下記以外の値を指定しないこと<br><br>"normal"：通常のコマンドボタン<br><br>"toggle"：On/Offがトグルで切り替わるボタン<br><br>"alt"：ラジオボタン<br><br> | "normal" |
| carouselOption | Object | <br>内部で生成するCarouselの生成時オプション。<br><br>本資料で挙げたもの以外のオプションについては無視されるもしくは、意図しない動作を引き起こすことがあるため、動作保証しない。<br><br>カルーセルの場合のみ有効。<br><br>showScrollBar<br>　　　　false：スクロールバーを表示しない。<br><br>　　　　true：スクロールバーを表示する　min/maxが指定されている必要がある。<br><br>※当オプションで指定する「grid」とは、本資料の「GridWidget」ではなく、CarouselWidgetの1ページ当たりの高さを指す概念」のことを言う。<br><br> | false |
| selected | Integer | <br>指定されたインデックス番号のアイテムを選択状態にする<br><br> | -1 |
| statusStyle | String | <br>GridItem選択時の振る舞いを指定する<br><br>下記以外の値を指定しないこと<br><br>"single"：GridItem選択時に背景色が変化する<br><br>"multi"：GridItem選択時に子要素として持つ特定のGlyphWidget*2の色が変化する<br><br> | "single" |

\*1　Tableウィジェットとは違い、gridウィジェットが各アイテムにitemHeightを設定する。

\*2　クラスにcscw-gi-changesGlyphColorを持つGlyphWidget

-   onUpdateに設定する関数の定義

| func(prop) |   |   |   |   |
|:---------- |:--- |:--- |:--- |:--- |
| Grid内に表示されるGridItemの更新処理を行う。 |  |  |  |  |
| 引数の説明 |  |  |  |  |
| **name** | **type** | **property**<br>**name**<br> | **property**<br>**type**<br> | **description** |
| prop | Object | assignStart | Integer | 表示候補として準備された(実GridItemに割り当てられた) 最初のデータを示すインデックス。 |
|  |  | assignEnd | Integer | 表示候補として準備された(実GridItemに割り当てられた) 最後のデータを示すインデックス。 |
|  |  | update | Array<br>(Integer) | 更新が必要なデータを示すインデックスの配列。 |

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> サポートしない

-   Fixedグリッドへのアイテム追加について

> グリッド配下へのアイテム追加は、後述するメソッド（.cscwCall”body”）を用いてグリッドの親要素を取得し、それに対して子要素を追加する方法で行う。取得した親要素の下に存在しうる要素は以下となる。

-   表示中のグリッドアイテム（GridItem）

<!-- -->

-   メソッド

| .cscwCall(“refresh”) |
|:------------------ |
| グリッドの表示更新を行う。<br>配下にあるGridItem数の増減（見た目の数ではなくDOMノードとしての増減）があった場合は、本メソッドをコールすること。 |

| .cscwCall(“body”) |   |   |
|:----------------- |:--- |:--- |
| <br>グリッドの親要素（グリッド内部にアイテムを追加する場合の基準となる要素）を取得する。<br><br>固定グリッドの場合のみ有効。<br><br> |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Object | Gridの親要素 |

| .cscwCall(“emptyCaption”, emptyCaption) |   |   |
|:--------------------------------------- |:--- |:--- |
| <br>グリッドが空になったときに表示される文字列を設定する。<br><br>Carousel適用時のみ有効。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| emptyCaption | String | グリッドが空になったときに表示される文字列 |

| .cscwCall(“emptyCaption”) |   |   |
|:------------------------- |:--- |:--- |
| <br>グリッドが空になったときに表示される文字列を取得する。<br><br>Carousel適用時のみ有効。<br><br> |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | グリッドが空になったときに表示される文字列 |

| .cscwCall(“item”, index) |   |   |
|:------------------------ |:--- |:--- |
| <br>Grid内の指定したインデックスを持つGridItemを取得する。<br><br>Carousel適用時には、指定したインデックスを持つデータが割り当てられている実GridItemを取得する。<br><br>インデックスが割り当てられていない場合はエラーとなる。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| index | Integer | 取得したいGridItemを示すインデックス |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | jQueryObject | 対応するGridItemを示すjQueryObject |

| .cscwCall(“position”, pos[, transition]) |   |   |
|:-------------------------------------- |:--- |:--- |
| 指定位置にスクロールする。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| pos | Integer | スクロール位置 |
| transition | Integer | <br>Transitionを行う時間( ミリ秒 )<br><br>指定なき場合は、transtionなし。<br><br> |

| .cscwCall(“position”) |   |   |
|:--------------------- |:--- |:--- |
| スクロール位置を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | スクロール位置 |

| .cscwCall(“nItems”, nItems, index) |   |   |
|:--------------------------- |:--- |:--- |
| <br>グリッド内部で扱う総データ数を設定する。<br><br>Carousel適用時のみ有効。<br><br>indexが指定されている場合には指定位置に移動する(スクロールはしない)。0 ≦ n < nItemsの整数のみをサポートする。 |  |  |\
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| nItems | Integer | グリッド内部で扱う総データ数 |
| index | Integer | 先頭行に表示するgridのindex番号 |

| .cscwCall(“nItems”) |   |   |
|:------------------- |:--- |:--- |
| <br>グリッド内部で扱う総データ数を取得する。<br><br>Carousel適用時のみ有効。<br><br> |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | グリッド内部で扱う総データ数 |

| .cscwCall(“index”, index[, transition]) |   |   |
|:------------------------------------- |:--- |:--- |
| <br>指定したインデックスを持つアイテムの位置にスクロールする。<br><br>Carousel適用時のみ有効。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| Index | Integer | スクロール位置を示すインデックス |
| transition | Integer | <br>Transitionを行う時間( ミリ秒 )<br><br>指定なき場合は、transtionなし。<br><br> |

| .cscwCall(“selected”, selected) |   |   |
|:------------------------------- |:--- |:--- |
| 指定したインデックスを持つアイテムを選択状態にする。<br><br>action:"alt"のときのみ有効。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| selected | Integer | 選択状態にするアイテムのインデックス |

| .cscwCall(“selected”) |   |   |
|:--------------------- |:--- |:--- |
| 選択されているアイテムのインデックスを返す。<br><br>action:"alt"のときのみ有効。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | 選択されているアイテムのインデックス |

| .cscwCall(“carousel”) |   |   |
|:------------------- |:--- |:--- |
| <br>グリッド内部で扱うカルーセル要素のjQueryObjectを取得する。<br><br>Carousel適用時のみ有効。<br><br> |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | jQueryObject | グリッド内部で扱うカルーセル要素のjQueryObject |