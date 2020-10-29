[Popover](../abstractwidgetcontents)
======

機能
-------

-   概要

> ふきだし

-   機能

> ターゲット要素に付属するふきだしを表示する。ふきだし上にはを表示できる。本Widgetはコンテナとして、基本的には上に配置された部品に対して背景と同じ色を背景に持つことを考慮した色彩を適用するが、指定により、ふきだし自体の背景色を黒色とするとともに、その上の部品に対しても黒色背景上の色彩を適用することもできる。
>
> ふきだしを表示する位置と向きは、ターゲット要素の画面上の位置と大きさ、タップされた位置から決定される。
>
> ふきだしの大きさは、内包する項目の大きさに応じて決定されるケースと、アプリケーションから指定されるケースが存在する。
>
> ふきだしは、画面全体がブランケットで覆われた上に表示される。

-   操作

> ふきだし外の領域（ブランケット）のタップにより、ブランケットとふきだしを非表示にする。

-   音

> ブランケット部分押下時に、valid音が鳴動する。

-   レイアウト

> 　＜<span class="underline">ふきだしの描画＞</span>
>
> **全体レイアウト**
>
> **各種スタイル定義**

<table>
<thead>
<tr class="header">
<th>Display Size</th>
<th><strong>width</strong></th>
<th><p><strong>max</strong></p>
<p><strong>width</strong></p></th>
<th><p><strong>min</strong></p>
<p><strong>width</strong></p></th>
<th><strong>height</strong></th>
<th><p><strong>max</strong></p>
<p><strong>height</strong></p></th>
<th><p><strong>min</strong></p>
<p><strong>height</strong></p></th>
<th><p><strong>border</strong></p>
<p><strong>radius</strong></p></th>
<th><p><strong>padding</strong></p>
<p><strong>(inside)</strong></p></th>
<th><strong>box-shadow</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>5inch</td>
<td><p>アプリ</p>
<p>指定値</p></td>
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
<p>指定値</p></td>
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

> ふきだしには、background-imageが適用される。ここで適用されるテクスチャは、Application
> themeがDarkGrayのときのみDarkGray、それ以外の場合は、Grayのテクスチャ画像とする。
>

>
> <span class="underline">＜ブランケット＞</span>
>
> ブランケットは、画面全体を覆うように表示される塗りつぶし領域である。
>
> <span class="underline">配置ルール１</span>
>
> 基本的に、Popoverは本ルールに従って表示位置制御される。

-   ターゲットの上部にふきだしを配置することが望ましい。配置できない場合の優先度は、左、右、下の順とする。

-   配置可否判断は、Targetの上/左/右/下　に対して、ふきだしが表示できる領域が残されているか否かである。

-   ふきだしが表示可能な領域とは、パネル端からまで（5inchパネル）とする。

-   ふきだしの表示位置は、タップ位置を基準として計算される。

-   ターゲットの上もしくは下にふきだしを表示する場合は、ターゲットアイテムの長辺に対して、“ターゲットの辺に重ねる”のルールの適用により縦方向の位置が決定された上で、タップ位置、ふきだしの矩形部、が全て水平方向の中央揃えとなる。

-   ターゲットの左もしくは右に吹き出しを表示する場合は、ターゲットの縦方向の中心座標、ふきだしの矩形部、が全て垂直方向の中央揃えとなる。

-   吹き出しを配置しようとしたときに、吹き出しの矩形部が表示可能領域を超える場合は、矩形部のみをパネル中央方向にスライドさせて表示可能領域に収めるものとする。

> **ターゲットの上に表示する場合と左に表示する場合の位置**
>
> **矩形部のスライドが行われた例**
>
> <span class="underline">配置ルール２</span>
>
> Popoverが大きくtargetが画面中央付近に存在する場合、配置ルール１ではPopoverが表示できないケースが存在する。このとき、本ルールによる表示を試みる。

-   画面の右半分がタップされた場合、画面左端からを吹き出しの左端とする。ただし吹き出しの右端を「target右端から内側」あるいは「画面右端から」より右側に配置しなければならない場合配置失敗とする。画面の左半分がタップされた場合、
    画面右端からを吹き出しの右端とする。ただし吹き出しの左端を「target左端から内側」あるいは「画面左端から」より左側に配置しなければならない場合配置失敗とする。

-   タップ位置、ふきだしの矩形部、が全て垂直方向の中央揃えとなる配置が望ましいが、吹き出しの矩形部が表示可能領域を超える場合は、矩形部をパネル中央方向にスライドさせて表示可能領域に収めるものとする。

> **配置ルール２が適用されるケース**
>
> **（左：画面端からの条件が適用された場合　右：targetの端からの条件が適用された場合）**
>
> <span class="underline">配置ルール３</span>
>
> Popoverが非常に大きく、targetが画面中央付近にある場合、配置ルール１/２のいずれを適用してもPopoverが表示できないケースが存在する。この場合、このとき、Popoverは表示可能範囲の中央部に表示される。アプリケーションは、このケースが発生しないよう、Popoverの大きさやtargetの位置を適切に保つ設計をすべきである。
>
> <span class="underline">タップ位置が明示されない場合の挙動</span>
>
> 　表示指示時にタップ位置が明示されない場合、ふきだしは以下の位置に表示される。
>
> 　　ターゲットの上下に表示される場合：　ターゲットの中央部がタップされたときと同等の位置に表示。
>
> 　　ターゲットの左右に表示される場合：　ターゲットの左右に隣接して表示。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> PopoverはRTL/LTRを関知しない。
> Popover内に表示されるSwitchingや説明文などのRTL/LTR指定は、そのおのおので指定する。Popoverは関与しない。
>
> タップ位置からPopoverの表示する位置を決めるルールは、RTL表記であっても変わらない。例えば、ターゲットの上部にふきだしを配置することが望ましい。配置できない場合の優先度は、左、右、下　の順とする、などのルールは、LTR/RTLで同一とする。

