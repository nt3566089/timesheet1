[Grid Item](../abstractwidgetcontents)
======

機能
---------------------

-   概要

> 操作可能なグリッドアイテム（Gridの行）

-   機能

> グリッドの中に配置され、セルの表示を行うとともに、操作に応じて表示状態を変更し、イベントを発行する。

-   操作

> タップするとオプションの指定に従い、表示状態を切り替える。Disable状態の場合は操作を受け付けない。

-   音

> コンストラクタで鳴らすことを指定した場合は、操作を受け付けるとvalid音が鳴る。同じく、コンストラクタで鳴らすことを指定した場合は、操作を受け付けない場合にinvalid音が鳴る。

-   レイアウト

> ＜通常の全体レイアウト＞
>
> 以下、Widgetが持つレイアウトを利用した場合の仕様を示す。この仕様に沿わないグリッドアイテムを必要とする場合には、Widgetによる内部レイアウトを行わない指定を行うとともに、アプリケーションから詳細を指示すること。
>
> 以下に例を示す。他のパターンについても、同じルールに従って配置される。
>
> **アイコン/ラベル/固定幅を持つ部品が配置されたリストアイテム**
>
> **アイコン/ラベル/フィードバックが配置されたグリッドアイテム**
>
> **各種スタイル定義**

|   | height | font | Image | <br>Optimized<br><br>Image<br><br> | Glyph | Internal mergin |Icon left | margin | Icon-label margin |
|:--- |:------ |:---- |:----- |:---------------------------------- |:----- |:--------------- |:-------- |:----- |:----------------- |
| 5” |  |  |  |  |  |  |  |  |  |
| 10” |  |  |  |  |  |  |  |  |  |

> ※1　イメージアイコンと並列に使用されることを考慮し、のエリア内でセンタリング表示。
>
> 実際のレイアウト処理は、本Widgetのtruncate指示に依存して異なるものが適用される。ア��リケーションが処理の詳細を把握しなければならないケースはさほどないが、フリーフィードバックを用いる場合については、
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
> 　内部に配置されたWidgetのStatusは、GridItem自体のStatusと連動しない。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> Interactive Grid Item内のアイコン、ラベル、ボタン等のレイアウトはLTR,
> RTLに関わらず一定。ミラーリングはしない。
>
> Interactive Grid
> Itemのラベル文字列は、指定に従い、rtlあるいはltrで表示するが、base
> directionにかかわらず常に左寄せで表示する。

-   制限事項

> 本Widgetは、コンテナ色gray　の上に配置された場合は、本節記載の全ての機能/使い方　に対応しているが、他のコンテナ色の上に配置された場合は、GridItem上へのToggleSwitchおよびSwitchItemの配置に対応していない。
>
> Gray, colorおよび以外のコンテナ色には対応していない。

API Documentation
---------------------

-   オブジェクト名

> GridItem

-   コンストラクタ

