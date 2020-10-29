[Switch Item](../abstractwidgetcontents)
======

機能
-------

-   概要

> SwitchItemを実装する。

-   機能

> Switching内に含まれるSwitchItem
> (ボタン)を表示し、操作に応じて表示状態を変更すると共にイベントを発行する。Switching外でSwitchItemが利用されることはない。

-   操作

> タップするとOff/On状態を順に切り替える。Disable状態の場合は操作を受け付けない。

-   音

> コンストラクタで鳴らすことを指定した場合は、操作を受け付けるとvalid音が鳴る。同じく、コンストラクタで鳴らすことを指定した場合は、操作を受け付けない場合にinvalid音が鳴る。

-   レイアウト

> 以下、Widgetが持つレイアウトを利用した場合の仕様を示す。この仕様に沿わないSwitchItem（ボタン）を必要とする場合には、Widgetによる内部レイアウトを行わない指定を行うとともに、アプリケーションから詳細を指示すること。
>
> SwitchItemは、SwitchItem（ボタン）を視覚的に表す矩形領域とそこに配置されたアイコン
> and/or ラベルとタッチマージンからなる。
>
> 色に関する属性は、Application
> theme、SwitchItemのstateごとに定義される。
>
> 詳細は、スタイルガイドの指定を参照のこと。ただし、tableサイズでの描画の場合に限り、SwitchItem自体が適切な背景テクスチャを持った仕様で描画される。
>
> SwitchItemのレイアウトは指定されたsizeにおいて、SwitchItem自身のlayoutと中身、cssの指定SwitchItem
> Controlからの指示によって定まる。
>
> SwitchItemは、SwitchItem自体で定まる幅で作成され,Switchingによって最終的な幅へ変更される。さらに、後にSwitchingによって再度幅が変更される場合がある。
>
> つまり、レイアウトは、
>
> ・segmnet自体のオプション
>
> ・Switchingのオプション
>
> の双方に依存して決定される。

SwitchItemのレイアウト（アイコンとラベルを持つ場合）

SwitchItemのレイアウト（アイコンのみ/ラベルのみの場合）

タッチマージン (Tableサイズのみに存在)

**各種スタイル定義**

| size | height | min- width | Font | Icon | Glyph | Internal margin | Icon left margin | Icon-label margin |
|:---- |:------ |:---------- |:---- |:---- |:----- |:--------------- |:---------------- |:----------------- |
| Table |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |
| Medium(デフォルト) |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |
| Large |  |  |  |  |  |  |  |  |

> \*1　SwitchItemは上下のタッチマージンを含むが、heightは、タッチマージンを含まない高さ。
>
> タッチマージンを含んだheightは

**OptimizedImage 利用時のレイアウト調整**

| size | Optimized Image | Icon left margin | Icon-label margin |
|:---- |:--------------- |:---------------- |:----------------- |
| Table |  |  |  |
|  |  |  |  |
| Medium |  |  |  |
|  |  |  |  |
| Large |  |  |  |

> **Icon over labelにおけるレイアウト**
>
> **Icon over label　における各種スタイル定義**

| Size | Height | Min. width | Font | <br>Icon<br><br>size<br><br> |  <br>glyph<br><br>size*2<br><br> | Internal margin | Vertical margin | <br>Label<br><br>height<br><br> |
|:---- |:------ |:---------- |:---- |:---------------------------- |:-------------------------------- |:-------------- |:--------------- |:------------------------------- |
| Medium |  |  |  |  |  |  |  |  |
| Large |  |  |  |  |  |  |  |  |

> ※この配置では、ラベルの縦位置は、Label
> heightの中で縦方向センタリングされる。
>
> \*1　白枠分を含めたサイズ（）を引いて良い。
>
> \*2　イメージアイコンと同じサイズの領域にセンタリング表示とする。

**OptimizedImage 利用時のレイアウト調整**

| Size | Icon size | Vertical margin | Label | height |
|:---- |:--------- |:--------------- |:----- |:------ |
| Medium |  |  |  |  |
| Large |  |  |  |  |

> アイコンとラベルが横並びであり、かつ、SwitchingからSwitchItemの横並び配置が指示されたときに限り、以下に示すようにアイコン/ラベルの組みでセンタリングされたレイアウトに調整される。

アイコンとラベルが横並び配置でのセンタリング

> <span class="underline">＜枠線＞</span>
> SwitchItemは、束ねられたときの位置により、4方向のborderのうちの一部が欠落するが、これはSwitchingButton
> の仕様として定義される。また、segmnetの角Rも、束ねられたときの位置により、適用される場合とされない場合があるが、これもSwitchingButtonの仕様として定義される。
> <span class="underline">＜アイコン＞</span>>
>
>

