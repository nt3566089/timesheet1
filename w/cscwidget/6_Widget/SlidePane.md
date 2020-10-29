[Slide Pane](../abstractwidgetcontents)
======

機能
---------

-   概要

> 画面右端からスライドインする画面

-   機能

> Slide Pane画面を表示する。
>
> Slide Pane画面の上にさらに別のSlide
> Pane画面、あるいはPopup画面を表示可能である。
>
> Slide
> Paneは、Popupと同様に画面の枠と表示・非表示のトランジション、Slide
> Pane内のHeaderの生成を行う。 Slide
> Paneのcontentの生成は上位プログラムの責務である。また、Slide
> Pane画面内がスクロールするケースについては、Scroll
> Paneとの組み合わせで実現するものとし、本Widgetにて特殊な処理は行わない。
>
> Slide Paneが開く/閉じる動作の間、Slide PaneはSlide
> Paneへの利用者の画面操作を無視する。

-   操作

> 操作者はSlide Pane画面の位置やサイズを変更できない。多くの場合、Slide
> PaneのHeaderにはSlide Paneを閉じるための navigation left
> ボタンが配置されるが、その動作は上位プログラムによって実行される。Slide
> Paneが直接実現する機能ではない。
>
> Slide
> Pane画面左端からの範囲でのフリックあるいはドラッグ操作によりSlide
> Paneが閉じる。

-   音

> なし（Header上のボタンについては、ボタンの仕様にしたがって鳴動）

-   レイアウト

> レイアウトは、以下のとおり。
>
> **全体レイアウト**
>
> <span class="underline">＜SlidePaneのHeader＞</span>
>
> SlidePaneでは、タイトルと左右ボタンを持つHeaderにおいてタイトルのtitle
> max-widthを生成時に選択できる。jQuery objectを配置する場合のtitle
> max-widthは、生成時の指定にかかわらずである。

| Display Size | 生成時の指定 | title max-width |
|:------------ |:----------- |:--------------- |
| 5inch / 10inch |  |  |
|  |  |  |

> &lt;RTL表記でのレイアウトについて&gt;
>
> SlidePaneは、Contentに関してRTL/LTRを関知せず、ミラーリングをサポートしない。
>
> SlidePaneのActiopn
> Barのタイトルおよび左右ボタンのラベルは、指定に従いrtlもしくはltrで表示される。
>
> Slide Paneは常に画面右端から左へ向かって現れ、常に画面右端へ消える。
>
> SlidePaneの中に配置される項目のLTR/RTL表記はそれぞれの項目で行う。SlidePaneは関与しない。

-   遷移動作

> Slide Pane画面が開く/閉じる動作ではスライドイン/スライドアウト
> の視覚効果を行う。
>
> 開く時：　Slide Pane画面が左から Duration は .
>
> 。　
>
> 閉じる時: 　Slide Pane画面が右方向に. Duration は.

API Documentation
----------

-   オブジェクト名

> slidePane

-   コンストラクタ

