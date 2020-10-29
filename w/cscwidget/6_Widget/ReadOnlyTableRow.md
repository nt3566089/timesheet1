[Read Only Table Row](../abstractwidgetcontents)
======

機能
-------------------

-   概要

> 表示のみを行うTableRow（テーブルの行）

-   機能

> テーブルの中に配置され、1行の表示を行う。

-   操作

> なし

-   音

> なし

-   表示言語

> トップElementにlang属性を指定することで表示言語を個別に指定することができる。詳細は[<span
> class="underline">3.3.5表示言語の指定</span>](#_表示言語の指定)を参照。

-   レイアウト

> Style指定がnormalのケースについては、TableRowに同じ。ReadOnly要の見た目のスタイルが適用される。
> (ex.toggleSwitchはdisable同様のスタイルが適用される)
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> TableRowに準じる
>
> Readonly Table Item内のアイコン、ラベル、ボタン等のレイアウトはLTR,
> RTLに関わらず一定。ミラーリングはしない。
> Itemのラベル文字列は指定に従い、LTR表記あるいはRTL表記で表示するが、base
> directionにかかわらず常に左寄せで表示する。
>
> Readonly Table
> Itemのアイコン(グリフ)やナビゲーショングリフは、常に同一の字形。左右反転などはしない。
>
> 

API Documentation
-------------------

-   オブジェクト名

> ReadOnlyTableRow

-   コンストラクタ　

> $.cscwReadOnlyTableRow (\[options\])
> :表示専用行を生成するコンストラクタ。
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | <br>&lt;div id=”Table1”&gt;<br>&lt;div id=”ReadOnlyTableRow1”&gt;&lt;/div&gt;<br>&lt;/div&gt;<br><br>&lt;div id=”Table2”&gt;<br>&lt;div id=”ReadOnlyTableRow2”&gt;<br>&lt;div id="Text" class=”cscw-tr-widget”&gt;&lt;/div&gt;<br>&lt;/div&gt;<br>&lt;/div&gt;<br><br> |
| Script | <br>$(“#ReadOnlyTableRow1”).cscwReadOnlyTableRow();<br><br>$(“#Text”).cscwText();<br>$(“#ReadOnlyTableRow2”).cscwReadOnlyTableRow();<br><br> |

>※Badgeを付与する場合も、BadgeWidgetをあらかじめ初期化する必要はない。本Widgetの初期化処理の中で生成される。

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| layout | String | <br>"normal"：規定されたレイアウトを適用する。<br>"free"：規定されたレイアウトを利用しない。<br><br> | "normal" |
| label | String /<br>Array /<br>jQueryObject | <br>項目上に配置されるラベル文字列*1 <br>ラベルが２行になる場合は、改行を含む文字列または配列で渡す。<br>単純なテキスト形式で指示できないスタイル混在が必要な場合はjQueryObjectを利用する。<br>jQueryObjectで指示した場合は、truncateオプションは適用されない。<br><br> | null |
| dir | String | <br>ラベル文字列の書き進む方向( text direction)を指定する。<br><br>"global" 表示言語の共通初期設定に従う<br><br>“ltr”：左から右へ書き進む。<br><br>“rtl”：右から左へ書き進む。<br><br> | "global" |
| truncate | String | <br>ラベル長がラベル領域を超過したときの省略描画の適用<br><br>null：超過が起きない場合に使うことを前提とする。超過した場合の挙動は保証しない。<br><br>"end"：ラベルの前方を優先して表示し、エリアを超過した後方を省略表示とする。<br><br>"begin"：ラベルの後方を優先して表示し、エリアを超過した前方を省略表示とする。<br><br> | null |
| autoWrap | Boolean | <br>ラベル長が領域幅を超える場合の折り返しを行うか否か。<br><br>true：自動改行を行う<br><br>false：自動改行を行わない<br><br>truncateで"begin", "middle"を指定した場合はtrueにしてはならない<br><br> | false |
| image | String | 項目に表示するアイコンイメージのパス。 | null |
| glyph | String | 項目に表示するグリフ。 | null |
| navigationGlyph | String | 項目に表示するdisclosureやロックマークなどの付加グリフ。 | null |
| visible | Boolean | falseにすると、TableRowが非表示状態で初期化される | true |
| badge | Object | 付随するバッジの生成パラメータ。 | null |
| reverseTextStyle | Boolean | <br>フォントスタイルを反転させるか。<br><br>true：feedbackTextとLabelのフォントスタイルを反転させる。<br><br>false：feedbackTextとLabelのフォントスタイルを反転させない。<br><br> | false |

> \*1　Array型指定における各配列要素は、改行を含んではならない。
>
> \*2　規定レイアウト利用時に、image、glyphのうちの複数を初期化時に指定した場合は、image
> &gt; glyph の優先度で適用される。

-   badgeで使用するObjectの定義

> Badge　Widgetの項に定義された、コンストラクタオプションに同じ。<br>
> ただし、typeは"tableRow"固定とする。

-   オプション相当情報のMarkupによる指定
> なし

-   関連情報のMarkupによる指定
> コンストラクタをコールする要素の子要素に以下のタグが存在する場合、
> -   div(class=”cscw-tr-borderlessButton”) …ボーダレスボタン
> -   div(class=” cscw-tr-widget ”) …コントロール部品、フィードバックテキスト
>
> としてレイアウトされる。
>
> Freeレイアウトを利用する際に、上記指定は意味を持たない。

-   オプション相当情報のCSSによる指定
> コンストラクタをコールする要素に対して、heightを指定することで、高さを指定することができる。ただし、高さの指定はスタイルガイドからの逸脱を意味するため、以下のケースに限って利用することが望ましい。
>
> ・Freeレイアウトを適用している。
>
> 幅指定機能は持たない。幅の指定は、本Widgetを束ねるTable Widgetから行うこと。
>
> Example:　　\#readOnlyTableRow { width:200px; height:50px;}

-   関連情報のCSSによる指定
> なし
-   LabelオプションにjQueryObjectを指定した場合について

> TableRowの仕様に同じ。

-   メソッド

| .cscwCall(“visible”, visible[, transition]) |   |   |   |
|:------------------------------------------- |:--- |:--- |:--- |
| <br>行の表示/非表示を切り替える。<br><br>Carouselが適用されたTable内部に配置する場合は利用できない。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| visible | Boolean | 行の表示/非表示 |  |
|  |  | true | 表示 |
|  |  | false | 非表示 |
| transition | Boolean | true | <br>transitionを適用する<br><br>省略時はtrueとして扱われる<br><br> |
|  |  | false | transitionを適用しない |

| .cscwCall(“visible”) |   |   |   |
|:-------------------- |:--- |:--- |:--- |
| 行が表示されているかどうかを取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | 行の表示/非表示 |  |
|  |  | true | 表示 |
|  |  | false | 非表示 |

| .cscwCall(“label”, label [, dir])  |   |   |   |
|:---------------------------------- |:--- |:--- |:--- |
| labelを切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| label | String /<br>Array /<br>jQueryObject | - | <br>ラベル文字列<br><br>もしくは文字列を示す配列、jQueryObject<br><br> |
| dir | String | “ltr” | 左から右 |
| dir | String | “rtl” | 右から左 |
|  |  | 省略時 | 現在の書き進む方向のまま。変更しない。 |

| .cscwCall(“label”) |   |   |
|:------------------ |:--- |:--- |
| labelを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String/jQueryObject | <br>表示されているラベル文字列<br><br>もしくは文字列を示すjQueryObject<br><br> |

| .cscwCall(“image”, image) |   |   |   |
|:------------------------- |:--- |:--- |:--- |
| Icon画像のパスを設定する。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **property** | **description** |
| image | String | - | Icon画像のパス |

| .cscwCall(“image”) |   |   |
|:------------------ |:--- |:--- |
| <br>Icon画像の場所を示す文字列を取得する。<br><br>※本メソッドはデバッグ用であり、製品ロジックでの利用は不可とする<br><br> |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | Icon画像のパス |

| .cscwCall(“glyph”, glyph) |   |   |   |
|:------------------------- |:--- |:--- |:--- |
| GlyphのGlyphCodeを設定する。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| glyph | String/Object | - | GlyphCode |

| .cscwCall(“glyph”) |   |   |
|:------------------ |:--- |:--- |
| GlyphのGlyphCodeを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | 表示されているGlyphのGlyphCode |

| .cscwCall(“navigationGlyph”, navigationGlyph)  |   |   |   |
|:---------------------------------------------- |:--- |:--- |:--- |
| navigationGlyphのGlyphCodeを設定する。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **property** | **description** |
| glyph | String | - | GlyphCode |

| .cscwCall(“navigationGlyph”) |   |   |
|:---------------------------- |:--- |:--- |
| navigationGlyphのGlyphCodeを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | 表示されているnavigationGlyphのGlyphCode |

| .cscwCall(“badge”) |   |   |
|:------------------ |:--- |:--- |
| badgeを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | jQueryObject | 付与されているbadgeを示すjQueryObject |

-   イベント

| イベントタイプ |
|:------------- |
| cscwContentsChanged |
| **イベントのトリガ** |
| <br>・行のvisibleの切り替えが行われた。<br><br>※Table　Widgetが受け取ることを想定。これにより、Tableがrefreshされる。<br><br> |