>
> Buttonの項に記載された仕様と同等とする。
>
> <span class="underline">＜グリフ＞</span>
>
> Buttonの項に記載された仕様と同等とする。
>
> <span class="underline">＜ラベル＞</span>
> Buttonの項に記載された仕様と同等とする。ただし、SwitchItemは単独では描画の幅を決定できないケースもあるため、その場合は、SwitchingButtonによって最終的に決定された幅を元に表示の調整が行われる。
> <span class="underline">＜バッジ＞</span>
>

>
> なお、内部にアイコンが配置された、規定スタイルのSwitchItemには、オプションによりバッジを付与することができる。バッジの位置は、以下に従う。
>
> **アイコンにバッジが付与されるケース**
>
> 　初期化後のメソッドコールにより、アイコンが削除された場合は、該アイコンに付与されていたバッジも削除される。その後、アイコンを再度追加した場合も、バッジが自動的に元の状態に戻ることはない。明示的にBadgeの表示を指示することで再表示されるが、そのときのBadgeはSwitchItem初期化時に与えたパラメータに従ったものとなるため、必要に応じてBadge用のパラメータを書きかえる必要がある。
>
> <span class="underline">＜タッチマージン＞</span>
>
> Table
> サイズのSwitchItemのみ上下にタッチマージンを持つ。詳細は、Switchingの項参照。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> 指定に従い、ラベルをLTR表示もしくはRTL表示する。なお、ラベルの寄せ方向はLTR/RTL表示に寄らない。
> アイコンとラベルが横並びの配置の場合、常にアイコンは左で、その右に左寄せでラベルがLTRもしくはRTLで表示される。
>
> base
> directionに関わらず、グリフの字形は変更しない。左右反転などは行わない。
>
> base
> directionに関わらずbadgeの表示位置は一定。ミラーリングをサポートしないので、badgeは変更なし
>
> フリーレイアウトのSwitchItemについては、その構成要素のLTR/RTL表記について関与しない。何も設定しない。

API Documentation
-------

-   オブジェクト名

> SwitchItem

-   コンストラクタ

