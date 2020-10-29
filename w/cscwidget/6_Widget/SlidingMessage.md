[Sliding Message](../abstractwidgetcontents)
======

機能
------

-   概要

> 通知用メッセージ表示領域

-   機能

> 表示指示に従い、画面上部からスライド表示する。閉じるボタンのみを内部に持ち、他のSlidingMessage内の表示事項は、アプリケーションがすべて記載することを前提とする。
>
> SlidingMessage表示完了後、指定時間が経過すると自動的に非表示状態への移行を開始する。
>
> 本Widgetはコンテナとして、上に配置される部品に対してを背景に持つことを考慮した色彩を適用する。

-   操作

> SlidingMessage自体のタップと、SlidingMessage内の閉じるボタンのタップを受け付ける。
>
> 閉じるボタンがタップされた場合は、自身を非表示とする。

-   音

> なし

-   レイアウト

**全体レイアウト**

**各種スタイル定義**

<table>
<thead>
<tr class="header">
<th></th>
<th>height</th>
<th>min-height</th>
<th>width</th>
<th>inside padding</th>
<th><p>close button</p>
<p>width/height</p></th>
<th><p>button</p>
<p>margin1</p></th>
<th><p>button</p>
<p>margin2</p></th>
<th>font-size</th>
<th>no react margin</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>5inch</td>
<td><p>アプリ</p>
<p>指定</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>10inch</td>
<td><p>アプリ</p>
<p>指定</p></td>
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

**色彩定義**

<table>
<thead>
<tr class="header">
<th>box-shadow</th>
<th>background-color</th>
<th>font-color</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

> なお、アプリケーションから指定された、SlidingMessage内表示項目は、SlidingMessage領域内に縦方向にセンタリングされて配置される。
>
> SlidingMessage内のフォント指定はデフォルト値であり、アプリケーションからの書き換えを可能とする。
>
> 他、ボタンの色等は、のテーマに従う。
>
> &lt;RTL表記でのレイアウトについて&gt;

「閉じる」ボタンは常にSlidingMessageの右端に表示される。「閉じる」ボタンのグリフは、常にLRT表記。

SlidingMessageの中に表示される内容は、SlidingMessageとは別に生成されて配置される。そのため、SlidingMessageは表記のLTR/RTLを関知しない。

-   Transition

> 表示時は、パネル下部から　durationは
>
> 非表示にする際は、パネル下部に向かってDutationは

API Documentation
------

-   オブジェクト名

> SlidingMessage

-   コンストラクタ

