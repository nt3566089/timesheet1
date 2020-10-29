[Popup](../abstractwidgetcontents)
======

機能
------

-   概要

> ポップアップ画面

-   機能

> ポップアップ画面を表示する。
>
> ポップアップ画面の上にさらに別のポップアップ画面を表示することも可能である。
>
> Popupは、画面の枠とblanketの生成・制御、Popup内のHeaderの生成を行う。ポップアップ画面のcontentの生成は上位プログラムの責務である。またポップアップ画面内がスクロールするケースについては、ScrollPane　との組み合わせで実現するものとし、本Widgetにて特殊な処理は行わない。
>
> 本Widgetはコンテナとして、基本的には上に配置された部品に対して背景に持つことを考慮した色彩を適用するが、指定により、黒色彩を適用することもできる。
>
> Popup画面が開く/閉じる動作の間、PopupはPopup画面への利用者の画面操作を無視する。

-   操作

> ポップアップ画面自身への操作は何もない。操作者はポップアップ画面の位置やサイズを変更できない。多くの場合、ポップアップのHeaderにはポップアップを閉じるためのボタンが配置されるが、その動作は上位プログラムによって実行される。Popupが直接実現する機能ではない。
>
> Blanketへの操作は何もない。Blanketをタッチしてもポップアップ画面が閉じることはない。

-   音

> なし。（Header上のボタンについては、ボタンの仕様にしたがって鳴動）

-   レイアウトと色彩

> Popupのレイアウトはスクリーンサイズにより異なる。
>
> Small screenの場合、popup画面は全画面を覆う。
>
> Popup画面の地色はPopupを開くアプリケーションのテーマと用途によって定まる。Application
> themaがDark Grayである場合は、DarkGray
> のテクスチャ、それ以外のApplication themaの場合はGray
> のテクスチャ画像を適用する。
>
> 10inchのPopupはテーマカラーにしたがったドロップシャドウを持つ。詳細はスタイルガイドを参照のこと。

各種スタイル定義

| Disaply Size | width | height | <br>max<br><br>height<br><br> | <br>min<br><br>height<br><br> | <br>max<br><br>width<br><br> | <br>min<br><br>width<br><br> | R (角丸の設定) |
|:------------ |:----- |:------ |:----------------------------- |:----------------------------- |:--------------------------- |:---------------------------- |:------------- |
| 5inch |  |  | - | - | - | - |  |
| 10inch |  |  |  |  |  |  |  |

全体レイアウト

> <span class="underline">＜Popup画面に固有のHeader＞</span>
>
> Popup画面では、タイトルと左右ボタンを持つHeaderにおいてタイトルのtitle
> max-widthを生成時に選択できる。jQuery objectを配置する場合のtitle
> max-widthは、生成時の指定にかかわらず310px (5 inch)である。

| Display Size | 生成時の指定 | title max-width |
|:------------ |:----------- |:--------------- |
| 5inch/10inch |  |  |

> Popup画面には、タイトルと左右ボタンを持つHeader以外に、SwitchingとボタンをHeaderを持つ場合がある。SwitchingとボタンからなるHeaderのレイアウトは以下のとおり。

Switchingとボタンを持つHeaderのレイアウト

> **ポップアップ内Headerの各種サイズ定義**

| Display Size | height | width | Standard padding |
|:------------ |:------ |:----- |:---------------- |
| 5 inch |  |  |  |
| 10inch |  |  |  |

> 配置される左ボタン/右ボタンに関する詳細は、以下に示すとおり通常のHeader
> widgetと同一。
>
> **ボタンレイアウト**

| Button サイズ | Button TouchMargin | width | maxWidth |
|:------------- |:------------------ |:----- |:-------- |
| medium |  |  |  |

> Alert様のPopupにおいては、Header部を含む全面に背景画像を指定することができる。

このとき、指定された背景画像は、

> ・リピートなし
>
> ・画面縦横中央部に配置
>
> ・画像欠け、縦横比の変更なしに、画面内にぴったりと収まるサイズに拡大もしくは縮小
>
> されて表示され、Headerは、背景画像の上に透過で表示される。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> 指定に従い、タイトルやHeaderのボタンをLTR表記もしくはRTL表記する。
>
> Headerのボタンの左右配置はbase
> directionに関わらず一定。ミラーリングはしない。Switching
> とボタンを持つHeaderにおいても、Switchingとbuttonの位置関係は
> RTL/LTRに関わりなく一定。
>
> Popup内の各要素のLTR/RTL表記は、そのおのおので指定する。Popoverは何も関与しない。

-   Transition

> Popup画面が開く/閉じる動作ではDisolve/Slide, In/Outの視覚効果を行う。
>
> 開く時：　blanket、popup画面両方が. Duration は(300msec)
>
> 閉じる時: blanket, popup画面両方が. Duration は(300msec)

