
6.0 Widget
======

各Widget(Component)は単一のクラスまたは複数クラスの組み合わせにより実現されている。

6.1. Widget List
-----------

　提供Widget一覧、およびスタイルガイドとの対応関係は以下の通りである。

**Widget一覧**

| Name | Description | スタイルガイド | 参照箇所 |
|:---- |:----------- |:------------- |:-------- |
| [**Header**](../header) | サービス画面上部に表示するバー |  |  |
| [**Alert**](../alert) | アラート表示用ポップアップ画面 |  |  |
| [**App Button**](../appbutton) | アプリケーションを示すボタン |  |  |
| [**Badge**](../badge) | 他の部品に付随し、付加的な情報を示すためのバッジ |  |  |
| [**Sliding Message**](../slidingmessage) | 通知用SlidingMessage |  |  |
| [**Button**](../button) | ボタン |  |  |
| [**Carousel**](../carousel) | カルーセル |  |  |
| [**Embedded Keypad**](../embeddedkeypad) | 画面に埋め込んで利用する、数値入力用キーパッド |  |  |
| [**Embedded Phone Num Keypad**](../embeddedphonenumkeypad) | 画面に埋め込んで利用する、電話番号入力用キーパッド |  |  |
| [**Fault**](../fault) | フォルト表示用画面 |  |  |
| [**Glyph**](../glyph) | グリフ |  |  |
| [**Grid**](../grid) | グリッド（全体） |  |  |
| [**Grid Item**](../griditem) | 操作可能なグリッドアイテム（Gridの行） |  |  |
| [**Area**](../area) | 上記を含めたすべての領域 |  |  |
| [**Indicator**](../indicator) | 処理の状況を示すためのインジケータ |  |  |
| [**Input Field**](../inputfield) | カーソルを持たないTextField |  |  |
| [**Table Row**](../tablerow) | タップ可能なTableRow。明確なカラムの概念は持たない |  |  |
| [**Label**](../) | テキストラベル |  |  |
| [**Level Indicators**](../levelindicator) | 残量表示用のインジケータ |  |  |
| [**Table**](../table) | 明確なカラムの概念を持たないTable |  |  |
| [**Popover**](../popover) | ふきだし |  |  |
| [**Popup**](../popup) | ポップアップ画面 |  |  |
| [**Read Only Table Row**](../readonlytablerow) | 表示のみのTableRow。明確なカラムの概念は持たない |  |  |
| [**Scroll Pane**](../scrollpane) | スクロールバーとシャドウの表示および表示管理 |  |  |
| [**Search Field**](../searchfield) | 検索用文字列の入力フィールド |  |  |
| [**Switch Item**](../switchitem) | Switchingl内に配置されるボタン様の部品 |  |  |
| [**Switching**](../switching) | 排他的な動作をするボタン群（SwitchItem）のまとまり |  |  |
| [**Separator Line**](../separatorline) | 区切り線 |  |  |
| [**Slide Base**](../slidebase) | SlidePaneのtransitionを補完するためウィジェット |  |  |
| [**Slide Pane**](../slidepane) | ポップアップの一種。全画面表示され、スライド動作する |  |  |
| [**Slider**](../slider) | スライダー |  |  |
| [**Spin Box**](../spinbox) | 数値を＋－ボタンで増減させるスピンボックス |  |  |
| [**Suggestion Panel**](../suggestionpanel) | 入力文字列から推定される候補値の表示用パネル |  |  |
| [**Table Index**](../tableindex) | 文字集合。アルファベット全部、「あかさたな」とアルファベットなど）から特定の文字を選び出す。 |  |  |
| [**Text**](../text) | テキストボックス |  |  |
| [**Text Area**](../textarea) | カーソルを持つ複数行の入力エリア |  |  |
| [**Text Field**](../textfield) | カーソルを持つ1行の入力エリア |  |  |
| [**Toggle Switch**](../toggleswitch) | 2値の切り変え用スイッチ |  |  |
| [**Slide Start**](../slidestart) | 始点から始まり領域の50%を過ぎたら終端位置まで移動するボタン |  |  |

6.2. 機能
----

各Widgetの詳細について記載する。

> Widgetの機能として以下を定義する。

-   概要 … 機能概要

-   機能…機能・動作の詳細

-   操作…Widgetが処理可能なユーザ操作

-   音… 鳴動音

-   レイアウト…描画仕様

&lt;注意事項&gt;


6.3. API Documentation
-----------------

> 各Widgetの詳細について記載する。
>
> API仕様として以下を定義する。

-   オブジェクト名 … Widgetを一意に定義するオブジェクト名称

-   コンストラクタ…
    Widgetを使用するためのコンストラクタ、オプションCSSクラス、利用サンプル、マークアップの書き方

-   オプション… Widgetコンストラクタで指定可能なオプション項目

-   メソッド… WidgetがもつメソッドおよびそのAPI仕様

-   イベント…
    Widgetが生成するイベント名と引数、その他のイベントに関する処理

> &lt;注意事項&gt;

-   オプション…特に記載が無い限り、指定は任意である。

-   メソッド

> 引数 … \[ \]
> で括られた名称の引数は、任意で指定が可能であることを示す。
>
> 戻り値 …各Widget固有の戻り値が追加で定義されるもののみ記載する。jQuery
> Objectに関する記載は省略する。

-   イベント

> 戻り値 …各Widget固有の戻り値が追加で定義されるもののみ記載する。jQuery
> Event Objectに関する記載は省略する。

### 6.3.1. Widget共通


> 　ここでは、Widget共通で同等の仕様にて提供するI/Fについて記述する。
>
> ただし、本仕様書に定義されたWidgetのうち、BoudingBoxは例外とする。

-   コンストラクタ

<!-- -->

-   コンストラクタ名

> $.cscw + Widget名

-   利用方法

HTML上にマークアップしたタグに対して、コンストラクタメソッドをコールする。

同一のマークアップ要素に対して、複数回コンストラクタを適用することはできない。

-   メソッド

| .cscwHasMethod(“methodName”) |   |   |   |
|:---------------------------- |:--- |:--- |:--- |
| 指定されたメソッドが、該Widgetに定義されているか否かを判断する。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| methodName | String | <br>メソッド名。<br><br>ここでは、cscwCall()　の第一引数として与えることを想定した文字列。<br><br> |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | true | 指定された文字列は、メソッドとして定義されている。 |
|  |  | false | メソッドとして定義されていない。 |

| .cscwCall(methodName[,options]) |   |   |
|:------------------------------- |:--- |:--- |
| <br>指定されたメソッドを実行する。<br><br>指定可能なメソッド名、および該メソッドが取るオプションは、各Widgetの項に定義する。<br><br> |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| methodName | String | <br>メソッド名。<br><br>指定可能な名称は、各Widgetの項に定義する。<br><br> |
| options | - | <br>該メソッドが取る引数。<br><br>引数の数および型は、各Widgetの項に定義する。<br><br> |
| 戻り値 |  |  |
|  | **type** | **descriptyion** |
|  | - | 戻り値の型は、各Widgetの項に定義する。 |

| .cscwCall(“destroy”) |
|:-------------------- |
| <br>Widgetを破棄する。<br><br>一度Destroyされた要素は、再利用してはならない。<br><br> |