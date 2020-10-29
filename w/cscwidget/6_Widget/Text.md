[Text](../abstractwidgetcontents)
======

機能
----

-   概要

> テキストボックス

-   機能

> 文字列領域を提供し、内部に文字列をレイアウトするとともに指示に応じたスタイルを適用する

-   操作

> なし

-   音

> なし

-   表示言語

> トップElementにlang属性を指定することで表示言語を個別に指定することができる。詳細は[<span
> class="underline">3.3.5表示言語の指定</span>](#_表示言語の指定)を参照。

API Documentation
----

-   オブジェクト名

> text

-   コンストラクタ

> $.cscwText (\[options\]) :テキストを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”Text”&gt;&lt;/div&gt; |
| Scripts | $(“#Text”).cscwText(); |

> &lt;注意事項&gt;
>
> Textは、アプリケーション開発者に自由に部品配置が許されているエリア、および、リストアイテムのフィードバックエリアに配置可能である。
>
> 本ウィジェットは、display:
> blockまたは、display:inline-blockの要素に対して適用されることを想定している。display:inlineの要素で、テキストに装飾を施すなどの使用方法は、本ウィジェットの想定対象外である。

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| text | <br>String /<br><br>jQueryObject<br><br> | <br>表示されるデータ。<br><br>文字列の場合、"<"や">"なども含めて渡されたものが表示される。改行コードは改行表示される。<br><br>jQueryObjectの場合、0番目の要素のみ表示対象となる。<br><br> | null |
| isGlyph | boolean | <br>trueにすると<br><br>グリフ用のフォントが適用される<br><br>（Glyphウィジェットから利用が想定ユースケース)<br><br> | false |
| width | Integer | <br>文字列領域の幅<br><br>指定がない場合は内部の規定値となる | null |
| height | Integer | <br>文字列領域の高さ<br><br>指定がない場合は文字行数分の文字列の高さとなる | null |
| lineHeight | String/Integer | 文字列の高さ<br><br>small　smallスタイルが適用される<br><br>medium　mediumスタイルが適用される<br><br>large　largeスタイルが適用される<br><br>数値で指定された場合は、cssのlineHeightがpixelで指定される。<br><br>指定がない場合は要素のスタイルが適用される。 | null |
| maxHeight | Integer | 文字列領域の最大高さ<br><br>指定がない場合は文字行数分の文字列の高さとなる | null |
| maxWidth | Integer | 文字列領域の最大幅<br><br>指定がない場合は親要素の幅が適用される。 | null |
| hAlign | String | 文字列の水平方向の配置指示<br><br>left　文字列が左詰めで表示される<br><br>center　文字列が中央寄せで表示される<br><br>right　文字列が右詰めで表示される<br><br>規定の文字列以外を指定しないこと | left |
| vAlign | String | 文字列の垂直方向の配置指示<br><br>top　文字列が上詰めで表示される<br><br>middle　文字列が中央寄せで表示される<br><br>bottom　文字列が下詰めで表示される<br><br>規定の文字列以外を指定しないこと | middle |
| dir | String | <br>文字列の書き進む方向<br><br>“ltr” 左から右<br><br> | CSCWidgetのデフォルト<br>指定に従う |
| fontSize | String/Integer | <br><br>フォントサイズ<br><br>x_small　x_smallスタイルが適用される<br><br>small　smallスタイルが適用される<br><br>medium　mediumスタイルが適用される<br><br>large　largeスタイルが適用される<br><br>common_m　common_mスタイルが適用される<br><br>common_l　common_lスタイルが適用される<br><br>数値で指定された場合は、cssのfontSizeがpixelで指定される。<br><br>指定がない場合は要素のスタイルが適用される。 | null |
| specialFontStyle | String | <br>特殊な用途に見合ったフォントスタイル(color)を付与する<br><br>後述の「特殊フォントスタイル名」を参照。<br>「特殊フォントスタイル名」に既定された文字列以外を指定しないこと。 | <br>null<br><br>特殊スタイルは適用されず、親要素の設定に従う。<br><br> |
| truncate | String | <br>テキスト長が、領域幅を超過したときの省略描画の適用*1<br><br>null　超過が起きない場合に使うことを前提とする。超過した場合の挙動は保証しない。<br><br>end ⽂字列後⽅を省略表⽰。<br><br>begin ⽂字列前⽅を省略表⽰。<br><br> | null |
| autoWrap | Boolean | テキスト長が領域幅を超える場合の折り返しを行うか否か。<br><br>true　自動改行を行う<br><br>false　自動改行を行わない<br><br>maxHeightかheightを指定した場合に限りtruncate:"end"と同時指定が可能。 | false |
| wordBreak | Boolean | <br>テキスト長が領域幅を超える場合の折り返しのルールの指定。autoWrapがtrueの場合のみ有効<br><br>true 単語を意識せず折り返す<br><br>false 極力、単語の切れ目で折り返す<br><br> | false |
| isHtml | Boolean | <br>trueにすると文字列をHTMLとして認識する<br><br>true　HTMLとして認識する<br><br>false　HTMLとして認識しない<br><br> | false |

> \*1
beginでは、サロゲートペアの文字が使われた場合の省略が適切に行われることまでを保証する。それ以上大きな塊(合字など)では、部分省略になる場合がある。後方省略については、ブラウザの能力に依存する。
なお、textをjQueryObjectで指定した場合は、beginは適用できない。

-   特殊フォントスタイル名

| 設定値 |
|:--- |
| font-color-primary |
| font-color-secondary |
| font-color-tertiary |
| font-color-ready |
| font-color-alert |
| font-color-warning |
| font-color-selected |
| paperColor-gray |
| paperColor-ivory |
| paperColor-orange |
| paperColor-red |
| paperColor-white |
| paperColor-pink |
| paperColor-yellow |
| paperColor-blue |
| paperColor-green |
| paperColor-buf |
| paperColor-goldenrod |
| paperColor-other |
| paperColor-clear |
| paperColor-customColor |
| paperColor-customColor1 |
| paperColor-customColor2 |
| paperColor-customColor3 |
| paperColor-customColor4 |
| paperColor-customColor5 |


-   レイアウト

> lineHeightのパラメータに"small", "medium", "large"を指定したときの実際の値。

各種スタイル定義（上段：5inch/下段：10inch）

| 値 | lineHeight |
|:--- |:----------- |
| small |  |
|  |  |
| medium |  |
|  |  |
| large |  |
|  |  |

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> 　　**なし**

-   メソッド

| .cscwCall(“text”, text[, dir]) |   |   |   |
|:------------------------------ |:--- |:--- |:--- |
| 文字列を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| Text | <br>String<br><br>jQueryObject<br><br> | <br>文字列もしくは、文字列を示すjQueryObject<br><br>文字列からjQueryObject、jQueryObjectから文字列への変更も可能。<br>nullを指定することで明示的に文字列を消すことができる。<br><br> |  |
| dir | String | <br>タイトルの書き進む方向を指定する。<br><br>省略時は変更しない。<br><br> | |
| | |“ltr”  | 左から右へ書き進む。 |
| | |“rtl”  | 右から左へ書き進む。 |

| .cscwCall(“text”) |   |   |
|:----------------- |:--- |:--- |
| 文字列を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | <br>String<br><br>jQueryObject<br><br> | 文字列 もしくは文字列を示すjQueryObject<br><br>文字列が設定されていない場合はnullを返す。<br><br> |

| .cscwCall(“specialFontStyle”, specialFontStyle)  |   |   |
|:------------------------------------------------ |:--- |:--- |
| 適⽤する特殊フォントスタイルを 変更する。  |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| specialFontStyle | <br>String<br><br> | <br>適⽤する特殊フォントスタイル名<br><br>すでに適⽤されているspecialFontStyleがあれば、そ れらをクリアし、新たに指定されたspecialFontStyle を適⽤する。nullの場合、既存スタイルのクリアのみ⾏なう。<br><br> |

| .cscwCall(“specialFontStyle”)  |   |   |
|:------------------------------ |:--- |:--- |
| 適⽤されている特殊フォントスタイル名を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | <br>String<br><br> | 適⽤されている特殊フォントスタイル名<br><br>特殊フォントスタイルが設定されていない場合はnullを返す。<br><br> |

-   イベント

> なし

-   注意制限事項

> 指定されたheightとline-heightが同じ値あるいは近い値でかつ、vAlignがmiddleの場合、レイアウトが期待通りにならない場合がある。このような場合は、vAlignをtopかbottomに指定するか、heightを未指定にすると改善される場合がある。

6.3. Textウィジェットのレイアウト

> Textウィジェットでは、表示データ（textパラメータ）が文字列なのかjQueryオブジェクトなのかで、それ以外のパラメータのレイアウトに対する影響が変わってくる。ここでは、textが文字列の場合、jQueryオブジェクトの場合、それぞれにおいて、各パラメータがどのようにレイアウトに影響するかを説明する。

<span class="underline">textが文字列の場合に適用されるcss</span>

> textが文字列の場合、文字列のコンテナとなる要素はTextウィジェットによって決定され、その要素には以下のcssが適用され

-   wordbreakの想定ユースケース

> デフォルトはfalseであるが、文字列としてURLやpathなど、単語区切りでの折り返し表示が適切でない場合はtrueを指定する。cssの詳細は非公開。

文字列を渡す場合のレイアウト例

以下、実線はTextウィジェットの大きさを示し、点線はテキスト表示用の要素（があれば）を示す。実際のウィジェットに点線や実線のBorderが表示されるわけではないことに注意。

-   単純ケース

> <img src="./media/CSCWidget仕様書_3/media/image4.png" style="width:6.00052in;height:2.50022in" />

-   widthを文字列幅にする場合は、コンストラクタでwidthを未指定にして、cssでposition:absoluteにするかdisplay:inline-blockにする

<!-- -->

-   定型height指定

> <img src="./media/CSCWidget仕様書_3/media/image5.png" style="width:6.00069in;height:2.5in" />

-   フィードバックデキスト

> <img src="./media/CSCWidget仕様書_3/media/image6.png" style="width:6.76725in;height:5.75383in" />

-   複数行

> <img src="./media/CSCWidget仕様書_3/media/image7.png" style="width:6.00052in;height:2.75357in" />

-   文字列中に含まれる改行コードは改行表示になる。&lt;br&gt;などは文字列のまま表示される。

<!-- -->

-   truncate（最適化あり）

> <img src="./media/CSCWidget仕様書_3/media/image8.png" style="width:6.00069in;height:2.5in" />

-   自動改行

> <img src="./media/CSCWidget仕様書_3/media/image9.png" style="width:6.00052in;height:2.75357in" />

-   autoWrapはデフォルトでは、可能な限り単語区切りを尊重する

<!-- -->

-   自動改行＋wordBreak:true

> <img src="./media/CSCWidget仕様書_3/media/image10.png" style="width:6.00052in;height:2.75357in" />

-   wordBreak:trueをつけると、領域枠で折り返す。URLやpathなどの表示使われることが想定される。

textがjQueryオブジェクトの場合に適用されるcss

> textがjQueryオブジェクトの場合、渡されたjQueryオブジェクトに対して、以下の様なcssが適用される。
>
> 注意事項：whte-spaceプロパティは子要素に継承されるが、overflowおよびtext-overflowは子要素に継承されない。

-   wordbreak

> wordBreakの値に応じて、渡されたjQueryオブジェクトに文字列の場合と同様のcssを適用する（cssの詳細は非公開）。このルールは子要素に継承される。

-   ol要素/ul要素

> 渡されたjQueryオブジェクトに含まれるol/ul要素には、SGにあう余白が設定される

-   jQueryオブジェクトの構造

> Textウィジェットは、渡されたjQueryオブジェクト以下の構造について規定しない。Textウィジェットが適用するcssではレイアウトが不十分な場合は、利用者が引数に渡したjQueryオブジェクト内部をレイアウトする必要がある。

jQueryオブジェクトを渡す場合のレイアウト例

-   単純ケース

> <img src="./media/CSCWidget仕様書_3/media/image11.png" style="width:6.02719in;height:5.25379in" /><img src="./media/CSCWidget仕様書_3/media/image12.png" style="width:6.00052in;height:2.50022in" />

-   <img src="./media/CSCWidget仕様書_3/media/image13.png" style="width:6.00052in;height:4.2537in" />複数行

-   インライン要素とtruncate

> <img src="./media/CSCWidget仕様書_3/media/image14.png" style="width:6.00052in;height:3.75366in" /><img src="./media/CSCWidget仕様書_3/media/image15.png" style="width:6.00052in;height:4.2537in" />

-   inlineスタイルの要素はtruncateの対象となる

-   glyphを文字列の一部として含める場合は、spanにclass="cscw-glyph"をつける

<!-- -->

-   インライン要素とautoWrap

-   faultメッセージ

    -   箇条書き（ol、ul）が含まれる場合は、Textウィジェットは適切な余白設定を行う

    -   autoWrapは内部要素にも継承されるので、必要に応じて有効にする