-   Transition

> ふきだしの表示開始時に、表示終了時にする。Durationはとする。

API Documentation
-------

-   オブジェクト名

> popover

-   コンストラクタ

> $.cscwPopover (\[options\]) : ふきだしを生成するコンストラクタ。
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | <br>&lt;div id=”Popover” &gt;<br>&lt;div id=oneOfThree &gt;<br>&lt;div id=”SwitchItem1” &gt;&lt;/div&gt;<br>&lt;div id=”SwitchItem2” &gt;&lt;/div&gt;<br>&lt;div id=”SwitchItem3” &gt;&lt;/div&gt;<br>&lt;/div&gt;<br>&lt;/div&gt;<br><br> |
| Script | <br>$(“#SwitchItem1”).cscwSwitchItem();<br>$(“#SwitchItem2”).cscwSwitchItem();<br>$(“#SwitchItem3”).cscwSwitchItem();<br>$(“#oneOfThree”).cscwSwitching ();<br>$(“#Popover”). cscwPopover();<br><br> |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| target | jQueryObject | 表示基準となる要素。 | null |
| width | integer | <br>ふきだしの幅(px)。<br><br>外側に不随する要素の大きさは含まない。<br><br>指定がない場合は、ふきだし内に配置されたもののサイズから自動計算される。<br><br> | null |
| height | integer | <br>ふきだしの高さ(px)。<br><br>外側に不随する要素の大きさは含まない。<br><br>指定がない場合は、ふきだし内に配置されたもののサイズから自動計算される。<br><br> | null |
| layerDiff | integer | <br>targetとして指定された要素の表示レイヤとふきだしの表示レイヤとの差分。ふきだしは、targetに指定されたlayer値よりも指定値分大きなlayer値をとる。<br><br>1～1000<br><br> | 1 |

-   オプション相当情報のMarkupによる指定

> 　　なし

-   オプション相当情報のCSSによる指定

> コンストラクタをコールする要素に対して、widthとheightを指定することで、サイズを指定できる。
>
> Example:　　\#popover { width:200px; height:100px;}

-   メソッド

| .cscwCall(“status”, status, event[, transition]) |   |   |   |
|:------------------------------------------------ |:--- |:--- |:--- |
| ふきだしおよびその内部に配置されたアイテムを表示/非表示にする。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | ふきだしおよびその内部に配置されたアイテムの表示状態  | |
|  |  | show | 表示する |
|  |  | hide | 非表示にする |
| event | Event Object | タップされた位置の情報を含むイベント<br>cscwTapもしくは、clickなどclientXプロパティを持つことを条件とする。<br>本引数の指定として、nullを許容する。nullの場合の挙動は、機能説明の、タップ位置が明示されない場合に関する記載を参照。<br> |  |
| transition | Boolean | transitionの可否<br>省略時はtrueとして扱われる | |
|  |  | true | transitionを適用する |
|  |  | false | transitionを適用しない |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Promise | 以下のタイミングで、コールバックが呼ばれる。クリティカルなタイミングにおける挙動については、Alertの同名メソッドの注釈を参照。|  |
|  |　| done　| 指定されたstatusへの内部状態、および描画を含む全ての処理が完了したとき |
|  |　 | fail | 上記の完了前に、指定されたstatusとは、別のstatusへの変更が指示されたとき |

| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| ふきだしの表示状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | ふきだしの表示状態 | |
|  |  |　show | 表示中状態 |
|  |  | hide | 非表示 |

| .cscwCall(“target”, target) |   |   |
|:--------------------------- |:--- |:--- |
| 表示基準となるtargetを変更する。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| target | jQueryObject | <br>表示基準となるターゲット要素。種別は問わない。<br><br>ただし、targetもしくはその子要素があげたイベントが、本Widgetのstatusメソッドの引数（event）として指定できること。<br><br> |

| .cscwCall(“layerDiff”, layerDiff) |   |   |
|:--------------------------------- |:--- |:--- |
| <br>ふきだしの表示階層レイヤと、target要素が属する表示階層レイヤとの差を指定する。<br><br>値が不正である場合はエラーを返す。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| layerDiff | Integer | targetの表示階層レイヤとふきだしの表示階層レイヤとの差分 |

| .cscwCall(“layerDiff”) |   |   |
|:---------------------- |:--- |:--- |
| ふきだしの表示階層レイヤと、target要素が属する表示階層レイヤとの差を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | targetの表示階層レイヤとふきだしの表示階層レイヤとの差分 |

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwChanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| ふきだしの状態が変わった時に発生 |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | status | String | show | 表示開始 |
|  |  |  | hide | 表示終了 |

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwTransitionEnd |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| 状態変更に伴う、描画処理を含むすべての処理が完了したことを示す |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | property | String | status（固定） |  |
|  | value | String | show | 表示開始 |
|  |  |  | hide | 表示終了 |
|  | result | String | completed | 正常に完了した |
|  |  |  | cancelled | キャンセルされた |