[Header](../abstractwidgetcontents)
======

機能
---------

-   概要

> サービス画面上部に表示されるバー

-   機能

> サービス画面上部のバーを前面に表示する。バー上には指示によりボタンを表示する。
>
> 本Widgetはコンテナとして、上に配置される部品に対してアプリケーションテーマとして指定された色(color)を背景に持つことを考慮した色彩を適用する。

-   操作

> バー自体のタップ、バー上に配置されたボタンのタップを受け付ける。

-   音

> なし（バー上のボタンに関しては、ボタンの仕様にしたがって鳴動）

-   表示言語

> トップElementにlang属性を指定することで表示言語を個別に指定することができる。詳細は[<span
> class="underline">3.3.5表示言語の指定</span>](#_表示言語の指定)を参照。

-   レイアウト

> **Header　全体レイアウト**
>
> **各種スタイル定義**

| Display Size | height | width | Standard padding | Title font-size | Title max-width |
|:------------ |:------ |:----- |:---------------- |:--------------- |:--------------- |
| 5 inch | パネル幅	| <br>X_large (1行)<br><br>medium (２行)<br><br> |  |
| 10 inch | パネル幅 | <br>X_large (1行)<br><br>medium (２行)<br><br> |  |

> タイトル位置の縦方向の位置は、タイトル文字列のLineHeightを考慮した上でセンタリング。
>
> タイトルは、タイトルに与えられた所定幅に、必要な場合は省略処理を自動付与した上で配置する。2行表示が指示されている場合は、2行用のレイアウトに従う。
>
> 配置される左ボタン/右ボタンに関する詳細は以下。
>
> **左ボタン/右ボタンのスタイル定義**

| Button Size | Button TouchMargin | width | ボタン領域の最大幅 |
|:----------- |:------------------ |:----- |:----------------- |
| medium |  | <br>アプリ指定。<br><br>※通常はauto<br> |  |

> タイトル文字列と左右ボタンの表示幅の割り振りは次のとおり。まず、タイトル文字列に対してtitle
> max-widthを上限として必要な表示幅が割り当てられる。次に、残りの幅を二等分しHeader幅のを上限として左右それぞれのボタン領域(ボタンとその両側のstandard
> padding)に割り当てられる。
>
> Headerは、テーマカラーで定義されたテクスチャでHeader下部に配置されるRunActivityIndicatorの色が変化する。Header上に配置されたボタンは、上に配置されたボタンと同等の色彩を持つ。
>
> ボタンに代えてjQueryオブジェクトを配置する場合、jQueryオブジェクトはHeaderに左上/右上寄せで配置される。jQueryオブジェクトを配置する場合も、まずタイトル文字列に対して必要な表示幅が割り当てられる。従って、jQueryオブジェクトの幅は、タイトル文字列の表示に干渉しない幅としなければならない。（タイトルにjQueryオブジェクトを指定された場合、下記のルールではなく、こちらのルールが適用される）
>
> タイトルにjQueryオブジェクトを配置する場合は、Headerは、全体から左右ボタン幅を引いた幅のdivを生成し、そのdivに渡されたjQueryオブジェクトを配置する。渡されたjQueryオブジェクトに対する幅調整は行なわれないが、利用側でwidth:100%をつけることにより、空き領域をすべて利用することができる。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> RTL表記でも左右のボタンの位置は変更せず、LTR表記と同じとする。例えば、コピーの画面ではRTL表記でも右ボタンがコピー開始ボタンで、左ボタンがログイン/ログアウト
> ボタンであることは変更なし。
>
> タイトル文字列や左右ボタンの文字列は、それぞれ指定されたtext-directionで表示される。左右ボタンのボタン内のレイアウトはButtonを参照のこと。

API Documentation
---------

-   オブジェクト名

> Header

-   コンストラクタ

> $.cscwHeader (\[options\]) :Headerを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id="Header"&gt;&lt;/div&gt; |
| Scripts | $("#Header").cscwHeader(); |

> &lt;注意事項&gt;
>
> Headerは、Container　Themeを持つものの子要素としては配置できない。

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| color | String | <br>ヘッダ下部にあるインジケーターの色を指定する<br><br>下記以外の値を指定しないこと<br><br>"blue"：青に変更する<br><br>"yellow"：黄色に変更する<br><br>"green"：緑に変更する<br><br>"purple"：紫に変更する<br><br>"gray"：灰色に変更する<br><br>"red"：赤に変更する<br><br> | "blue" |
| indicatorStatus | String | <br>ヘッダ下部にあるインジケーターのアニメーションのON/OFFを変更する<br>colorで"gray"もしくは"red"を指定した場合、内部的にはindicatorStatusがONになるが、アニメーションはしない。<br><br>"on"/"off"以外の値を指定しないこと<br><br>"on"：インジケーターがアニメーションする<br><br>"off"：インジケーターがアニメーションしない<br><br> | "off" |
| title | <br>String/<br><br>Array/<br><br>jQuery object<br><br> | <br>タイトル文字列<br><br>タイトルが２行になる場合は、改行を含む文字列または配列で渡す。 *１単純なテキスト形式で指示できないスタイル混在が必要な場合はjQueryObjectを利用する。jQueryObjectで指示した場合は、truncateオプションは適用されない。 | "" |
| titleWidth | String | <br>タイトル文字列のスタイル(サイズ)を適用する<br><br>下記以外の値を指定しないこと<br><br>"narrow"：文字列の狭いスタイルを適用する<br><br>"normal"：通常の文字列のスタイルを適用する<br><br>"wide"：文字列が広いスタイルを適用する<br><br> | "normal" |
| truncate | String | <br>テキスト長が、領域幅を超過したときの省略描画の適用<br><br>下記以外の値を指定しないこと<br><br>null：超過が起きない場合に使うことを前提とし、超過した場合の挙動は保証しない<br><br>"end"：⽂字列後⽅を省略表⽰する<br><br>"middle"：⽂字列の中央を省略表⽰する<br><br> "begin"：⽂字列前⽅を省略表⽰する<br><br> | null |
| autoWrap | Boolean | テキスト長が領域幅を超える場合の折り返しを行うか否か<br><br>truncateで"begin", "middle"を指定した場合はtrueにしてはならない | false |
| dir | String | <br>タイトル文字列の書き進む方向( text direction)を指定する<br><br>下記以外の値を指定しないこと<br><br>"global"：表示言語の共通初期設定に従う<br><br>"ltr"：左から右へ書き進む<br><br>"rtl"：右から左へ書き進む<br><br> | "global" |
| leftButton | Object /<br>jQuery object | <br>ヘッダ左側に配置されるボタンを指定する<br><br> | null |
| rightButton | Object /<br>jQuery object | <br>ヘッダ右側に配置されるボタンを指定する<br><br> | null |

\*1　
String型指定時は複数の改行を含んではならない。また、Array型指定時における各配列要素は、改行を含んではならない。

-   leftButton / rightButton で使用するObjectの定義

| property | type | 内容 | Default |
|:-------- |:---- |:--- |:------- |
| layout | String | <br>ボタン内のレイアウトを指定する<br><br>下記以外の値を指定しないこと<br><br>"normal"：通常のレイアウトを指定する<br><br>"vertical"：グリフ、ラベルが縦並びになるレイアウトを指定する<br><br>"free"：規定されたレイアウトを使用しない<br><br> | "normal" |
| width | Integer / String | <br>ボタンの幅<br><br>"auto" ⽂字列⻑に応じて伸縮<br><br> | auto |
| glyph | String | ボタン上に配置されるグリフコード | null |
| label | String / Array / jQueryObject  | ボタン上に配置されるラベル文字列 <br><br>ラベルが２行になる場合は、改行を含む文字列または配列で渡す。単純なテキスト形式で指示できないスタイル混在が必要な場合はjQueryObjectを利用する。jQueryObjectで指示した場合は、truncateオプションは適用されない。 | null |
| dir | String | <br>文字列の書き進む方向( text direction)を指定する<br><br>下記以外の値を指定しないこと<br><br>"global"：表示言語の共通初期設定に従う<br><br>"ltr"：左から右へ書き進む<br><br>"rtl"：右から左へ書き進む<br><br> | "global" |
| truncate | String | <br>ラベル長がラベル領域を超過したときの省略描画の適用<br><br>下記以外の値を指定しないこと<br><br>null　超過が起きない場合に使うことを前提とし、超過した場合の挙動は保証しない<br><br>"end"：ラベルの後方を省略表示する<br><br>"middle"：⽂字列の中央を省略表⽰する<br><br>"begin"：ラベルの前方を省略表示する<br><br> | null |
| enable | Boolean | ボタンの使用可否<br><br>falseにするとDisable状態となり、操作を受け付けない | true |
| soundEnable | Boolean | <br>Widgetによる操作音(valid音)の鳴動制御<br><br>true 操作音を鳴らす<br><br>false 操作音を鳴らさない<br><br> | true |
| invalidSoundEnable | Boolean | <br>Widgetによる操作音(invalid音)の鳴動制御<br><br>true 操作音を鳴らす<br><br>false 操作音を鳴らさない<br><br> | true |

　 leftButton/rightButtonにおける、Buttonのプロパティは、styleが"transparent",actionが"normal"となる。

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> 　　なし

-   メソッド
> Descriptionで示された値以外を用いた場合の動作は保証しない。

| .cscwCall("color", color) |   |   |   |
|:-------------------------------- |:--- |:--- |:--- |
| ヘッダー下部にあるインジケーターの色を変更する。<br><br> 既定文字列以外が指定された場合は"blue"として扱われる|  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| color | String |インジケーターの色を示す文字列|  |
|  |  | "blue" | 青に変更する |
|  |  | "yellow" | 黄色に変更する |
|  |  | "green" | 緑に変更する |
|  |  | "purple" | 紫に変更する |
|  |  | "gray" | 灰色に変更する |
|  |  | "red" | 赤に変更する |

| .cscwCall(color) |   |   |   |
|:------------------------ |:--- |:--- |:--- |
| ヘッダー下部にあるインジケーターの色を取得する。 |  |  |  |
|  | **type** | **description** |  |
|  | String | インジケーターの色を示す文字列 |  |
|  |  | "blue" | 青色 |
|  |  | "yellow" | 黄色 |
|  |  | "green" | 緑色 |
|  |  | "purple" | 紫色 |
|  |  | "gray" | 灰色 |
|  |  | "red" | 赤色 |

| .cscwCall("indicatorStatus", indicatorStatus)) |   |   |   |
|:-------------------------------- |:--- |:--- |:--- |
| ヘッダー下部にあるインジケーターのアニメーションのON/OFFを変更する。<br>ただし、ヘッダーのindicatorの色が"red","gray"のときは、内部的にはindicatorStatusがONになるが、アニメーションはしない。<br> 既定文字列以外が指定された場合はpng画像が表示される。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| indicatorStatus | String | インジケーターの状態を示す文字列 |  |
|  |  | "on"　|インジケーターがアニメーションする |
|  |  | "off"　|インジケーターがアニメーションしない |

