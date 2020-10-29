[Text Area](../abstractwidgetcontents)
======

機能
---------

-   概要

> カーソル表示を伴う複数行の入力エリア。

-   機能

> 入力用エリアを表示する。
>
> Keyboardと連携し、それらから入力した値やハードキーで入力した値を(T.B.D.)ボタン上に表示する。
>
> 入力可能な最長文字列が指定されている場合は、最長文字列長を超える入力を抑止する機能を持つ。ただし、本機能は、明示的に入力手段から文字単位の入力イベント（keypress）が上がってきたときのみ作用し、最長文字列長を超過した初期値で初期化された場合、メソッドを利用して値が書きかえられた場合、あるいはコピー＆ペーストなどの手段により入力が更新された場合、については、ケアしない。

-   操作

> Off状態のエリアをタップすると表示状態を変更するとともに、連携する入力手段が設定されている場合は該入力手段を表示し、入力済みのテキストがあれば全選択される。
>
> 入力可能状態では、エリア上のタップ、ダブルタップ、トリプルタップを受け付け、それぞれ、カーソルの移動、語句選択、全選択、として機能する。
>
> 入力が開始されたタイミングで、クリアボタンを表示することができる。クリアボタンは、押下を受け付けると入力中文字をクリアする。エリアの見た目の大きさに対して内部の文字列が長い場合には、見た目の大きさ（高さ）を自動的に伸ばして表示するか、縦方向のスクロールバーによるインジケータが表示される。

-   音

> TextFieldに同じ。

-   レイアウト

入力エリアを視覚的に表す角丸の矩形領域である。矩形領域内には、実際の文字列入力フィールドおよび必要に応じてクリアボタンが配置される。

クリアボタンは、入力中、何らかの入力文字が存在するときにのみ表示される。watermark表示時については、クリアボタン出現領域は考慮されず、文字列表示領域の一部として扱われるレイアウトとなる。Off状態におけるフィードバック文字列(ただしwatermarkではないもの)表示時は、クリアボタン出現領域への文字列表示は回避される。これは、TextAreaのOn/Off切り替えにより、内部文字列の自動改行位置が変わるのを避けるためである。

**一般的なテキストエリア**

**ラベルおよびクリアボタンが付与された場合**

RTL表記でのレイアウト

ウォーターマークの表示例

入力途中の例

テキストエリアにフィードバック文字列を表示した例

グリフ、ラベル付き。入力値があり、クリアボタンが付与された場合

領域内に他のアイテム（ボタンなど）を配置する必要がある場合は、その大きさを考慮して、文字列入力エリアの大きさを設定することで対応する。図は、TextFieldの項を参照のこと。

**各種スタイル定義（上段:5inch / 下段:10inch）**

<table>
<thead>
<tr class="header">
<th>size</th>
<th>height</th>
<th>width</th>
<th>font*1</th>
<th>Glyph</th>
<th>Image</th>
<th>Left Inside padding</th>
<th>Middle/Right Inside Padding</th>
<th>Icon-label margin</th>
<th>cursor padding</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>small</td>
<td>アプリ指定</td>
<td>アプリ指定</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>medium</td>
<td>アプリ指定</td>
<td>アプリ指定</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>large</td>
<td>アプリ指定</td>
<td>アプリ指定</td>
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

\*1　ただし、ラベルについては、font-weightとしてlightを適用

適用される色情報は、入力フィールドのステイタスとApplication Thema,
Container Thema から決定される。

なお、WaterMark文字列については、通常のfont指定に対してopacity とする。

クリアボタンの色は、クリアボタン表示時に適用されているfont色に対してopacityとし、クリアボタンプレス時にはopacity
つまりfont指定色と同一となる。

エリアの見た目の大きさに対して内部の文字列が長く、スクロールバーが必要とされる場合、バーの形状はScroll
Paneの項に定義されたものと同等である。スクロールバーの位置についても、内部に設定された左右のPaddingやクリアボタンの有無などに影響されず、固定の位置となる。ただし、実際にスクロールするのは、テキスト入力可能なエリアのみである。

詳細はスタイルガイド（TextField&Areaの項）を参照のこと。

