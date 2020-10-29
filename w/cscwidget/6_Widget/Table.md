[Table](../abstractwidgetcontents)
======

機能
----

-   概要

> テーブル（全体）。

-   機能

> 内部に配置された複数のテーブルアイテムをまとめて、テーブル全体としての見た目や挙動の整合をとる。

-   操作

> フリック（内部にスクロールが適用された場合のみ）
>
> 他の操作は、内部に配置されたテーブルアイテムが受け付ける。

-   音

> なし

-   レイアウト

> <span
> class="underline">＜テーブルの最大高さ（maxHeight）および高さ（Height）の指定有無による描画内容の違い＞</span>
>
> <span class="underline">いずれも指定しない場合</span>
>
> テーブルとしては何も描画しない。
>
> 高さは、中に入ったTableRowの大きさ/数によって決定され、外形はTableRowの外形線で構築される。
>
> <span class="underline">maxHeightのみを指定した場合</span>
>
> テーブルは、中に入ったTableRowの大きさ/数によって決定される高さと、maxHeightにて指定された高さのうち値が小さい方に従って、外形線を描画する。
>
> <span class="underline">heightのみを指定した場合</span>
>
> <span class="underline"> </span>
> テーブルは、heightで指定された高さに従って、外形線を描画する。
>
> 中に入ったTableRowの大きさ/数によって決定される高さが、heightで指定された値よりも小さい場合には、外形線が透過(opacity
> )で描画される。さらに、中にTableRowがひとつもない場合には、アプリケーションが指定した文字列が、Table上部(1番目のTableRow相当エリア内)に、センタリング表示される。
>
> **テーブルの高さもしくは最大高さが規定される場合のスタイル定義（上段:5inch/下段:10inch）**

<table>
<thead>
<tr class="header">
<th>width</th>
<th>max-width</th>
<th>maxHeight</th>
<th>border-width</th>
<th>border-radius</th>
<th>border-color</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>アプリ指定</td>
<td></td>
<td><p>アプリ指定</p>
<p>(任意)</p></td>
<td></td>
<td></td>
<td>テーマカラーに依存。*1</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

> \*1　適用されているApplication / Container
> themaにおける、Buttonの外形線の色に従う
>
> **内部にTableRowがひとつもない場合の表示例**
>
> <span class="underline">＜Altanatting　デザインの適用＞</span>
>
> **Altanating デザイン**
>
> 奇数行目のテーブルローに対して、別途テクスチャが適用される。
>
> テクスチャは、Application themaがDark
> Grayのときは、DarkGrayの代替用テクスチャ、その他の場合は、Grayの代替用テクスチャを用いるものとする。
>
> <span class="underline">＜角丸(border-radius)の適用＞</span>
>
> 複数のTableRowおよびReadOnlyTable
> Rowを、Tableとしてまとめた際、一番上に配置されたTableRowに対して、左上、右上の角に対して、border-radius　の規定値を適用する。同様に、一番下に配置されたTableRowに対しては、左下、右下の角に対して、border-radiusの規定値を適用する。さらに、一番下に配置されたTableRowについては、通常存在しない下辺に対して、上辺と同じスタイルを適用して描画する。
>

-   内部に配置されたテーブルローの並び変えについて

> 並び変え可能である旨が設定されたTableの配下に存在するテーブルロー間では、テーブルローの操作により並び変えが可能である。並び変えの挙動は、一つのテーブルローをドラッグしていくと、ドラッグしているテーブルロー以外のアイテムは、ドラッグ中のテーブルローが挿入されるべき場所を都度空けるように連動して動く。これは、jQueryUI
> sortableのデフォルト挙動に従ったものである。
>
> テーブルローは、ソート中であっても自身が属するテーブルの外側に動かすことはできず、テーブル縦方向への移動のみ受け付ける。
>
> Alternatingデザインにて、テーブルローの並び変えを行った場合は、並び変えが確定したタイミングで適切な見た目に更新される。
>
> 内部にスクロールが適用されたテーブルの場合、テーブルローをドラッグしたまま、テーブル領域の上端/下端まで来ると、テーブルのスクロールが行われる。また、テーブルがスクロール可能領域の内部に配置された場合は、テーブルローをドラッグしたままスクロール可能領域（CSCWidgetとして提供されているScrollPane）の上端/下端まで来ると、スクロール可能領域のスクロールが行われる。
>
> 現状、テーブルの内外を問わず、ScrollPaneの入れ子2つ分まで、本スクロールの挙動に対応している。

-   カルーセルの適用について

> Table内に表示すべきデータ数が非常に多い場合、データ数に対応した数のTableRowを作成するのではなく、内部にカルーセルを適用するとともに、一度に表示される行数＋α　のTableRowを使いまわす方法を用いることが望ましい。
>
> カルーセルを用いた場合の仕組みについて記載する。
>
> **カルーセルを利用した場合の仕組み**
>
> 　アプリケーションは、必要な数のTableRowを作成し、Table配下に配置する。Tableに対して、Alternatingデザインを適用する場合は、偶数個のTableRowを作成すること。
>
> カルーセルをスクロールすると、見えている範囲が変化するため、TableRow内に表示する内容の変更が必要となる。Tableは、その旨をコールバックにてアプリケーションに伝える。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> 内部にTableRowが一つもないことを示す文字列: empty caption
> は、CSCWidgetのデフォルト設定に従いtrlまたはltrで表示される。(センタリング表示は変わらない)
>
> RTL表記であっても、スクロールインジケータは右端に表示する。