| .cscwCall(indicatorStatus) |   |   |   |
|:------------------------ |:--- |:--- |:--- |
| ヘッダー下部にあるインジケーターのアニメーションのON/OFFを取得する。 |  |  |  |
|  | **type** | **description** |  |
|  | String | インジケーターの状態を示す文字列 |  |
|  |  | "on" | インジケーターがアニメーションしている |
|  |  | "off" | インジケーターがアニメーションしていない |

| .cscwCall(“title”, title[, dir]) |   |   |   |
|:-------------------------------- |:--- |:--- |:--- |
| タイトルを同種のタイトルに切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| title | <br>String/Array(String)/<br><br>jQueryObject<br><br> | タイトル文字列。 |  |
| dir | String | タイトルの書き進む方向(text direction)を指定する。<br>省略時は、現在の書き進む方向のまま変更しない。|  |
|  |  | "global" | 表示言語の共通初期設定に従う |
|  |  | "ltr" | 左から右へ書き進む |
|  |  | "rtl" | 右から左へ書き進む |

| .cscwCall(“title”) |   |   |
|:------------------ |:--- |:--- |
| タイトルを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | <br>String/Array(String)/<br><br>jQueryObject<br><br> | 表示されているタイトルラベル文字列 |

| .cscwCall(“leftButton”) |   |   |
|:----------------------- |:--- |:--- |
| 左側ボタンを取得する。 |  |  |
|  | **type** | **description** |
|  | jQuery Object | 表示されている左側ボタンを示す、jQuery Object |

| .cscwCall(“rightButton”) |   |   |
|:------------------------ |:--- |:--- |
| 右側ボタンを取得する。 |  |  |
|  | **type** | **description** |
|  | jQuery Object | 表示されている右側ボタンを示す、jQuery Object |

-   イベント

| イベントタイプ |
|:------------- |
| cscwTap |
| **イベントのトリガ** |
| Header/ leftButton / rightButtonがタップされた時に発生<br><br>targetプロパティの指す要素は<br><br>- ボタンがタップされたときはボタン<br><br>- ボタン以外の領域がタップされたときはHeader自身 |