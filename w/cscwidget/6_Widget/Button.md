[Button](../abstractwidgetcontents)
======

機能
------

-   概要

> コマンドボタンなどの各種ボタン

-   機能

> ボタンを表示し、操作に応じて表示状態を変更するとともに、イベントを発行する。

-   操作

> タップするとオプションの指定に従い、表示状態を切り替える。Disable状態の場合は操作を受け付けない。

-   音

> コンストラクタで鳴らすことを指定した場合は、操作を受け付けるとvalid音が鳴る。同じくコンストラクタで鳴らすことを指定した場合は、操作を受け付けない場合にinvalid音が鳴る。

-   レイアウト

> 以下、Widgetが持つレイアウトを利用した場合の仕様を示す。この仕様に沿わないボタンを必要とする場合には、Widgetによる内部レイアウトを行わない指定を行うとともに、アプリケーションから詳細を指示すること。
>
> Buttonは、ボタンを視覚的に表す角丸の矩形領域とそこに配置されたアイコン
> and/or
> ラベルからなる。オプションにより、Badgeを付与することもできる。
>
> **全体レイアウト**
>
> 　Buttonの矩形内、およびBadgeの配置は、生成時に指定するサイズ(small/medium/large)と、オプション指定から、次のように定まる。
>
> **左寄せbadge付きで、アイコンとラベルを持つボタンのレイアウト**
>
> **中央揃えbadgeなしで、ラベルのみを持つボタンとアイコンのみを持つボタンのレイアウト**

各種スタイル定義（上段：5inch/下段：10inch）

| size | height | Font | Glyph | image | <br>min<br><br>width<br><br> | min　padding | width | R | Icon left margin | Icon-label margin |
|:---- |:------ |:---- |:----- |:----- |:---------------------------- |:------------ |:----- |:--- |:---------------- |:----------------- |
| small |  |  |  |  |  |  | アプリ指定*1 |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
| medium<br>(default) |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
| large |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |

\*1　 autoの場合はpaddingのミニマム値が適用された結果として決定される。

> Border widthはtheme、styleに依存して、0～2pxのいずれかとなる。
>
> その他、色に関する属性が、Application theme、Container theme
> に応じて、ボタンのstateごとに定義される。
>
> 詳細は、スタイルガイドの指定を参照のこと。
>
> <span class="underline">＜アイコン（image）＞</span>　
>
> アイコン画像は、先に示したボタンのサイズに対応した画素サイズを利用することを推奨する。アイコンには、共通仕様に従った白枠が付与される。なお、ボタンがDisable表示の時、アイコンは白枠も含めてopacity
> にて表示される。
>
> <span class="underline">＜グリフ＞</span>
>
> グリフは、表1に示すサイズに対応したサイズで描画される。Stateによる見た目の変化は、labelと同じものが適用される。
>
> <span class="underline">＜ラベル＞</span>
>
> buttonには、任意の文字列をラベルとして指定できる。
>
> 文字列は、1行固定表示とし、自動改行や改行指定はサポートしない。
>
> 指定されたwidthから算出されるラベル幅に、文字列が表示しきれない場合、あるいは、widthがauto指定であり、maxWidthまでボタンを伸長しても割り当てられた幅に文字列が収まらない場合は、ボタンは文字列の末尾を切縮めてellipsis(省略符号)に置き換えることでラベルに割り当てられた幅に収める処理を行うことも可能である。
>
> <span class="underline">＜Badge＞</span>
>
> Badgeの位置はボタンのサイズにかかわらず常に一定。Buttonは、badgeをボタンの矩形領域の右上隅から上と右に外側の位置をbadgeの右上隅に揃え、枠線、アイコン、ラベルを覆う位置に配置する。
>
> Badgeは、動的に追加・削除できる。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> Buttonは指定に従い、ラベル文字表記をltrあるいはrtlで表記する。
> ラベル文字列の寄せ方向は、LTR/RTL表記に関わらず一定。
>
> iconに使われるグリフは、RTL表記であっても、ltrで表示する。変更しない。
>
> ミラーリングをしないのでRTL表記であっても、バッジの位置、アイコンとラベルを並置する場合の位置関係、ラベル文字列の寄せ方向はLTR表記の場合と同じ。変更しない。

API Documentation
------

-   オブジェクト名

> button

-   コンストラクタ

