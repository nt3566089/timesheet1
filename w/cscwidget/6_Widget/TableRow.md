[Table Row](../abstractwidgetcontents)
======

機能
---------------------

-   概要

> 操作可能なテーブルロー（Tableの行）

-   機能

> テーブルの中に配置され、1行の表示を行うとともに、操作に応じて表示状態を変更し、イベントを発行する。

-   操作

> タップするとオプションの指定に従い、表示状態を切り替える。Disable状態の場合は操作を受け付けない。

-   音

> コンストラクタで鳴らすことを指定した場合は、操作を受け付けるとvalid音が鳴る。同じく、コンストラクタで鳴らすことを指定した場合は、操作を受け付けない場合にinvalid音が鳴る。

-   表示言語

> トップElementにlang属性を指定することで表示言語を個別に指定することができる。詳細は[<span
> class="underline">3.3.5表示言語の指定</span>](#_表示言語の指定)を参照。

-   レイアウト

> ＜通常の全体レイアウト＞
>
> 以下、Widgetが持つレイアウトを利用した場合の仕様を示す。この仕様に沿わないテーブルローを必要とする場合には、Widgetによる内部レイアウトを行わない指定を行うとともに、アプリケーションから詳細を指示すること。
>
> 以下に例を示す。他のパターンについても、同じルールに従って配置される。
>
> **アイコン/ラベル/固定幅を持つ部品が配置されたテーブルロー**
>
> **アイコン/ラベル/幅が規定されたフィードバック文字列とディスクロージャが配置されたテーブルロー**
>
> **アイコン/ラベル/ディスクロージャが配置され、フリーのフィードバック表示を行うテーブルロー**
>
> **アイコン/ラベル/フィードバックが配置されたテーブルロー**
>
> **ボーダレスボタンが配置されたテーブルロー**
>
> **各種スタイル定義**

| size |   | height | font | Image | <br>Optimized<br><br>Image<br><br> | Glyph | Internal<br>mergin |   |   | Icon left<br>margin |   |   | Icon-label<br>margin |    |   | nav-label<br>margin |   |   |
|:---- |:--- |:------ |:---- |:----- |:---------------------------------- |:----- |:------------------ |:--- |:--- |:----------------- |:--- |:--- |:------------------- |:--- |:--- |:------------------ |:--- |:--- |
| mediuim | 5” |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  | 10” |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| large | 5” |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  | 10” |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |

> ※1　イメージアイコンと並列に使用されることを考慮し、48x48のエリア内でセンタリング表示。
>
> 実際のレイアウト処理は、本Widgetのtruncate指示に依存して異なるものが適用される。アプリケーションが処理の詳細を把握しなければならないケースはさほどないが、フリーフィードバックを用いる場合については、
>
> ・truncate有の場合は、レイアウト図が示すように、フリーフィードバック領域の幅をWidgetが決定する。
>
> ・truncate無の場合は、実際にはWidgetはフィードバック領域の幅を持たないため、アプリケーション任せとなる。
>
> という挙動の違いを把握しておく必要がある。
>
> スタイルについては、基本的にはButtonと同等の定義が適用される。
>
> ただし、selected状態を持つ場合、そのスタイルは、pressedではなくnormalのスタイルが適用される。
>
> テーブルの並び変えを行う場合、移動（ドラッグ）中のアイテムには、pressedのスタイルが適用される。また、並び変え中は、通常状態では下端のボーダーが表示されていないアイテムについても、これを表示するものとする。
>
> 　内部に配置されたWidgetのStatusは、TableRow自体のStatusと連動しない。
>
> 内部に配置されるボーダレスボタンは、基本サイズ（）のみをサポートし、最大5個まで配置可能とする。複数配置する場合は、マークアップ上に記載された順に、右から配置される。
>
> テーブルローには、オプションによりバッジを所定位置に付与することができる。バッジの位置はnavigationGlyphの有無により2パターンのレイアウトが存在する。他の要素がテーブル内右側に存在した場合の位置は不定である。
>
> **バッジが付与されるケース**
>
> **バッジのレイアウト位置（上：navigationGlyphあり　下：navigationGlyphなし）**
>
> **バッジのレイアウト位置（共通）**

| Internal mergin | nav-label margin |
|:--------------- |:---------------- |
|  |  |

> なお、内部にアイコンが配置された、規定スタイルのテーブルローには、オプションによりアイコン用のバッジを所定位置に付与することができる。バッジの位置はSwitchItemウィジェットと同様である。
>
> ＜テーブル様の見た目を実現する場合＞
>
> レイアウトは、基本的にアプリケーションで行うが、セルに対応する要素をつくり、適切なスタイル指定を行うことにより、各カラム内に推奨される値のPaddingが適用できる。Border幅を考慮し、以下のように適用するが、アプリケーションはこれを意識する必要はない。
>
> **テーブル様の見た目を実現するスタイル指定を行った場合に適用されるパディング**

| 条件 | padding-left | padding-right |
|:---- |:------------ |:------------- |
| 左端のセル |  |  |
| 右端のセル |  |  |
| それ以外 |  |  |

> &lt;RTL表記でのレイアウトについて&gt;
>
> TableRow内のアイコン、ラベル、ボタン等のレイアウトはLTR,
> RTLに関わらず一定。ミラーリングはしない。
>
> TableRow のラベル文字列は、指定に従い、rtlあるいはltrで表示するが、base
> directionにかかわらず常に左寄せで表示する。
>
> TableRow のアイコン(グリフ)やナビゲーショングリフは、常に同一の字形。左右反転などはしない。(
> 項目の詳細画面が開くことを示す”＞”の形をしたnavigate\_rightグリフは、RTL表記であっても同じ”＞”の形。また、その詳細画面が右から滑り出てくる動きはRTL表記であっても同じく画面右から滑り出る。)

-   制限事項

> 本Widgetは、コンテナ色gray　の上に配置された場合は、本節記載の全ての機能/使い方　に対応しているが、他のコンテナ色の上に配置された場合は、TableRow上へのToggleSwitchおよびSwitchItemの配置に対応していない。
>
> Gray, colorおよび以外のコンテナ色には対応していない。

API Documentation
---------------------

-   オブジェクト名

> TableRow

-   コンストラクタ

> $.cscwTableRow (\[options\])
> :操作可能なテーブル項目を生成するコンストラクタ。
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | <br>&lt;div id=”Table1”&gt;<br>&lt;div id=”TableRow1”&gt;&lt;/div&gt;<br>&lt;/div&gt;<br><br>&lt;div id=”Table2”&gt;<br>&lt;div id=”TableRow2”&gt;<br>&lt;div id=”Button” class=”cscw-tr-borderlessButton”&gt;&lt;/div&gt;<br>&lt;/div&gt;<br>&lt;/div&gt;<br><br>&lt;div id = “Table3”&gt;<br>&lt;div id=”TableRow3”&gt;<br>&lt;div id=”Text” class=”cscw-tr-widget”&gt;&lt;/div&gt;<br>&lt;/div&gt;<br>&lt;/div&gt;<br><br>&lt;div id=”Table4”&gt;<br>&lt;div id=”TableRow4”&gt;<br>&lt;div id=”Toggle” class=”cscw-tr-toggleSwitch”&gt;&lt;/div&gt;<br>&lt;/div&gt;<br>&lt;/div&gt;<br><br> |
| Script | <br>$(“#TableRow1”).cscwTableRow();<br><br>$(“#Button”).cscwButton();<br>$(“#TableRow2”).cscwTableRow();<br><br>$(“#Text”).cscwText();<br>$(“#TableRow3”).cscwTableRow();<br><br>$(“#Toggle”).cscwToggleSwitch();<br>$(“#TableRow4”).cscwTableRow();<br><br> |

> ※Badgeを付与する場合も、BadgeWidgetをあらかじめ初期化する必要はない。本Widgetの
>
> 初期化処理の中で生成される。

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| layout | String | <br>normal　規定されたレイアウトを適用する。<br><br>free　規定されたレイアウトを利用しない。<br><br> | normal |
| label | String/Array(String)<br>jQueryObject | <br>項目上に表示するラベル文字列*1。単純なテキスト形式で指示できないスタイル混在が必要な場合はjQueryObjectを利用する。jQueryObjectで指示した場合は、truncateオプションは適用されない。<br><br> | null |
| dir | String | <br>ラベル文字列の書き進む方向( text direction)を指定する。<br><br>“ltr” 左から右へ書き進む。<br><br>“rtl” 右から左へ書き進む。<br><br> | CSCWidget<br>のデフォル<br>ト設定 |
| truncate | String | <br>ラベル長がラベル領域を超過したときの省略描画の適用<br><br>null　超過が起きない場合に使うことを前提とする。超過した場合の挙動は保証しない。<br><br>end　ラベルの前方を優先して表示し、エリアを超過した後方を省略表示とする。<br><br>begin　ラベルの後方を優先して表示し、エリアを超過した前方を省略表示とする。<br><br> | null |
| autoWrap | Boolean | <br>ラベル長が領域幅を超える場合の折り返しを行うか否か。<br><br>true：自動改行を行う<br><br>false：自動改行を行わない<br><br>truncateで"begin", "middle"を指定した場合はtrueにしてはならない<br><br> | false |
| image | String | 項目に表示するアイコンイメージのパス。 | null |
| glyph | String | 項目に表示するグリフ。 | null |
| glyphColor | Object | <br>特殊な用途に見合ったフォントスタイル(colorおよびshadow)を付与する<br><br>font-color-primary<br><br>font-color-secondary<br><br>font-color-tertiary<br><br>font-color-ready<br><br>font-color-alert<br><br>font-color-warning<br><br>font-color-selected<br><br>nullが指定されると特殊なフォントスタイルは解除される<br><br>glyph指定がない状態で指定するとエラーになる<br><br> | <br>null<br><br>特殊スタイルは適用されず、親要素の設定に従う。<br><br> |
| navigationGlyph | String | <br>項目に表示するdisclosureやロックマークなどの付加グリフ。<br><br> | null |
| status | String | <br>on　On状態<br><br>off　Off状態<br><br> | off |
| enable | Boolean | falseにするとDisable状態となり、操作を受け付けない。 | true |
| visible | Boolean | falseにすると、非表示状態で初期化される | true |
| badge | Object | 付随するバッジの⽣成パラメータ。 | null |
| reverseTextStyle | Boolean | <br>フォントスタイルが反転するかどうかを判別する。<br><br>true:　feedbackTextとLabelのフォントスタイルが反転する。<br><br>false:　feedbackTextとLabelのフォントスタイルが反転しない。<br><br> | false |

> \*1　String型およびObject型指定における各プロパティ(String型)による指定値は、改行を含んではならない。
>
> \*2　規定レイアウト利用時にimage、glyphの両方を初期化時に指定した場合は、
> image &gt; glyph の優先度で適用される。


-   badgeで使用するObjectの定義

> Badge　Widgetの項に定義された、コンストラクタオプションに同じ。
>
> ただし、typeは"tableRow"固定とする。

-   オプション相当情報のMarkupによる指定

> なし

-   関連情報のMarkupによる指定

> コンストラクタをコールする要素の子要素に以下のタグが存在する場合、

-   div(class=”cscw-tr-widget”)
    …固定幅を持つ部品、および幅が指定可能なラベルや&lt;div&gt;要素

-   div(class=”cscw-tr-borderlessButton”) …ボーダレスボタン

-   div(class=”cscw-tr-toggleSwitch”) …トグルスイッチ

-   div(class=”cscw-li-free”) …その他汎用フィードバック表示　

> としてレイアウトされる。
>
> Freeレイアウトを利用する際に、上記指定は意味を持たない。

-   オプション相当情報のCSSによる指定

> コンストラクタをコールする要素に対して、heightを指定することで、高さを指定することができる。ただし、高さの指定はスタイルガイドからの逸脱を意味することもあり、Freeレイアウトに限定する。Normalレイアウトの場合は、heightを指定できない。
>
> 幅指定機能は持たない。幅の指定は、本Widgetを束ねるTable
> Widgetから行うこと。
>
> Example:　　\#tablerow1{height:50px;}

-   関連情報のCSSによる指定

> 複数のTableRowを、同じカラム幅で分割したスタイルを実現したい場合（テーブル様の見た目を実現したい場合）は、Freeレイアウトを適用する。このとき、各カラム（セル）に対応する要素はアプリケーションが用意するとともに、最低限以下の指定が必要となる。ここで、全てのセルのwidthを合計した値は、TableRow自体のwidthよりも2px（border相当分）小さい値とする必要がある。

left：左端からのpx値。つまり該セルより左にあるセルのwidthを合計した値。左端のセルは0。

width：それぞれのセルの幅。

なお、該要素にclass=” cscw-li-cell”
を適用することで、スタイルガイドに準拠したパディングが適用される。

-   labelオプションにjQueryObjectを指定した場合について

> jQueryObjectに含まれるテキスト要素については、デフォルトではlabelを文字列で指定した時と同等のスタイルが適用される。なお、デフォルトではwhite-space: nowrap となるため、自動折り返しが必要な場合には、widthの指定とともに、white-space：normal、および他の適切なcssを適宜利用すること。

-   規定レイアウトを適用しない場合（Free）について

<!-- -->

-   TableRowの一部として配置されるもの（ラベル、アイコンなど）および、TableRow上に配置されるパーツ（ボーダレスボタンなど）に全ての要素に対して規定レイアウトが適用されないため、アプリケーションから適切なcssにて規定する必要がある。

-   通常は、レイアウト規定によりイメージアイコン、グリフアイコンの共存はできないが、規定レイアウトを適用しない場合は、複数の要素をボタン内に配置することも可能となる。

-   TableRow自体の色彩については、statusおよびenableの変化に伴う見た目の変化を含めて、Widgetから提供される。これを変更したい場合は、適宜cssにて上書きすることで対応できる。

-   TableRowの高さ、ラベル・グリフアイコン・フィードバック文字列に適用されるフォントサイズ、イメージアイコンのサイズ、については、デフォルト値がそのまま適用される。変更を必要とする場合は、アプリケーションから適宜cssで上書きすることで対応できる。

-   規定レイアウトに含まれるラベル、グリフ、の色については、それらを示すMarkupで表されている（適切なタグとクラスが適用されている）ものはTableRowの管理下に入り、statusおよびenableの変化に伴う追従機能を含めて、Widgetから提供される。これを変更したい場合は、適宜cssにて上書きすることで対応できる。

-   規定レイアウトに含まれる、イメージアイコンについては、”関連情報のMarkupによる指定“に合致する場合のみ、TableRowの管理下に入り、statusおよびenableの変化に伴う追従機能がWidgetから提供される。これを変更したい場合、および、管理下に入っていないアイコンの見た目を変更したい場合は、適宜cssにて上書きすることで対応できる。

-   規定レイアウトに含まれる、ラベル、アイコンに相当するものを使用した場合、初期化後のTableRowでは、ラベル：cscw-tr-label、アイコン：cscw-tr-icon　のクラスが付与される。ラベル、アイコンおよびその構成要素に対してスタイルの上書きを利用する際には、該クラスが利用できる。

-   メソッド

| .cscwCall(“status”, status) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| TableRowの状態を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | TableRowの状態 |  |
|  |  | on | On状態 |
|  |  | off | Off状態 |

| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| TableRowの状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | TableRowの状態 |  |
|  |  | on | On状態 |
|  |  | off | Off状態 |

| .cscwCall(“enable”, enable) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| TableRowの有効/無効を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| enable | Boolean | TableRowの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“enable”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| TableRowが有効かどうかを取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | TableRowの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“visible”, visible[, transition]) |   |   |   |
|:------------------------------------------- |:--- |:--- |:--- |
| <br>TableRowの表示/非表示を切り替える。<br><br>Carouselが適用されたTable内部に配置する場合は利用できない。<br><br> |  |  |   |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| visible | Boolean | TableRowの表示/非表示  |  |
|  |  | true | 表示 |
|  |  | false | 非表示 |
| transition | Boolean | transitionの適用有無 |  |
|  |  | true | <br>transitionを適用する<br><br>省略時はtrueとして扱われる |
|  |  | false | transitionを適用しない |

| .cscwCall(“visible”) |   |   |   |
|:-------------------- |:--- |:--- |:--- |
| TableRowが表示されているかどうかを取得する。 |  |  |
|  | **type** | **description** |  |
|  | Boolean | TableRowの表示/非表示 |  |
|  |  | true | 表示 |
|  |  | false | 非表示 |

| .cscwCall(“label”, label [, dir]) |   |   |   |
|:---------------------------------- |:--- |:--- |:--- |
| labelを切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| label | String /<br>Array /<br>jQueryObject | - | label文字列もしくは文字列を示す配列及びjQueryObject |
| dir | String | 文字の書き進む方向。省略時は現在の書き進む方向のまま変更しない。 |  |
|  |  | “ltr” | 左から右に書き進む |
|  |  | “rtl” | 右から左に書き進む |

| .cscwCall(“label”) |   |   |
|:------------------ |:--- |:--- |
| labelを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String /<br>Array /<br>jQueryObject | label文字列もしくは文字列を示す配列及びjQueryObject |

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
|  | **String** | **アイコンの画像** |


| .cscwCall(“glyph”, glyph) |   |   |   |
|:------------------------- |:--- |:--- |:--- |
| GlyphのGlyphCodeを設定する。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| glyph | String | - | GlyphCode<br><br> |

| .cscwCall(“glyph”) |   |   |
|:------------------ |:--- |:--- |
| GlyphのGlyphCodeを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | 表示されているGlyphのGlyphCode<br><br> |


| .cscwCall("glyphColor", glyphColor) |   |   |   |
|:------------------------- |:--- |:--- |:--- |
| glyphColorを設定する。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| glyphColor | String | - | glyphColor |

| .cscwCall("glyphColor") |   |   |
|:------------------ |:--- |:--- |
| glyphColorを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | 表示されているglyphColor |

| .cscwCall(“navigationGlyph”, navigationGlyph) |   |   |   |
|:---------------------------------------------- |:--- |:--- |:--- |
| navigationGlyphのGlyphCodeを設定する。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **property** | **description** |
| navigationGlyph | String | - | GlyphCode<br><br> |

| .cscwCall(“navigationGlyph”) |   |   |   |
|:---------------------------- |:--- |:--- |:--- |
| navigationGlyphのコードを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | 表示されているnavigationGlyphのGlyphCode<br><br> |

| .cscwCall(“interactive”, interactive) |   |   |   |
|:------------------------------------- |:--- |:--- |:--- |
| <br>TableRowがタップ操作を受け付けるか否かを設定する。<br><br>本メソッドは、一次的にタップ操作を無視する必要がある場合に利用する。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| interactive | Boolean | タップ操作の受け付け可否 |  |
|  |  | true | 有効 |
|  |  | false | 無効 |

| .cscwCall(“interactive”) |   |   |   |
|:------------------------ |:--- |:--- |:--- |
| TableRowがタップ操作を受け付けるか否かの設定を取得する。 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | TableRowの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効 |

-   イベント

| イベントタイプ |
|:------------- |
| cscwTap |
| **イベントのトリガ** |
| <br>TableRow、およびその上に置かれた部品がタップされた時に発生。<br><br>targetプロパティの指す要素は<br><br>- TableRow上に置かれたタップ可能な部品がタップされたときは該部品<br><br>- 上記以外の領域がタップされたときは、TableRow自身<br><br>となる |

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwChanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |
| 項目の状態が変わった時に発生 |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | status | String | ボタンの状態 |  |
|  |  |  | on | On状態 |
|  |  |  | off | Off状態 |

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwContentsChanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| TableRowのvisibleの切り替えが行われた時に発生<br><br>※Table　Widgetが受け取ることを想定。これにより、Tableがrefreshされる。 |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | visible | Boolean | TableRowの状態 |  |
|  |  |  | true | 表示状態 |
|  |  |  | false | 非表示状態 |