[Indicator](../abstractwidgetcontents)
======

機能
---------

-   概要

> 進捗を示すビジュアルを提供する。

-   機能

> 回転する円弧を表示する。指定したパーセントの静止した円弧を描画する。
>
> 中央に、テキストあるいはグリフを配置する。それらを任意に差し替える。
>
> トランジションを付けてチェックマークグリフを中央に配置する。
>
> アプリケーションからの指示により円弧の表示を変える。アプリケーションからの指示により、回転する円弧(Activity
> indicator,)と進捗を表す静止した円弧(progress
> indicator)を相互に切り替える。

-   操作

> Indicator へのタップに応答してイベントを発生する。

-   音

> コンストラクタで鳴らすことを指定し、Indicator内にグリフ（チェックマークグリフを除く）が配置された場合は、タップ操作に伴いValid音が鳴る。

-   レイアウト

> **全体レイアウト**

| サイズ (用途) | width | height |
|:------------ |:----- |:------ |
| 小 | 24px | 24px |
| 中 | 32px | 32px |
| 大 | 48px | 48px |
| 特大 | 64px | 64px |

> **各種スタイル定義**

| サイズ (用途) | Glyph Size | Glyphのcolor <sup>＊</sup>1 | 文字列のフォント | 文字列のcolor <sup>＊</sup>1 |
|:------------ |:---------- |:--------------------------- |:--------------- |:---------------------------- |
| large (Notification Alert) |  | <br>チェックマーク：<br><br>Indicator background-color<br><br>それ以外のglyph：<br><br>Buttonに準じる<br><br> |  | Buttonに準じる |
| <br>medium<br><br>(Notification SlidingMessage)<br><br> |  | <br>チェックマーク：<br><br>Indicator background-color<br><br>それ以外のglyph：<br><br>Buttonに準じる<br><br> |  | Buttonに準じる |
| <br>table<br><br>(Table Row)<br><br> |  | <br>チェックマーク：<br><br>Indicator background-color<br><br>それ以外のglyph：<br><br>Buttonに準じる<br><br> | N/A | N/A |
| <br>small<br><br>(Text Box)<br><br> |  | <br>チェックマーク：<br><br>Indicator background-color<br><br>それ以外のglyph：<br><br>Buttonに準じる<br><br> | N/A | N/A |

> <sup>※</sup>1: Glyph, 文字列にtext-shadowは無い。
>
> **サイズ（用途）ごとのサイズ定義**

| サイズ (用途) | Indicator diameter | Background Channel Diameter | Indicator Stroke |
|:------------ |:------------------ |:--------------------------- |:---------------- |
| large (Notification Alert) |  |  |  |
| medium (Notification SlidingMessage) |  |  |  |
| table(Table Row) |  |  |  |
| small(Text Box) |  |  |  |

> 回転する円弧は、アプリケーションからの指定がない場合1/4円の円弧がおおむねで一周するスピードで回転表示する。
>
> 進捗パーセントを表示する円弧は12時方向から時計回りに伸び、100%で一周する。
>
> ＜参考＞Style Guideの記述との関係
>
> Indicatorへのタップ操作とIndicatorの表示状態は独立である。例えば、Activity
> Indicatorの
> pauseグリフタップ時に円弧の回転が止まりplayグリフに変わる振る舞いは、Indicator
> ではなくアプリケーションが司る。
>
> Style Guideではactive
> indicatorがプロセス終了後3秒は表示されることを規定しているが、この動作はアプリケーションが行う。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> Indicator は、RTL表示をサポートしない。
>
> Indicatorの中央に進捗を数値で表示する場合、アラビア語であっても算用数字で表示する。
> API仕様上は、Indicatiorの中央に任意文字列を表示できるが、デザインの規定では、例えば
> 30%　というようなパーセント表記しか用いない。そのため、Indicatorの中央に表示する文字列は常にltrで表示する。
>
> Resumeを示す右向き三角形のグリフは、RTL表記であっても右向き三角形の字形とする。

API Documentation
---------

-   オブジェクト名

> indicator

-   コンストラクタ

> $.cscwGeneralActivityIndicator(\[options\]) :Indicatorを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |     |
|:------- |:--- |
| Markup | &lt;div id=”Indicator”&gt;&lt;/div&gt; |
| Script | $(“#Indicator”).cscwGeneralActivityIndicator(); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description	| Default |
|:-------- |:---- |:----------- |:------- |
| size | String | <br>Indicatorのサイズ<br><br>large<br><br>medium<br><br>small<br><br> | small |
| status | String | <br>円弧の表示状態<br><br>running　回転する円弧<br><br>stop　停止した円弧<br><br>規定の文字列以外を指定しないこと。<br><br> | stop |
| activityFrame | Integer | 1周あたりのフレーム数 | 12 |

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> なし

-   メソッド

| .cscwCall(“status”, status) |     |     |     |
|:--------------------------- |:--- |:--- |:--- |
| Indicatorの円弧の表示状態を設定する。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| status | String | 円弧の表示状態 | |
| | | running | 回転する円弧 |
| | | stop | 停止した円弧 |

| .cscwCall(“status”) |     |     |     |
|:------------------- |:--- |:--- |:--- |
| Indicatorの円弧の表示状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | 円弧の表示状態 | |
| | | running | 回転する円弧 |
| | | stop | 停止した円弧 |
