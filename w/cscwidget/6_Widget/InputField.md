[Input Field](../abstractwidgetcontents)
======

機能
-----------

-   概要

> 入力フィールド。
>
> ただし、本Widgetの範疇は、入力可能状態であってもカーソルを表示しないものに限る。
>
> （カーソル表示を伴うものは、TextFieldの項を参照。）

-   機能

> 入力用フィールドを表示する。
>
> Embedded KeyPadおよびEmbedded PhoneNum
> Keypadと連携し、Keypadやハードキー(T.B.D.)で入力した値をボタン上に表示する。
>
> 　なお、細かい挙動は、アプリケーションから指定されるインプットモデルによって制御される。
>
> <span class="underline">&lt;値域&gt;</span>
>
> コンストラクタオプションに設定可能な値の最大値、最小値、スケールを指定できる。
>
> インプットモデルが数値型の時：値の最大値/最小値/スケール　として扱う。スケールが0の場合は整数を扱う。
>
> スケールが1以上の場合は固定小数点を扱い、スケールはその小数点の位置を示す。
>
> インプットモデルが文字列型の時：最短文字列長/最長文字列長　として扱う。スケールは無視される。
>
> 　　インプットモデルがパスワード型の時：最短文字列長/最長文字列長　として扱う。スケールは無視される。
>
> 　　インプットモデルがパスコード型の時：最短文字列長/最長文字列長　として扱う。スケールは無視される。
>
> <span class="underline">&lt;値の表示&gt;</span>
>
> 入力フィールド上に値を表示する。値域範囲外の値や、不正な値であっても、入力フィールド上への表示は可能である。アプリケーションは、必要に応じてInput
> Fieldが提供するメソッドやイベントを使用し、後述する値の評価や確定の指示を行う必要がある。
>
> <span class="underline">インプットモデルが数値型の時</span>：
>
> 表示指示した値がスケールに従って解釈され、整数あるいはスケールによって定まる最小桁までの小数として表示される。クリアが指示された場合は、デフォルト値に戻す。
>
> <span class="underline">インプットモデルが文字列型の時</span>：
>
> 表示指示した値がそのまま表示される。
>
> 　　<span
> class="underline">インプットモデルがパスワード型の時</span>：
>
> 入力内容に関わらず、伏せ字()で表示される。クリアが指示された場合は、一文字消去する。
>
> <span class="underline">インプットモデルがパスコード型の時</span>：
>
> 表示指示した値が最短文字列長さ以上であればそのまま表示される。最短文字列長未満である場合は、最短文字列に足りない文字を所定の文字で補い表示する。　例)
> 値が12で最小が4文字の場合の表示は「12 - -」となる。
>
> <span class="underline">&lt;値の評価&gt;</span>
>
> 入力された値が正しいかどうかの評価を行い、評価結果を返す。
>
> <span class="underline">インプットモデルが数値型の時</span>：

数値を入力した場合、入力値が値域の範囲内であれば真となり、範囲外であれば偽となる。

> 数値以外を入力すると、評価結果は常に真となる。
>
> <span class="underline">インプットモデルが文字列型の時</span>：

　　　　　　　　入力文字列長が、値域の範囲内であれば真となり、範囲外であれば偽となる。

> 　　　　空文字は偽となる。入力が数値であるか否かは考慮しない。
>
> <span class="underline">インプットモデルがパスワード型の時</span>：

　　　　　　　　入力文字列長が、値域の範囲内であれば真となり、範囲外であれば偽となる。

> 　　　　空文字は偽となる。入力が数値であるか否かは考慮しない。
>
> <span class="underline">インプットモデルが</span>パスコード<span
> class="underline">型の時</span>：

　　　　　　　　入力文字列長が、値域の範囲内であれば真となり、範囲外であれば偽となる。

