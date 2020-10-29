[App Button](../abstractwidgetcontents)
======

機能
---------

-   概要

> Home screenのアプリケーション起動ボタン
>
> ※注意事項：
>
> \- アプリを示す単なるアイコン表示は、AppButton widgetの範疇ではない。

★TODO:後で修正。

-   機能

> バッジを表示/非表示する。
>
> 削除ボタンを表示/非表示する。
>
> Normal, customize,
> draggable間のモード切り替え。(バッジ、削除ボタンの表示/非表示は、モードとは連動しない)
>
> モード切り替えに連動したバッジ、削除ボタンの表示/非表示(ラベルは常に表示)

-   操作

> タップ (押下時にアイコン、badge、とラベルはpressed stateの表現あり)
>
> タッチアンドホールド(msecのホールドで該操作と判断)
>
> 削除ボタンへのタッチ。

-   音

> コンストラクタで鳴らすことを指定した場合は、タップ時に音が鳴動する。音の種別は、Enable状態の場合はvalid音、Disable状態の場合はinvalid音とする。
>
> 削除ボタンのドラッグ時は、コンストラクタの指定にかかわらずValid音が鳴動する。
>
> タッチアンドホールド、および✕ボタンの時は、音の鳴動はしない。

-   レイアウト

<span class="underline">＜全体＞</span>

全体のサイズとnormalモードでのアイコンの位置は下図のとおり。

**全体レイアウト**

**各種スタイル指定**

| <br> Display Size <br><br> | <br> Layout <br><br> | <br> height <br><br> | <br> width <br><br> | margin <br> <br> (top) | margin <br><br> (right) | margin <br><br> (bottom) | margin<br><br>(left) |
|:-------------|-----------:|:------:|:-----:|:------:|:-------:|:--------:|:------:|
| 5inch        | 3-Column   | 132px  | 200px | 0px    | 0px     | 2px      | 10px   |
| 10inch       | 3-Column   | 140px  | 200px | 0px    | 0px     | 20px     | 20px   |

※5inch及び10inch共に、1ページあたり3Column * 3Rowの9個表示を行う

<span class="underline">＜アイコン部＞</span>

**アイコンのスタイル**

| Display size | Image height | Image width |
|:------------:|:------------:|:-----------:|
| 5inch/10inch | 40px         | 40px        |

※アイコン画像のサイズが、推奨と異なる場合は、領域内に収まる形に処理される（‎3.3.4節の記載を参照。）

> **ステイタスに依存して適用される各種効果**

★TODO:後で対応。

| ステイタス      | 効果       |
|:--------------:|:----------:|
| -              | Box shadow |
| BG Color changes State | Overlay    |
|                | Box shadow |
| Disabled State | Opacity    |

<span class="underline">＜ラベル＞</span>

アイコンのラベル文字列はアイコンの下に左右中央揃えで表示する。ラベル文字列は１行または２行で明示的に指定する。それぞれの行でAppButtonに割り当てられた幅に収まらない場合は、文字列の末尾を切縮めてelipsis(…)に置き換えることでAppButtonに割り当てられた幅に収める。

ラベル文字列の縦位置は、１行であるか２行であるかで異なる。なお、ラベルがjQueryObject型で指定された場合は、文字列の描画が1行になるか2行になるかが不明であることから、ラベル高さが2行の場合のレイアウトを適用して、指定位置にそのまま配置する。

★TODO:後で対応。

ラベル文字列の最大幅は、AppButtonの幅である。

> **ラベル文字列のフォント指定**

★TODO:後で対応。

| Display Size | Font-size | Font-weight |
|:------------:|:---------:|:-----------:|
| 5inch/10inch | small | normal |

**ラベル文字列の色彩等**

