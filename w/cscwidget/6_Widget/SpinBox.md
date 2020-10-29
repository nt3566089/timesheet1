[Spin Box](../abstractwidgetcontents)
======

機能
--------

-   概要

> +,- ボタンの付いた入力欄。

-   機能

> 一つのInputField(valueFieldと呼ぶ)と二つのボタン(SpinBox用)を生成し、SpinBoxの形に並べる。
>
> Interactive、read-onlyとfocused stateの状態移行を行う。(focused
> stateと入力のfocusとは別の概念であることに注意.)
>
> ボタンの操作を受けてvalueFieldの値を変更する。valueFieldの値に応じてボタンの有効/無効を変更する。
>
> 無効なボタン操作があったことを通知する。

-   操作

> <span class="underline">＜InputField＞</span>
>
> InputFieldの項の記載に準じる。SpinBoxが、ListItem上に配置された場合は、ListItemへのタップ(read-onlyであるInputFieldへのタップを含むが、+/-ボタンへのタップは含まない)
> に応答してアプリがInputFieldに指示し、InputFieldをON(focused
> state)にすることが求められる。
>
> <span class="underline">＜ボタン＞</span>
>
> 二つのボタンは、通常のButtonWidgetとは次の点で異なる。
>
> \+/- ボタンを押下すると押下イベントが発生する。+/- ボタンを押下しつづけるとオートリピートする。オートリピートでは、一時停止するイベントが発生する。オートリピート時、あらかじめ複数の値を指定することで、指定した値から次の値へ移る時のイベント発生までの間隔を1に変更できる。
> (momentary detent)
>
>
> \+/- ボタンのグリフは作成時に任意に指定できる。
>
> 値の増減では、最大値に達した次は最小値/最小値に達した次は最大値へ移るwrap
> aroundありと、最大値/最小値に達したあとは変わらないwrap
> aroundなしのいずれの振る舞いをとるか指定できる。wrap
> aroundなしの場合、InputFieldの値が下限以下ならば –
> ボタンがdisableとなり、InputFieldの値が上限以上であれば +
> ボタンがdisableとなる。それ以外の場合は enableとなる。
>
> \+/- ボタン操作により値が上限/下限に達した場合のInputFieldの値の振る舞い、+/-ボタンの enable/disableの振る舞いはSpinBoxが受け持つ。
>
> InputFieldの値が数値でない場合、+, -
> ボタンのいずれもenableである。このとき、+/-
> ボタンの押下イベントはInputFieldの値を変更せず、イベントを通知する。アプリは、このイベントに応答して適切な値を設定する。

-   音

> ValueFieldのタップについては、InputFieldの仕様に従って鳴動する。
>
> +/-ボタンのタップについては、Buttonの仕様に従って鳴動する。最大値/最小値において、値の増加もしくは減少が指示できないケースにおいては、ボタンがdisable状態となるためinvalid音が鳴動することになる。
>
> オートリピートについては、オートリピート開始時にvalid音が鳴動し、値の変化中およびオートリピート終了時の音の鳴動は行われない。オートリピートの結果、最大値/最小値に到達した場合は、invalid音が鳴動し、その後のボタンからのリリースによる鳴動は行われない。

-   レイアウト

> InputFieldと増減ボタンの配置は、以下に示す4通りがある。それぞれの配置において、interactiveとread-onlyの２通りがある。
>
> Read-onlyであっても、設定によりInputFieldへのタップあるいはAPI呼び出しによりfocused
> stateに遷移する。focused stateの外観はinteractiveのfocused
> stateと同一。read-onlyでは、focused
> stateを抜けると元のread-onlyに戻る。



各種スタイル定義 (上段は5inch, 下段は10inch)

