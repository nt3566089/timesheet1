[Slider](../abstractwidgetcontents)
======

機能
------

-   概要

> スライダー。複数ステップ刻み、ステップなしの2種類がある。

-   機能

> 所定サイズのスライダーを表示する。
>
> Sliderへの操作に応答しcharacter viewerを表示する。
>
> Sliderは、enable 状態とdisable状態の二つの状態を持つ。

-   操作

> Thumb(つまみ)の左右方向へのドラッグ操作が可能。Thumbはchannelのどこでもリリースできる。
> ステップ刻みのsliderの場合、リリース後にリリース位置に一番近いtick
> mark(目盛)につまみが動く。
>
> Slider上のタップ操作では、ステップ刻みのslidderの場合、タップした位置に一番近い目盛につまみが動く。Channelの右外/左外(range
> valueの置かれる位置)をタップした場合、Thumbはchannelの右端/左端に移動する。

-   音

> Enable状態では、チャネルをタップした場合、RangeValueをタップした場合にValid音が鳴動する。

Disable状態では、チャネルをタップした場合、RangeValueをタップした場合にInvalid音が鳴動する。

> Thumbのドラッグにおいては、Thumbのリリース時にValid音が鳴動する。

-   レイアウト

> Sliderのサイズのバリエーションは1通りである。高さは固定で、幅は指定に従う。Style
> Guideで規定する最小幅は、Sliderを利用する側の責務である。
>
> Styleは、normalの1通り。
>
> Sliderは、channelの表現で標準のchannelと画像のchannelの二通りがある。
>
> Style
> Guideでは、標準のchannelでは利用者が指定している値に対応する部分(通常はthumbの左側)をStyle
> Aとよび、反対側(通常はthumbの右側)をStyle Bと呼びStyle A, Style
> Bで色彩等を指定する。標準のchannelには、Style AとStyle
> Bを持つものとStyleBのみの2通りがある。 Style
> Bのboarderは、solidのである。
>
> Sliderの色彩は、ThumbはToggle
> SwitchのThumbに準じ、グリフ、テキスト、channelはbuttonの色彩に準じる。
>
> <span
> class="underline">＜Glyph/Textなし、画像のchannelのスライダー＞</span>
>
> **全体レイアウト**
>
> Sliderは視覚的な外枠線を持たない。Channelの画像は、縦方向にセンタリングされる。
>
> 画像のchannelの場合、tick
> mark(目盛り)はchannelの画像に描かれているものとする。Sliderがtick
> markをさらに書き加えはしない。
>
> Glyph/Textが無い場合でも、タッチ領域はchannelの左右を含める。幅のchannelを4分割
> (5段階)した場合のThumbのセンターの位置とタッチ領域の例を示す。(Thumbは図示していない。)
>
> **タッチ領域の例**
>
> <span
> class="underline">＜Glyph/Textなし、標準のchannelのスライダー＞</span>
>
> Style Guide 参照
>
> <span class="underline">＜Glyphのみを持つスライダー＞</span>
>
> Glyphのみをrange
> valueに持つスライダーのレイアウトは以下のとおり。　Glyphのサイズは、である。ChannelとGlyphとの間隔は、Glyphの外側までが
> range valueとなる。従って、left/rightPaddingに以上の値を指定する。
>
> **Range Valueがグリフのケース**
>
> <span class="underline">＜テキストのみを持つスライダー＞</span>
>
> Textのみをrange valueに持つスライダーのレイアウト。
>
> **RangeValueがテキスト表示の場合**
>
> **スタイル定義**

| UI | Margin A | Margin B | フォントサイズ |
|:--- |:-------- |:-------- |:------------- |
| 5” / 10” |  |  | Medium regular |