> $.cscwSlidePane(\[options\]) :SlidePaneを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”slidePane”&gt;&lt;div&gt; |
| Script | $("#slidePane").cscwSlidePane(); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description	| Default |
|:-------- |:---- |:----------- |:------- |
| color | String | <br>ヘッダー下部にあるインジケーターの色を指定する<br><br>下記以外の値を指定しないこと<br><br>"blue"：青に変更する<br><br>"yellow"：黄色に変更する<br><br>"green"：緑に変更する<br><br>"purple"：紫に変更する<br><br>"gray"：灰色に変更する<br><br>"red"：赤に変更する<br><br> | "blue" |
| indicatorStatus | String | <br>ヘッダ下部にあるインジケーターのアニメーションのON/OFFを変更する<br>colorで"gray"もしくは"red"を指定した場合、内部的にはindicatorStatusがONになるが、アニメーションはしない。<br><br>"on"/"off"以外の値を指定しないこと<br><br>"on"：インジケーターがアニメーションする<br><br>"off"：インジケーターがアニメーションしない<br><br> | "off" |
| type | String | <br>ベースの種別<br><br>"popup"：フルスクリーン表示用。<br><br>"container"：部分スライド用。<br><br>規定の文字列以外を指定しないこと。<br><br> | "popup" |
| title*1 | String/<br>Array/<br>jqueryObject<br><br> | <br>Headerのタイトル部<br><br>String<br>タイトル文字列。改行を含めることで2行での表示が可能。<br>複数の改行を含んではならない。<br><br>Array<br>タイトル文字列。2行での表示が可能。<br>改行を含んではならない。<br><br>jQueryObject<br>タイトル文字列を示すjQueryObject。<br><br> | null |
| titleWidth | String | <br>タイトルが文字列の場合のタイトル部の最大幅。<br><br>"narrow"：幅狭<br><br>"normal"：標準<br><br>"wide"：幅広<br><br>規定の文字列以外を指定しないこと。<br><br> | "normal" |
| truncate | String | <br>テキスト長が、領域幅を超過したときの省略描画の適用<br><br>下記以外の値を指定しないこと<br><br>null：超過が起きない場合に使うことを前提とし、超過した場合の挙動は保証しない<br><br>"end"：⽂字列後⽅を省略表⽰する<br><br>"middle"：⽂字列の中央を省略表⽰する<br><br> "begin"：⽂字列前⽅を省略表⽰する<br><br> | null |
| autoWrap | Boolean | テキスト長が領域幅を超える場合の折り返しを行うか否か<br><br>truncateで"begin", "middle"を指定した場合はtrueにしてはならない | false |
| dir | String | <br>タイトル文字列の書き進む方向(text direction)を指定する。<br><br>“ltr”：左から右へ書き進む。<br><br>“rtl”：右から左へ書き進む。<br><br>null指定の場合、指定なしと同様の動作をする。<br><br> | CSCWidgetのデフォルト設定に従う |
| leftButton*1 | Object | Headerの左側に配置するボタンに関する情報　Objectの詳細はHeaderを参照 | null |
| rightButton*1 | Object | Headerの右側に配置するボタンに関する情報　Objectの詳細はHeaderを参照 | null |
| layer | Integer | <br>SlidePaneの表示階層を示す値。数字が大きいものほど前面に表示される。<br><br>popup　 100～299<br><br>container　0～無制限<br><br>範囲外を指定した場合、Widgetは生成されない。<br><br> | <br>"popup": 100<br><br>"container": 0<br><br> |
| base | jQueryObject | 必要に応じてSlideBaseウィジェットを指定する | <br>type:"popup"の場合null<br><br>type="container"の場合、parent要素<br><br> |
| target | jQueryObject | <br>このslidePaneによって隠される画面を表す要素<br><br>targetが指定された場合、slidePaneがtransitionを行なう際に、targetのcss leftプロパティも変更される。<br><br>targetにleft以外のプロパティ（例えばposition: absoluteなど）を設定するのは利用の責任である。<br><br> | null |
| body | jQueryObject | popupの本体部分を表す要素 | 指定がない場合は、SlidePaneの最初の子要素 |

\*1　tilte, leftButton, rightButtonがすべてnullの場合、Headerは作成されない

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> なし

-   メソッド

| .cscwCall(“header”) |   |   |
|:------------------- |:--- |:--- |
| Headerを取得する。<br>Headerが生成されていない場合、SlidePaneのjQueryObjectが返される。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | jQueryObject | Header widget |

| .cscwCall(“status”, status[, transition]) |   |   |   |
|:----------------------------------------- |:--- |:--- |:--- |
| Slide Paneおよびその内部に配置されたアイテムを表示/非表示にする。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | show | 表示する |
|  |  | hide | 非表示にする |
| transition | Boolean | トランジションの有無、省略時はtrue | |
| | | true | transitionを適用する |
|  |  | false | transitionを適用しない |
| 戻り値 |  | 以下のタイミングで、コールバックが呼ばれる。クリティカルなタイミングにおける挙動については、Alertの同名メソッドの注釈を参照。 |  |
|  | **type** | **description** |  |
|  | Promise | done | 指定されたstatusへの内部状態、および描画を含む全ての処理が完了したとき |
| | | fail | 上記の完了前に、指定されたstatusとは、別のstatusへの変更が指示されたとき |

| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| Slide Paneの表示状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | show | 表示状態 |
|  |  | hide | 非表示状態 |