> 　　　　空文字は偽となる。入力が数値であるか否かは考慮しない。
>
> <span class="underline">&lt;値の確定&gt;</span>
>
> 入力ボタン上の値を確定する。
>
> <span class="underline">インプットモデルが数値型の時</span>：
>
> 最小値以下の値が入力されている場合、最小値を設定する。最大値より大きい値が入力されている場合、最大値を設定する。表示は、数値の表示に適した形に調整される。
>
> <span class="underline">インプットモデルが文字列型の時</span>：
>
> 　　　　文字列長が不正だった場合は、空文字を設定する。
>
> <span class="underline">インプットモデルがパスワード型の時</span>：
>
> 　　　　文字列長が不正だった場合は、空文字を設定する。
>
> イ<span class="underline">ンプットモデルが</span>パスコード<span
> class="underline">型の時</span>：
>
> 　　　　文字列長が不正だった場合は、空文字を設定する。
>
> <span
> class="underline">&lt;インプットモデルとEmbeddedKeypad側の指定について&gt;</span>
>
> 　それぞれのインプットモデルは、提供する機能に見合った設定のEmbeddedKeypadと対で利用する必要がある。
>
> 　適切な組み合わせを以下に示す。
>
> **インプットモデルと　連携するEmbeddedKeypad /
> EmbeddedPhoneNumKeypadの設定組み合わせ**

|   | EmbeddedKeypad：タイプ | Embedded | PhoneNumKeypad |   |   |   |
|:--- |:--------------------- |:-------- |:-------------- |:--- |:--- |:--- |
|  | whole number | decimal | | integer |  |  |
| <br>InputField：<br><br>インプットモデル<br><br> | 数値型（スケール　0） | ○ |   | × | ○ | × |
|  | 数値型（スケール　1以上） | ○  |  | ○ | × | × |
|  | 文字列型 | × |  | ○ | × | ○ |
|  | パスワード型 | ○ |  | × | × | × |
|  | パスコード型 | ○ |  | × | × | × |

-   操作

> Off状態のフィールドをタップすると表示状態を変更する。連携するKeypadが常に同一画面に表示されているケースに備え、入力エリアの状態はOn状態固定とすることができる。
>
> Disable状態の場合、入力フィールドへの操作は受け付けられない。

-   音

> コンストラクタで鳴らすことを指定した場合は、States変更のためのタップ操作を受け付けると、Valid音が鳴る。同じく、コンストラクタで鳴らすことを指定した場合は、操作を受け付けない場合にInvalid音が鳴る。

-   レイアウト

入力フィールドを視覚的に表す矩形領域である。詳細を以下に示す。

**全体レイアウト**

**スタイル定義**

> **フィールドの定義**

|   | backgruond-color | border-color | color | opacity |
|:--- |:---------------- |:------------ |:----- |:------- |
| Default | #1a1b1f | #7e8799 | #ffffff |  |
| Focus |  | #37c6d9 |  |  |
| Placeholder |  |  | #ffffff |  |
| Caret |  |  | #666666 |  |

> **フォントの定義**

|   | numeric-size | text-align |
|:--- |:------------ |:---------- |
| 5inch/10inch | 40px | left |

適用される色情報は、入力フィールドのステイタスとApplication Theme,
Container Theme から決定される。

詳細はスタイルガイド（TextFieldの項）を参照のこと。ただし、InputFieldはAlerted状態を取らない。

> &lt;RTL表記でのレイアウトについて&gt;
>
> Input Fieldは、文字の書き順においてRTL表記であるかを関知しない。Input
> fieldは数値やパスコードの入力に用いるものであるため、CSCWidgetのデフォルト指定にかかわらず入力結果は常にltrで表示される。
>
> Input
> Fieldは、言語に依存した小数点の表記をサポートしない。表示言語が、フランス語やアラビア語であっても小数点にはピリオドを用いる。カンマには使えない。
>
> Input
> Fieldは、常に数値表示に算用数字を用いる。インド数字等はサポートしない(文字列扱い)。

API Documentation
-----------

-   オブジェクト名

> inputField

-   コンストラクタ

