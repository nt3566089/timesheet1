[Text Field](../abstractwidgetcontents)
======

機能
----------

-   概要

> カーソル表示を伴う1行の入力フィールド。

-   機能

> 入力用フィールドを表示する。
>
> Keyboardと連携し、それらから入力した値やハードキーで入力した値（T.B.D.）をボタン上に表示する。
>
> 入力可能な最長文字列が指定されている場合は、最長文字列長を超える入力を抑止する機能を持つ。ただし、本機能は、明示的に入力手段から文字単位の入力イベント（keypress）が上がってきたときのみ作用し、最長文字列長を超過した初期値で初期化された場合、メソッドを利用して値が書きかえられた場合、あるいはコピー＆ペーストなどの手段により入力が更新された場合、については、ケアしない。

-   操作

> Off状態のフィールドをタップすると表示状態を変更するとともに、連携する入力手段が設定されている場合は該入力手段を表示し、入力済みのテキストがあれば全選択される
>
> 入力可能状態では、フィールド上のタップ、ダブルタップ、トリプルタップを受け付け、それぞれ、カーソルの移動、語句選択、全選択、として機能する。
>
> 入力が開始されたタイミングで、クリアボタンを表示することができる。クリアボタンは、押下を受け付けると入力中文字をクリアする。
>
> フィールドの見た目の大きさに対して内部の文字列が長い場合には、領域の端にマスクが表示されるとともに、横方向のフリックを受け付け、スクロールする。

-   音

> コンストラクタで鳴らすことを指定した場合は、操作を受け付けるとvalid音が鳴る。同じく、コンストラクタで鳴らすことを指定した場合は、操作を受け付けない場合にinvalid音が鳴る。ただし、クリアボタン押下時のvalid音鳴動については、コンストラクタによる指定の影響を受けない。
>
> On状態のフィールドの内部のタップ（カーソル移動など）については、鳴動しない。

-   レイアウト

入力フィールドを視覚的に表す角丸の矩形領域である。矩形領域内には、実際の文字列入力フィールドおよび必要に応じてクリアボタンが配置される。

クリアボタンは、入力中、何らかの入力文字が存在するときにのみ表示される。Off状態におけるフィードバック文字列表示時、および、wartermark文字列表示時は、クリアボタン出現領域は考慮されず、文字列表示領域の一部として扱われるレイアウトとなる。

**一般的なテキストフィールド**

**ラベルおよびクリアボタンが付与された場合**

RTL表記でのレイアウト

グリフ、ラベルおよびWatermark,

グリフ、ラベル、入力中の文字列とクリアボタン

フィードバック文字列の表示例。textAlignがnormalの場合(上)とautoの場合(下)。

参考: RTLでのレイアウト (別案) –
ラベルはRTLの書き順に合わせて右に配置する案は採用しない。

この場合、ラベルと入力値の関係はより適切になるが、おなじような役割を持つアイコンは左端という配置の不統一さが現れるので採用しないことにした。

**各種スタイル定義（上段:5inch / 下段:10inch）**

|

<table>
<thead>
<tr class="header">
<th>size</th>
<th>height</th>
<th>width</th>
<th>font*1</th>
<th>Glyph</th>
<th>Image</th>
<th>Left inside padding</th>
<th><p>Right</p>
<p>inside padding,</p>
<p>Right</p>
<p>icon-text margin</p></th>
<th>Icon-label margin</th>
<th>cursor padding</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>small</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>medium</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>large</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

\*1　ただし、ラベルおよびWaterMark文字列については、font-weightとしてlightを適用

なお、領域内に他のアイテム（ボタンなど）を配置する必要がある場合は、その大きさを考慮して、文字列入力フィールドの大きさを設定することで対応する。マージン値は、全てアプリケーション指定とする。

> **色の定義(TextInput)**

<table>
<thead>
<tr class="header">
<th></th>
<th>background-color</th>
<th>border-color</th>
<th>color</th>
<th>opacity</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Default</td>
<td>#1a1b1f</td>
<td>#7e8799</td>
<td>#ffffff</td>
<td>-</td>
</tr>
<tr class="even">
<td>Focus</td>
<td>-</td>
<td>#37c6d9</td>
<td>-</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Placeholder</td>
<td>-</td>
<td>-</td>
<td>#ffffff</td>
<td>0.5</td>
</tr>
<tr class="even">
<td>Caret</td>
<td>-</td>
<td>-</td>
<td>#666666</td>
<td>-</td>
</tr>
</tbody>
</table>