> $.cscwSwitchItem(\[options\]) :SwitchItemを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”SwitchItem” &gt;&lt;/div&gt; |
| Script | $(“#SwitchItem”).cscSwitchItem(); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| layout | String | <br>SwitchItem内部のレイアウト種類<br><br>normal　アイコンとラベルが横並びの規定レイアウトを利用する。<br><br>vertical　アイコンとラベルが縦並びの規定レイアウトを利用する。<br><br>free　規定されたレイアウトを利用しない。<br><br>normal/vertical/free以外の文字列を指定しないこと。<br><br> | normal |
| size | String | <br>SwitchItemのサイズ<br><br>header<br><br>medium<br><br>ただし、layout指定がfreeの場合は無効。<br><br> | medium |
| label | <br>String/Array/ jQueryObject<br><br> | <br>SwitchItem上に表示するラベル文字列。ラベルが２行になる場合は、改行を含む文字列または配列で渡す*1。単純なテキスト形式で指示できないスタイル混在が必要な場合はjQueryObjectを利用する。jQueryObjectで指示した場合は、truncateオプションは適用されない。<br><br> | null |
| truncate | String | <br>ラベル長がラベル領域を超過したときの省略描画の適用<br><br>null/end/middle/begin以外の値を指定しないこと。<br><br>null　超過が起きない場合に使うことを前提とする。超過した場合の挙動は保証しない。<br><br>end　ラベルの前方を優先して表示し、エリアを超過した後方を省略表示とする。<br><br>middle　ラベルの前方、後方を優先して表示し、文字列の中央を省略表示する<br><br>begin　ラベルの後方を優先して表示し、エリアを超過した前方を省略表示とする。<br><br> | null |
| autoWrap | Boolean | テキスト長が領域幅を超える場合の折り返しを行うか否か。<br>truncateで"begin", "middle"を指定した場合はtrueにしてはならない | false |
| dir | String | <br>ラベル文字列の書き進む方向( text direction)を指定する。<br><br>global/ltr/rtl以外の文字列を指定しないこと。<br><br>global　表示言語の共通初期設定に従う<br><br>ltr 左から右へ書き進む。<br><br>rtl 右から左へ書き進む。<br><br> | global |
| image | String | <br>SwitchItem上に表示するアイコン画像を示すパス。<br><br> | null |
| glyph | String | <br>SwitchItem上に表示するGlyphコード。<br><br> | null |
| status | String | <br>on　On状態<br><br>off　Off状態<br><br>on/off以外の文字列を指定しないこと。<br><br> | off |
| enable | Boolean | falseにするとDisable状態となり、操作を受け付けない。 | true |
| visible | Boolean | falseにすると、非表示状態で初期化される | true |
| soundEnable | Boolean | <br>Widgetによる操作音(valid音)の鳴動制御<br><br>true 操作音を鳴らす<br><br>false 操作音を鳴らさない<br><br> | true |
| invalidSoundEnable | Boolean | <br>Widgetによる操作音(invalid音)の鳴動制御<br><br>true 操作音を鳴らす<br><br>false 操作音を鳴らさない<br><br> | true |

\*1　String型指定時は複数の改行を含んではならない。また、Array型指定時における各配列要素は、改行を含んではならない。

> \*2　規定レイアウト利用時に、image、glyphのうちの複数を初期化時に指定した場合は、image
>  &gt; glyph
> の優先度で適用される。後述するメソッドにより、imageもしくはglyphが初期化後に指定された場合は、後から指定されたものを有効として表示する。

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> コンストラクタをコールする要素に対して、heightを指定することで、高さを指定することができる。ただし、高さの指定はスタイルガイドからの逸脱を意味するため、Freeレイアウト時のみ有効となる。また、一つのSwitchingで束ねられるSwitchItemは、同じ高さが指定されることを想定している。
>
> 幅指定機能は持たない。幅の指定は、本Widgetを束ねるSwitching
> Widgetから行うこと。
>
> Example:　　\#SwitchItem{height:100px;}

-   LabelオプションにjQueryObjectを指定した場合について

> jQueryObjectに含まれるテキスト要素については、デフォルトではlabelを文字列で指定した時と同等のスタイルが適用される。プレス時のfont-wight制御も同等に行われる。なお、デフォルトではwhite-space:
> nowrap　となるため、自動折り返しが必要な場合には、widthの指定とともに、white-space：normal、および他の適切なcssを適宜利用すること。

-   規定レイアウトを適用しない場合について

<!-- -->

-   sizeオプションが無効となるため、SwitchItemの高さおよびフォントサイズがWidget内部で決定されない。アプリケーションから適切なcssにて規定する必要がある。

-   SwitchItem内に配置されるもの（ラベル、アイコンなど）は制限されず、他のアイテムも配置することができる。

-   通常は、レイアウト規定によりイメージアイコン、グリフアイコンの共存はできないが、規定レイアウトを適用しない場合は、複数の要素をボタン内に配置することも可能となる。

-   SwitchItem自体の色彩については、statusおよびenableの変化に伴う見た目の変化を含めて、Widgetから提供される。これを変更したい場合は、適宜cssにて上書きすることで対応できる。

-   規定レイアウトに含まれる、ラベル、アイコン、グリフ、の色については、それらを示すMarkupで表されている（適切なタグとクラスが適用されている）ものについては、statusおよびenableの変化に伴う追従機能を含めて、Widgetから提供される。これを変更したい場合は、適宜cssにて上書きすることで対応できる。

<!-- -->

-   メソッド

| .cscwCall(“status”, status) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| SwitchItemの状態を切り替える。<br><br>on/off以外の文字列を指定しないこと。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |
| status | String | SwitchItemの状態 |
|  |  | on | On状態 |
|  |  | off | Off状態 |

| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| SwitchItemの状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | SwitchItemの状態 |  |
|  |  | on | On状態 |
|  |  | off | Off状態 |

| .cscwCall(“enable”, enable) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| SwitchItemの有効/無効を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| enable | Boolean | SwitchItemの有効/無効 |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“enable”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| SwitchItemが有効かどうかを取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | SwitchItemの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“visible”, visible[, transition]) |   |   |   |
|:------------------------------------------- |:--- |:--- |:--- |
| <br>SwitchItemの表示/非表示を切り替える。<br><br>transitionオプションは、SwitchItemが属するSwitchingのlayoutがverticalのケースのみをサポートする。<br>サポート外のケースにおいては、常にfalseとなる。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| visible | Boolean | SwitchItemの表示/非表示 |  |
|  |  | true | 表示 |
|  |  | false | 非表示 |
| transition | Boolean | トランジションの有無、省略時はtrue |  |
|  |  | true | transitionを適用する |
|  |  | false | transitionを適用しない |

| .cscwCall(“visible”) |   |   |   |
|:-------------------- |:--- |:--- |:--- |
| SwitchItemが表示されているかどうかを取得する。 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | SwitchItemの表示/非表示 |  |
|  |  | true | 表示 |
|  |  | false | 非表示 |