> $.cscwInputField(\[options\]) :入力フィールドを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”inputField”&gt;&lt;/div&gt; |
| Script | $(“#inputField”).cscwInputField(); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| width | Integer | 入力フィールドの幅(pixel) | null |
| height | Integer | 入力フィールドの高さ(pixel) | null |
| inputModel | String | "number"：数値型<br>"string"：文字列型<br>"password"：パスワード型<br>"passcode"：パスコード型<br>| "number" |
| value | <br>String /<br>Integer<br><br> | 入力の初期値<br><br>nullの場合はdefaultValueを適用する。<br>String型の場合、改行を含んではならない。<br> | null |
| defaultValue | <br>String /<br>Integer<br><br> | 設定のクリアが指示されたときに戻す値。<br>String型の場合、改行を含んではならない。<br><br>nullの場合はvalue値を用いる。<br><br>valueもnullの場合は、以下を適用する。<br>数値型：入力値の下限値<br>文字列型：空文字<br>パスワード型：空文字<br>パスコード型：空文字 | null |
| min | Integer | 数値型の場合：入力値の下限値<br>文字列型の場合：最短文字列長<br>パスワード型の場合：最短文字列長<br>パスコード型の場合：最短文字列長<br> | 0 |
| max | Integer | 数値型の場合：入力値の上限値<br>文字列型の場合：最長文字列長<br>パスワード型の場合：最長文字列長<br>パスコード型の場合：最長文字列長<br>| null |
| action | String | "interactive"：操作を受け付け、stateの切り替えを行う<br>"none"：操作を受け付けない<br> | "none" |
| status | String | 入力フィールドの状態<br><br>"on"：On状態<br>"off"：Off状態<br> | "on" |
| enable | Boolean | 入力フィールドの有効/無効<br><br>true：有効<br>false：無効<br> | true |
| embeddedKeypad | jQueryObject | 連携する入力用キーパッド。<br>（EmbeddedKeypad）<br> | null |
| soundEnable | Boolean | Widgetによる操作音(valid音)の鳴動制御<br><br>true：操作音を鳴らす<br>false：操作音を鳴らさない<br> | true |
| invalidSoundEnable | Boolean | Widgetによる操作音(invalid音)の鳴動制御<br><br>true：操作音を鳴らす<br>false：操作音を鳴らさない<br> | true |
| scale | Integer | value, defaultValue, min, maxを1/(10のscale乗)倍した数値として扱う。<br>inputModel: "number"指定時のみ有効。<br><br>0：各値を整数として扱う。<br>1：各値を1/10倍した数値として扱う。maxに21を指定した場合、最大値は2.1となる。<br>2：各値を1/100倍した数値として扱う。maxに21を指定した場合、最大値は0.21となる。<br> | 0 |
| watermark | String | ウォーターマーク文字列。<br><br>文字列内に改行を含んではならない。<br>数値型、文字列型、パスワード型に用いる。<br>パスコード型では無視される。<br> | null |
| padding | String | inputModelがnumberかつscaleが0かつ数値が値として設定されている場合にのみ有効。<br><br>常に指定の桁数で表示する場合の、桁数と補う文字を指定する。補う文字を桁数だけ並べた文字列で指定する。値が指定桁数を超えた場合、正しく表示されない。<br><br>フィールドの表示のみを制御し、保持する値には影響しない。<br><br>例）<br>"00" 必要に応じて"0"を補って2桁に揃える。<br>例えば、3は 03 と表示する。<br>このときvalueメソッドで取得される値は3である。<br><br> | 桁数を指定しない。 |

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> コンストラクタをコールする要素に対して、widthとheightを指定することで、InputFieldの大きさが指定できる。
>
> Example: \#inputfield{ width:100px height:80px;}

-   メソッド

| .cscwCall(“status”, status) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| 入力フィールドの状態を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | 入力フィールドの状態 |  |
|  |  | "on" | On状態 |
|  |  | "off" | Off状態 |

| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| 入力フィールドの状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | 入力フィールドの状態 |
|  |  | "on" | On状態 |
|  |  | "off" | Off状態 |

| .cscwCall(“enable”, enable) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| 入力フィールドの有効/無効を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| enable | Boolean | 入力フィールドの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効 |

| .cscwCall(“enable”) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| 入力フィールドが有効かどうかを取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | 入力フィールドの有効/無効 |
|  |  | true | 有効 |
|  |  | false | 無効 |

| .cscwCall(“value”, value) |   |   |   |
|:------------------------- |:--- |:--- |:--- |
| 入力フィールドに値を入力する。入力した値はフィールド内に表示される。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| value | String / Integer | 入力フィールド内に表示する値 |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | valueの評価結果 |  |
|  |  | true | 真である |
|  |  | false | 偽である |

| .cscwCall(“value”) |   |   |
|:------------------ |:--- |:--- |
| 入力フィールド内の値を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String / Integer | 入力フィールド内の現在の値 |

| .cscwCall(“range”, min, max) |   |   |
|:---------------------------- |:--- |:--- |
| 入力フィールドの値の範囲を設定する。指定値が不正であった場合は、エラーを返す。<br><br>数値型の場合：入力値の最小値、最大値<br>文字列型, パスワード型, パスコード型の場合：最短文字列長、最長文字列長<br> |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| min | Integer | 最小値もしくは最短文字列長 |  |
| max | Integer | 最大値もしくは最長文字列長 |  |

| .cscwCall(“range”) |   |   |   |
|:------------------ |:--- |:--- |:--- |
| 入力フィールド内の値の範囲を取得する。 |  |  |  |
| 戻り値 |  |  |  |
| **type** | **property** | **property type** | **description** |
| Object | min | Integer | 最小値もしくは最短文字列長 |
|  | max | Integer | 最大値もしくは最長文字列長 |

| .cscwCall(“defaultValue”, defaultValue) |   |   |
|:-------------------------------------- |:--- |:--- |
| 入力フィールドの値のクリアが指示された時に戻す値を変更する。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| defaultValue | String / Integer | クリアが指示された時に戻す値<br><br>nullが指定された場合は、<br>数値型の場合：入力値の下限値<br>文字列型、パスワード型、パスコード型の場合：空文字<br>にて再設定される。<br><br> |

| .cscwCall(“defaultValue”) |   |   |
|:------------------------- |:--- |:--- |
| 入力フィールド内の値のクリアが指示された時に戻す値を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String / Integer | クリアが指示された時に戻す値 |

| .cscwCall(“isValid”) |   |   |   |
|:-------------------- |:--- |:--- |:--- |
| 入力フィールド内の値を評価する。評価基準については機能の項を参照。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | 値の評価結果 |  |
|  |  | true | 真である |
|  |  | false | 偽である |

| .cscwCall(“add”, value) |   |   |   |
|:----------------------- |:--- |:--- |:--- |
| 入力フィールドの値に追加する。<br><br>数値型の場合：<br>valueで指定した値を現在値に加算する。<br>値を追加した結果、値が設定可能な最大値より大きくなる場合、<br>最大値を設定し、実行結果としてtrueを返す。<br>値を追加した結果、値が設定可能な最小値より小さくなる場合、<br>最小値を設定し、実行結果としてtrueを返す。<br>現在値が文字列であった場合、引数を無視して<br>defaultValueを設定し、実行結果としてtrueを返す。<br>上記にて、defaultValueも文字列であった場合は、<br>最小値を設定し、実行結果としてtrueを返す。<br><br>文字列型、パスワード型、パスコード型の場合：<br>現在値に対して、valueで指定した文字列の結合を行う。<br>結合した結果、文字列長が設定可能な範囲内の場合、<br>結合後の値を設定し、実行結果としてtrueを返す。<br>結合した結果、文字列長が設定可能な範囲を超えた場合、<br>結合前の値に戻し、実行結果としてfalseを返す。<br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| value | Integer(数値型)<br>String(文字列型 他)<br> | 増加量、もしくは結合文字列 |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | メソッド実行の結果 |  |
|  |  | true | 成功 |
|  |  | true | 失敗 |

|.cscwCall(“fix”[, statusOff]) |   |   |   |
|:----------------------------- |:--- |:--- |:--- |
| 入力フィールド上の値を確定する。<br><br>数値型の場合：<br>Scaleが1以上の場合、必要に応じて足りない0を補う。<br>maxより大きい値が入力されている場合、max値を設定し、trueを返す。<br>minより小さい値が入力されている場合、min値を設定し、trueを返す。<br><br>文字列型、パスワード型、パスコード型の場合：<br>設定可能な文字列長の範囲外である場合、空文字を設定し、falseを返す。<br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| statusOff | Boolean | 値確定後にstatusをoffにするか<br>省略時はfalse |  |
|  |  | true | 値確定後にstatusをoffにする |
|  |  | false | 値確定後にstatusを変更しない |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | 値の評価結果 |  |
|  |  | true | 真である |
|  |  | false | 偽である |

| .cscwCall(“setDefault”) |   |   |   |
|:----------------------- |:--- |:--- |:--- |
| 入力フィールドの値を、defaultValueに戻す。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | 値の評価結果 |  |
|  |  | true | 真である |
|  |  | false | 偽である |

| .cscwCall(“backup”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| 現在の入力フィールドの値をバックアップする。<br>複数回コールした場合は最後にバックアップした値が保持される。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | 値の評価結果 |  |
|  |  | true | 真である |
|  |  | false | 偽である |

| .cscwCall(“restore”[, statusOff]) |   |   |   |
|:--------------------------------- |:--- |:--- |:--- |
| 入力フィールドの値を、バックアップされていた値に戻す。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| statusOff | Boolean | 値確定後にstatusをoffにするか<br>省略時はfalse |  |
|  |  | true | 値確定後にstatusをoffにする |
|  |  | false | 値確定後にstatusを変更しない |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | 値の評価結果 |  |
|  |  | true | 真である |
|  |  | false | 偽である |

| .cscwCall(“processEvent”, event) |   |   |   |
|:----------------------- |:--- |:--- |:--- |
| キーイベント処理を指示する。処理が受け付けられると、入力ボタンの値を設定する。<br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| event | Event | イベントオブジェクト。イベント種別がkeypressまたはkeydownでない場合、処理は受け付けられない。 ||
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | 処理が受け付けられたかどうか ||
|  |  | valid | 受け付けられた(valid音を鳴動すべき) |
|  |  | invalid | 受け付けられなかった(invalid音を鳴動すべき) |
|  |  | ignored | 受け付けられた(無音であるべき) |

| .cscwCall(“suppressValueChanged”, enable) |   |   |   |
|:----------------------- |:--- |:--- |:--- |
| イベント発火制御をする。<br><br>抑制中は、valueが変化した場合にもcscwChangedイベントは発生しない。<br><br>発火の開始を指示すると、直前に発生したイベントが発火する。<br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| enable | Boolean | イベント発火の抑制制御 |  |
|  |  | true | イベントの発火を抑制する |
|  |  | false | イベントの発火を開始する |

| .cscwCall(“valueChangedListener”, listener) |   |   |
|:------------------------------------------- |:--- |:--- |
| cscwValueChangedイベントの別形式のリスナを登録する。通常のイベントリスナと違ってこのメソッドで登録されたリスナ関数はsuppressValueChanged中にもイベントを受け取ることができる。また通常リスナよりも優先して呼び出される。<br><br>このメソッドではリスナは一つのみ登録できる（後優先登録）。listenerにnullを渡すと解除される。<br><br>listener(ev, data)の書式は以下の通り。<br> |  |  |
| listenerの仕様 |  |  |
|  | **type** | **description** |
| ev | object |  |
|  | type | "cscwValueUnchanged" |
|  | target | valueFieldのnodeオブジェクト |
| data | Object | cscwValueChangedイベントと同じ |

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwChanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| widgetの状態が変わった時に発生 |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | status | String | Widgetの状態 |
|  |  | on | On状態 |
|  |  | off | Off状態 |

| イベントタイプ |   |   |   |
|:------------- |:--- |:--- |:--- |
| cscwValueChanged |  |  |  |
| **イベントのトリガ** |  |  |  |
| 入力フィールドの値が変わった時 |  |  |  |
| 戻り値 |  |  |  |
| **type** | **property** | **property type** | **description** |
| Object | value | String | 入力フィールドの値 |
|  | valid | Boolean | 有効な値かどうか |
|  | min | Integer | 最小値もしくは最短文字列長 |
|  | max | Integer | 最大値もしくは最長文字列長 |
|  | reason | String | 値の変更理由 |
|  |  |  | "minAdjusted"：最小値以下<br>"maxAdjusted"：最大値より大きい<br>"scaleAdjusted"：最小桁より下の桁が入力された<br>"added"：addメソッドにより値が変更された<br>null：通常の場合<br> |
|  | delta | Number/String | addメソッドで値が変更された際の差分 |

| イベントタイプ |
|:------------- |
| cscwTap |
| **イベントのトリガ** |
| 入力フィールドがタップされた時に発生(statusにより挙動が変わることはない) 。 |