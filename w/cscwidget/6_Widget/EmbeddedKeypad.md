[Embedded Keypad](../abstractwidgetcontents)
======

機能
----------------

-   概要

> 数値入力用のキーパッド。画面内に埋めこんで利用する。
>
> 長さや量などの数値を入力するときに使用。
> Numeric Text Boxとセットで用いる。
>
> 1～0の数字と、小数を入力させる場合は左下に小数点を配置し、
> 右下にはクリアキーまたはバックスペースキーを配置する。


-   機能

> キーパッドを表示する。

キーパッド内のボタンのタップを受けつけ、関連づけられた入力フィールドに対して値を入力する。

> キーパッド内クリアキーのタップを受け付けた場合は、関連付けられた入力フィールドに対してその旨を通知する。クリアキーがタップされたことによる振る舞いは、入力フィールド側に設定されたインプットモデルに依存して決定される。なお、この挙動は、キーパッド内クリアキーの見た目（グリフ）によらず一定である。
>
> なお、Embedded
> Keypadによる数値キーのタップでは、InputFieldの値の確定処理は行われないため、アプリケーションは適切なタイミングで値の確定を指示する必要がある。
>
> キーパッドのタイプと、InputField側の設定は整合が取れている必要がある。詳細はInputFIeldの項の組み合わせに関する記述を参照のこと。

-   操作

> 各キーのタップにより、表示状態を変更し、値の入力などを行う。

-   音

> キーパッド上のボタン操作受付時は、連携したInputField側の受け入れ可否判断に基づいて、valid音もしくはinvalid音が鳴る。　

-   レイアウト

> **全体レイアウト**
>
> **各種スタイル定義**

<table>
<thead>
<tr class="header">
<th></th>
<th>Button Width</th>
<th>Button Height</th>
<th><p>Border-width</p>
<p>色に関する属性</p></th>
<th>font-size</th>
<th>font-weight</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>5inch</td>
<td>158px</td>
<td>80px</td>
<td>2px</td>
<td>26px</td>
<td>-</td>
</tr>
<tr class="even">
<td>10inch</td>
<td>114px</td>
<td>57px</td>
<td>同上</td>
<td>22px</td>
<td>同上</td>
</tr>
</tbody>
</table>

> **Whole Number type と　Decimal Typeのキー配置**
>
> **Integer Type のキー配置**
>
> 上記レイアウト図で、Glyphと書かれたキーには、clear\_allもしくはbackspceを示すGlyphが配置される。
>
> &lt;RTL表記でのレイアウトについて&gt;
>
> Embedded Keypadは、RTL表記/LTR表記に関わらず一定で変更はない。
>
> Embedded Keypadのキー配置は、表示言語やLTR/RTLの別にかかわりなく一定。
>
> Embedded Keypadは数値に表示言語に関わりなく算用数字を用いる。
>
> Embedded Keypadのglyphは、常にLTR表記で表示する。

API Documentation
---------------

-   オブジェクト名

> embeddedKeypad

-   コンストラクタ

> $.cscwEmbeddedKeypad (\[options\]) :
> 埋め込み型キーパッドを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”keypad”&gt;&lt;/div&gt; |
| Script | $(“#keypad”).cscwEmbeddedKeypad(); |

-   オプション

| **Property** | **Type** | **Description** | **Default** |
|:------------ |:-------- |:--------------- |:----------- |
| type | String | <br>キーセットのタイプ<br><br>下記以外の値を指定しないこと<br><br>"wholeNumber"：0-9の数値<br><br>"decimal"：0-9の数値と.(dot)<br><br>"integer"：0-9の数値と+/-<br><br> | "wholeNumber" |
| clearGlyph | String |  <br>クリアボタンに表示されるグリフの指定<br><br>下記以外の値を指定しないこと<br><br>"clear"：クリアグリフが表示される<br><br>"clearAll"：クリアオールグリフが表示される<br><br>"backSpace"：バックスペースグリフが表示される | "clear" |

-   オプション相当情報のMarkupによる指定

なし

-   オプション相当情報のCSSによる指定

なし

-   メソッド

| .cscwCall(“target”, target) |   |   |
|:--------------------------- |:--- |:--- |
| キーパッドの表示ターゲットを変更する |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| target | jQuery Object | キーパッドの表示ターゲットとする要素（InputField） |


-   イベント

> 以下は、ハードキーを利用する場合に考慮されるべき事項である。
>
> キーパッドはキーイベントを受けて入力フィールドに対し値の入力を行うが、キーイベントの伝播は継続される。イベントオブジェクトを参照することで、伝播したイベントが既に使用済みであるかが判断することができる。

<span class="underline">関連イベント処理</span>

| Event type: keypress |   |   |
|:------------------- |:--- |:--- |
| keypressイベントを処理した場合に以下のプロパティを設定する。 |  |  |
| Properties |  |  |
| **name** | **type** | **description** |
| cscwConsumed | Boolean | <br>イベントがWidgetによって処理されたかどうか<br><br>true 処理された<br><br>false 処理されていない<br><br> |

| Event type: keydown |   |   |
|:------------------- |:--- |:--- |
| keydownイベントを処理した場合に以下のプロパティを設定する。 |  |  |
| Properties |  |  |
| **name** | **type** | **description** |
| cscwConsumed | Boolean | <br>イベントがWidgetによって処理されたかどうか<br><br>true 処理された<br><br>false 処理されていない<br><br> |