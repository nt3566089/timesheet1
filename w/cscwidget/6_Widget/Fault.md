[Fault](../abstractwidgetcontents)
======

機能
-----

-   概要

> フォルト画面

-   機能

> パネル画面全体を覆う、フォルト画面を表示する。
>
> 本Widgetはコンテナとして、上に配置される部品に対して黒色(black)を背景に持つことを考慮した色彩を適用する。ただし、Header部に関しては、赤色(red)を背景に持つことを考慮した色彩を適用する。
>
> Fault画面が開く/閉じる動作の間、FaultはFault画面への利用者の画面操作を無視する。

-   操作

> なし。
>
> 画面内に配置された部品が操作を受け付けるが、ここでは言及しない。

-   音

> なし

-   レイアウト

> フォルト画面内に配置されたcscwidgetに対して、フォルト内に配置されていることを示すコンテキスト（Container
> theme black）を提供する。
>
> 　Fault内の表示内容は、タイトルエリア(Header)、メディアエリア（省略可）、コンテンツエリア、　コマンドエリア、マシンイメージエリアに分けて定義され、それぞれが適切なPadding値を持って配置される。
>
> タイトルエリアは、Headerの定義に従う。ただし、色彩はApplication
> themeには依存せず、バー本体、バー上のボタンともに、常にのカラーテーマが適用される。また、タイトル文字列の最大幅(title
> max-width) はフォルト画面幅のである。
>
> メディアエリアは、基本的には、規定サイズの動画ファイルを配置するための領域である。フォーマットは、ogvファイルを想定している。必要に応じて、動画だけではなく、イメージファイルも配置可能である。
>
> コンテンツエリアは、アプリケーションが指定したテキストやボタン、ScrollPaneとその内部のテキストなどを配置するための領域である。
>
> エラーコードエリアは、chain-linkを示す文字列を表示するエリアである。
>
> **メディアエリアを持つフォルトのレイアウト**
>
> **メディアエリアを持たないフォルトのレイアウト**
>
> **各種スタイル（サイズ）定義**

<table>
<thead>
<tr class="header">
<th>UI</th>
<th>width</th>
<th>height</th>
<th>CL</th>
<th>Center padding</th>
<th>Media</th>
<th>Contents</th>
<th></th>
<th></th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td>height</td>
<td>Outside padding</td>
<td></td>
<td>width</td>
<td>height</td>
<td>border-radius</td>
<td>width</td>
<td>height</td>
</tr>
<tr class="even">
<td>5”</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>10””</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

> 44**色定義**

<table>
<thead>
<tr class="header">
<th>background-color</th>
<th>font-color</th>
<th>Header</th>
<th>Media Area</th>
<th>エラーコード</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
<td>background-color</td>
<td>Button色定義等</td>
<td>background-color</td>
<td>font-color</td>
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

> Header内のフォントサイズについては、Headerの規定に従う。
>
> エラーコードエリアに対しては、のフォントが適用される。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> Fault画面内の各コンテンツの配置、およびHeaderのボタンの配置は、LTR/RTLにかかわりなく一定。変更しない。(
> コンテンツエリアに表示される各表示項目は、それぞれの表示項目のレイアウトルールに従う。なお、複数行の説明文を配置する場合、原則としてRTL表記では右寄せのrtl
> で表示する。)
>
> FaultのHeader
> のボタンとタイトルは、指定に従い、LTR表記またはRTL表記で表示する。
>
> エラーコードエリアの表示は、常にLTR表示で表記する。変更しない。エラーコードエリアには、025-007
> のような3ケタの数字二つをハイフンで結んだエラーコード、もしくはそれらをカンマで並べたものが表示される。エラーコードの二つの数字の順序はアラビア語であっても英語と同じ順序にする取決めとしているので、LTR/RTLでの違いはない。

-   Transition