ただし、選択中文字列の色彩は、スタイルガイド規定値ではなくブラウザ仕様に従う。

> &lt;RTL表記でのレイアウトについて&gt;
>
> CSCWidgetのデフォルト指定に従い、LTR表示またはRTL表示でテキストの入力を受け付ける。同じ入力オプションに従い入力エリア内のラベル、watermarkをLTR/RTL表示する。
>
> LTR/RTL表示に関わらず、アイコン、クリアボタンの配置は変わらない。入力テキストが右寄せ表示の場合、常にクリアボタンの場所は確保される結果、空の場合は右端にカーソルが表示されるが、入力があるとクリアボタンが現れた分だけ入力文字列が左に移動する。
>
> LTR/RTL表示の指定にかかわりなく、ラベルは枠内に左寄せで配置する。
>
> 生成パラメータのtextAlignに選択肢autoを追加し、入力テキストの左寄せ/右寄せはLTR/RTL表示の指定に連動してLTR表示は左寄せRTL表示は右寄せとする、という振る舞いを指定可能。

-   Transition

> On状態からOff状態への移行：　durationは。
>
> Off状態からOn状態への移行： 　durationは。

API Documentation
---------

-   オブジェクト名

> textArea

-   コンストラクタ

> $.cscwTextArea(\[options\]) :入力エリアを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”TextArea”&gt;&lt;/div&gt; |
| Script | $(“#TextArea).cscwTextArea(); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| **Property** | **Type** | **Description** | **Default** |
|:------------ |:-------- |:--------------- |:----------- |
| style | String | <br>スタイル<br><br>"normal"：通常スタイル<br><br>"borderless"：枠線描画を行わない<br><br> | "normal" |
| width | Integer | <br>入力フィールド外形の幅(pixel)<br><br>指定無き場合は、cssによる指定が適用される。<br><br> | null |
| height | Integer/<br>String | <br>入力エリアの外形の高さを示す数値(pixel)もしくは"auto"<br><br>指定無き場合は、1行の高さが適用される。<br>autoの場合は、未入力時は1行の高さ、入力に伴い高さが変動する。<br><br> | null |
| maxHeight | Integer | <br>入力エリアの外形の高さがautoで指定されたときに適用される、高さの最大値。<br>中身の大きさがこの値を超えた場合は、スクロールが適用される。<br><br> | null |
| label | String | <br>入力エリア内に表示するラベル文字列。改行を含んではならない。<br><br> | null |
| margin | Object | <br>入力エリア内に空けておくmargin値を示すオブジェクト<br><br> | null |
| textAlign | String | <br>入力文字列の位置(水平方向)<br><br>"left"：左揃え<br><br>"auto"：表示言語の共通初期設定に従い、ltr なら左揃え、rtl なら右揃え<br><br> | "auto" |
| watermark | String | ウォーターマーク文字列 | null |
| clearButton | Boolean | <br>true：入力が開始されたら、クリアボタンを表示する。<br><br>false：クリアボタンを表示しない<br><br> | false |
| value | String | 入力の初期値 | null |
| maxLength | Integer | <br>受け付け可能な最大文字列長.<br><br>IME動作中は指定した文字列長を超えて入力できる。確定後の文字列長が指定した文字列長を超える場合、超過分は切り捨てられる。<br><br> | null |
| status | String | <br>入力エリアの状態<br><br>"off"：Off状態<br><br>"on"：On状態<br><br> | "off" |
| enable | Boolean | <br>入力エリアの有効/無効<br><br>true：有効<br><br>false：無効<br><br> | true |
| keyboard | Object | <br>入力手段として用いられるキーボードおよびスライド型キーパッドの情報<br><br>省略の際は、後述のkeyboardオブジェクトのデフォルト値が適用される。<br><br> | null |
| actionEventHandler | Function | キーボード内のPrimaryキー/Dismissキーが押下された際に呼び出されるコールバック関数。 | null |
| soundEnable | Boolean | <br>Widgetによる操作音(valid音)の鳴動制御<br><br>true：操作音を鳴らす<br><br>false：操作音を鳴らさない<br><br> | true |
| invalidSoundEnable | Boolean | <br>Widgetによる操作音(invalid音)の鳴動制御<br><br>true：操作音を鳴らす<br><br>false：操作音を鳴らさない<br><br> | true |

-   keyboardで使用するObjectの定義

> 「keyboardパラメータ」の項を参照。正規表現の詳細についても、「keyboardパラメータ」の項を参照。

-   actionEventHandlerに設定する関数の定義

| actionEventHandler(type) |   |   |
|:------------------------ |:--- |:--- |
| <br>キーボード内のPrimaryキー/Dismissキーが押下された際に呼び出されるコールバック関数。<br><br>戻り値によってキーが押下された際のキーボードの動作、鳴動音を制御する。<br><br>KbUtilのsetActionEventHandlerに登録したコールバックに優先して本コールバック関数が呼ばれる。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| type | String | <br>押下されたキーの種別を表す文字列<br><br>“dismiss”, “enter”, “ok”, “search”, “done”, “next”のいずれか<br><br> |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | <br>String /<br>Promise<br><br> | <br>”okClose”： 入力完了と判断し、PrimaryキーまたはDissmissの動作を行う。(typeが‘next’の場合は、次の入力可能領域にフォーカスが移動し、他のtypeの場合は、現在の入力可能領域からフォーカスがはずれ、キーボードが非表示になる。)操作音validが鳴動する。<br><br>“ngClose”： ”okClose”同様にフォーカスがはずれ、キーボードが非表示になる。操作音invalidが鳴動する。 “ngKeepValue”： フォーカス、キーボードの表示状態は不変。操作音invalidが鳴動する。入力中の文字列は維持される。<br><br>コールバック内で非同期処理を実行し、その結果を待って上記制御を行う場合、Deferredを作成してPromiseを返却する。非同期処理完了後に上記いずれかの文字列を引数に与えてDeferredのresolveメソッドを呼ぶ。<br><br> |

-   marginで使用するObjectの定義

> TextFieldの項に同じ。
>
>
> ただし、本Widgetでは、marginが高さに与える影響に注意する必要がある。
>
> コントラクタオプションにて、height指定が行われない場合：
>
> 上下のmarginが指定された場合、その分全体（外形）の高さが高くなる。
>
> コントラクタオプションにて、height指定が行われた場合：
>
> margin指定により外形は変化せず、内側の入力可能エリアが狭くなる。

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> コンストラクタをコールする要素に対して、widthを指定することで幅を指定できる。
>
> 高さについては、CSSによる指定はできない。（margin値設定との競合によるわかりにくさを避けるため）
>
> Example:　　\#textarea{ width:100px}

-   メソッド

| .cscwCall(“status”, status) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| <br>入力エリアの状態を切り替える。<br><br>IME動作中に本メソッドによりoff状態になる場合、入力中の文字列は無変換確定された上で処理される。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | 入力エリアの状態 |  |
|  |  | on | On状態 |
|  |  | off | Off状態 |

| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| 入力エリアの状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | 入力エリアの状態 |  |
|  |  | on | On状態 |
|  |  | off | Off状態 |

| .cscwCall(“enable”, enable) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| <br>入力エリアの有効/無効を切り替える。<br><br>IME動作中に本メソッドによりdisable状態になる場合、入力中の文字列は無変換確定された上で処理される。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| enable | Boolean | 入力エリアの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“enable”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| 入力エリアが有効かどうかを取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | 入力エリアの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“watermark”, watermark) |   |   |
|:--------------------------------- |:--- |:--- |
| watermark文字列を設定する。  |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| watermark | String | watermark文字列 |