| .cscwCall(“title”, title[, dir]) |   |   |   |
|:-------------------------------- |:--- |:--- |:--- |
| titleを同種のtitleに切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** | |
| title | String/<br>Array(String)/<br>jqueryObject | タイトル文字列 | |
| dir | String | タイトル文字列の書き進む方向(text direction)を指定する。省略時は、現在の書き進む方向のままとし、変更しない。 | |
| | | “ltr” | 左から右へ書き進む |
|  |  | “rtl” | 右から左へ書き進む |

| .cscwCall(“title”) |   |   |
|:------------------ |:--- |:--- |
| titleを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String/<br>Array(String)/<br>jqueryObject | タイトル文字列 |

| .cscwCall(“leftButton”) |   |   |
|:----------------------- |:--- |:--- |
| 左側ボタンを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | jQueryObject | 表示されている左側ボタンを示す、jQuery Object |

| .cscwCall(“rightButton”) |   |   |
|:------------------------ |:--- |:--- |
| 右側ボタンを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | jQueryObject | 表示されている右側ボタンを示す、jQuery Object |

| .cscwCall(“layer”, layer) |   |   |
|:------------------------- |:--- |:--- |
| SlidePaneの表示階層を示す値を設定する。値が不正である場合はエラーを返す。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| layer | Integer | SlidePaneの表示階層 |

| .cscwCall(“layer”) |   |   |
|:------------------ |:--- |:--- |
| SlidePaneの表示階層を示す値を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | SlidePaneの表示階層 |

| .cscwCall("color", color) |   |   |   |
|:-------------------------------- |:--- |:--- |:--- |
| ヘッダー下部にあるインジケーターの色を変更する。<br><br> 既定文字列以外が指定された場合は"blue"として扱われる|  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| color | String |Indicatorの色を示す文字列|  |
|  |  | "blue" | 青色に変更する |
|  |  | "yellow" | 黄色に変更する |
|  |  | "green" | 緑色に変更する |
|  |  | "purple" | 紫色に変更する |
|  |  | "gray" | 灰色に変更する |
|  |  | "red" | 赤色に変更する |

| .cscwCall(color) |   |   |   |
|:------------------------ |:--- |:--- |:--- |
| ヘッダー下部にあるインジケーターの色を取得する。 |  |  |  |
|  | **type** | **description** |  |
|  | String | Indicatorの色を示す文字列 |  |
|  |  | "blue" | 青色 |
|  |  | "yellow" | 黄色 |
|  |  | "green" | 緑色 |
|  |  | "purple" | 紫色 |
|  |  | "gray" | 灰色 |
|  |  | "red" | 赤色 |

| .cscwCall("indicatorStatus", indicatorStatus)) |   |   |   |
|:-------------------------------- |:--- |:--- |:--- |
| ヘッダー下部にあるインジケーターのアニメーションのON/OFFを変更する。<br>ただし、ヘッダーのindicatorの色が"red","gray"のときは、内部的にはindicatorStatusがONになるが、アニメーションはしない。<br> 既定文字列以外が指定された場合はpng画像が表示される。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| indicatorStatus | String | Indicatorの状態を示す文字列 |  |
|  |  | "on"　|インジケーターがアニメーションする |
|  |  | "off"　|インジケーターがアニメーションしない |

| .cscwCall(indicatorStatus) |   |   |   |
|:------------------------ |:--- |:--- |:--- |
| ヘッダー下部にあるインジケーターのアニメーションのON/OFFを取得する。 |  |  |  |
|  | **type** | **description** |  |
|  | String | indicatorの状態 |  |
|  |  | "on" | インジケーターがアニメーションしている |
|  |  | "off" | インジケーターがアニメーションしていない |

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwChanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| Slide Paneの表示状態が変わった時に発生 |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | status | String | show | 表示開始 |
|  |  |  | hide | 表示終了 |

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwTransitionEnd |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| <br>状態変更に伴う、描画処理を含むすべての処理が完了したことを示す。<br><br>ユーザ操作(SlidePane自身のドラッグ/フリック)による状態変更が試みられた場合、意図した操作およびその結果にかかわらず、最終状態(表示/非表示)のcompleteとして扱われる。<br><br>(ex　hide操作を試みたが、ドラッグ距離が足りずにshowに戻った場合：value:show result:completed)<br><br> |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | property | String | status | 固定 |
|  | value | String | show | 表示開始 |
|  |  |  | hide | 表示終了 |
|  | result | String | completed | 正常に完了した |
|  |  |  | cancelled | キャンセルされた |