[Slide Start](../abstractwidgetcontents)
======

API Documentation
-------------

-   オブジェクト名

> slideStart

-   コンストラクタ

> $.cscwSlideStart(\[options\]) :
> スライドスタートを生成するコンストラクタ
>
> 適用可能なタグ: div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”slideStart” &gt;&lt;/div&gt; |
| Script | $(“#slideStart”).cscwSlideStart(); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| enable | Boolean | <br>falseにするとDisable状態となり、操作を受け付けない。<br><br> | true |
| glyph | String | ハンドル部に載るグリフのコード | "\u2192"(右矢印) |
| label | String/<br>Array/<br>jQueryObject | <br>ベース右端に表示する文字列<br>ラベルが2行になる場合は、改行を含む文字列または配列で渡す*１。<br>単純なテキスト形式で指示できないスタイル混在が必要な場合はjQueryObjectを利用する。<br>jQueryObjectで指示した場合は、truncateオプションは適用されない。<br><br> | null |
| truncate | String | <br>truncateさせる位置を指定<br><br>null：超過が起きない場合に使うことを前提とする。超過した場合の挙動は保証しない。<br><br>"end"：文字列の終端を省略表示する<br><br>"middle"：文字列の中央を省略表示する<br><br>"begin"：文字列の先端を省略表示する<br><br> | null|
| autoWrap | Boolean | <br>テキスト長が領域幅を超える場合の折り返しを行うか否か<br><br>true：自動改行する<br><br>false：自動改行しない<br><br>truncateで"begin", "middle"を指定した場合はtrueにしてはならない<br><br> | false |
| status | String | <br>スライドスタートの状態<br><br>"on"：On状態<br><br>"off"：Off状態<br><br>on/off以外の文字列を指定しないこと。<br>on/off以外を指定した場合off状態で生成されるが、正常な動作は保証しない<br><br> | "off" |

\*1
String型指定時は複数の改行を含んではならない。また、Array型指定時における各配列要素は、改行を含んではならない。

-   メソッド

| .cscwCall("label", label) |   |   |
|:------------------------- |:--- |:--- |
| スライドスタート内に表示する文字列を設定する |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| label | String/<br>Array/<br>jQueryObject | スライドスタート内に表示する文字列<br>ラベルが２行になる場合は、配列または改行を含む文字列で渡す*1。<br>単純なテキスト形式で指示できないスタイル混在が必要な場合はjQueryObjectを利用する。<br>jQueryObjectで指示した場合は、Widgetによるtruncateは行われない。 |

| .cscwCall(“label”) |   |   |
|:------------------- |:--- |:--- |
| スライドスタート内に表示する文字列を取得する |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String/<br>Array/<br>jQueryObject | スライドスタート内に現在表示されている文字列。 <br><br>設定されていない場合は空文字が戻る。|

| .cscwCall(“status”, status[, transition]) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| スライドスタートの状態を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | スライドスタートの状態 |  |
|  |  | on | On状態 |
|  |  | off | Off状態 |
| transition | Boolean | トランジションの有無、省略時はtrue |  |
|  |  | true | ハンドル部がスライドするトランジションが発生する。 |
|  |  | false | ハンドル部がスライドするトランジションが発生しない。 |

transitionありでステータス変更を行った場合、ステータス変更中（transition中）でも内部的にはtransition完了を待たずにステータスは切り替わる。

| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| スライドスタートの状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | スライドスタートの状態 |  |
|  |  | on | On状態 |
|  |  | off | Off状態 |

| .cscwCall(“enable”, enable) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| スライドスタートの有効/無効を切り替える。　|  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| enable | Boolean | スライドスタートの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“enable”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| スライドスタートが有効かどうかを取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | スライドスタートの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwChanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| スライドが右端に到達した時に発生 |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | status | String | スライドスタートの状態 | |
|  |  |  | on | On状態 |
|  |  |  | off | Off状態 |

| イベントタイプ |
|:------------- |
| cscwTap |
| **イベントのトリガ** |
| スライドスタートがタップされた時に発生 |