> $.cscwButton(\[options\]) :ボタンを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”button” &gt;&lt;/div&gt; |
| Script | $(“#button”).cscwButton(); |

> ※Badgeを付与する場合も、BadgeWidgetをあらかじめ初期化する必要はない。本Widgetの
>
> 初期化処理の中で生成される。

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| layout | String | <br>"normal"　規定されたレイアウトを利用する<br><br>"free"　規定されたレイアウトを利用しない<br><br>"vertical"　グリフ、ラベルが縦並びになるレイアウトを指定する<br><br> | "normal" |
| size | String | <br>ボタンのサイズ<br><br>"small"<br><br>"medium"<br><br>"large"<br><br>ただし、layout 指定が"free"の場合は無効<br><br> | "medium" |
| style | String | <br>ボタンのスタイル<br><br>"normal"　通常のスタイル<br><br>"transparent"　背景色なしのスタイル<br><br>"positive"　背景色が緑色のスタイル<br><br>"negative"　背景色が赤色のスタイル<br><br> | "normal" |
| align | String | <br>"normal" レイアウトにおけるボタン内のグリフ、ラベル文字列の配置<br><br>"auto"　Style Guideの既定に従う<br><br>"left"　左寄せ<br><br>"center"　センタリング<br><br> | "auto" |
| action | String | <br>ボタンの動作種類<br><br>"normal" 通常のコマンドボタン<br><br>"toggle"　On/Offがトグルで切り替わるボタン<br><br>"none" Widget規定の動作を利用しない<br><br> | "normal" |
| width | Integer/String | <br>ボタンの幅<br><br>数値（pixel）　固定幅<br><br>"auto" ⽂字列⻑に応じて伸縮<br><br>指定ない場合はcss指定もしくは内部のミニマム値を利用<br><br>layout 指定が"free"の場合、"auto"は無効<br><br> | null |
| maxWidth | Integer | <br>ボタンの最大幅(pixel)<br><br>文字列長に応じて伸縮可能な最大値<br><br> | null |
| label | <br>String/<br>Array/<br>jQueryObject/<br><br> | <br>ボタン上に表示するラベル文字列。<br>ラベルが２行になる場合は、配列または改行を含む文字列で渡す。*1<br>単純なテキスト形式で指示できないスタイル混在が必要な場合はjQueryObjectを利用する。<br>jQueryObjectで指示した場合は、truncateオプションは適用されない。<br><br> | null |
| dir | String | <br>ラベル文字列の書き進む方向(text direction)を指定する。<br><br>"global" 表示言語の共通初期設定に従う<br><br>"ltr" 左から右へ書き進む<br><br>"rtl" 右から左へ書き進む<br><br> | "global" |
| truncate | String | <br>テキスト長が、領域幅を超過したときの省略描画の適用<br><br>null　超過が起きない場合に使うことを前提とし、超過した場合の挙動は保証しない<br><br>"end"　⽂字列後⽅を省略表⽰する<br><br>"middle"　⽂字列の中央を省略表⽰する<br><br> "begin"　⽂字列前⽅を省略表⽰する<br><br> | null |
| autoWrap | Boolean | テキスト長が領域幅を超える場合の折り返しを行うか否か。<br><br>truncateで"begin", "middle"を指定した場合はtrueにしてはならない | <br>false<br><br> |
| image | String | <br>ボタン上に表示するアイコン画像を示すパス。*2<br><br> | null |
| glyph | String | <br>ボタン上に表示するGlyphコード。*2<br><br> | null |
| glyphColor | Object | <br>ボタン上のGlyphの色を指定する<br><br>※指定できる値については[Text] 特殊フォントスタイル名の項を参照 | <br>null<br><br>特殊スタイルは適用されず、親要素の設定に従う。<br><br> |
| status | String | <br>on　On状態<br><br>off　Off状態<br><br> | off |
| enable | Boolean | falseにするとDisable状態となり、操作を受け付けない。 | true |
| badge | Object | 付随するバッジの生成パラメータ。 | null |
| soundEnable | Boolean | <br>Widgetによる操作音(valid音)の鳴動制御<br><br>true 操作音を鳴らす<br><br>false 操作音を鳴らさない<br><br> | true |
| invalidSoundEnable | Boolean | <br>Widgetによる操作音(invalid音)の鳴動制御<br><br>true 操作音を鳴らす<br><br>false 操作音を鳴らさない<br><br> | true |
\*1　
String型指定時は複数の改行を含んではならない。また、Array型指定時における各配列要素は、改行を含んではならない。<br>
\*2　規定レイアウト利用時に、image、glyphのうちの複数を初期化時に指定した場合は、image
&gt; glyph
の優先度で適用される。後述するメソッドにより、imageもしくはglyphが初期化後に指定された場合は、後から指定されたものを有効として表示する。

-   badgeで使用するObjectの定義

> badge　Widgetの項に定義された、コンストラクタオプションに同じ。
>
> ただしtypeは"button","icon"を用いることを想定している。

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> コンストラクタをコールする要素に対して、widthとheightを指定することで、サイズ固定のボタンとして扱われる。タッチマージンは付与されない。また、heightの指定は、スタイルガイドからの逸脱を意味するため、Freeレイアウト適用時のみ有効とする。
>
> Example：　\#button { width:200px; height:50px;}

-   LabelオプションにjQueryObjectを指定した場合について

> jQueryObjectに含まれるテキスト要素については、デフォルトではlabelを文字列で指定した時と同等のスタイルが適用される。これより、デフォルトではwhite-space:
> nowrap　となるため、自動折り返しが必要な場合には、widthの指定とともに、white-space：normal、および他の適切なcssを適宜利用すること。

-   規定レイアウトを適用しない場合について

<!-- -->

-   sizeオプションが無効となるため、ボタンの高さおよびフォントサイズがWidget内部で決定されない。アプリケーションから適切なcssにて規定する必要がある。

-   ボタン内に配置されるもの（ラベル、アイコンなど）は制限されず、他のアイテムも配置することができる。

-   通常は、レイアウト規定によりイメージアイコン、グリフアイコンの共存はできないが、規定レイアウトを適用しない場合は、複数の要素をボタン内に配置することも可能となる。

-   ボタン自体の色彩については、statusおよびenableの変化に伴う見た目の変化を含めて、Widgetから提供される。これを変更したい場合は、適宜cssにて上書きすることで対応できる。

-   規定レイアウトに含まれる、ラベル、イメージアイコン、グリフ、の色については、それらを示すMarkupで表されている（適切なタグとクラスが適用されている）ものについては、statusおよびenableの変化に伴う追従機能を含めて、Widgetから提供される。これを変更したい場合は、適宜cssにて上書きすることで対応できる。

<!-- -->

-   規定動作を適用しない場合について

> プレス時の見た目の変化は起きるが、その後もとの状態に戻る。状態変更は、メソッドを用いてアプリケーションから指示する必要がある。

-   メソッド

| .cscwCall(“width”, width)　 |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| ボタン幅を変更する。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| width | String/Integer | ボタンの幅 |   |
|  |  | auto | 文字列長に合わせたボタン幅  |
|  |  | 数値 | ボタン幅（px） |

| .cscwCall(“width”)　 |   |   |   |
|:-------------------- |:--- |:--- |:--- |
| ボタンの幅指定を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String/Integer | ボタンの幅 |   |
|  |  | auto | ボタン幅は文字列長から算出されている  |
|  |  | 数値 | 現在指示されているボタン幅（px） |

| .cscwCall(“status”, status) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| ボタンの状態を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | ボタンの状態 |   |
|  |  | on | On状態  |
|  |  | off | Off状態 |

| .cscwCall(“status”)　 |   |   |   |
|:--------------------- |:--- |:--- |:--- |
| ボタンの状態を取得する。 |  |  |  |
| 引数の説明 |  |  |  |
|  | **type** | **description** |  |
|  | String | ボタンの状態 |   |
|  |  | on | On状態  |
|  |  | off | Off状態 |

| .cscwCall(“enable”, enable) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| ボタンの有効/無効を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| enable | Boolean | ボタンの有効/無効 |   |
|  |  | true | 有効  |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“enable”)　 |   |   |   |
|:--------------------- |:--- |:--- |:--- |
| ボタンが有効かどうかを取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | ボタンの有効/無効 |   |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“toggle”) |
|:------------------- |
| ボタンのOn/Offを排他で切り替える。Action=”toggle”の場合のみ有効。 |

