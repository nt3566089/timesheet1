[Badge](../abstractwidgetcontents)
======

機能
-----

-   概要

> バッジ。Button等、他のアイテムに付随して存在する。
>
> 付随元となるアイテムは、以下を想定し、それ以外の用途では利用者側で配置することができる。

-   AppButton

-   Button

-   TableRow（FetureIcon、およびFeedback）

-   ReadOnlyTableRow（FetureIcon、およびFeedback）

-   機能

> バッジを表示する。内部に表示するものは、アプリから指定された文字列もしくはグリフとする。
>
> ただし、文字列長の上限はとし、それを超える場合は、のみを表示する。

-   操作

> なし。

-   音

> なし。

-   レイアウト

**全体レイアウト**

> **各種スタイル定義（共通）**

| <br> 用途 <br><br>    |  <br> Width <br><br> | <br> min-width <br><br> | <br> height <br><br> | <br> Padding <br><br> | <br> border-radius <br><br> | <br> font-size <br><br> | glyph <br><br> fontSize <br><br> |
|:---------------- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
| AppButton        |  |  |  |  |  |  |  |
| Button           |  |  |  |  |  |  |  |
| TableRow         |  |  |  |  |  |  |  |
| ReadOnlyTableRow |  |  |  |  |  |  |  |

-   ※FeedbackのglyphFontSizeは、SG・補完ガイドには未定義

-   ※FeatureIconのpaddingは、SG・補完ガイドには未定義

-   font-weightはすべてbold

色については、通常の赤色のものと、特殊用途に用いる緑色のもの、およびテーマカラーに依存した色彩をとるものが存在する。

バッジは、付随元のEnable/Disable
に連動してその見た目が変化する。Disable状態では、opacityが適用され、がつかない。また、設定により、付随元のPress状態に連動してその見た目が変化する。

色彩の定義は以下。

**Badgeの色彩**

| normal | press | normal / press 共通 |     |     |
|:------ |:----- |:------------------- |:--- |:--- |
| font-color | background-color | font-color | background-color | box-shadow |

詳細は、スタイルガイドを参照のこと。

> &lt;RTL表記でのレイアウトについて&gt;

Badgeは、RTL表記を関知しない。Badge内の文字列は常にltr表記とする。

プログラムの仕様上は任意の文字列をゆるすが、デザインの規定では算用数字の数値しか使わないので、常にltr表記とする。グリフ文字で、RTL/LTRでグリフの字形を切り替える想定のグリフは無いのでグリフ文字も常にltr表記とする。

-   Transition

表示開始時: スケールアップ () /
フェードイン　が同時に適用される。　Durationは　

表示終了時: スケールダウン () /
フェードアウト　が同時に適用される。Durationは　

ただし、初期化時に、Badgeの表示指示が行われていた場合は、Badgeはtransitionを伴わずに表示される。

また、他のタイミングにおいても、transitionなしで表示開始/終了を行うことが可能である。

API Documentation
-----

-   オブジェクト名

> Badge

-   コンストラクタ

> $.cscwBadge (\[options\]) : バッジを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”badge”&gt;&lt;/div&gt; |
| Script | $(“#badge”).cscwBadge(); |

-   オプション

| **Property** | **Type** | **Description** | **Default** |
|:------------ |:-------- |:--------------- |:----------- |
| type | String | <br>ユースケースを表す文字列を指定する<br>指定されたユースケースに合うようなスタイルおよびビヘイビアが適用される<br><br>下記以外の値を指定しないこと<br><br>"icon"：AppButton及びButtonのアイコン用<br><br>"button"：Button用<br><br>"tableRow"：TableRow用<br><br> | "icon" |
| status | String | <br>バッジの表示状態<br><br>下記以外の値を指定しないこと<br><br>"show"：表示する<br><br>"hide"：表示しない<br><br> | "hide" |
| label | String | 内部に表示する文字列。<br>4文字以上指定した場合の動作は保証しない。改行を含んではならない。 | null |

-   オプション相当情報のMarkupによる指定

なし

-   オプション相当情報のCSSによる指定

なし

-   メソッド

| .cscwCall(“status”, status[, transition]) |   |   |   |
|:----------------------------------------- |:--- |:--- |:--- |
| バッジを表示/非表示にする。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | バッジを表示/非表示にする |  |
|  |  | "show" | 表示する |
|  |  | "hide" | 非表示にする |
| transition | Boolean | transitionの適用有無 <br>省略時はtrueとして扱われる | |
|  |  | true | transitionを適用する |
|  |  | false | transitionを適用しない |

| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| バッジの状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | バッジの状態 |  |
|  |  | "show" | 表示中状態 |
|  |  | "hide" | 非表示 |

| .cscwCall(“label”, label) |   |   |
|:------------------------- |:--- |:--- |
| バッジ内に表示する文字列を設定する。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| label | String | バッジ内に表示する文字列 |

| .cscwCall(“label”) |   |   |
|:------------------ |:--- |:--- |
| バッジ内に表示される文字列を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | バッジ内に現在表示されている文字列 |

-   イベント

なし