> **フォントの定義**
<table>
<thead>
<tr class="header">
<th></th>
<th>size</th>
<th>glyph</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>5inch</td>
<td>26px</td>
<td>32px</td>
</tr>
<tr class="odd">
<td>10inch</td>
<td>-</td>
<td>-</td>
</tr>
</tbody>
</table>

**マージンを設けた場合**

カーソル位置は、マージンエリアを除いた実際の入力可能エリア内で制御される。

つまり、中央揃えを指示した場合、入力文字列は、矩形の中央ではなく、マージンエリアを除いた領域内の中央に表示される。

適用される色情報は、入力フィールドのステイタスとApplication Thema,
Container Thema から決定される。

なお、WaterMark文字列については、通常のfont指定に対してopacity とする。

クリアボタンの色は、クリアボタン表示時に適用されているfont色に対してopacity
とし、クリアボタンプレス時にはopacity つまりfont指定色と同一となる。

Open時、フィールドの見た目の大きさに対して内部の文字列が長い場合には、表示しきれていないことを示すためにフィールドの片側もしくは両側の端の範囲に対して、背景色と透過0.2のグラデーションによるマスクが表示される。Close時は、必要に応じてtruncateが適用される。

詳細はスタイルガイド（TextField&Areaの項）を参照のこと。

ただし、選択中文字列の色彩は、スタイルガイド規定値ではなくブラウザ仕様に従う。

> &lt;RTL表記でのレイアウトについて&gt;
>
> 生成オプションに従いLTR表示またはRTL表示でテキストの入力を受け付ける。
>
> LTR/RTL表示に関わらず、アイコン、クリアボタンの配置は変わらない。入力テキストが右寄せ表示の場合、空の場合は、右端にカーソルが表示されるが、一文字入力するとクリアボタンが現れて文字とカーソルの位置が左に移動する。
>
> LTR/RTL表示に関わらず、ラベルは枠内に左寄せで配置する。ラベルの左寄せ/右寄せは入力テキストの左寄せ/右寄せとは無関係。
>
> watermarkの表示位置(右寄せ/左寄せ)
> は、入力テキストの左寄せ/右寄せに連動する。

-   Transition

> On状態からOff状態への移行：　durationは。
>
> Off状態からOn状態への移行： 　durationは。

-   キーボードとフィールドのpadding

> キーボード表示時のキーボードの上端とフィールドの下端のpaddingの最小値は、
>
> SuggestionPanelの表示がない場合10”UIで、5”UIでである。
>
> SuggestionPanelの表示がある場合10”UI, 5”UI共にである。
>
> キーボード表示の際に上記paddingが確保できない場合には画面のスクロール位置が自動的に調整される。

API Documentation
----------

-   オブジェクト名

> textField

-   コンストラクタ

> $.cscwTextField(\[options\]) :入力フィールドを生成するコンストラクタ
>
> 適用可能なタグ : div