> 表示開始時：スケールダウン(とフェードインが同時に適用される。Durationは
>
> 表示終了時：スケールアップ(とフェードアウトが同時に適用される。Durationは

API Documentation
-----

-   オブジェクト名

> Fault

-   コンストラクタ

> $.cscwFault (\[options\]) :アラート画面を生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”Fault”&gt;&lt;/div&gt; |
| Script | $(“#Fault”).cscwFault(); |

-   オプション

| Property | Type | Description	| Default |
|:-------- |:---- |:----------- |:------- |
| title\*1 | <br>String/<br>Array/<br>jqueryObject<br><br> | <br>Headerのタイトル部*1<br><br>String<br>タイトル文字列。改行を含めることで2行での表示が可能。<br><br>Array<br>タイトル文字列。2行での表示が可能。(文字列が長い場合は各行でtruncateする)<br><br>jQueryObject<br>タイトル文字列を示すjQueryObject。<br><br>どのTypeの指定でも3行以上の改行は行わないこと。<br><br> | null |
| truncate | String | <br>テキスト長が、領域幅を超過したときの省略描画の適用<br><br>下記以外の値を指定しないこと<br><br>null：超過が起きない場合に使うことを前提とし、超過した場合の挙動は保証しない<br><br>"end"：⽂字列後⽅を省略表⽰する<br><br>"middle"：⽂字列の中央を省略表⽰する<br><br> "begin"：⽂字列前⽅を省略表⽰する<br><br> | null |
| autoWrap | Boolean | テキスト長が領域幅を超える場合の折り返しを行うか否か<br><br>truncateで"begin", "middle"を指定した場合はtrueにしてはならない | false |
| dir | String | <br>タイトル文字列の書き進む方向( text direction)を指定する。<br><br>“ltr”：左から右へ書き進む。<br><br>“rtl”：右から左へ書き進む。<br><br>null指定の場合、指定なしと同様の動作をする。<br><br> | CSCWidgetのデフォルト設定に従う |
| leftButton | Object | 左側に配置するボタンに関する情報 | null |
| rightButton | Object | 右側に配置するボタンに関する情報 | null |
| errorCode	| String | <br>エラーコードエリアに表示する文字列。改行を含んではならない。<br><br>null の場合、エラーコードエリアには何も表示しない。<br><br> | null |
| titleWidth | String | <br>タイトル領域の幅<br><br>"wide"：広い領域幅<br><br>"normal"：通常の領域幅<br><br>"narrow"：狭い領域幅<br><br> | "normal" |

\*1　
StringおよびArray型指定時における各配列要素は、改行を含んではならない。

-   leftButton / rightButton で使用するObjectの定義

> Headerの項を参照。

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> 　　なし

-   関連情報のMarkupによる指定

> コンストラクタをコールする要素の子要素に以下のタグが存在する場合、

-   class=”
    cscw-fault-media”　を持つ任意の要素（Div要素である必要はない）

-   div(class=” cscw-fault-content”) …　コンテント

-   div(class=” cscw-fault-commandArea”) …　コマンドエリア

-   div(class=” cscw-fault-machineImageArea”) …　マシンイメージエリア

> として認識される。

-   メソッド

| .cscwCall(“errorCode”, errorCode) |   |   |
|:--------------------------------- |:--- |:--- |
| エラーコードエリアに表示する文字列を指定された文字列に差し替える |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| errorCode | String | <br>エラーコードエリアに表示する文字列。<br><br>null の場合、エラーコードエリアには何も表示しない。<br><br> |

| .cscwCall(“errorCode”) |   |   |
|:---------------------- |:--- |:--- |
| エラーコードエリアに表示している文字列を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | エラーコードエリアに表示している文字列 |

| .cscwCall(“status”, status[, transition]) |   |   |   |
|:----------------------------------------- |:--- |:--- |:--- |
| フォルト画面およびその内部に配置されたアイテムを表示/非表示にする。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | show | 表示する |
|  |  | hide | 非表示にする |
| transition | Boolean | true | <br>transitionを適用する<br><br>省略時はtrueとして扱われる<br><br> |
|  |  | false | transitionを適用しない |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Promise | <br>以下のタイミングで、コールバックが呼ばれる。クリティカルなタイミングにおける挙動については、Alertの同名メソッドの注釈を参照。<br><br>done　指定されたstatusへの内部状態、および描画を含む全ての処理が完了したとき<br><br>fail　上記の完了前に、指定されたstatusとは、別のstatusへの変更が指示されたとき<br><br> |  |

| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| フォルト画面の表示状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | show | 表示状態 |
|  |  | hide | 非表示状態 |

| .cscwCall(“title”, title [,dir]) |   |   |
|:-------------------------------- |:--- |:--- |
| タイトルラベルを切り替える。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| title | String/Array | タイトルラベル文字列 |
| dir | String | <br>タイトル文字列の書き進む方向( text direction)を指定する。省略時は、現在の書き進む方向のままで変更しない。<br><br>“ltr” 左から右へ書き進む。英語など<br><br>“rtl” 右から左へ書き進む。アラビア語<br><br> |

| .cscwCall(“title”) |   |   |
|:------------------ |:--- |:--- |
| タイトルラベルを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String/Array | 表示されているタイトルラベル文字列 |

| .cscwCall(“leftButton”) |   |   |
|:----------------------- |:--- |:--- |
| 左側ボタンを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Object/jQuery | 表示されている左側ボタンを示す |

| .cscwCall(“rightButton”)	 |   |   |
|:-------------------------- |:--- |:--- |
| 右側ボタンを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Object/jQuery | 表示されている右側ボタンを示す |

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwChanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| フォルト画面の状態が変わった時に発生	 |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | status | String | show | 表示開始 |
|  |  |  | hide | 表示終了 |

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwTransitionEnd |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| 状態変更指示に伴う、描画処理を含むすべての処理が完了したことを示す |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | property | String | status　固定 |  |
|  | value | String | show | 表示開始 |
|  |  |  | hide | 表示終了 |
|  | result | String | completed | 正常に完了した |
|  |  |  | 	cancelled | キャンセルされた |