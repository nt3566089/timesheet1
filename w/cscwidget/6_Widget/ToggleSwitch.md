[Toggle Switch](../abstractwidgetcontents)
======

機能
-------------

-   概要

> 2値を切り替えるスイッチ

-   機能

> 操作に応じてボタン状態を切り替える。切り替え時にはハンドルが左右にスライドし、表示が切り替わる。

-   操作

> タップまたはハンドル部分のドラッグで切り替えが行われる。
>
> ドラッグ時はオブジェクトの以上の長さをドラッグするとボタン状態が切り替わる。

-   音

> 操作完了時（タップ/ドラッグともThumbのリリース時）にvalid音が鳴る。Disable状態ではユーザ操作時にinvalid音が鳴る。

-   レイアウト

> **Normal　サイズにおけるレイアウト**
>
> **Tableサイズにおけるレイアウト**
>
> **Thumb**

| UI | size | Widget height | Widget width | Thumb width | Sep. line height |
|:--- |:---- |:------------- |:------------ |:----------- |:---------------- |
| 5” | medium | 24px | 60px | 30px | - |
|  | table |  |  |  |  |
| 10” | medium |  |  |  |  |
|  | table |  |  |  |  |

> 図中にRで示すborder-radiusは, Glyph sizeは。
>
> Tableサイズの場合は、タッチエリアの高さが（TableRowの高さ）に拡大される。このときマージンは上下とも共通値をとる。
>
> その他、色に関する属性が、Application theme、Conteiner theme
> に応じて、トグルボタンのstateおよびThumbのプレス状態に依存して定義される。
>
> 詳細は、スタイルガイドの指定を参照のこと。ただし、tableサイズでの描画の場合に限り、トグルスイッチ自体が適切な背景テクスチャを持った仕様で描画される。

> **Base**

|   | background-color |
|:--- |:---------------- |
| Default | 不明 |
| Checked | #00838d |

> **Knob**

|   | border-style | border-width | background-color |
|:--- |:------------ |:------------ |:---------------- |
| Default | solod | 1px | #f5f5f5 |

> **Transition**

|   | duraton | property | timing-function |
|:--- |:------- |:-------- |:--------------- |
| Default | 0.15s | all | ease |

> &lt;RTL表記でのレイアウトについて&gt;
>
> toggle Switch は、LTR/RTLを関知しない。
>
> ハンドル(thumb)の位置と意味はRTL表記でもLTR表記と同じとする。Thumbが左の場合はOFF、Thumbが右の場合はONとなることはRTL表記でも同じとする。

API Documentation
-------------

-   オブジェクト名

> toggleSwitch

-   コンストラクタ

> $.cscwToggleSwitch(\[options\]) :
> トグルスイッチを生成するコンストラクタ
>
> 適用可能なタグ: div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”switch” &gt;&lt;/div&gt; |
| Script | $(“#switch”).cscwToggleSwitch(); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| status | String | <br>トグルスイッチの状態<br><br>"on"：On状態<br><br>"off"：Off状態<br><br>on/off以外の文字列を指定しないこと。 | "off" |
| enable | Boolean | <br>トグルスイッチの有効/無効<br><br>falseにするとDisable状態となり、操作を受け付けない。<br><br> | true |
| soundEnable | Boolean | <br>Widgetによる操作音(valid音)の鳴動制御<br><br>true：操作音を鳴らす<br><br>false：操作音を鳴らさない<br><br> | true |
| invalidSoundEnable | Boolean | <br>Widgetによる操作音(invalid音)の鳴動制御<br><br>true：操作音を鳴らす<br><br>false：操作音を鳴らさない<br><br> | true |

-   メソッド

| .cscwCall(“status”, status[, transition]) |   |   |   |
|:--------------------------------------- |:--- |:--- |:--- |
| トグルスイッチの状態を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | トグルスイッチの状態 |  |
|  |  | on | On状態 |
|  |  | off | Off状態 |
| transition | Boolean | transtionの有無. 省略時はtrue |  |
|  |  | true | Transition あり |
|  |  | false | Transition なし |

| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| トグルスイッチの状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | トグルスイッチの状態 |  |
|  |  | on | On状態 |
|  |  | off | Off状態 |

| .cscwCall(“enable”, enable) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| トグルスイッチの有効/無効を切り替える。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| enable | Boolean | トグルスイッチの有効/無効  |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“enable”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| トグルスイッチが有効かどうかを取得する。 |  |  |  |
|  | **type** | **description** |  |
| 戻り値 |  |  |  |
|  | Boolean | トグルスイッチの有効/無効  |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“toggle”) |
|:------------------- |
| トグルスイッチの状態を切り替える。<br>On状態の場合はOff状態に、Off状態の場合はOn状態に切り替える |

-   ステータス変更中のステータス変更
> transitionありでステータス変更を行った場合、ステータス変更中（transition中）でも内部的にはtransition完了を待たずにステータスは切り替わる。

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwChanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| トグルスイッチの状態が変わった時に発生 |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | status | String | トグルスイッチの状態 |
|  |  |  | on | On状態 |
|  |  |  | off | Off状態 |

| イベントタイプ |
|:------------- |
| cscwTap |
| **イベントのトリガ** |
| トグルスイッチがタップされた時に発生 |