> $.cscwSlidingMessage (\[options\]) :SlidingMessageを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”SlidingMessage”&gt;&lt;/div&gt; |
| Script | $(“#SlidingMessage”).cscwSlidingMessage(); |

-   オプション

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| height | Integer | <br>SlidingMessageの高さ（px）<br><br>指定無き場合はcssで指定された値を適用。<br><br>css指定もない場合はSlidingMessageに含まれる要素とSlidingMessageのマージン値から、ブラウザによって計算される。<br><br> | "auto" |
| closeButton | Object | <br>閉じるボタンに関する情報。<br><br>指定無き場合は、デフォルトのボタンが配置される。<br><br> | 下記デフォルト値を参照 |
| timeout | Integer | <br>自動的に非表示になるまでのタイムアウト時間(msec)<br><br>-1　が指定された場合は、タイムアウトしない。<br><br> | 3000 |
| layer | Integer | <br>SlidingMessageの表示階層を示す値。数字が大きいものほど前面に表示される。<br><br>400～499<br><br> | 400 |
| left | Integer | <br>SlidingMessageの表示位置(CSSのleft)。画面左端からのpx値で指定する。<br><br> | 100 |

-   closeButton で使用するObjectの定義

| property | type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| enable | Boolean | <br>falseにするとDisable状態となり、操作を受け付けない<br><br> | true |
| soundEnable | Boolean | <br>Widgetによる操作音(valid音)の鳴動制御<br><br>true：操作音を鳴らす<br><br>false：操作音を鳴らさない<br><br> | true |
　
なお、closeButtonを利用しない場合は、明示的にcloseButtonにnullを設定すること。

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> コンストラクタをコールする要素に対して、heightを指定することで、サイズを指定できる。
>
> Example:　　\#SlidingMessage{ height:80px;}

-   メソッド

| .cscwCall(“status”, status[, transition]) |   |   |   |
|:----------------------------------------- |:--- |:--- |:--- |
| SlidingMessageおよびその内部に配置されたアイテムを表示/非表示にする。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | SlidingMessageおよびその内部に配置されたアイテムの表示可否 |  |
|  |  | show | 表示する |
|  |  | hide | 非表示にする |
| transition | Boolean | transitionの可否<br>省略時はtrueとして扱われる |  |
|  |  | true | transitionを適用する |
|  |  | false | transitionを適用しない |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Promise | SlidingMessageおよびその内部に配置されたアイテムの表示表示可否<br>クリティカルなタイミングにおける挙動については、Alertの同名メソッドの注釈を参照 | |
| | | done | 指定されたstatusへの内部状態、および描画を含む全ての処理が完了したとき|
| | | fail |　上記の完了前に、指定されたstatusとは、別のstatusへの変更が指示されたとき |



| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| SlidingMessageの表示状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | show | 表示状態 |
|  |  | hide | 非表示状態 |

| .cscwCall(“timeout”, timeout) |   |   |   |
|:----------------------------- |:--- |:--- |:--- |
| SlidingMessageの表示が開始されてから、自動的に消えるまでのタイムアウト時間(msec)を設定する。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| timeout | Integer | -1 もしくは0以上の整数 | タイムアウト時間 |

| .cscwCall(“timeout”) |   |   |   |
|:-------------------- |:--- |:--- |:--- |
| SlidingMessageの表示が開始されてから、自動的に消えるまでのタイムアウト時間(msec)を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Integer | -1 もしくは0以上の整数 | タイムアウト時間 |

| .cscwCall(“layer”, layer) |   |   |
|:------------------------- |:--- |:--- |
| SlidingMessageの表示階層を示す値を設定する。値が不正である場合はエラーを返す。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| layer | Integer | SlidingMessageの表示階層 |

| .cscwCall(“layer”) |   |   |
|:------------------ |:--- |:--- |
| SlidingMessageの表示階層を示す値を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | SlidingMessageの表示階層 |

| .cscwCall(“refresh”) |
|:-------------------- |
| <br>Widgetの表示更新を行う。<br><br>SlidingMessage内部の構成要素（body）のサイズが変更された場合は、本メソッドをコールすること。<br><br> |

| .cscwCall(“left”, left ) |   |   |
|:------------------------- |:--- |:--- |
| SlidingMessageの表示位置(CSSのleft)を設定する。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| layer | Integer | SlidingMessageのleftの値 |

| .cscwCall(“left”) |   |   |
|:------------------ |:--- |:--- |
| SlidingMessageの表示位置(CSSのleft)を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | SlidingMessageのleftの値 |

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwChanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| SlidingMessageの状態が変わった時に発生 |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | status | String | show | 表示開始 |
|  |  |  | hide | 表示終了 |

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwTransitionEnd |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| <br>状態変更に伴う、描画処理を含むすべての処理が完了したことを示す。<br><br>ユーザ操作(closeButtonの押下及びタイムアウト)による状態変更が試みられた場合、意図した操作およびその結果にかかわらず、最終状態(表示/非表示)のcompleteとして扱われる。<br><br>(ex　hide操作を試みたが、ドラッグ距離が足りずにshowに戻った場合：value:show result:completed)<br><br> |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | property | String | status（固定） |  |
|  | value | String | show | 表示開始 |
|  |  |  | hide | 表示終了 |
|  | result | String | completed | 正常に完了した |
|  |  |  | cancelled | キャンセルされた |

| イベントタイプ |
|:------------- |
| cscwTap |
| **イベントのトリガ** |
| 状態変更に伴う、描画処理を含むすべての処理が完了したことを示すSlidingMessageの状態が変わった時に発生 |  |  |  |  |