API Documentation
------

-   オブジェクト名

> popup

-   コンストラクタ

> $.cscwPopup (\[options\]) :ポップアップを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”Popup”&gt;&lt;div&gt; |
| Script | $(“#Popup”).cscwPopup(); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| color | String | <br>ヘッダー下部にあるインジケーターの色を指定する<br><br>下記以外の値を指定しないこと<br><br>"blue"：青に変更する<br><br>"yellow"：黄色に変更する<br><br>"green"：緑に変更する<br><br>"purple"：紫に変更する<br><br>"gray"：灰色に変更する<br><br>"red"：赤に変更する<br><br> | "blue" |
| indicatorStatus | String | <br>ヘッダ下部にあるインジケーターのアニメーションのON/OFFを変更する<br>colorで"gray"もしくは"red"を指定した場合、内部的にはindicatorStatusがONになるが、アニメーションはしない。<br><br>"on"/"off"以外の値を指定しないこと<br><br>"on"：インジケーターがアニメーションする<br><br>"off"：インジケーターがアニメーションしない<br><br> | "off" |
| width | Integer | <br>Popup画面の幅<br><br>指定なき場合はcssで指定された値を適用。<br><br>Css指定もない場合は内部の規定値を使用。<br><br> | null |
| height | Interger | <br>Popup画面の高さ<br><br>指定無き場合はcssで指定された値を適用。<br><br>Css指定もない場合は内部の規定値を使用。<br><br> | null |
| title\*2 | <br>String/<br>Array/<br>jqueryObject<br><br> | <br>Headerのタイトル部*1<br><br>String<br>タイトル文字列。改行を含めることで2行での表示が可能。<br><br>Array<br>タイトル文字列。2行での表示が可能。(文字列が長い場合は各行でtruncateする)<br><br>jQueryObject<br>タイトル文字列を示すjQueryObject。<br><br>どのTypeの指定でも3行以上の改行は行わないこと。<br><br> | null |
| titleWidth | String | <br>タイトルが文字列の場合のタイトル部の最大幅。<br><br>"normal"：標準<br><br>"wide"：幅広<br><br>"narrow"：幅狭<br><br>上記以外の値を指定した場合、タイトル文字列分の幅になる。<br><br> | "normal" |
| truncate | String | <br>テキスト長が、領域幅を超過したときの省略描画の適用<br><br>下記以外の値を指定しないこと<br><br>null：超過が起きない場合に使うことを前提とし、超過した場合の挙動は保証しない<br><br>"end"：⽂字列後⽅を省略表⽰する<br><br>"middle"：⽂字列の中央を省略表⽰する<br><br> "begin"：⽂字列前⽅を省略表⽰する<br><br> | null |
| autoWrap | Boolean | テキスト長が領域幅を超える場合の折り返しを行うか否か<br><br>truncateで"begin", "middle"を指定した場合はtrueにしてはならない | false |
| dir | String | <br>タイトル文字列の書き進む方向(text direction)を指定する。<br><br>“ltr”：左から右へ書き進む。<br><br>“rtl”：右から左へ書き進む。<br><br>null指定の場合、指定なしと同様の動作をする。<br><br> | CSCWidgetのデフォルト設定に従う |
| leftButton*2 | Object | Headerの左側に配置するボタンに関する情報　Objectの詳細はHeaderを参照 | null |
| rightButton*2 | Object | Headerの右側に配置するボタンに関する情報　Objectの詳細はHeaderを参照 | null |
| layer | Integer | <br>ポップアップの表示階層を示す値。数字が大きいものほど前面に表示される。<br><br>100～299 (transition：slideの場合)<br><br>600～699 (transition：dissolveの場合)<br><br>null指定の場合、指定なしと同様の動作をする<br><br> | <br>200 (transition：slideの場合)<br><br>600 (transition：dissolveの場合)<br><br> |
| body | jQueryObject | popupの本体部分を表す要素 | 指定がない場合は、popupの最初の子要素 |
| transition | String | <br>Transitionを設定する<br><br>"dissolve"：フェードインするTransition<br><br>"slide"：右からスライドするTransition<br><br> | "dissolve" |

\*1　
Array型指定時における各配列要素は、改行を含んではならない。

\*2　tilte, leftButton,
rightButtonがすべてのnullの場合、Headerは作成されない

> Header内にSwitchingを配置する場合、「Switching、SeparatorLine、Header右側に配置するButton」を内包したjQueryObjectをrightButtonオプションに渡して、Popupを初期化する。Switchingに相当するマークアップの記載は、Popupを示す要素の直下か、あるいはPopupと無関係の場所に行うものとする。

-   オプション相当情報のMarkupによる指定

> 　　なし

-   オプション相当情報のCSSによる指定

-   　　なし

-   メソッド

| .cscwCall(“header”) |   |   |
|:------------------- |:--- |:--- |
| Headerを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | jQueryObject | Header widget |

| .cscwCall(“status”, status[, transition, origin]) |   |   |   |
|:--------------------------------------------------- |:--- |:--- |:--- |
| <br>ポップアップおよびその内部に配置されたアイテムを表示/非表示にする。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | アイテムの表示/非表示 |  |
|  |  | show | 表示する |
|  |  | hide | 非表示にする |
| transition | Boolean | <br>トランジションの適用有無。省略時はtrueとして扱われる<br><br> |  |
|  |  | true | transitionを適用する |
|  |  | false | transitionを適用しない |
| origin | String | トランジションの方向設定。省略された場合はrightとなる。 |  |
|  |  | left | <br>画面左側から表示される。<br><br>画面左側に向かって消える。<br><br> |
|  |  | right | <br>画面右側から表示される。<br><br>画面右側に向かって消える。<br><br> |
|  |  | top | <br>画面上側から表示される。<br><br>画面上側に向かって消える。<br><br> |
|  |  | bottom | <br>画面下側から表示される。<br><br>画面下側に向かって消える。<br><br> |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Promise | <br>以下のタイミングで、コールバックが呼ばれる。クリティカルなタイミングにおける挙動については、Alertの同名メソッドの注釈を参照。<br><br>done：指定されたstatusへの内部状態、および描画を含む全ての処理が完了したとき<br><br>fail：上記の完了前に、指定されたstatusとは、別のstatusへの変更が指示されたとき<br><br> |  |

| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| ポップアップの表示状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | ポップアップの表示状態 |  |
|  |  | "show" | 表示中状態 |
|  |  | "hide" | 非表示状態 |

| .cscwCall(“title”, title [,dir]) |   |   |   |
|:-------------------------------- |:--- |:--- |:--- |
| titleを同種のtitleに切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |   |
| title | String/<br>Array(String)/<br>jQueryObject | <br>タイトル文字列、タイトル文字列の配列　もしくは、タイトル文字列を示すjQueryObject<br><br> |  |
| dir | String | <br>タイトル文字列の書き進む方向(text direction)を指定する。省略時は、書き進む方向を変更せず現在の方向のままとする。<br><br> |  |
|  |  | “ltr” | <br>左から右へ書き進む。<br><br> |
|  |  | “rtl” | <br>右から左へ書き進む。<br><br> |

| .cscwCall(“title”) |   |   |
|:------------------ |:--- |:--- |
| titleを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String/<br>Array(String)/<br>jQueryObject | タイトル文字列、タイトル文字列の配列　もしくは、タイトル文字列を示すjQueryObject |

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
| ポップアップの表示階層を示す値を設定する。値が不正である場合はエラーを返す。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| layer | Integer | ポップアップの表示階層 |

| .cscwCall(“layer”) |   |   |
|:------------------ |:--- |:--- |
| ポップアップの表示階層を示す値を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | ポップアップの表示階層 |

| .cscwCall("color", color) |   |   |   |
|:------------------------- |:--- |:--- |:--- |
| ヘッダー下部にあるインジケーターの色を変更する。<br><br> 既定文字列以外が指定された場合は"blue"として扱われる |  |  |   |
| 引数の説明 |  |  |   |
| **name** | **type** | **description** |   |
| color | String | Indicatorの色を示す文字列 |   |
|  |  | "blue" | 青色に変更する |   |
|  |  | "yellow" | 黄色に変更する |   |
|  |  | "green" | 緑色に変更する |   |
|  |  | "purple" | 紫色に変更する |   |
|  |  | "gray" | 灰色に変更する |   |
|  |  | "red" | 赤色に変更する |   |

| .cscwCall(“color”) |   |   |  |
|:------------------ |:--- |:--- |:--- |
| ヘッダー下部にあるインジケーターの色を取得する。 |  |  |  |
| 戻り値 |  |  |  |
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

| .cscwCall("indicatorStatus") |   |   |   |
|:------------------------ |:--- |:--- |:--- |
| ヘッダー下部にあるインジケーターのアニメーションのON/OFFを取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | indicatorの状態 |  |
|  |  | "on" | インジケーターがアニメーションしている |
|  |  | "off" | インジケーターがアニメーションしていない |

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwChanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| ポップアップの表示状態が変わった時に発生 |  |  |  |  |
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
| Object | status | String | status　固定 |  |
|  | value | String | show | 表示開始 |
|  |  |  | hide | 表示終了 |
|  | result | String | completed | 正常に完了した |
|  |  |  | cancelled | キャンセルされた |