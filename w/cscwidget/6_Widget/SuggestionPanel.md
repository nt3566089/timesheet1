[Suggestion Panel](../abstractwidgetcontents)
======

機能
----------------

-   概要

> 簡単な入力を実現するため、候補を複数提示したなかから選択することで入力の手間を軽減する機能。

-   機能

> アプリからの指示により、表示/非表示する。
>
> アプリからの指示により、候補のリストあるいはindicatorを表示する。
>
> ボタン操作により、候補表示エリアの表示数を1行<->複数行に切り替える。
> 1行表示の場合は最初の1件のみを表示する。
> 複数行表示の場合はスクロールで全件表示できる。
>
> アプリから候補のリストを受けとり、表示を更新する。候補順序はリストでの順序に従う。
>
> アプリからの指示より、indicator (generalActivity
> Indicator)を表示する。Indicatorを表示する場合、少なくともSuggestion
> panel表示中はindicatorのstatusは常にrunningである。
>
> タップされた候補をアプリに通知する。

-   操作

> タップ：候補をタップできる。押下しているあいだ、その候補は表示色を変える。候補を押下中に候補のリストの更新があったばあい、指を離す動作があってもタップとして認識されてはならない。　　
>
> スクロール：　候補のすべてがsuggestion
> panelの幅に収まらない場合、フリック/ドラッグ操作によって、上下にスクロールできる。

-   音

> コンストラクタで鳴らすことを指定した場合は、タップによりValid音が鳴動する。

-   レイアウト

> 各候補は、`<secondary> - <primary>`の形式で、secondaryとprimaryをハイフンでつなげて1行に表示する
>
> Suggestion Panelは、scrollbarを表示する
>
> Indicatorの仕様はgeneralActivityIndicatorに従う。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> 生成オプションの指定に従い、label をLTR表示またはRTL表示で表示する。(メールアドレスなどを表示する場合は表示言語がアラビア語であってもltrの表示が適当であるため。)
>
> Suggestion Panel は、ミラーリングをサポートしないので、base direction
> の設定にかかわらず、左寄せで表示する。
>
> Suggestion Panel
> は、ミラーリングをサポートしないので、候補は常に上から下に配置される。画面に全体が収まらない場合の初期表示は、常に後の候補が下にスクロールアウトした状態とする。
>
> Suggestion Panel は、ミラーリングをサポートしないので
> indicatorは常に中央に表示される。

-   Transition

> 表示は、キーボード上からスライドイン。非表示では、キーボード上へスライドアウト。
> 「upallowhead」を押下した際は上部へスライドイン。

API Documentation
----------------

-   オブジェクト名

> SuggestionPanel

-   コンストラクタ

> $.cscwSuggestionPanel(\[options\])
> :入力フィールドを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |     |
|:------- |:--- |
| Markup | &lt;div id=”Suggestion” &gt;&lt;/div&gt; |
| Script | $(“#Suggestion”).cscwSuggestionPanel (); |

-   オプション

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| soundEnable | Boolean | <br>Widgetによる操作音の鳴動制御<br><br>true 操作音を鳴らす<br><br>false 操作音を鳴らさない<br><br> | true |
| layer	| Integer | <br>SuggestionPanelの表示階層を示す値。数字が大きいものほど前面に表示される。<br><br>700～799<br><br> | 700 |
| dir | String | <br>labelのtext direction<br><br>“global” 表示言語の共通初期設定に従う<br><br>“ltr” 左から右へ書く<br><br> | "global" |

> Suggestion Panelは、常に候補なし、非表示で生成される。

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> なし

-   メソッド

| .cscwCall(“add”, suggestions) |     |     |
|:----------------------------- |:--- |:--- |
| 新たな候補を追加する。それまでの候補はそのままに新たな候補を追加して表示する。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| suggestions | 候補Objectの配列 | <br>新たに表示する内容<br><br>候補の配列が設定されていた場合<br><br>それまでの候補の表示、スクロール状態はそのままに、新たな候補を追加して表示する。新たな候補が空の配列 (もしくはnull)の場合、Suggestion Panelの表示は変化しない。<br><br>文字列 “running”が設定されていた場合<br><br>indicatorを破棄し、新たな候補を設定する。新たな候補が空の配列 (もしくはnull) であってもindicatorは破棄する。<br><br> |

| .cscwCall(“status”, status, transition) |     |     |     |
|:--------------------------------------- |:--- |:--- |:--- |
| 現在の候補の数に関わりなく、Suggestion panel の表示/非表示を設定する。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | show | <br>表示する。<br><br>既にSuggestion panelが表示されている場合、何もしない。<br><br> |
|  |  | hide | <br>非表示にする。<br><br>Suggestion panelが表示されていない場合は何もしない。<br><br> |
| transition | Boolean | transitionの有無 |  |
|  |  | true | 行う（デフォルト） |
|  |  | false | 行わない |

| .cscwCall(“status”) |     |     |     |
|:------------------- |:--- |:--- |:--- |
| 表示/非表示の状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |
|  | String | show | 表示 |
|  |  | hide | 非表示 |

| .cscwCall(“suggestions”, suggestions) |     |     |
|:------------------------------------- |:--- |:--- |
| 新たな候補に入れ替える。それまでの表示内容を破棄し、新たな候補あるいはactivity indicatorを表示する。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| suggestions | 候補Objectの配列/ 文字列 | <br>入れ替えで新たに表示する内容<br><br>候補のオブジェクトの配列の場合<br><br>候補を表示する。それまでのスクロール状態は失われる。<br><br>空の配列 (もしくはnull) の場合、Suggestion Panelの表示は空になる。<br><br>文字列 “running” の場合<br><br>indicatorを表示する。Indicatorは、少なくともsuggestion panelが表示されている間は常にrunning状態である。<br><br> |

-   Add, suggestionsで使用する候補Objectの必須属性の定義

| property | Type | 内容 |
|:-------- |:---- |:---- |
| primary | 文字列 | labelの「-」以降に表示する文字列。文字列は改行を含んではならない。 |
| secondary | 文字列 | labelの「-」以前に表示する文字列。文字列は改行を含んではならない。 |

| .cscwCall(“suggestions”) |     |     |
|:------------------------ |:--- |:--- |
| 設定されている候補を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | 候補Objectの配列/文字列 | 候補の配列 または 文字列 ”running” |

| .cscwCall(“layer”, layer) |     |     |
|:------------------------- |:--- |:--- |
| Suggestion Panelの表示階層を示す値を設定する。値が不正である場合はエラーを返す。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| layer | Integer | Suggestion Panelの表示階層 |

| .cscwCall(“layer”) |     |     |
|:------------------ |:--- |:--- |
| Suggestion Panelの表示階層を示す値を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | Suggestion Panelの表示階層 |

-   イベント

| イベントタイプ |     |     |     |
|:------------- |:--- |:--- |:--- |
| cscwSelected |  |  |  |
| **イベントのトリガ** |  |  |  |
| 候補がタップされた時に発生。 |  |  |  |
| 戻り値 |  |  |  |
| **type** | **property** | **property type** | **description** |
| Object | selected	| 候補Object | タップされた候補の候補Object |