-   制限事項

<!-- -->

-   本Widgetは、コンテナ色gray　の上に配置された場合は、本節記載の全ての機能/使い方　に対応しているが、コンテナ色colorおよびの上に配置された場合は、Altanatingデザインに対応していない。

-   gray, color,black以外のコンテナ色には対応していない。

-   内部に配置されたテーブルローの並び替え時の見た目に関しては、限られたユースケースについてのみ正常表示されることを保証する。以下の条件に合致するテーブルローについては、適切な見た目が適用されない。

<!-- -->

-   Alternatingデザインが適用されていないTableの下に配置された、ReadonlyTableRow。

-   Alternatingデザインが適用されていないTableの下に配置された、TableRowであり、statusがdisable。

-   コンテナ色として、が適用されたもの。

API Documentation
----

-   オブジェクト名

> table

-   コンストラクタ

> $.cscwTable (\[options\]) :テーブルを生成するコンストラクタ。
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”Table”&gt;&lt;/div&gt; |
| Script | $("#Table").cscwTable(); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| width | Integer | <br>テーブル全体の幅<br><br>null指定の場合親要素の幅に合わせたテーブル幅となる<br><br> | null<br><br>css指定を見る。指定無き場合はmaxWidth適用 |
| maxHeight | Integer | <br>テーブル全体の高さの最大値。中に配置されたアイテムの高さの合計がこれを超える場合は、スクロールが適用される。<br><br>null指定の場合(TableRowの高さ+2)*内部Rowの数-2で算出される<br><br> | null |
| height | Integer | <br>テーブル全体の高さ。中に配置されたアイテムの高さの合計がこれを超える場合は、スクロールが適用される。<br><br>null指定の場合(TableRowの高さ+2)*内部Rowの数-2で算出される<br><br> | null |
| emptyCaption | String | <br>Table内部にTableRowもしくはReadOnlyTableRowがひとつも存在しなかったときに表示される文字列。複数の改行を含んではならない。<br><br>null指定の場合、文字列を表示しない<br><br> | null |
| carousel | Object | <br>内部にカルーセルを適用し、TableRowの節約を行うための設定<br><br>null指定の場合、カルーセルを適用しない<br><br> | null |
| action | String | <br>各TableRowの動作種類<br>下記以外の値を指定した場合はタップイベントが正常に動作しない<br><br>"normal"：通常のコマンドボタン<br><br>toggle：On/Offがトグルで切り替わるボタン<br><br>"alt"：ラジオボタン<br><br>"reorder"：ドラッグによる行の入れ替え処理のみをサポート<br><br>normal / toggle / alt の指定は、readonlyTableRowに対しては無効。<br><br>| "normal" |
| statusStyle | String | <br>各TableRowの選択形式<br>下記以外の値を指定した場合、"single"と同様の動作をする。<br><br>"single"：選択時、TableRow全体の色が変化する<br><br>"multi"：選択時、TableRow内のGlyphの色が変化する(navigationGlyphは対象外)<br><br> | "single" |

-   carouselで使用するObjectの定義

| property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| onUpdate | Function | 内部に表示されるTableRowの更新用コールバック関数 | null |

\*1　ここで設定するのは、あくまでもTable Widgetのパラメータである。

別途生成したTableRow/ReadonlyTableRowのheightとして、この値が反映されるわけではない。

適宜、TableRow側で同等の値をheightとして指定する必要がある。

-   onUpdateに設定する関数の定義

| func(prop) |   |   |   |   |
|:---------- |:--- |:--- |:--- |:--- |
| Table内に表示されるTableRowの更新処理を行う |  |  |  |  |
| 引数の説明 |  |  |  |  |
| **name** | **type** | **property<br>name** | **property<br>type** | **description** |
| prop | Object | assignStart | Integer | 表示候補として準備された(実TableRowに割り当てられた) 最初のデータを示すインデックス。 |
|  |  | assignEnd | Integer | 表示候補として準備された(実TableRowに割り当てられた) 最後のデータを示すインデックス。 |
|  |  | update | Array<br>(Integer) | 更新が必要なデータを示すインデックスの配列。 |

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> コンストラクタをコールする要素に対して、widthを指定することで、サイズを指定することができる。
>
> maxHeightおよびheightのCSSによる指定には対応しない。
>
> Example:　　\#header{ width:500px;}

-   テーブルへのアイテム追加について

