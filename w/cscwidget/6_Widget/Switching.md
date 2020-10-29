[Switching](../abstractwidgetcontents)
======

機能
---------------

-   概要

> 複数のボタンをグループ化したもの

-   機能

> 複数のボタン(SwitchItem)をグループとして扱う、操作に応じて表示状態を変更する。
>
> グループ内のいずれか1つのボタンが選択された状態となる。

-   操作

> Off状態のボタンをタップするとOn状態となり、グループ内の他のボタンはOff状態となる。
>
> 各ボタンは、Buttonオブジェクトとしてふるまう。

-   音

> なし。

-   レイアウト

> standardのSwitchItemとicon over
> labelのSwitchItemを混在することはない。SwitchItemの配列は水平方向1列(横並び)、垂直方向1列(縦並び)の二通りがある。
>
> MediumサイズあるいはlargeサイズのSwitchingは、SwitchItemの配列がスクロールするデザインがある。スクロールする場合、概念的には、角丸の表示窓からその向こうのSwitchItemの配列が見えていると考えてよい。
>
> **スクロールの考え方**
>
> 水平方向1列配置の場合、表示窓の高さはSwitchingのサイズで定まり、表示窓の幅は生成時に指定する、maxWidth,
> SwitchItemWidthと全SwitchItemの幅から定まる。なお、表示窓の幅は、SwitchItemの幅の整数倍とは限らない。水平方向1列配置の表示窓の高さは、SwitchItemの高さと生成時に指定するsize
> (tableか否か) に従う。
>
> 垂直方向1列配置の場合、表示窓の高さは指定した最大値と全SwitchItemを積み上げた高さのいずれか小さい値となる。表示窓の高さの最大値は、SwitchItemの高さの整数倍とは限らない。垂直方向1列配置の表示窓の幅は、生成時に指定するmaxWidth
> とmaxWidthと各SwitchItemの幅から定まる。
>
> 縦並び、横並びのいずれにおいても、それぞれのSwitchItemの幅はSwitchingが調整する。
>
> SwitchItem内の要素の配置を以下に示す。
>
> **横並び配置における全体レイアウト**
>
> **縦並び配置における全体レイアウト**
>
> 水平方向1列配置の全体のレイアウトを以下に示す。
>
> SwitchItemの幅を一律指定した場合、指定した幅のSwitchItemが並ぶ。SwitchItemの配列の幅がSwitchingの幅(表示窓の幅)を超える場合、SwitchItemの配列はスクロールの対象となる。
>
> **水平方向1列配置（セグメント幅指定）の場合のレイアウト詳細**
>
> SwitchItemの幅を均等指定とした場合、指定されたSwitchingの幅に各SwitchItemがほぼ均等の幅で収まるようSwitchItemの位置と幅が決定される。
>
> **水平方向1列配置（セグメント幅均等割り付け）の場合のレイアウト詳細**
>
> 垂直方向1列配置の場合、指定した最大高さをSwitchItemの配列の高さが超えるならば指定した指定した最大高さとなる。SwitchItemの配列はスクロールの対象となる。
>
> **垂直方向配置の場合（スクロールが適用されるケース）のレイアウト詳細**
>
> SwitchItemの配列の高さが指定した最大高さを超えない時は、SwitchItemの配列の高さとなる。
>
> **垂直方向配置の場合（スクロールが適用されないケース）のレイアウト詳細**
>
> なお、外枠のborder-radius は とする。
>
> <span class="underline">＜タッチマージン＞</span>
>
> Table
> サイズのSwitchItemは上下にタッチマージンを持つ。これにより、table内のSwitchingは、上下2方向のマージンを持つ。
>
> <span class="underline">参考</span>
>
> 参考として、table rowtouch marginの例を示す。

Table rowにあるSwitchingのタッチマージン

> &lt;RTL表記でのレイアウトについて&gt;
>
> Switchingは、RTL/LTRを関知せず、ミラーリングをサポートしない。
>
> 横並びのSwitchingでは、SwitchItemは常に左から右へ配置される。スクロールの初期値は常に左端である。縦並びのSwitchingでは、スクロールインジケータは常に右端に表示される。

API Documentation
---------------

-   オブジェクト名

> Switching

-   コンストラクタ