<table>
<thead>
<tr class="header">
<th></th>
<th>InputFieldのHeight</th>
<th>InputFieldのWidth</th>
<th>LabelのHeight</th>
<th>InputFieldのFontSize</th>
<th>ボタンのWidth/Height</th>
<th>+/-ボタンのglyph (Width/Height/FontSize)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>small</td>
<td>70px</td>
<td>67px</td>
<td>56px</td>
<td>30px</td>
<td>52px</td>
<td>32px</td>
</tr>
<tr class="even">
<td></td>
<td>78px</td>
<td>92px</td>
<td>56px</td>
<td>30px</td>
<td>60px</td>
<td>32px</td>
</tr>
<tr class="odd">
<td>normal</td>
<td>70px</td>
<td>311px</td>
<td>56px</td>
<td>30px</td>
<td>52px</td>
<td>32px</td>
</tr>
<tr class="even">
<td></td>
<td>78px</td>
<td>478px</td>
<td>56px</td>
<td>30px</td>
<td>60px</td>
<td>32px</td>
</tr>
</tbody>
</table>


-   参考: スタイルガイドとの対比

> StyleGuideでSpinBoxとして記載されている内容のうち、SpinBox
> LabelとRange LabelはSpinBox Widgetに含まれない。SpinBox
> Widgetにとっては、単に近くに配置された文字列である。
>
> &lt;rtl表記でのレイアウトについて&gt;
>
> SpinBoxはrtl表記/ltr表記を関知しない。
>
> SpinBoxは、言語に依存した小数点の表記をサポートしない。表示言語が、フランス語やアラビア語であっても小数点にはピリオドを用いる。カンマには変更しない。
>
> SpinBoxは、常に数値表示に算用数字を用いる。インド数字等はサポートしない(文字列扱い)。
>
> SpinBoxは、ミラーリングをサポートしない。つまり、ValueField(値)とincButton (+ボタン), decButton (-ボタン)の位置関係は、rtl表記/ltr表記で同一。

API Documentation
--------

-   オブジェクト名

> spinBox

-   コンストラクタ