> channelからの左右のpadding
> (張り出し量)は、常にSlider生成での指定値としテキスト等の長さに合わせることはしない。テキストが張り出し領域に収まることはアプリケーション側の責任とする。
>
> <span class="underline">＜Character Viewer＞</span>
>
> Sliderは、thumbを押下している間thumbの上にthumbの位置に対応する(離散値を取るsliderの場合はもっとも近い目盛りに対応する)フィードバック文字列をCharacter
> Viewerで表示する。Character
> viewerは、押下に対応して直ちに表示され、指を離すと直ちに非表示となる。
>
> Sliderは、channelあるいはrange
> valueがタップされた場合、thumbを移動したのち短時間だけcharacter
> viewerを表示する。
>
> Character
> viewerの水平位置は、原則としてThumbに対して中央揃え。ただし、Character
> viewerの表示が欠ける恐れのある場合、具体的にはfeedbackAreaをはみ出す恐れのある場合は、表示位置を調整して表示する。画面左右端では、画面端とCharactere
> viewerとがgridデザインで定めるoutside gutter
> だけ開くよう右/左にずらして表示する。Thumbの上方にCharacter
> viewerが収まらない場合、Character
> viewerはthumbの下方に表示可能であれば上方に代えて下方に表示する。
>
> Character
> viewerは、押下に対応して直ちに表示され、指を離すと直ちに非表示となる。
>
> **Character Viewer（フィードバック表示）のレイアウト**
>
> **Character
> Viewerが画面左端よりはみ出さないように設定されたfeedbackAreaの設定に基づき**
>
> **位置を右にずらした表示例。**
>
> **feedbackAreaからはみ出さないようにThumbの下に表示位置を変えた例.**
>
> 点線であらわしたCharacter
> Viewer標準的な位置ではfeedbackAreaで指定された範囲から上にはみ出るため、Character
> Viewerの表示位置をThumbの下に変更し、さらに右にもはみ出ているので左へ位置をずらした例を示す。なお、Character
> Viewerが上、下いずれの場合もfeedbackAreaからはみ出る場合はfeedbackAreaか上にはみでるがthumbの上に表示する。Character
> Viewerの左辺をfeedbackAreaの左辺にあわせた時、Character
> ViewreがfeedbackAreaを右にはみ出してしまう場合は、右にはみ出したままとする。
>
> **Character Viewrの各種スタイル定義**

| Display Size | height | width | Padding A | Padding B | outside gutter |
|:------------ |:------ |:----- |:--------- |:--------- |:-------------- |
| 5inch |  |  |  |  |  |
| 10inch |  |  |  |  |  |

**Character Viewerの色彩**

| background | box-shadow |
|:---------- |:---------- |
|  |  |

> **Character Viewerのフォント**

| Display Size | フォントのサイズとウエイト | color | text-shadow |
|:------------ |:------------------------ |:----- |:----------- |
| 5inch / 10inch |  |  |  |

> <span class="underline">＜Thumb＞</span>
>
> Thumb のレイアウトは以下のとおり。図中にRで示すborder-radiusは。

　Normal時とPress時のthumbのレイアウト

> **Thumbの各種スタイル定義**

| Display Size | Height | Sep. line height　| R |
|:------------ |:------ |:----------------- |:--- |
| 5inch |  |  |  |
| 10inch |  |  |  |

> Thumbの色彩はToggle SwitchのThumbに準じ、二つの追加のDrop
> Shadowを持つ。
>
> Thumbは、Toggle SwitchのThumbと同じDrop Shadow(inside)に加え独自のDrop
> Shadow(outside)を同時に持つ。なお、disableの場合　drop
> shadow(outside)は持たない。(詳細は、補完ガイドを参照)
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> Sliderの左右端に文字列を配置する場合、その文字列はCSCWidgetのデフォルト指定に従い、ltrまたはrtlで表示する。
>
> Sliderはミラーリングをサポートしない。
> RTL表記であるかLTR表記であるかにかかわらず値やrange
> valueの位置に変更はない。 range
> valueのグリフの形状は常に一定で、左右の反転などはしない。
>
> その時の値をthumbの上方に表示するCharacter
> viewerは、オプションの指定に従い、LTRもしくはRTLで表示する。「+2」や「-1」といった符号付の数値だけの場合と「Less
> -1」(のアラビア語訳)
> といったアラビア語混じりの符号付き数値では、アラビア語のネイティブスピーカーにとっての自然な文字順序が異なるということから、アラビア語表記画面であってもLTR/RTLを使い分けることができる

API Documentation
------

-   オブジェクト名

> slider

-   コンストラクタ