| Example |   |
|:------- |:--- |
| Markup | &lt;div id=”TextField” class=”cscw-textField&gt;&lt;/div&gt; |
| Script | $(“#TextField”).cscwTextField(); |

-   オプション

> 生成時のオプションとして以下を任意に指定できる。

| Property | Type | Description | Default |
|:-------- |:---- |:----------- |:------- |
| width | Integer | <br>入力フィールド外形の幅(pixel)<br><br>指定無き場合は、cssによる指定が適用される。<br><br>cssによりmin-widthが指定されている場合、min-widthより小さい値を設定してもmin-widthが優先される。<br>max-widthが指定されている場合も同様に、max-widthより大きい値を設定してもmax-widthが優先される。<br><br> | null |
| dir | String | <br>テキストを書き進む方向を指定する。<br><br>global　表示言語の共通初期設定に従う<br><br>ltr　左から右へ書き進む<br><br> | global |
| watermark | String | <br>ウォーターマーク文字列*2。改行を含んではならない。<br><br> | null |
| clearButton |  | <br>true　入力が開始されたら、クリアボタンを表示する。<br><br>false　クリアボタンを表示しない<br><br> | false |
| passwordMode | Boolean | <br>true　入力文字列、およびフィードバック文字列を伏せて表示<br><br>false　通常表示<br><br> | false |
| value | String | 入力の初期値。改行を含んではならない。 | null |
| feedbackValue | String | <br>Off状態のフィールド内に表示するフィードバック文字列の初期値。改行を含んではならない。実際の描画内容は、後述するtruncate / ellipsisの設定に応じて判断される。<br><br>設定無き場合は、valueと同等の文字列が適用される。<br><br> | null |
| truncate | String | <br>フィードバック文字列長が領域を超過したときの省略描画の適用*1<br><br>null　超過が起きない場合に使うことを前提とする。超過した場合は省略表示をせず、超過分は表示されない。<br><br>end　文字列の前方を優先して表示し、領域を超過した後方を省略表示とする。<br><br>middle　文字列の前方と後方を優先して表示し、文字列の中央を省略表示する。<br><br>begin　文字列の後方を優先して表示し、領域を超過した前方を省略表示とする。<br><br>規定の文字列以外を指定しないこと。<br><br> | null |
| ellipsis | String | 省略表示の際に、3点リーダの代わりに表示する文字列またはグリフコード | "\u2026" |
| maxLength | Integer | <br>受け付け可能な最大文字列長<br><br>IME動作中は指定した文字列長を超えて入力できる。確定後の文字列長が指定した文字列長を超える場合、超過分は切り捨てられる。<br><br> | null |
| status | String | <br>入力フィールドの状態<br><br>off　Off状態<br><br>on　On状態<br><br>on/off以外の文字列を指定しないこと。 | off |
| enable | Boolean | <br>入力フィールドの有効/無効<br><br>true 有効<br><br>false 無効<br><br> | true |
| keyboard | Object | <br>入力手段として用いられるキーボードおよびスライド型キーパッドの情報<br><br>省略の際は、後述のkeyboardオブジェクトのデフォルト値が適用される。<br><br> | null |
| embeddedKeypad | Object | <br>連携する入力用キーパッド。<br><br>（EmbeddedKeypad）<br><br> | null |
| actionEventHandler | Function | <br>キーボード内のPrimaryキー/Dismissキーが押下された際に呼び出されるコールバック関数。<br><br>※[TextArea] actionEventHandlerに設定する関数の定義を参照<br><br> | null |
| soundEnable | Boolean | <br>Widgetによる操作音(valid音)の鳴動制御<br><br>true 操作音を鳴らす<br><br>false 操作音を鳴らさない<br><br> | true |
| invalidSoundEnable | Boolean | <br>Widgetによる操作音(invalid音)の鳴動制御<br><br>true 操作音を鳴らす<br><br>false 操作音を鳴らさない<br><br> | true |
| textAlign | String | <br>入力文字列の位置（水平方向）<br><br>left　左揃え<br><br>center　中央揃え<br><br>right　右揃え<br><br>auto テキストを書き進む方向が、ltrなら左揃え、rtlなら右揃え<br><br>normal statusがoffの時は左揃え。statusがonの時はテキストを書き進む方向がltrなら左揃え、rtlなら右揃え<br><br>left/auto/normal以外の文字列を指定しないこと。<br><br> | normal |

> \*1　ここで領域超過判断に用いられるのは、「領域サイズ」であり、maxLengthは無関係である。
>
> \*2　WaterMark文字列は、feedbackValueおよびvalueの双方が空である場合に表示される。

-   keyboardで使用するObjectの定義

> 「keyboardパラメータ」の項を参照。正規表現の詳細についても、「keyboardパラメータ」の項を参照。

-   オプション相当情報のMarkupによる指定

> なし

-   オプション相当情報のCSSによる指定

> コンストラクタをコールする要素に対して、widthを指定することで幅を指定できる。
>
> 高さについては、CSSによる指定はできない。（スタイルガイドを逸脱した指定がなされた際の影響が、外形の高さだけにとどまらないため）
>
> Example:　　\#textfield{ width:100px}

-   メソッド

| .cscwCall(“status”, status) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| <br>入力フィールドの状態を切り替える。<br><br>IME動作中に本メソッドによりoff状態になる場合、入力中の文字列は無変換確定された上で処理される。<br><br>on/off以外の文字列を指定しないこと。 |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |
| status | String | 入力フィールドの状態 |  |
|  |  | on | On状態 |
|  |  | off | Off状態 |

| .cscwCall(“status”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| 入力フィールドの状態を取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | 入力フィールドの状態 |  |
|  |  | on | On状態 |
|  |  | off | Off状態 |

| .cscwCall(“enable”, enable) |   |   |   |
|:--------------------------- |:--- |:--- |:--- |
| <br>入力フィールドの有効/無効を切り替える。<br><br>IME動作中に本メソッドによりoff状態になる場合、入力中の文字列は無変換確定された上で処理される。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |
| enable | Boolean | <br>入力フィールドの有効/無<br><br>効<br><br> |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“enable”) |   |   |   |
|:------------------- |:--- |:--- |:--- |
| 入力フィールドが有効かどうかを取得する。 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Boolean | 入力フィールドの有効/無効 |  |
|  |  | true | 有効 |
|  |  | false | 無効(Disable状態) |

| .cscwCall(“watermark”, watermark) |   |   |
|:--------------------------------- |:--- |:--- |
| ウォーターマーク文字列を設定する。 |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| watermark | String | ウォーターマーク文字列 |

| .cscwCall(“watermark”) |   |   |
|:---------------------- |:--- |:--- |
| ウォーターマーク文字列を取得する。<br><br>ウォーターマーク文字列が設定されていない場合はnullを返す。<br><br> |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | ウォーターマーク文字列 |  |

| .cscwCall(“value”, value) |   |   |   |
|:------------------------- |:--- |:--- |:--- |
| <br>入力フィールドに値を入力する。入力した値はフィールド内に表示される。<br><br>本メソッドによる値の設定時は、コンストラクタで指定されたmaxLengthを超えて設定することができる。その場合、評価結果はfalseとなる。<br><br>IME動作中に本メソッドが呼び出された場合、入力中の文字列はクリアされ、valueが入力される。この際Widgetはoff状態となりキーボードは閉じられる。<br><br> |  |  |  |
| 引数の説明 |  |  |  |
| **name** | **type** | **description** |  |
| value | String | 入力フィールド内に表示する値 |  |
| 戻り値 |  |  |  |
| **name** | **type** | **description** |  |
|  | Boolean | valueの評価結果 |  |
|  |  | true | <br>真で<br>ある<br><br> |
|  |  | false | <br>偽で<br>ある<br><br> |

| .cscwCall(“value”) |   |   |
|:------------------ |:--- |:--- |
| 入力フィールド内の値を取得する。<br><br>入力フィールド内の値が設定されていない場合はnullを返す。<br><br>	 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | 入力フィールド内の現在の値 |  |

| .cscwCall(“maxLength”, maxLength) |   |   |
|:--------------------------------- |:--- |:--- |
| 入力文字列として許容される最大文字列長を設定する。<br><br>すでに入力されている文字列長より小さい値を設定した場合、超過分は切り捨てられない。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| maxLength | Integer | 最大文字列長 |

| .cscwCall(“maxLength”) |   |   |
|:---------------------- |:--- |:--- |
| 入力文字列として許容される最大文字列長を取得する。<br><br>最大文字列長が設定されていない場合はnullを返す。<br><br>		 |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | Integer | 最大文字列長 |  |

| .cscwCall(“feedbackValue”, feedbackValue) |   |   |
|:----------------------------------------- |:--- |:--- |
| <br>フィードバック文字列を設定する。<br><br>入力した値は、elipsis/truncate　指示に従った加工を行った上で、Off状態のフィールド内に表示される。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| feedbackValue | String | 入力フィールド内に表示する値 |

| .cscwCall(“feedbackValue”) |   |   |
|:-------------------------- |:--- |:--- |
| フィードバック文字列を取得する。<br><br>フィードバック文字列が設定されていない場合はnullを返す。<br><br> |  |  |  |
| 戻り値 |  |  |  |
|  | **type** | **description** |  |
|  | String | フィードバック文字列として設定されている現在の値 |  |

| .cscwCall(“selected”, selected) |   |   |   |   |   |
|:------------------------------- |:--- |:--- |:--- |:--- |:--- |
| <br>入力フィールド内文字列の選択状態を、現在の選択状態に関わらず、指定の選択状態に切り替える。<br><br>IME動作中は本メソッドの呼び出しは無視される。<br><br> |  |  |  |  |  |
| 引数の説明 |  |  |  |  |  |
| **name** | **type** | **description** |  |  |  |
| selected | <br>Boolean<br><br>Object<br><br> | 入力フィールド内文字列の選択状態 |  |  |  |
|  |  | Booleanによる指定 |  |  |  |
|  |  |  | true | 全選択状態 |  |
|  |  |  | false | 非選択状態 |  |
|  |  | Objectによる指定 |  |  |  |
|  |  |  | **property** | **property type** | **description** |
|  |  |  | selectionStart | Integer | 選択開始位置 |
|  |  |  | selectionEnd | Integer | 選択終了位置 |

| .cscwCall(“insert”, insert) |   |   |
|:--------------------------- |:--- |:--- |
| <br>入力フィールド内のカーソル位置に文字列を挿入する。<br><br>文字列が選択状態の場合、選択状態の文字列を指定の文字列に置き換える。また、最大文字列長を超えて文字列を挿入することはできない。その場合、評価結果はfalseとなる。<br><br>IME動作中は本メソッドの呼び出しは無視される。<br><br> |  |  |
| 引数の説明 |  |  |
|  | **type** | **description** |
| insert | String | 挿入する文字列 |
| 戻り値 |  |  |  |
| **name** | **type** | **description** |  |
|  | Boolean | 挿入後文字列の評価結果 |  |
|  |  | true | <br>真で<br>ある<br><br> |
|  |  | false | <br>偽で<br>ある<br><br> |

| .cscwCall(“keyboard”, keyboard) |   |   |
|:------------------------------- |:--- |:--- |
| <br>入力時に自動表示されるキーボードに与える情報を変更する。<br><br>本メソッドは、キーボード表示中も動作する。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| keyboard | Object | <br>キーボードに与える情報<br><br>（詳細は、コンストラクタオプション説明　keyboard　Objectの定義を参照）<br><br> |

| .cscwCall(“keyboard”) |   |   |
|:--------------------- |:--- |:--- |
| 現在のキーボード情報を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Object	| <br>キーボードに設定されている情報<br><br>（詳細は、コンストラクタオプション説明　keyboard　Objectの定義を参照）<br><br> |

| .cscwCall(“width”, width) |   |   |
|:------------------------- |:--- |:--- |
| 入力フィールドの幅を変更する。<br><br>cssによりmin-widthが指定されている場合、min-widthより小さい値を設定してもmin-widthが優先される。<br>max-widthが指定されている場合も同様に、max-widthより大きい値を設定してもmax-widthが優先される。<br><br> |  |  |
| 引数の説明 |  |  |
| **name** | **type** | **description** |
| width | Integer | 入力フィールドの幅 |

| .cscwCall(“width”) |   |   |
|:--------------------- |:--- |:--- |
| 入力フィールドの幅を取得する。 |  |  |
| 戻り値 |  |  |
|  | **type** | **description** |
|  | Integer | 入力フィールドの現在の幅 |

-   イベント

| イベントタイプ |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |
| cscwChanged |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |
| widgetの状態が変わった時に発生 |  |  |  |  |
| 戻り値 |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |
| Object | status | String | Widgetの状態 |  |
|  |  |  | on | On状態 |
|  |  |  | off | Off状態 |

| イベントタイプ |
|:------------- |
| cscwTap |
| **イベントのトリガ** |
| Off状態にて、Widget自身がタップされた時に発生。 |

| イベントタイプ |   |   |   |   |   |
|:------------- |:--- |:--- |:--- |:--- |:--- |
| cscwValueChanged |  |  |  |  |  |
| **イベントのトリガ** |  |  |  |  |  |
| 入力フィールド内の値が変わった時に発生 |  |  |  |  |  |
| 戻り値 |  |  |  |  |  |
| **type** | **property** | **property type** | **description** |  |  |
| Object | value | String | 入力フィールドの値 |  |  |
|  | maxLength | Integer | 最大文字列長 |  |  |
|  |  |  | **property** | **property type** | **description** |
|  | previous | Object | value | String | 変更前の文字列 |
|  |  |  | selectionStart | Integer | 変更前の文字列選択開始位置 |
|  |  |  | selectionEnd | Integer | 変更前の文字列選択終了位置 |
|  | current | Object | value | String | 変更後の文字列 |
|  |  |  | selectionStart | Integer | 変更後の文字列選択開始位置 |
|  |  |  | selectionEnd | Integer | 変更後の文字列選択終了位置 |
|  | imInfo | Object | state | String / null | <br>[“update”] IME動作中の更新による変化通知<br><br>[“end”] IME確定による変化通知<br><br>[null]<br><br>IME未使用時の変化通知<br><br> |
|  |  |  | data | String | <br>	[state:“update”の場合]<br><br>変換中の文字列<br><br>[state:”end”の場合]<br><br>確定した文字列<br><br>[stateがnullの場合]<br><br>空文字<br><br> |