> $.cscwSpinBox(\[options\]) :Spin Boxを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”spinBox”&gt;&lt;/div&gt; |
| Script | $(“#spinBox”).cscwSpinBox({width:200}); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| size | String | <br>Spin Boxのサイズ<br><br>下記の値以外の文字列を指定しないこと<br>下記の値以外を指定した場合エラーとなる<br><br>"small"：小型サイズで生成される<br><br>"normal"：通常サイズで生成される<br><br> | normal |
| width | integer | SpinBox全体の幅<br><br>size指定より優先される | null |
| wrapAround | Boolean | <br>上/下限に達している状態で+ / -ボタンを押下した場合の振る舞い<br><br>true：最大値から最小値/最小値から最大値へ移る<br><br>false：最大値/最小値に留まる<br><br> | true |
| interactive | Boolean | 外観がinteractive (true)かread-only (false) かを示す | true |
| valueField | Object | 値を表示するinput fieldに関する情報 | 別表を参照 |
| incButton | Object | +ボタンに関する情報 | 別表を参照 |
| decButton | Object | - ボタンに関する情報 | 別表を参照 |
| pausePoint | Array(integer) | オートリピート時に増減が一時停止する値。| null (オートリピート時の一時停止なし)
| scale | integer |<br>0：整数のSpinBox. デフォルトでは、+/- ボタンで１増減する。<br><br>1：小数点以下1桁の数値からなるSpinBox. デフォルトでは、 + / - ボタンで0.1増減する。<br><br>2：小数点以下2桁の数値からなるSpinBox. デフォルトでは、 + / - ボタンで0.01増減する。<br><br> | 0 |
| delta | integer | + / - ボタンで増減する量 | 1 |
| turbo | bool | + / - ボタンを押下し続けた際にオートリピートがターボモードに遷移するか | true |

-   valueFieldで使用するObjectの定義

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| value | String/integer | 入力の初期値 (数値を表すとは限らない。) | null |
| min | integer | 入力値の下限 | 0 |
| max | integer | 入力値の上限。指定なき場合は上限なし。| null |
| defaultValue | integer | クリアボタン(バックスペース)押下時に設定される値。| null |
| embeddedKeypad | jQueryObject | <br>連携する入力用キーパッド。<br><br>（EmbeddedKeypad）<br><br> | null |
| padding | String | InputFieldのオプション paddingを参照 | 同左 |

-   incButton, decButtonで使用するObjectの定義

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| glyph | String | <br>ボタン上に表示するGlyphコード<br><br>指定なき場合、incButtonはプラス記号, decButtonは マイナス記号<br><br> | null |

> <span class="underline">数値の扱いについて</span>
>
> 生成パラメータのpausePoint, value, min, max, defaultValue
> の値は、scaleの指定に従って解釈される。たとえば、scaleが1でmax が
> 12の場合、利用者の認識する最大値は 1.2
> である。Scaleが2でdeltaが5の場合、+ / -
> ボタンで0.05増減する。deltaに１以外の値を指定する場合、pausePoint,
> value, min, max,
> defaultValueにはdeltaの値と整合のとれた値を設定しなければならない。整合がとれていない場合の振る舞いは実装依存である。

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> なし

-   メソッド

| .cscwCall(“enable”, enable) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| SpinBox全体の有効/無効を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| enable | Boolean | SpinBoxの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効(disable状態) |

| .cscwCall(“enable”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| SpinBoxが有効かどうかを取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | SpinBoxの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効(disable状態) |

| .cscwCall(“valueField”) |   |   |
|:----------------------- |:--- |:--- |
| <br>valueFieldを取得する。<br><br>取得した InputField オブジェクトに対して安全に利用できるメソッドは、status, range, value のみ。<br>SpinBox動作の整合性を保つため、InputFieldの他のメソッドの利用は避けること。<br><br> |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | object | valueFieldのオブジェクト(InputField widget) |

| .cscwCall(“incButton”) |   |   |
|:---------------------- |:--- |:--- |
| <br>incButtonを取得する。<br><br>取得したButtonオブジェクトに対して安全に利用できるメソッドはなし。<br>SpinBox動作の整合性を保つため、Buttonの他のメソッドの利用は避けること。<br><br> |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | object | incButtonのオブジェクト |

| .cscwCall(“decButton”) |   |   |
|:---------------------- |:--- |:--- |
| <br>decButtonを取得する。<br><br>取得したButtonオブジェクトに対して安全に利用できるメソッドはなし。<br>SpinBox動作の整合性を保つため、Buttonの他のメソッドの利用は避けること。<br><br> |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | object | decButtonのオブジェクト |

| .cscwCall(“valueChangedListener”, listener) |   |   |
|:------------------------------------------- |:--- |:--- |
| <br>cscwValueChangedイベントの別形式のリスナを登録する。通常のイベントリスナと違ってこのメソッドで登録されたリスナ関数はリピート中にイベントを受け取ることができる。また通常リスナよりも優先して呼び出される。<br><br>このメソッドではリスナは一つのみ登録できる（後優先登録）。listenerにnullを渡すと解除される。<br><br>listener(ev, data)の書式は以下の通り。<br><br> |  |  |
| listenerの仕様 |  |  |
|  | **type** | **description** |
| ev | Object | イベント内容の戻り値 |
|  | type | "cscwValueChanged" |
|  | target | valueFieldのnodeオブジェクト |
|  | currentTarget | SpinBoxのnodeオブジェクト |
| data | Object | イベントデータの戻り値 |
|  |  | cscwValueChangedイベントと同じ |

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwValueUnchanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| 不適切なユーザ操作が行われたことを通知する。 |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | reason | String | イベント発生の理由|  |
|  |  |  | minLimit | SpinBox自体は有効で、‘－’ ボタンが無効にもかかわらず押下された。 |
|  |  |  | maxLimit | SpinBox自体は有効で、‘+’ ボタンが無効にもかかわらず押下された。 |
|  |  |  | decNaN | ’－’ボタン押下イベント時にvalueFieldの値が数値ではないため値を減少できない。 |
|  |  |  | incNaN | ’＋’ボタン押下イベント時に、valueFieldの値が数値ではないため値を増加できない。 |
|  |  |  | disabled | SpinBox自体が無効で、’+’ボタンもしくは’―’ボタンが押下された。 |