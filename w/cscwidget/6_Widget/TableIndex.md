[Table Index](../abstractwidgetcontents)
======

機能
----------

-   概要

> 文字集合（ex
> アルファベット全部、「あかさたな」とアルファベットなど）から特定の文字を選び出す。

-   機能

> 自身の領域へ、文字集合を表示
>
> ユーザが領域上をドラッグ、タップしたときの、選択された文字の表示
>
> 選択された文字のアプリケーションへの通知

-   操作aaa

> ドラッグ
>
> タップ

-   音

> リリース時にウィジェットのenable/disable状態に合わせた音がなる

-   レイアウト

> ガイドを参照
>
> http://xxxxx
>
> cscwidgetではTableIndexの幅・高さに、コンテナ（やPopup）が持っているpaddingも含め、デフォルトでposition:
> absolute; top:0, right:0が適用される
>
> アプリは通常は配置・レイアウトを気にしなくて良い

API Documentation
----------

-   オブジェクト名

> tableIndex

-   コンストラクタ

> $.cscwTableIndex (\[options\])
> :テーブルインデックスを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup  | &lt;div id=”tableIndex”&gt;&lt;/div&gt; |
| Script | <br>$(“#tableIndex”).cscwTableIndex({<br><br>type: "number500",<br><br>}); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| type | String | <br>TableIndexの種別 <br><br>下記以外の値を指定しないこと<br><br>"en"：種別を英語に設定する<br><br>"ja"：種別を日本語に設定する<br><br>"ko"：種別を韓国語に設定する<br><br>"zh-CN"：種別を中国語 (簡体)に設定する<br><br>"number200"：種別を200までの数字に設定する<br><br>"number500"：種別を500までの数字に設定する<br><br>| "en" |
| style | String | <br>レイアウト種別<br><br>下記以外の値を指定しないこと<br><br>"medium"：通常サイズ<br><br>"large"：大型サイズ<br><br> | "medium" |
| enable | boolean | falseにするとDisable状態となり、操作を受け付けない。 | true |
| suppressSelecting | boolean | cscwValueSelectedイベントでtype:"selecting"を抑制するかどうか。 | true（通知しない） |

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> なし

-   メソッド

| .cscwCall(“enable”, enable) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| TableIndexの有効/無効を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| name | **type** | **description** |  |
| enable | Boolean | ボタンの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“enable”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| TableIndexが有効かどうかを取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | ボタンの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwValueSelected |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
|  |  |  |  |  |
| **戻り値** |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | value | String | <br>ユーザが選択した値<br><br>文字系のTableIndexでは下記の表を参照<br><br>数値系のTableIndexでは、charViewerに表示されている値（"001"～最大値）が文字列で渡される<br><br> |  |
|  | type | String | TableIndexの選択状態 |  |
|  |  |  | "selecting" | 選択中(ドラッグ中) |
|  |  |  | "selected" | 選択完了(リリース時) |

<img src="./media/CSCWidget仕様書_3/media/image3.png" style="width:5.08681in;height:5.39375in" />