> テーブル配下へのアイテム追加は、後述するメソッド（.cscwCall(”body”)）を用いてテーブルの親要素を取得し、それに対して子要素を追加する方法で行う。取得した親要素の下に存在しうる要素は以下となる。
>
> -   表示中のテーブルアイテム（TableRowおよびReadOnlyTableRow。いずれもcscw-tr-visibleが適用されている）
>
> -   非表示となっているテーブルアイテム（&lt;span&gt;要素として存在。cscw-tr-invisibleが適用されている。）
>
> -   sort実現のための仮オブジェクト（&lt;span&gt;要素として存在。）
>
> 表示中のテーブルアイテムのみを考慮した処理を行う必要がある場合には、上記を踏まえてcssセレクタを適用する必要がある。
>
> また、上記方針に従い、TableHeader要素はbody配下の要素として扱われない。ReadOnlyTableRowのsectionスタイルのものは、body配下の要素として扱われる。両者は見た目が似通っているため、注意が必要である。

-   メソッド

| .cscwCall(“body”) |   |   |
|:----------------- |:--- |:--- |
| テーブルの親要素（テーブル内部にアイテムを追加する場合の基準となる要素）を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Object | Tableの親要素. |

| .cscwCall(“header”) |   |   |
|:------------------- |:--- |:--- |
| テーブル内のヘッダ要素を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Object | TableHeader要素 |

| .cscwCall(“emptyCaption”, emptyCaption) |   |   |
|:--------------------------------------- |:--- |:--- |
| テーブルが空になったときに表示される文字列を設定する<br>複数の改行を含んではならない。<br>null指定の場合、文字列を表示しない |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| emptyCaption | String | テーブルが空になったときに表示される文字列 |

| .cscwCall(“emptyCaption”) |   |   |
|:------------------------- |:--- |:--- |
| テーブルが空になったときに表示される文字列を取得する |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | テーブルが空になったときに表示される文字列 |

| .cscwCall(“item”, index) |   |   |
|:------------------------ |:--- |:--- |
| <br>Table内の指定したインデックスを持つTableRowを取得する。<br><br>Carousel適用時には、指定したインデックスを持つデータが割り当てられている実TableRowを取得する。<br><br>割り当てられていない場合はエラーとなる。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| index | Integer | 取得したいTableRowを示すインデックス |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | jQueryObject | 対応するTableRowを示すjQueryObject |

| .cscwCall(“position”, pos[, transition]) |   |   |
|:-------------------------------------- |:--- |:--- |
| 指定位置にスクロールする |  |  |
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
| <br>テーブル内部で扱う総データ数を設定する。<br><br>Carousel適用時のみ有効。<br><br>indexが指定されている場合には指定位置に移動する(スクロールはしない)。0 ≦ n < nItemsの整数のみをサポートする。|  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| nItems | Integer | テーブル内部で扱う総データ数 |
| index | Integer | 指定位置を示すインデックス |

| .cscwCall(“nItems”) |   |   |
|:------------------- |:--- |:--- |
| <br>テーブル内部で扱う総データ数を取得する<br><br>Carousel適用時のみ有効。<br><br> |  |  |
| 引数の説明 |  |  |
|  | **type** | **description** |
|  | Integer | テーブル内部で扱う総データ数 |

| .cscwCall(“addItems”, index, count) |   |   |
|:--------------------------- |:--- |:--- |
| <br>データを所定の位置に追加する。<br><br>Carousel適用時のみ有効。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| index | Integer | データを追加する位置を示すインデックス |
| count | Integer | 追加するデータ数 |

| .cscwCall(“removeItems”, index, count) |   |   |
|:-------------------------------------- |:--- |:--- |
| <br>データを所定の位置から削除する。<br><br>Carousel適用時のみ有効。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| index | Integer | データを削除する位置を示すインデックス |
| count | Integer | 削除するデータ数 |

| .cscwCall(“index”, index[, transition]) |   |   |
|:------------------------------------- |:--- |:--- |
| <br>指定位置にスクロールする。<br><br>スクロール機能(Carouselによるものを含む)を持たないテーブルに対しては、何も行わない。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| index | Integer | スクロール位置を示すインデックス |
| transition | Integer | <br>Transitionを行う時間( ミリ秒 )<br><br>指定なき場合は、transtionなし。<br><br> |

-   イベント

| イベントタイプ |   |   |
|:------------- |:--- |:--- |
| cscwTouchAndHold |  |  |
| **イベントのトリガ** |  |  |
| Table配下のアイテムが押下され所定の時間が経過し、ドラッグが開始されたとき発生。 |  |  |
| 戻り値 |  |  |
| **type** | **property** | **description** |
| Integer | index | <br>長押しされたアイテムのインデックス値<br><br>インデックスは、Table配下に置かれたTableRowおよびReadonlyTableRowに対して、非表示のものも含めて0から順に採番される。<br><br> |

| イベントタイプ |   |   |
|:------------- |:--- |:--- |
| cscwRelease |  |  |
| **イベントのトリガ** |  |  |
| cscwTouchAndHoldイベントが発生したのち、アイテムからリリースした(指を離した)時に発生 |  |  |
| 戻り値 |  |  |
| **type** | **property** | **description** |
| Integer | index | アイテムのインデックス値 |