| .cscwCall(“watermark”) |   |   |
|:---------------------- |:--- |:--- |
| watermark文字列を取得する。  |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | watermark文字列 |

| .cscwCall(“value”, value) |   |   |   |
|:------------------------- |:--- |:--- |:--- |
| 入力エリアに値を入力する。入力した値はエリア内に表示される。<br><br>本メソッドによる値の設定時は、コンストラクタで指定されたmaxLengthは考慮されない。<br><br>IME動作中に本メソッドが呼び出された場合、入力中の文字列はクリアされ、valueが入力される。この際Widgetはoff状態となりキーボードは閉じられる。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| value | String | 入力エリア内に表示する値 |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | valueの評価結果 |  |
|  |  | true | 真である |
|  |  | false | 偽である |

| .cscwCall(“value”) |   |   |
|:------------------ |:--- |:--- |
| 入力エリア内の値を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | 入力エリア内の現在の値 |

| .cscwCall(“maxLength”, maxLength) |   |   |
|:--------------------------------- |:--- |:--- |
| 入力文字列として許容される最大文字列長を設定する。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| maxLength | Integer | 最大文字列長 |

| .cscwCall(“maxLength”) |   |   |
|:---------------------- |:--- |:--- |
| 入力文字列として許容される最大文字列長を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | 最大文字列長 |

