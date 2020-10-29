[Level Indicator](../abstractwidgetcontents)
======

機能
---------------

-   概要

> 資源の残量を示すためのインジケータ

-   機能

> 資源の残量を、適切に表示する。

-   操作

> なし

-   音

> なし

-   レイアウト

> ＜<span class="underline">標準レイアウト</span>＞
>
> 　指定された大きさの矩形内にて、残量に相当する割合を塗りつぶしで表現する。
>
> 塗りつぶしについては、規定された色を使用する場合と、指定されたテクスチャを適用するケースがある。
>
> **全体レイアウト**
>
> **スタイル定義**

| width | height | Level Height | <br>background<br><br>channel<br><br> | colored | fillborder-radius |
|:----- |:------ |:------------ |:------------------------------------- |:------- |:----------------- |
| <br>アプリ指定<br><br>Default：<br><br> | <br>アプリ指定<br><br>Default：<br><br> | アプリが指定する「残量」から算出 |  | 別表 |  |

> **塗りつぶし色（colored fill）の定義**

| normal |
|:------ |
| cyan_toner |
| magenta_toner |
| yellow_toner |
| black_toner |

> ＜<span class="underline">マスクの適用</span>＞
>
> 　標準レイアウトに対して、指定されたマスクを適用し、何の資源の残量を示しているかをより的確に表現することができる。マスク画像としては、pngもしくはsvgが利用できる。

　　　　

> **塗りつぶしとマスク画像　および生成されるインジケータ**
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> Indicatorは、LTR/RTLについて関知しない。変更しない。
>
> 残量を示す数値は、常に算用数字に%をつけて表示する。
>
> トナー残量に用いる、のインジケータは、アラビア語であってものままとする。

API Documentation
---------------

-   オブジェクト名

> LevelIndicator

-   コンストラクタ

> $.cscwLevelIndicator(\[options\])
> :レベルインジケータを生成するコンストラクタ。
>
> 適用可能なタグ : div

| Example |     |
|:------- |:--- |
| Markup | &lt;div id=”level” class=”level”&gt;&lt;/div&gt; |
| Script | $("LevelIndicator").cscwLevelIndicator(); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| width | Integer | インジケータの幅 | <br>null<br><br>指定無き場合はcss指定を見る。<br><br> |
| height | Integer | インジケータの高さ | <br>null<br><br>指定無き場合はcss指定を見る。<br><br> |
| value | Integer | <br>残量レベルを表す値（割合）<br><br>指定可能な値域は0～100<br><br>0以下は0, 100以上は100として扱われる<br><br> | 0 |
| color | String | <br>塗りつぶし色<br><br>下記以外の値を指定しないこと<br><br>"normal"：トナー以外の資源残量用<br><br>"cyan_toner"：シアントナー用<br><br>"magenta_toner"：マゼンタトナー用<br><br>"yellow_toner"：イエロートナー用<br><br>"black_toner"：ブラックトナー用<br><br> | "normal" |
| texture | String | 塗りつぶし色の代替として用いるテクスチャ画像のパス | null |

-   オプション相当情報のCSSによる指定

> コンストラクタをコールする要素に対して、width,
> heightを指定することで、サイズを指定することができる。
>
> Example:　　\#level{ width: 80height:80px;}

-   メソッド

| .cscwCall(“value”, value) |     |     |
|:------------------------- |:--- |:--- |
| 残量レベルを設定する |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| value | Integer | 残量レベル（0～100） |

| .cscwCall(“value”) |     |     |
|:------------------ |:--- |:--- |
| 現在設定されている残量レベルを取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | 残量レベル（0～100） |

| .cscwCall(“color”, color) |     |     |     |
|:------------------------- |:--- |:--- |:--- |
| <br>塗りつぶし色を設定する<br><br>本メソッドの実行により、テクスチャ指定は無効となる。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| color | String | 塗りつぶし色 |
|  |  | "normal" | トナー以外の資源残量用 |
|  |  | "cyan_toner" | シアントナー用 |
|  |  | "magenta_toner" | マゼンタトナー用 |
|  |  | "yellow_toner" | イエロートナー用 |
|  |  | "black_toner" | ブラックトナー用 |

| .cscwCall(“color”) |     |     |     |
|:------------------ |:--- |:--- |:--- |
| 現在設定されている塗りつぶし色を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | 塗りつぶし色 |  |
|  |  | "normal" | トナー以外の資源残量用 |
|  |  | "cyan_toner" | シアントナー用 |
|  |  | "magenta_toner" | マゼンタトナー用 |
|  |  | "yellow_toner" | イエロートナー用 |
|  |  | "black_toner" | ブラックトナー用 |

| .cscwCall(“texture”, texture) |     |     |
|:----------------------------- |:--- |:--- |
| <br>テクスチャ画像のパスを設定する<br><br>本メソッドの実行により、塗りつぶし色の指定は無効となる。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
|  | String | テクスチャ画像のパス |

| .cscwCall(“texture”) |     |     |
|:-------------------- |:--- |:--- |
| <br>現在設定されているテクスチャ画像のパスを取得する。<br><br>※本メソッドはデバッグ用であり、製品ロジックでの利用は不可とする<br><br> |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | String | テクスチャ画像のパス |