> $.cscwSwitching(\[options\])
> :Switchingを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | <br>&lt;div id=”oneOfThree” &gt;<br><br>&lt;div id=”SwitchItem1&gt;&lt;/div&gt;<br><br>&lt;div id=”SwitchItem2&gt;&lt;/div&gt;<br><br>&lt;div id=”SwitchItem3&gt;&lt;/div&gt;<br><br>&lt;/div&gt; |  |
| Scripts | <br>$(“#SwitchItem1”).cscwSwitchItem();<br><br>$(“#SwitchItem2”).cscSwitchItem();<br><br>$(“#SwitchItem3”).cscSwitchItem();<br><br>$(“#oneOfThree”).cscwSwitching(); |

> 基本的には、上述のとおり内部のSwitchItem生成後にSwitchingを生成することを想定している。
>
> ただし、Switching生成後にSwitchItemの追加は可能であることから、内部SwitchItemが0個の状態でSwitchingを生成することは許容する。

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| selected | Integer | <br>選択済みSwitchItemのインデックス<br><br>0～<br><br>1つも選択しない場合は-1 を指定する。<br><br>SwitchItemの数以上の値を指定した場合の動作は保証しない。<br><br>selectedが省略されてdefault値が適用される場合も含め、それぞれのSwitchItemの状態は<br>Switching生成時にSwitchingへの指定値に従って変更される。<br> | -1 |
| direction | String | <br>‘vertical’ 縦並び<br><br>‘horizontal’　横並び<br><br>vertical/horizontal以外の文字列を指定しないこと。<br><br> | vertical |
| maxHeight | Integer | <br>縦並びにおいて、Switchingの高さの最大値を指定する。Switchingの外枠の高さは、含まれるSwitchItemに従うが、maxHeightを超える場合はscroll paneが適用され外枠の高さがmaxHeightにな<br>る。<br><br>横並びでは無視される。<br><br> | <br>null(常にすべてのSwitchItemを表示するのに十分な高さとなる)<br><br> |
| SwitchItemWidth | <br>Integer /<br>auto /<br> justify | <br>SwitchItemをSwitchingに配置する際のSwitchItemの幅の扱いを指定する。意味は以下のとおり。direction, maxWidthの指定との組み合わせで個々のSwitchItemの最終的な幅が決まる。<br><br>Integer 指定された幅にする<br><br>auto もっとも幅の広いSwitchItemに揃える<br><br>justify 可能な幅いっぱいに広げる<br><br> Integer/auto/justify以外の値を指定しないこと。| auto |
| maxWidth | Integer | Switchingの外枠の最大幅を指定する。Switchingの外枠の幅は含まれるSwitchItemに従うが、maxWidthを超える場合はscroll paneが適用され外枠の幅がmaxWidthになる。 | null(Switchingの外枠の幅が全SwitchItemの合計幅となる。)|
| canExpand | Boolean | <br>Switchingの開閉の許可/不許可を指定する。<br><br>true　開閉を許可する<br><br>false　開閉を許可しない<br><br>directionがhorizontalの場合、指定値ににかかわらず開閉を許可しない<br><br> | false |
| expand | Boolean | <br>Switchingの開閉状態を指定する。<br><br>true　開く<br><br>false　閉じる<br><br>directionがhorizontalの場合、指定値に関わらず開いた状態で生成される。<br><br>canExpandがfalseの場合、本オプションの指定は無視され、開いた状態で生成される<br><br>falseを指定する場合、selectedに0～(SwitchItemの数未満)の値が指定されている必要がある<br><br> | true |

> Direction, SwitchItemWiidth,
> maxWidthとSwitchingの幅の関係を表に示す。

| .No | direction | SwitchItemWidth | maxWidth | 振る舞い | コメント |
|:--- |:--------- |:------------ |:-------- |:------- |:-------- |
| 1 | horizontal | 数値を指定 | 数値を指定 | SwitchItemWidthで指定された幅のSwitchItemが横並びになる。外枠は中身に合わせるが、maxWidthを超える場合はmaxWidthとなり、scroll paneが適用される。 |  |
| 2 |  |  | 指定なし | SwitchItemWidthで指定された幅のSwitchItemが横並びになる。中身に合わせてSwitchingの幅が決まる | TableサイズのSwitchingは、これかNo.4を使う |
| 3 |  | auto | 数値を指定 | 最も幅のあるSwitchItemに合わせたサイズのSwitchItemが横並びになる。maxWidthを超える場合は、ScrollPaneが適用され、外枠の幅がキープされる。 |  |
| 4 |  |  | 指定なし | 最も幅のあるSwitchItemに合わせたサイズのSwitchItemが横並びになる。 Scroll paneが適用されることはない。 | TableサイズのSwitchingは、これかNo.2を使う |
| 5 |  | justify | 数値を指定 | Switchingの外枠幅はmaxWidthになる。SwitchItemはmaxWidthを等分するように個々の幅が調整される。 | Header内のSwitchingが主な用途 |
| 6 |  |  | 指定なし | 不可 |  |
| 7 | vertical | 数値を指定 | 数値を指定 | Switchingおよび全SwitchItemは、SwitchItemWidthとmaxWidthのどちらか小さい値の幅に設定される。 |  |
| 8 |  |  | 指定なし | Switchingおよび全SwitchItemは、SwitchItemWidthの幅に設定される |  |
| 9 |  | auto | 数値を指定 | 最も幅のあるSwitchItemの幅とmaxWidthのどちらか小さい値の幅になる。 |  |
| 10 |  |  | 指定なし | 最も幅のあるSwitchItemの幅になる。 |  |
| 11 |  | justify | 数値を指定 | Switchingおよび全SwitchItemは、maxWidthの幅に設定される |  |
| 12 |  |  | 指定なし | 不可 |  |

-   メソッド

| .cscwCall(“selected”, index) |   |   |
|:---------------------------- |:--- |:--- |
| ボタンを選択状態にする。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| index | Integer | <br>選択状態にするボタンのインデックス<br><br>0～<br><br>1つも選択しない場合は-1 を指定する。<br><br>SwitchItemの数以上の値を指定した場合の動作は保証しない。 |

| .cscwCall(“selected”) |   |   |
|:--------------------- |:--- |:--- |
| 選択状態のボタンを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | <br>選択状態のボタンのインデックス<br><br>0～<br><br>1つも選択されていない場合は-1 が返る。 |

| .cscwCall("expand", expand[, transition]) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| Switchingの開閉を切り替える。<br><br>directionがhorizontalの場合、本メソッドの呼び出しは無視される。<br><br>canExpandがfalseの場合、本メソッドの呼び出しは無視される。<br><br>selectedが-1の場合、本メソッドの呼び出しは無視される。|  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| expand | Boolean | Switchingの開閉 |
|  |  | true | 開く |
|  |  | false | 閉じる |
| transition | Boolean | トランジションの有無、省略時はtrue |  |
|  |  | true | transitionを適用する |
|  |  | false | transitionを適用しない |

| .cscwCall("expand") |   |   |   |
|:------------------- |:--- |:--- |:--- |
| Switchingの開閉状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | Switchingの開閉 |
|  |  | true | 開いた状態 |
|  |  | false | 閉じた状態 |

| .cscwCall(“body”) |   |   |
|:----------------- |:--- |:--- |
| SwitchItemの親要素を取得する。 |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Object | SwitchItemの親要素. |

| .cscwCall(“maxHeight”, value) |   |   |
|:----------------------------- |:--- |:--- |
| maxHeightを変更し、新しいmaxHeightにあわせてSwitchingを更新する。<br><br>directionがhorizontalの場合、本メソッドの呼び出しは無視される。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| value | Integer | <br>Switchingの高さの最大値。<br><br>maxHeightを指定して生成したSwitchingのみmaxHeightを変更できる。 |

| .cscwCall(“maxWidth”, value) |   |    |
|:---------------------------- |:--- |:--- |
| maxWidthを変更し、新しいmaxWidthにあわせてSwitchingを更新する。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| value | Integer | <br>Switchingの幅の最大値。<br><br>maxWidthを指定して生成したSwitchingのみmaxWidthを変更できる。<br><br>switchItemWidthが"justify"の場合、nullを指定するとエラーとなる。 |

| .cscwCall(“position”, pos[, transition]) |   |   |
|:-------------------------------------- |:--- |:--- |
| 指定位置にスクロールする。<br><br>scroll paneが適用されていない場合、スクロールしない。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| pos | Integer | スクロール位置 |
| transition | Integer | Transitionを行う時間( ミリ秒 )、省略時はtranstionなし |

| .cscwCall(“position”) |   |   |
|:--------------------- |:--- |:--- |
| スクロール位置を取得する。<br><br>scroll paneが適用されていない場合、0を取得する。  |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | 位置 |

| .cscwCall(“refresh”) |
|:-------------------- |
| <br>Switchingの更新を行う。<br><br>配下にあるSwitchItem数の増減（見た目の数ではなくDOMノードとしての増減）があった場合は、本メソッドをコールすること。 |

> 補足
>
> Switching自体にはenable/disableの状態を持たない。Switchingがdisableであることは、すべてのSwitchItemがdisableであることである。

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwTransitionEnd |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| 開閉状態の変更に伴う、描画処理を含むすべての処理が完了したことを示す |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | property | String | expand　|  |
|  | value | String | true | 開いた状態 |
|  |  |  | false | 閉じた状態 |
|  | result | String | completed | 正常に完了した |
|  |  |  | cancelled | キャンセルされた |

> Switchingは、含まれるSwitchItemが投げる以下のイベントを取得して処理する。

| イベントタイプ |
|:------------- |
| cscwContentsChanged |
| **イベントのトリガ** |
| SwitchItem内のラベル文字列等が変更されたときに発生する本イベントを受けて、SwitchItemとSwitchingの幅を再調整する。なお、このときscroll paneの適用/非適用の切り替えを行うか否かは実装依存であり、仕様書では規定しない。 |

-   参考情報

1.  Transitionを伴うSwitchItemControlの高さ変更について

-   Switchingのheightプロパティ(css)を、変更後の高さに設定する。このときに所定のアニメーションを付与する。なお、Switchingのheightは基本的にWidget内部で計算され、アプリケーションから指定されることを想定していない。Cssによるheight指定は、本目的の実現のためだけに利用すること。

-   アニメーション完了時に、maxHeightを、変更後の高さに設定する。