| .cscwCall(“label”, label[, refresh, dir]) |   |   |   |
|:------------------------------------------- |:--- |:--- |:--- |
| <br>labelを切り替える。<br><br>引数としてnullを指定することで、label指定を明示的に解除できる。<br><br>|  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |
| label | String/ jQueryObject |ラベル文字列<br><br>もしくは文字列を示すjQueryObject |
| refresh | Boolean | 設定に伴いボタンの表示更新を行うか否か（trueがデフォルト値） |
|  |  | true | ボタンの表示更新を行う |
|  |  | false | ボタンの表示更新を行わない |
| dir | String | ラベル文字列の書き進む方向(text direction)を変更する。<br>省略時は現在の書き進む方向のまま変更しない |  |
|  |  | "ltr" | 左から右へ書き進む |
|  |  | "rtl" | 右から左へ書き進む |

| .cscwCall(“label”) |   |   |
|:------------------ |:--- |:--- |
| labelを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String/jQueryObject | <br>表示されているラベル文字列。もしくは文字列を示すjQueryObject。<br><br>設定されていない場合はnullが戻る。<br><br> |

| .cscwCall(“glyph”, glyph[, refresh]) |   |   |   |
|:------------------------------------ |:--- |:--- |:--- |
| Glyphのコードを設定する。<br><br>引数としてnullを指定することで、glyph指定を明示的に解除できる。|  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |
| glyph | String/ jQueryObject | グリフコード |
| refresh | Boolean | 設定に伴いボタンの表示更新を行うか否か<br>省略時はtrue |
|  |  | true | ボタンの表示更新を行う |
|  |  | false | ボタンの表示更新を行わない |

