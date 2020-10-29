[Search Field](../abstractwidgetcontents)
======

機能
------------

-   概要

> 必要に応じてactivity indicatorを表示できるテキストフィールド

-   機能

> 入力フィールドを表示する。
>
> Keyboard,
> embeddedPhoneNumKeypadと連携し、それらから入力した値やハードキー（T.B.D.）で入力した値をボタン上に表示する。
>
> 入力フィールド上の値の有無に従いクリアボタンを表示/削除する。
>
> アプリの指示により、Inidicatiorの表示/削除をする。
>
> 入力フィールドの値の変化を通知する。(インクリメンタルサーチのための機能)

-   操作

> Text Fieldに準じるが、以下の点がことなる。
>
> Search Fieldに値がある場合、Search Fieldはフォーカスを失うと Focus (no
> cursor) の表示ステイタスになる。
>
> キーボードが表示されていない状態(Focus (no cursor),
> インジケータ表示中も含む)で、clearボタンをタップした場合、値がクリアされると共にSearch
> Fieldはフォーカスを失う(Normal (with Watermark) state)。(Focus (no
> cursor)の)Search
> Field自身をタップした場合、キーボードを表示し、カーソルを表示する(Forcus
> (with user content).

-   音

> Text Fieldと同一

-   レイアウト

> Search Fieldのステイタスとその表示様態との関係はStyle
> Guildeを参照のこと。
>
> **全体レイアウト**
>
> **各種スタイル定義**

| UI | width | Left inside padding | Glyph/Indicator-Text margin | Text-Icon margin | Right inside padding |
|:--- |:----- |:------------------- | :-------------------------- |:---------------- |:----------------- |
| 5”/10” | 指定値 |  |  |  |  |

| UI | height | border-radius | font size | glyph size “search” | indicator size | glyph size (clear_all) |
|:--- |:------ |:------------- |:--------- |:------------------- |:-------------- |:---------------------- |
| 5” |  |  |  |  |  |  |
| 10” |  |  |  |  |  |  |

> \*Glyphは領域内にセンタリング配置される
>
> 参考) Search Fieldとmedium size のText
> Fieldは、テキストのフォントサイズとそれに伴うテキスト域の高さ、左のGlyphとテキスト域とのマージンが異なる。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> 生成オプションの指定に従い、入力値をLTR表示もしくはRTL表示する。また、別の生成オプションの指定に従い入力値を指定された方向に寄せて表示する。CSCWidgetのデフォルト指定とは独立に指定できる。
>
> RTL/LTRに関わらず、グリフ、インジケータおよびクリアグリフの配置は一定で変更はない。ミラーリングはしない。例えば、虫眼鏡のグリフや検索中を示すindicator
> が枠内の左端に表示され、入力を全削除するclearボタンが枠内の右端に配置されるのは、RTL表記でも同じ。
>
> 生成オプションでRTL表示の右寄せを指定された場合に、watermarkは右端からclear
> ボタン分を開けた位置からrtlで表示される。

API Documentation
------------

-   オブジェクト名

> searchField

-   コンストラクタ

> $.cscwSearchField(\[options\]) :入力フィールドを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”input” class=”search-field&gt;&lt;/div&gt; |
| Script | $(“#input”).cscwSearchField(); |

-   オプション

> 指定できる生成時のオプションはTextFieldと同じ。
> 詳細はTextField オプションの項を参照。
> ここではTextFieldとの差分のみ記述する。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| textAlign | TextField textAlignを参照 | <br>TextField textAlignを参照。TextFieldとはデフォルト値のみ異なる。<br><br> | auto |
| clearButton | TextField clearButtonを参照 | <br>TextField clearButtonを参照。TextFieldとはデフォルト値のみ異なる。<br><br> | true |
| passwordMode | Boolean | <br>SearchFieldでは指定不可<br><br> | false |

> Search Fieldは、常にactivity indicatorが非表示の状態で生成される。

-   keyboardで使用するObjectの定義

> 「keyboardパラメータ」の項を参照。正規表現の詳細についても、「keyboardパラメータ」の項を参照。

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> コンストラクタをコールする要素に対して、widthを指定することで、幅を指定できる。
>
> 高さについては、CSSによる指定はできない。（スタイルガイドを逸脱した指定がなされた際の影響が、外形の高さだけにとどまらないため）
>
> Example:　　\#searchfield{ width:100px;}

-   メソッド

> TextFieldと同じメソッドを利用できる。
> 詳細はTextField メソッドの項を参照。
> ここではTextFieldとの差分のみ記述する。

| .cscwCall(“searching”, searching) |   |   |   |
|:--------------------------------- |:--- |:--- |:--- |
| Activity indicatorの表示/非表示を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| searching | boolean | activity indicatorの表示状態 |  |
|  |  | true | Activity indicatorを表示する |
|  |  | false | Activity indicatorを消し、元の表示に戻す |

| .cscwCall(“searching”) |   |   |   |
|:---------------------- |:--- |:--- |:--- |
| Activity indicatorの表示/非表示の状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | boolean | activity indicatorの表示状態 |  |
|  |  | true | activity indicatorが表示されている。 |
|  |  | false | activity indicatorは表示されていない。 |

-   イベント

> 発生するイベントはTextFieldと同じ。
> 詳細はTextField イベントの項を参照。