| .cscwCall(“label”, label[, refresh]) |   |   |   |
|:------------------------------------ |:--- |:--- |:--- |
| <br>labelを切り替える。<br><br>引数としてnullを指定することで、label指定を明示的に解除できる。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **property** | **description** |
| label | String/Array/ jQueryObject | - | <br>ラベル文字列、ラベル文字列の配列<br><br>もしくは文字列を示すjQueryObject<br><br>ラベルが２行になる場合は、改行を含む文字列または配列で渡す*1。<br>単純なテキスト形式で指示できないスタイル混在が必要な場合はjQueryObjectを利用する。<br>jQueryObjectで指示した場合は、Widgetによるtruncateは行われない。 |
| refresh | Boolean | ボタンの表示更新の有無、省略時はtrue |  |
|  |  | true | 設定に伴いボタンの表示更新を行う。 |
|  |  | false | 設定に伴いボタンの表示更新を行わない。 |

\*1
String型指定時は複数の改行を含んではならない。また、Array型指定時における各配列要素は、改行を含んではならない。

| .cscwCall(“label”) |   |   |
|:------------------ |:--- |:--- |
| labelを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String/Array/jQueryObject | <br>表示されているラベル文字列、ラベル文字列の配列もしくは文字列を示すjQueryObject。<br><br>設定されていない場合は空文字が戻る。<br><br> |

| .cscwCall(“glyph”, glyph[, refresh]) |   |   |   |
|:------------------------------------ |:--- |:--- |:--- |
| <br>Glyphのコードを設定する。<br><br>引数としてnullを指定することで、glyph指定を明示的に解除できる。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **property** | **description** |
| glyph | String | - | グリフ |
| refresh | Boolean | ボタンの表示更新の有無、省略時はtrue |  |
|  |  | true | 設定に伴いボタンの表示更新を行う。 |
|  |  | false | 設定に伴いボタンの表示更新を行わない。 |

| .cscwCall(“glyph”) |   |   |
|:------------------ |:--- |:--- |
| Glyphのコードを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | <br>表示されているグリフコード<br><br>設定されていない場合はnullが戻る。<br><br> |

| .cscwCall(“image”, image[, refresh]) |   |   |   |
|:------------------------------------ |:--- |:--- |:--- |
| <br>アイコン画像のパスを設定する。<br><br>引数としてnullを指定することで、image指定を明示的に解除できる。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **property** | **description** |
| image | String | - | アイコン画像のパス |
| refresh | Boolean | ボタンの表示更新の有無、省略時はtrue |  |
|  |  | true | 設定に伴いボタンの表示更新を行う。 |
|  |  | false | 設定に伴いボタンの表示更新を行わない。 |

| .cscwCall(“image”) |   |   |
|:------------------ |:--- |:--- |
| <br>アイコン画像の場所を示す文字列を取得する。<br><br>※本メソッドはデバッグ用であり、製品ロジックでの利用は不可とする<br><br> |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | アイコン画像のパス |

| .cscwCall(“refresh”) |
|:-------------------- |
| <br>ボタンの表示更新を行う。<br><br>複数の構成要素の変更を行う場合は、構成要素変更時のrefresh指定を無効にして全ての変更を行い、変更が終わったタイミングで本メソッドをコールすること。<br><br> |

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwChanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| SwitchItemの状態が変わった時に発生 |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | status | String | ボタンの状態 |  |
|  |  |  | on | On状態 |
|  |  |  | off | Off状態 |

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwContentsChanged |
| **イベントのトリガ** |  |  |  |  |
| <br>SwitchItem内のイメージアイコン、グリフ、ラベル文字列の変更<br><br>SwitchItemのvisibleの切り替え<br><br>もしくは利用者指示によりrefreshが行われたときに発生する。<br><br>※Switching Widgetが受け取ることを想定。<br><br>これにより、Switchingがrefreshされる。<br><br> |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | parts | Boolean | 表示更新 |  |
|  |  |  | true | イメージアイコンの変更時、グリフの変更時、ラベル文字列の変更時、 refresh実行時|
|  | visibility | Boolean | 表示/非表示の変更時 |  |
|  |  |  | true | 表示 |
|  |  |  | false | 非表示 |
|  | animated | Boolean | transition発生時 |  |
|  |  |  | true | transitionを適用 |
|  | enable | Boolean | SwitchItemの有効/無効変更時 |  |
|  |  |  | true | 有効 |
|  |  |  | false | 無効 |

| イベントタイプ |
|:------------- |
| cscwTap |
| **イベントのトリガ** |
| SwitchItemがタップされた時に発生 |