| .cscwCall(“selected”, selected) |   |   |   |   |   |
|:------------------------------- |:--- |:--- |:--- |:--- |:--- |
| 入力エリア内文字列の選択状態を切り替える。<br><br>IME動作中は本メソッドの呼び出しは無視される。 |  |  |  |  |  |
| 引数の説明 |  |  |  |  |  |
| **name** | **type** | **description** |  |  |  |
| selected | Boolean/<br>Object | 入力エリア内文字列の選択状態 |  |  |  |
|  |  | Booleanによる指定 |  |  |  |
|  |  |  | true | 全選択状態 |  |
|  |  |  | false | 非選択状態 |  |
|  |  | Objectによる指定 |  |  |  |
|  |  |  | **property** | **property type** | **description** |
|  |  |  | selectionStart | Integer | 選択開始位置 |
|  |  |  | selectionEnd | Integer | 選択終了位置 |

| .cscwCall(“insert”, insert) |   |   |
|:--------------------------- |:--- |:--- |
| <br>入力エリア内のカーソル位置に文字列を挿入する。<br><br>IME動作中は本メソッドの呼び出しは無視される。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
|  | String | 挿入する文字列 |

| .cscwCall(“keyboard”, keyboard) |   |   |
|:------------------------------- |:--- |:--- |
| <br>入力時に自動表示されるキーボードに与える情報を変更する。<br><br>本メソッドは、キーボード表示中も動作するが、typeがewbの場合、以下のパラメータはキーボードが一度閉じるまで反映されない。<br><br>modeFirst、ascii、feedback、prediction、color、faxTypeFirst、acceptableFaxType、faxAddButton<br><br>不正な値を含む場合はエラーを返す。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| keyboard | Object | <br>キーボードに与える情報<br><br>（詳細は、コンストラクタオプション説明　keyboard　Objectの定義を参照）<br><br> |

| .cscwCall(“keyboard”) |   |   |
|:--------------------- |:--- |:--- |
| 現在のキーボード情報を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Object | <br>キーボードに設定されている情報<br><br>（詳細は、コンストラクタオプション説明　keyboard　Objectの定義を参照<br><br>ただし、全てのプロパティについてString型での取得となる）<br><br> |

-   イベント

| イベントタイプ |
|:------------- |
| cscwTap |
| **イベントのトリガ** |
| Off状態にて、Widget自身がタップされた時に発生。 |

| イベントタイプ |   |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |:--- |
| cscwValueChanged |  |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |  |
| 戻り値 |  |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |  |
| Object | value | String | 入力エリアの値 |  |  |
|  | maxLength | Integer | 最大文字列長 |  |  |
|  |  |  | **property** | **property type** | **description** |
|  | previous | Object | value | String | 変更前の文字列 |
|  |  |  | selectionStart | Integer | 変更前の文字列選択開始位置 |
|  |  |  | selectionEnd | Integer | 変更前の文字列選択終了位置 |
|  | current | Object | value | String | 変更後の文字列 |
|  |  |  | selectionStart | Integer | 変更後の文字列選択開始位置 |
|  |  |  | selectionEnd | Integer | 変更後の文字列選択終了位置 |
|  | imInfo | Object | state | String / null | <br>[“update”] IME動作中の更新による変化通知<br><br>[“end”] IME確定による変化痛通知<br><br>[null]<br><br>IME未使用時の変化通知<br><br> |
|  |  |  | data | String | <br>[state:“update”の場合]<br><br>変換中の文字列<br><br>[state:”end”の場合]<br><br>確定した文字列<br><br> |