| Status | color |
|:--------:|:--------------:|
| Normal | white(#ffffff) |
| Pressed | white(#ffffff) |
| Disabled | 定義なし |

ラベル文字列位置は以下の通り。

ラベル文字列の位置 (左：1行、右：2行の場合)

**ラベル文字列　レイアウト**

| Display Size |　ラベル⾏数 | TextArea <br><br>Height | Padding<br><br>(top) | Padding <br><br>(bottom) | 備考 |
|:------------ |:---------- |:----------------------- |:-------------------- |:------------------------ |:---- |
| 5inch  | 1行 | 60px |  |  |  |
|  | 2行 |  |  |  |  |
| 10inch | 1行 | 52px |  |  |  |
|  | 2行 |  |  |  |  |

<span class="underline">＜Badge＞</span>

AppButtonでのbadgeの配置は以下のとおり。

**Badgeのレイアウト**

| Display Size | 横位置(offset) | 縦位置 |
|:------------:|:--------------:|:------:|
| 5inch        | 右揃え         | 上揃え |
| 10inch       | 右揃え         | 上揃え |

<span class="underline">＜Remove Button＞</span>

削除ボタン自身とそのタッチマージンのレイアウトは以下のとおり。

**削除ボタンサイズ定義**

**削除ボタン スタイル**

| button height | button width | border-radius | box-shadow | touch margin |  |  |  |
|:-------------:|:------------:|:-------------:|:----------:|:------------:|:------:|:-------:|:-------:|
|               |              |               |            | top          | bottom | left    | right   |
| 60px          | 60px         | 0px           | -          | 0px          | -1px   | 0px     | 0px     |

★TODO:後で対応。

※touch marginのStyleは削除ボタン のStyle基準

色彩および、削除ボタン内部のグリフ指示は、スタイルガイドの指定に従う。

AppButtonでの削除ボタンのレイアウトは以下のとおり。

**削除ボタンレイアウト**

> **削除ボタンレイアウト**

| Display Size | 横位置(offset) | 縦位置 |
|:------------:|:--------------:|:------:|
| 5inch        | 左揃え         | 上揃え |
| 10inch       | 左揃え         | 上揃え |

> &lt;RTL表記でのレイアウトについて&gt;

★TODO:後で対応。

RTL表記の場合、ラベル文字列がltr表記からrtl表記に変わるのみ。

アイコン画像の右上にbadge、左上に削除ボタンを置く配置はRTL表記でもLTR表記でも変えない。

アイコン画像、削除ボタン内のグリフは、
LTRとRTLで変更すべきデザインは無く、英語向けから変更なし。

-   Transition

draggable mode でのtransitionは以下のとおり。

> \- draggableへ変更
>
> スケールアップ ()　およびフェードアウト(Label を非表示Duration
>
> \- draggable から normal, customize へ変更
>
> スケールダウン() およびフェードイン(Labelを表示Duration

削除ボタンのtransitionは以下のとおり。

\- Entrance: スケールアップ () /フェードイン　Duration　

\- Exit: スケールダウン() /フェードアウト　Duration　

ただし、初期化時に、削除ボタンの表示指示が行われていた場合は、削除ボタンはtransitionを伴わずに表示される。また削除ボタンの表示開始/終了で明示的にtransitionなしを指定できる。

API Documentation
---------

-   オブジェクト名

> AppButton

-   コンストラクタ

> $.cscwAppButton (\[options\]) : AppButtonを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |  |
|:-------:|:-------------:|
| Markup  | &lt;div id="copy"&gt;&lt;/div&gt; |
| Script  | $("copy").cscwAppButton(); |

-   オプション

> AppButton の生成オプション

| Property | Type | Description | Default |
|:--------:|:----:|:-----------|:-------|
| label | String/Array/<br>jQueryObject | ラベル文字列。ラベルが２行になる場合は、改行を含む文字列または配列で渡す*１。単純なテキスト形式で指示できないスタイル混在が必要な場合はjQueryObjectを利用する。jQueryObjectで指示した場合は、Widgetによるtruncateは行われない。 | null |
| image | String | App Icon画像を示すパス | 必須 |
| badge | Object | Badgeの生成オプション<br>badgeのtransitionはなし | null |
| mode | String | モードを指定<br>normal<br>customize<br>draggable<br>blank<br><br>規定の文字列以外を指定しないこと | normal |
| enable | Boolean | falseにするとnormalモードではDisable状態となり、操作を受け付けない。<br>modeがnormal以外で、falseを指定したときの動作は保証されない | true |
| removeButton | string | Remove buttonの有無<br>show　remove button付き<br>hide　remove buttonなし<br><br>規定の文字列以外を指定しないこと | hide |
| soundEnable | Boolean | Widgetによる操作音(valid音)の鳴動制御. (Remove button操作音は対象外)<br>true 操作音を鳴らす<br>false 操作音を鳴らさない |
| invalidSoundEnable | Boolean | Widgetによる操作音(invalid音)の鳴動制御<br>true 操作音を鳴らす<br>false 操作音を鳴らさない | true |
| truncate | String | <br>ラベル長がラベル領域を超過したときの省略描画の適用<br><br>null/end/middle/begin以外の値を指定しないこと。<br><br>null　超過が起きない場合に使うことを前提とする。超過した場合の挙動は保証しない。<br><br>end　ラベルの前方を優先して表示し、エリアを超過した後方を省略表示とする。<br><br>middle　ラベルの前方、後方を優先して表示し、文字列の中央を省略表示する<br><br>begin　ラベルの後方を優先して表示し、エリアを超過した前方を省略表示とする。<br><br> | null |
| autoWrap | Boolean | テキスト長が領域幅を超える場合の折り返しを行うか否か。<br>truncateで"begin", "middle"を指定した場合はtrueにしてはならない | false |

\*1　
String型指定時の改行は複数含んではならない。また、Array型指定時における各配列要素は、改行を含んではならない。

-   Badgeの生成オプション:

> Badgeの生成オプションは、Badge widgetの生成オプションと同一。
>
> ただし、type="icon"固定

-   オプション相当情報のMarkupによる指定

なし

-   オプション相当情報のCSSによる指定

> 　　なし

-   メソッド

| .cscwCall(“badge”) |  |  |
|:------------------ |:--- |:--- |
| バッジを取得する | | |
| 戻り値 | | |
| | **type** | **description** |
| | Object | Badge Widgetを返す<br><br>badge生成オプションなしで生成したAppButtonの場合、badgeメソッドを呼んだ時点でbadgeが生成される。 |

| .cscwCall(“mode”, mode) |  |  |  |
|:----------------------- |:--- |:--- |:--- |
| モードを切り替える。<br>(badge, remove buttonの表示/非表示はstatus切り替えと別に行う。) | | |
| 引数の説明 | | | |
| **name** | **type** | **description** | |
| mode | String | モードを指定 | |
| | | normal | 通常のモードへ |
| | | customize | Customizeモードへ |
| | | draggable | draggableモードへ |
| | | blank | blankモードへ |


| .cscwCall(“mode”) |  |  |  |
|:----------------- |:--- |:--- |:--- |
| 現在のモードを取得する | | | |
| 戻り値 | | | |
| | **type** | **description** |
| | String | 現在のモード | |
| | | normal | 通常のモード |
| | | customize | Customizeモード |
| | | draggable | draggableモード |
| | | blank | blankモード |

| .cscwCall(“enable”, enable) |  |  |  |
|:--------------------------- |:--- |:--- |:--- |
| <br>AppButtonの有効/無効を切り替える。<br><br>mode=normal以外でdisableでの動作は保証しない。<br><br> | | |
| 引数の説明 | | | |
| **name** | **type** | **description** | |
| enable | Boolean | AppButtonの有効/無効 | |
| | | true | 有効 |
| | | false | 無効(Disable状態) |

| .cscwCall(“enable”) |  |  |  |
|:------------------- |:--- |:--- |:--- |
| AppButtonが有効かどうかを取得する。 | | | |
| 戻り値 | | | |
| | **type** | **description** | |
| | Boolean	| AppButtonの有効/無効 | |
| | | true | 有効 |
| | | false | 無効(Disable状態) |

| .cscwCall(“removeButton”, status[, transition]) |  |  |  |
|:--------------------------------------------- |:--- |:--- |:--- |
| remove buttonをtransition 付で表示/削除する。表示/削除の状態が変わらないのであれば何もしない。 | | | |
| 引数の説明 | | | |
| **name** | **type** | **description** | |
| status | String | remove buttonの表示状態 |
| | | show | remove buttonが無ければremove buttonを付ける |
| | | hide | remove buttonがあればremove buttonを消す |
| transition | Boolean | トランジションの有無、省略時はtrue |  |
|  |  | true | transitionを付けてremove buttonを表示/削除する |
|  |  | false | transitionなしで remove buttonを表示/削除する |

| .cscwCall(“removeButton”) |  |  |  |
|:------------------------- |:--- |:--- |:--- |
| remove buttonが表示中であるか否かを取得する。 | | | |
| 戻り値 | | | |
| | **type** | **description** | |
| | String | remove buttonの表示状態 | |
| | | show | remove buttonあり |
| | | hide | remove buttonなし |

| .cscwCall(“label”,label) |  |  |
|:---------------------------- |:--- |:--- |
| labelを切り替える。 | | |
| 引数の説明 | | |
| **name** | **type** | **description** |
| label | String/Array/<br>jQueryObject | ラベル文字列。<br><br>ラベルが２行になる場合は、改行を含む文字列または配列で渡す*1。<br>単純なテキスト形式で指示できないスタイル混在が必要な場合はjQueryObjectを利用する。jQueryObjectで指示した場合は、Widgetによるtruncateは行われない。 |

| .cscwCall(“iconImage”, path) |  |  |
|:---------------------------- |:--- |:--- |
| アイコン画像のパスを設定する。 | | |
| 引数の説明 | | |
| **name** | **type** | **description** |
| path | String | アイコン画像のパス。 |

| .cscwCall(“hover”,hover) |   |   |   |
|:------------------------ |:--- |:--- |:--- |
| <br>mode=blank時のhover状態を変更する。<br><br>mode=blankの時のみ使用可。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| hover | Boolean | hoverの有効状態 |  |
|  |  | true | hover中のレイアウトが適用される。 |
|  |  | false | hover中のレイアウトが解除される。 |

-   イベント

| イベントタイプ |
|:------------- |
| cscwRemoveMe |
| **イベントトリガ** |
| remove buttonがタップされた時に発生 |

| イベントタイプ |
|:------------- |
| cscwRelease |
| **イベントトリガ** |
| cscwTouchAndHoldの発生後、タッチリリースした(指を離した)時に発生*。 |

> \* ”cscwMouseUp” イベントにて判断

| イベントタイプ |
|:------------- |
| cscwTap |
| **イベントトリガ** |
| ボタンがタップされた時に発生 |

| イベントタイプ |
|:------------- |
| cscwTouchAndHold |
| **イベントトリガ** |
| <br>ボタンが押下され所定の時間が経過したとき発生。<br><br>Customizeモードのみ。 |

| イベントタイプ |  |  |  |  |
|:------------- |:--- |:--- |:--- |:--- |
| cscwTransitionEnd |  |  |  |  |
| **イベントトリガ** | | | | |
| 状態変更に伴う、描画処理を含むすべての処理が完了したことを示す | | | | |
| 戻り値 | | | | |
| **Type** | **property** |	**property type** |	**description** | |
| Object | property | String | removeButton | removeButtonの表示状態変更 |
| | | | mode | modeの変更 |
| | value | String |
| | | | [propertyがremoveButtonの場合] |
| | | | show | 表示開始 |
| | | | hide | 表示終了 |
| | | | [propertyがmodeの場合] |
| | | | normal | normalモードに移行 |
| | | | customize | customizeモードに移行 |
| | | | draggable | draggableモードに移行 |
| | | | blank | blankモードに移行 |
| | result | String | completed | 正常に完了した |
| | | | cancelled | キャンセルされた |