> $.cscwInteractiveGridItem (\[options\])
> :操作可能なGrid項目を生成するコンストラクタ。
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | <br>&lt;div id=”Grid”&gt;<br>&lt;div id=”GridItem”&gt;<br>&lt;div id=”Button”&gt;&lt;/div&gt;<br>&lt;/div&gt;<br>&lt;/div&gt;<br><br> |
| Script | <br>$(“#Button”).cscwButton();<br>$(“#GridItem”).cscwInteractiveGridItem();<br>$(“#Grid”).cscwGrid();<br><br> |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description	| Default |
|:-------- |:---- |:----------- |:------- |
| layout | String | <br>下記以外の値を指定しないこと<br><br>"normal"：規定されたレイアウトを適用する。<br><br>"free"：規定されたレイアウトを利用しない。<br><br> | "normal" |
| label | <br>String/<br>Array/<br>jQueryObject<br><br> | <br>項目上に表示するlabel文字列<br><br>タイトルが２行になる場合は、改行を含む文字列または配列で渡す*1。<br><br>単純なテキスト形式で指示できないスタイル混在が必要な場合はjQueryObjectを利用する。jQueryObjectで指示した場合は、truncateオプションは適用されない。<br><br> | null |
| dir | String | <br>label文字列の書き進む方向( text direction)を指定する。<br><br>下記以外の値を指定しないこと<br><br>"global"：表示言語の共通初期設定に従う<br><br>“ltr”：左から右へ書き進む。<br><br>“rtl”：右から左へ書き進む。<br><br> | CSCWidgetのデフォルト設定 |
| truncate | String | <br>label長がlabel領域を超過したときの省略描画の適用<br><br>下記以外の値を指定しないこと<br><br>null：超過が起きない場合に使うことを前提とする。超過した場合の挙動は保証しない。<br><br>"end"：labelの前方を優先して表示し、エリアを超過した後方を省略表示とする。<br><br>"middle"：⽂字列の中央を省略表⽰する<br><br>"begin"：labelの後方を優先して表示し、エリアを超過した前方を省略表示とする。<br><br> | null |
| autoWrap | Boolean | <br>テキスト長が領域幅を超える場合の折り返しを行うか否か。<br><br>true：自動改行を行う<br><br>false：自動改行を行わない<br><br>truncateで"begin", "middle"を指定した場合はtrueにしてはならない<br><br> | false |
| image | String | <br>項目に表示するアイコンイメージのパス*2<br><br> | null |
| glyph | String | <br>項目に表示するグリフ*2<br><br> | null |
| status | String | <br>下記以外の値を指定しないこと<br><br>"on"：On状態<br><br>"off"：Off状態<br><br> | off |
| enable | Boolean | <br>GridItemの使用可不可<br><br>true：使用可能<br><br>false ：使用不可能(Disable状態)<br><br>null指定時はfalse指定の振る舞いとなる<br><br> | true |
| soundEnable | Boolean | <br>Widgetによる操作音(valid音)の鳴動制御<br><br>true：操作音を鳴らす<br><br>false：操作音を鳴らさない<br><br> | true |
| invalidSoundEnable | Boolean | <br>Widgetによる操作音(invalid音)の鳴動制御<br><br>true：操作音を鳴らす<br><br>false：操作音を鳴らさない<br><br> | true |

> \*1　String型指定時は複数の改行を含んではならない。また、Array型指定時における各配列要素は、改行を含んではならない。
>
> \*2　規定レイアウト利用時に、image、glyphのうちの複数を初期化時に指定した場合は、image
> &gt;  glyph の優先度で適用される。

-   オプション相当情報のMarkupによる指定

> サポートしない

-   関連情報のMarkupによる指定

> コンストラクタをコールする要素の子要素に以下のタグが存在する場合、

-   div(class=”cscw-gi-widget”)
    …固定幅を持つ部品、および幅が指定可能なlabelや&lt;div&gt;要素

-   div(class=”cscw-gi-free”) …その他汎用フィードバック表示　

> としてレイアウトされる。
>
> Freeレイアウトを利用する際に、上記指定は意味を持たない。

-   オプション相当情報のCSSによる指定

> サポートしない

-   labelオプションにjQueryObjectを指定した場合について

> jQueryObjectに含まれるテキスト要素については、デフォルトではlabelを文字列で指定した時と同等のスタイルが適用される。なお、デフォルトではwhite-space:
> nowrap　となるため、自動折り返しが必要な場合には、widthの指定とともに、white-space：normal、および他の適切なcssを適宜利用すること。

-   規定レイアウトを適用しない場合（Free）について

<!-- -->

> -   GridItemの一部として配置されるもの（label、アイコンなど）および、GridItem上に配置されるパーツに全ての要素に対して規定レイアウトが適用されないため、アプリケーションから適切なcssにて規定する必要がある。
>
> -   GridItem自体の色彩については、statusおよびenableの変化に伴う見た目の変化を含めて、Widgetから提供される。これを変更したい場合は、適宜cssにて上書きすることで対応できる。
>
> -   GridItemの高さ、label・グリフアイコン・フィードバック文字列に適用されるフォントサイズ、イメージアイコンのサイズ、については、デフォルト値がそのまま適用される。変更を必要とする場合は、アプリケーションから適宜cssで上書きすることで対応できる。ただし高さはコンストラクタパラメータで指定する必要がある。
>
> -   規定レイアウトに含まれるlabel、グリフ、の色については、statusおよびenableの変化に伴う追従機能を含めて、Widgetから提供される。これを変更したい場合は、適宜cssにて上書きすることで対応できる。
>
> -   規定レイアウトに含まれるイメージアイコンについては、statusおよびenableの変化に伴う追従機能がWidgetから提供される。これを変更したい場合および管理下に入っていないアイコンの見た目を変更したい場合は、適宜cssにて上書きすることで対応できる。
>
> -   規定レイアウトに含まれる、label、アイコンに相当するものを使用した場合、初期化後のGridItemでは、label：cscw-gi-label、アイコン：cscw-gi-icon　のクラスが付与される。label、アイコンおよびその構成要素に対してスタイルの上書きを利用する際には、該クラスが利用できる。

<!-- -->

-   メソッド

| .cscwCall(“status”, status) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| GridItemの状態を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | GridItemの状態 |  |
|  |  | on | On状態 |
|  |  | off | Off状態 |

| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| GridItemの状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
| status | String | GridItemの状態 |  |
|  |  | on | On状態 |
|  |  | off | Off状態 |

| .cscwCall(“enable”, enable) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| GridItemの有効/無効を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| enable | Boolean | GridItemの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“enable”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| GridItemが有効かどうかを取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | GridItemの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“label”, label [, dir]) |   |   |   |
|:--------------------------------- |:--- |:--- |:--- |
| labelを切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| label | String/<br>Array/<br>jQueryObject | <br>label文字列<br><br>もしくは文字列を示す配列およびjQueryObject<br><br> |  |
| dir | String | label文字列の書き進む方向( text direction)を指定する |  |
|  |  | “ltr” | 右から左 |
|  |  | “rtl” | 右から左 |
|  |  | 省略時 | 現在の書き進む方向のまま。変更しない。 |