| .cscwCall(“glyph”) |   |   |
|:------------------ |:--- |:--- |
| Glyphのコードを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | 表示されているグリフコード。設定されていない場合はnullが戻る。 |

| .cscwCall(“image”, image[, refresh]) |   |   |   |
|:------------------------------------ |:--- |:--- |:--- |
| <br>アイコン画像のパスを設定する。<br><br>引数としてnullを指定することで、image指定を明示的に解除できる。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |
| image | String | アイコンの画像 |
| refresh | Boolean | 設定に伴いボタンの表示更新を行うか否か<br>省略時はtrue |
|  |  | true | ボタンの表示更新を行う |
|  |  | false | ボタンの表示更新を行わない |

| .cscwCall(“image”) |   |   |
|:------------------ |:--- |:--- |
| <br>アイコン画像の場所を示す文字列を取得する。<br><br>※本メソッドはデバッグ用であり、製品ロジックでの利用は不可とする<br><br> |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | アイコン画像のパス |

| .cscwCall(“badge”) |   |   |
|:------------------ |:--- |:--- |
| バッジを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | jQuery Object | 付与されているバッジを示すjQuery Object<br><br>設定されていない場合はnullが戻る。 |

| .cscwCall(“refresh”) |
|:------------------ |
| <br>ボタンの表示更新を行う。<br><br>複数の構成要素の変更を行う場合は、構成要素変更時のrefresh指定を無効にして全ての変更を行い、変更が終わったタイミングで本メソッドをコールすること<br><br> |

| .cscwCall("glyphColor", glyphColor)  |   |   |
|:------------------------------------------------ |:--- |:--- |
| Glyphに適⽤する特殊フォントスタイルを 変更する。<br>Glyphがない状態でコールした場合はエラーとなる  |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| glyphColor | String | Glyphに適⽤する特殊フォントスタイル名<br><br>※※指定できる値については[Text] 特殊フォントスタイル名の項を参照 |
<br><br> |

| .cscwCall("glyphColor")  |   |   |
|:------------------------------ |:--- |:--- |
| Glyphに適⽤されている特殊フォントスタイル名を取得する。<br>Glyphがない状態でコールした場合はエラーとなる |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | Glyphに適⽤されている特殊フォントスタイル名<br><br>特殊フォントスタイルが設定されていない場合はnullを返す。 |

| .cscwCall("maxWidth", maxWidth)  |   |   |   |
|:------------------------------------------------ |:--- |:--- |:--- |
| maxWidthの値を変更する |  |  |  |
| 引数の説明 | maxWidthの値 |  |  |
| **name** | **type** | **description** |  |
| maxWidth | Integer | maxWidthの値(px) |  |

| .cscwCall("maxWidth")  |   |   |   |
|:------------------------------ |:--- |:--- |:--- |
| maxWidthの値を取得する |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Integer | maxWidthの値(px) |

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwChanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| ボタンの状態が変わった時に発生 |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | status | String | ボタンの状態 |  |
|  |  |  | on | On状態 |
|  |  |  | off | Off状態 |

| イベントタイプ |
|:------------- |
| cscwTap |
| **イベントのトリガ** |  |  |  |
| ボタンがタップされた時に発生 |