> $.cscwSlider (\[options\]) :スライダー生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”slider" class=”cscw-slider"&gt; |
| Script | $(“#slider”).cscwSlider(); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description	| Default |
|:-------- |:---- |:----------- |:------- |
| type | String | <br>離散値を取るか連続値を取るかを示す<br><br>discrete 離散値を取るSlider<br><br>continuous 連続値を取るSlider<br><br> | discrete |
| step | Integer | <br>両端を含む目盛の数<br><br>連続値を取るSliderでは標準のchannelに目安として表示される目盛の数<br><br>channelの幅がstep-1で割り切れない場合は、右端の目盛り間隔から順に1pxずつ広げて調整する。<br><br> | 2 |
| value | Integer | <br>Thumbの初期位置。<br><br>0からstep-1まで指定可能。<br><br>連続値を取る場合：<br><br>離散値を取る場合:<br><br>0からchannelWidth-1まで指定可能<br><br> | <br>離散値を取る場合：<br><br>目盛の中央値<br><br>連続値を取る場合：<br><br>channelWidth / 2<br><br> |
| label | Array/関数 | <br>Arrayの場合:<br><br>character viewerに表示するラベル文字列を配列で指定する。文字列は改行を含んではならない。配列の長さとstepで指定した目盛の数は同じでなければならない。<br><br>関数の場合:<br><br>character viewerに表示するラベル文字列を返す関数を指定する。<br><br> | <br>null<br><br>指定なきばあいは、character viewrは表示されない。<br><br> |
| dir | String | <br>Character viewerに表示するラベル文字列の書き進む方向を指定する。<br><br>“global” 表示言語の共通初期設定に従う<br><br>“ltr” 左から右へ<br><br> | global |
| channelImage | String | 画像のchannelを使用することを示し、場合で、channelを表す画像へのパスを与える | 省略時は、標準のchannelを使用する。 |
| channelWidth | integer | <br>channelの横幅 (px)<br><br>画像のchannelの場合、channelWidthと画像の幅は同一でなければならない。<br><br> | 省略不可 |
| channelHeight | integer | <br>channelの高さ(px)<br><br>画像のchannelの場合、channelHeightと画像の高さは同一でなければならない。<br><br> | 12 |
| channelFeedback | String | <br>標準のchannelの場合に、Style Bを使用する部分を指定する。l2rはthumbの左側をstyle Bにする。noneはstyle Bを使用しない。<br><br>画像のchannelの場合は、この値は無視される。<br><br> | l2r. |
| leftPadding | Integer | channel左端からSlider左端までの間隔. (Thumb画像がchannel左端から34pxまではみ出すので、それ以上の値を推奨。) | 省略時は54px |
| leftRangeValue | Object | channleの左端(leftPadding内)に右寄せで配置されるグリフやテキストなどの生成オプション。 | 省略時は何も配置されない。 |
| rightPadding | Integer | channel右端からslider右端までの間隔。(Thumb画像がchannel右端から34pxまではみ出すので、それ以上の値を推奨。) | 省略時は54px |
| rightRangeValue | Object | channelの右端に左寄せで配置されるグリフやテキストなどの生成オプション。 | 省略時は何も配置されない。 |
| feedbackArea | Object | 画面座標で表したCharacter viewer を表示できる領域。 | <br>画面全体からoutside gutterだけ内側を指定するobject.<br><br>top　outside gutter,<br><br>bottom　画面高 – outside gutter,<br><br>left　outside gutter,<br><br>right　画面幅 – outside gutter<br><br> |

-   leftRangeValue, rightRangeValueで指定するObject

| Property | Type | Description	| Default |
|:-------- |:---- |:----------- |:------- |
| glyph	| String | グリフコード	| グリフなし |
| text | String | テキストの文字列。改行を含んではならない。 | テキストなし |

> ※glyph とtextを同時に指定してはならない。
>
> ※ グリフやテキストの文字列がright/leftRangeValue
> の中に納まることは、アプリケーション側の責務である。

※ テキスト文字列は、改行を含んではならない。

-   labelで指定する関数

| func(pos, max) |   |   |
|:-------------- |:--- |:--- |
| Character viewに表示すべき文字列を渡す。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| value | integer | Thumbの位置 |
| max | integer | <br>連続値を取るSliderの場合　channelWidth<br><br>離散値を取るSliderの場合　step<br><br> |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | string | charavter viewerに表示する文字列。空文字列の場合、character viewerは表示されない。 |

-   feedbackAreaで指定するObject

| Property | Type | Description	| Default |
|:-------- |:---- |:----------- |:------- |
| top | integer | Character Viewerの上辺はこの位置より下でなければならない | 上辺の位置に制限なし |
| bottom | integer | Character Viewerの下辺はこの位置より上でなければならない | 下辺の位置に制限なし |
| left | integer | Character Viewerの左辺はこの位置より右でなければならない | 左辺の位置に追加の制限なし. |
| right | integer | Character Viewerの左辺はこの位置より右でなければならない | 右辺の位置に追加の制限なし |

-   メソッド

| .cscwCall(“channelImage”, channelImage) |   |   |
|:--------------------------------------- |:--- |:--- |
| channel画像を差し替える。Channelが画像のchannelでない場合は、エラーになる。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| channelImage | String | channelを表す新しい画像へのパス。新しい画像の幅/高さは元の画像の幅/高さと同一でなければならない。 |

| .cscwCall(“channelImage”) |   |   |
|:------------------------- |:--- |:--- |
| <br>channel画像の場所を示す文字列を取得する。<br><br>※本メソッドはデバッグ用であり、製品ロジックでの利用は不可とする<br><br> |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | channel画像のパス |

| .cscwCall(“feedbackArea”, feedbackArea) |   |   |
|:--------------------------------------- |:--- |:--- |
| character viewerが表示できる領域をあらかじめ絶対座標で指定する。	 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| feedbackArea | Object | character viewerが表示できる領域 |

| .cscwCall(“feedbackArea”) |   |   |
|:------------------------- |:--- |:--- |
| sliderに設定されているcharacter viewerが表示できる領域を取得する |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Object | character viewerが表示できる領域 |

| .cscwCall(“value”, value) |   |   |
|:------------------------- |:--- |:--- |
| 指定した位置にThumbが動く。		 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| value | Integer | <br>離散値を取る場合:<br><br>目盛位置のインデックス。0からstep-1まで指定可能。selectedと同じ<br><br>連続値を取る場合:<br><br>channel左端からの位置。0からchannelWidth-1まで指定可能。<br><br> |

| .cscwCall(“value”) |   |   |
|:------------------ |:--- |:--- |
| 現在のThumbの位置を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | <br>離散値を取る場合:<br><br>目盛位置のインデックス。0からstep-1まで指定可能。<br><br>連続値を取る場合:<br><br>channel左端からの位置。0からchannelWidth-1まで指定可能。<br><br> |

-   イベント

| イベントタイプ |   |   |   |
|:------------- |:--- |:--- |:--- |
| cscwValueChanged |   |   |   |
| **イベントのトリガ** |   |   |   |
| Thumbの位置が変わった時に発生。 cscwValueUnchangedと相補の関係。 |   |   |   |
| 戻り値 |   |   |   |
| **type** | **property** | **property type** | **description** |
| Object | value | Integer | <br>離散値を取る場合:<br><br>目盛位置のインデックス。0からstep-1までの数値。<br><br>連続値を取る場合:<br><br>channel左端からの位置。0からchannelWidth-1までの値<br><br> |

| イベントタイプ |   |   |   |
|:------------- |:--- |:--- |:--- |
| cscwValueUnchanged |   |   |   |
| **イベントのトリガ** |   |   |   |
| Thumbの位置がThumbの操作を始めた時点位置と同じ位置で終わった時に発生。cscwValueChangedと相補の関係。 |   |   |   |
| 戻り値 |   |   |   |
| **type** | **property** | **property type** | **description** |
| Object | value | Integer | <br>離散値を取る場合:<br><br>目盛位置のインデックス。0からstep-1までの数値。<br><br>連続値を取る場合:<br><br>channel左端からの位置。0からchannelWidth-1までの値<br><br> |

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwTransitionEnd |   |   |   |   |
| **イベントのトリガ** |   |   |   |   |
| 画面操作による状態変更に伴う、描画処理を含むすべての処理が完了したことを示す |   |   |   |
| 戻り値 |   |   |   |   |
| **type** | **property** | **property type** | **description** |
| Object | property | String | value　固定 |   |
|  | value | Integer | 設定されたvalue |   |
|  | result | String | completed | 正常に完了した  |
|  |  |  | cancelled | キャンセルされた |