| .cscwCall(“label”) |   |   |
|:------------------ |:--- |:--- |
| labelを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String/<br>Array/<br>jQueryObject | <br>表示されているlabel文字列<br><br>もしくは文字列を示す配列およびjQueryObject<br><br> |

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
| GlyphCodeを設定する。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **property** | **description** |
| glyph | String | - | GlyphCode |

| .cscwCall(“glyph”) |   |   |
|:------------------ |:--- |:--- |
| GlyphCodeを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | 表示されているGlyphCode |

| .cscwCall(“interactive”, interactive) |   |   |   |
|:------------------------------------- |:--- |:--- |:--- |
| <br>GridItemがタップ操作を受け付けるか否かを設定する。<br><br>本メソッドは、一次的にタップ操作を無視する必要がある場合に利用する。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| interactive | Boolean | タップ操作の受け付け可否 |  |
|  |  | true | 有効 |
|  |  | false | 無効 |

| .cscwCall(“interactive”) |   |   |   |
|:------------------------ |:--- |:--- |:--- |
| GridItemがタップ操作を受け付けるか否かの設定を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | GridItemの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効 |

-   イベント

| イベントタイプ |
|:------------- |
| cscwTap |
| **イベントのトリガ** |
| <br>GridItem、およびその上に置かれた部品がタップされた時に発生。<br><br>targetプロパティの指す要素は<br><br>- GridItem上に置かれたタップ可能な部品がタップされたときは該部品<br><br>- 上記以外の領域がタップされたときは、GridItem自身<br><br>となる<br><br> |

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwChanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | status | String | ボタンの状態 |  |
|  |  |  | on | On状態 |
|  |  |  | off | Off状態 |