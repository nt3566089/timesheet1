[Alert](../abstractwidgetcontents)
======

機能
-----

-   概要

> 機器の状態や操作指示が必要な場合であって、何らかのユーザー操作を求める為のWidget

-   機能

> パネル画面全体を覆う、警告画面を表示する。
>
> 本Widgetはコンテナとして、上に配置される部品に対して黒色(black)を背景に持つことを考慮した色彩を適用する。
>
> Alert画面が開く/閉じる動作の間、AlertはAlert画面への利用者の画面操作を無視する。

-   操作

> なし。
>
> 画面内に配置された部品が操作を受け付けるが、ここでは言及しない。

-   音

> なし

-   レイアウト

> パネル画面全面に対して、以下を適用する。Alert画面内に配置されたcscwidgetに対して、Alert内に配置されていることを示すコンテキスト（Container
> thema black）を提供する。
>
> Alert内の表示内容は、タイトルエリア、コンテンツエリア、ボタンエリア　に分けて定義され、それぞれが適切なPadding値を持って縦並び配置されるとともに、一つのまとまりとして画面内中央に表示される。
>
> Padding値はとする。
>
> スタイル定義は以下とする。
>
> **スタイル定義（色彩）**

| background-color | font-color | opacity |
|:---------------- |:---------- |:------- |
|  | タイトルエリア	コンテンツエリア ボタンエリア |  |
| black(#000000) |  | 1 |

<!--
> エリアによる、フォントのデフォルトは以下とする。
>
-->
> **フォント定義**

|   | size |
|:--- |:---- |
| 5inch | 24px |
| 10inch | 18px |

> なお、タイトル/コンテンツ/ボタンエリア　は必ずしも全て存在するわけではない。Alertは、それを非表示とする手段を、内部から提供する必要があるため、コンテンツエリアもしくはボタンエリアに、必ず自身を非表示とするボタンを配置する必要がある。
>
> **全体レイアウト**
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> Alert
> widgetは、警告画面の３つの部分の配置のみを提供しており、警告画面内に表示される文字等は別に設定する。そのため、Alert
> widgetそれ自身は、RTL表記かLTR表記かを関知しない。

-   Transition

> 表示開始時：スケールダウン と
> フェードインが同時に適用される。　Duration。
>
> 表示終了時：スケールアップとフェードアウトが同時に適用される。Duration

API Documentation
-----

-   オブジェクト名

> Alert

-   コンストラクタ

> $.cscwAlert (\[options\]) :アラート画面を生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | <br>&lt;div id=”alert”&gt;<br>&lt;div class=”cscw-alert-title&gt;タイトル&lt;/div&gt;<br>&lt;div class=”cscw-alert-body&gt;コンテンツ&lt;/div&gt;<br>&lt;div class=”cscw-alert-buttonArea&gt;&lt;/div&gt;<br>&lt;div id=”button1”&gt;&lt;/div&gt;<br>&lt;div id=”button2”&gt;&lt;/div&gt;<br>&lt;/div&gt;<br><br> |
| Script | <br>$(#button1).cscwButton();<br>$(#button2).cscwButton();<br>$(“#alert”).cscwAlert();<br><br> |

-   オプション

| **Property** | **Type** | **Description** | **Default** |
|:------------ |:-------- |:--------------- |:----------- |
| layer | Integer | <br>アラートの表示階層を示す値。数字が大きいものほど前面に表示される。<br><br>600～699<br><br> | 600 |
| opacity | number | 背景の透明度を指定する。 | 1.0 |

-   オプション相当情報のMarkupによる指定

> なし

-   関連情報のMarkupによる指定

> コンストラクタをコールする要素の子要素に以下のタグが存在する場合、

-   div(class=”cscw-alert-title”) …タイトルエリア

-   div(class=”cscw-alert-body”) …コンテンツエリア

-   div(class=”cscw-alert-buttonArea”) …ボタンエリア

> として認識される。

-   オプション相当情報のCSSによる指定

> 　　なし

-   ボタンエリアにおけるボタン配置方法について

> ボタンエリア内にボタンを横並び配置するためには、inline-block
> を適用することでこれを実現できる。
>
> 実現の仕組みについて補足する。
>
> Alertを構成する、ボタンエリアは、それを内包するWrapperを持つ。
>
> “タイトルエリア” “コンテンツエリア”
> “ボタンエリアのWrapper”　は、relative配置されることで縦に積み上げられたレイアウトを実現する。Wrapper内にあるボタンエリア自身は、absolute配置されている。従って、配置したいボタンに対して、inline-blockを適用することによって横並びが実現できる。

-   メソッド

| .cscwCall(“status”, status[, transition]) |   |   |   |
|:----------------------------------------- |:--- |:--- |:--- |
| <br>アラート画面およびその内部に配置されたアイテムを表示/非表示にする。<br><br>表示指示を行ったときに、自動的にrefreshが行われる。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | show | 表示する |
|  |  | hide | 非表示にする |
| transition | Boolean | true | <br>transitionを適用する<br><br>省略時はtrueとして扱われる<br><br> |
|  |  | false | <br>transitionを適用しない<br><br> |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Promise | <br>以下のタイミングで、コールバックが呼ばれる。クリティカルなタイミングにおける挙動については、*1を参照。<br><br>done：指定されたstatusへの内部状態、および描画を含む全ての処理が完了したとき<br><br>fail：上記の完了前に、指定されたstatusとは、別のstatusへの変更が指示されたとき<br><br> |  |

> \*1　

-   既にshowへのtransitionが完了しているときにshowへの遷移が指示された場合、コールバックはpromiseへdoneを登録した時点で呼ばれる。

-   showへのtransitionを行っている最中に、showへの遷移が指示された場合、

> ・transitionありで指示された場合、実行中のtransitionはそのまま実行される
>
> ・transitionなしで指示された場合、実行中のtransitionは即時完了となる
>
> 　
> いずれの場合も、実行していたtransitionが完了したときにdoneが呼ばれる
>
> hideについても同様。

| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| アラート画面の表示状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | show | 表示中状態 |
|  |  | hide | 非表示 |

| .cscwCall(“layer”, layer) |   |   |
|:------------------------- |:--- |:--- |
| アラートの表示階層を示す値を設定する。<br><br>値が不正である場合はエラーを返す。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| layer | Integer | アラートの表示階層 |

| .cscwCall(“layer”) |   |   |
|:------------------ |:--- |:--- |
| アラートの表示階層を示す値を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | アラートの表示階層 |

| .cscwCall(“refresh”) |
|:-------------------- |
| <br>Widgetの表示更新を行う。<br><br>ただし、タイトルエリア / コンテンツエリア / ボタンエリア　自体の追加 / 削除には対応しない。<br><br>タイトルエリア / コンテンツエリア / ボタンエリアのサイズ変更時は、本メソッドをコールすること。<br><br> |

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwTransitionEnd |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| 状態変更に伴う、描画処理を含むすべての処理が完了したことを示す	 |  |  |  |  |
| 戻り値 |  |  |  |  |
| **Type** | **property** | **property type** | **description** |  |
| Object | property | String | status　固定	 |  |
|  | value | String | show | 表示開始 |
|  |  |  | hide | 表示終了 |
|  | result | String | completed | 正常に完了した |
|  |  |  | cancelled | キャンセルされた |