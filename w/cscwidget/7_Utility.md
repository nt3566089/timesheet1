7.0. ユーティリティ
==============

ここでは、Widgetが内部コードとして利用している汎用メソッドのうち、アプリケーションにも有用なものを開示する。

7.1 StrUtil
-------

-   クラス定義

> $.cscw.StrUtil

-   メソッド

<table>
<thead>
<tr class="header">
<th>.truncateString(str, element, width, pos)</th>
<th></th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>文字列を、与えられた表示幅に表示可能な省略符号を使った形に変換する。</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>引数の説明</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>name</td>
<td>type</td>
<td>description</td>
<td></td>
</tr>
<tr class="even">
<td>str</td>
<td>String</td>
<td>表示したい文字列</td>
<td></td>
</tr>
<tr class="odd">
<td>element</td>
<td>jQueryObject</td>
<td>幅計算に必要なスタイル情報を提供する要素</td>
<td></td>
</tr>
<tr class="even">
<td>width</td>
<td>Integer</td>
<td>表示可能幅</td>
<td></td>
</tr>
<tr class="odd">
<td>pos</td>
<td>String</td>
<td>省略符号適用位置</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>begin</td>
<td>文字列の先頭を省略する。</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>end</td>
<td>文字列の最後を省略する。</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th>戻り値</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><strong>type</strong></td>
<td><strong>description</strong></td>
</tr>
<tr class="even">
<td></td>
<td>String</td>
<td>省略表記を適用した文字列</td>
</tr>
</tbody>
</table>

-   注意事項

> 本メソッドは、指定文字列をコード単位で増減させて、最適幅の省略表記を生成する。
>
> 文字の中には、2つ以上のコードで一文字を表すものが存在するが、本メソッドではサロゲートペアのみをサポートし、一部のアクセント記号や、タイ語等に存在する合字の制御は行っていない。
>
> 従って、これらの文字を含む文字列の省略表記生成が正しく行われないケースが存在する。

<table>
<thead>
<tr class="header">
<th>.strWidth(str, element)</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>文字列の表示幅を算出する。</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>引数の説明</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>name</td>
<td>type</td>
<td>description</td>
</tr>
<tr class="even">
<td>str</td>
<td>String</td>
<td>表示したい文字列</td>
</tr>
<tr class="odd">
<td>element</td>
<td>jQueryObject</td>
<td>幅計算に必要なスタイル情報を提供する要素</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th>戻り値</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><strong>type</strong></td>
<td><strong>description</strong></td>
</tr>
<tr class="even">
<td></td>
<td>Integer</td>
<td>文字列の表示幅（px）</td>
</tr>
</tbody>
</table>

7.1 KbUtil
------

-   概要

> キーボードを適切に使用するためのユーティリティである。

-   クラス定義

> $.cscw.KbUtil

-   メソッド

<table>
<thead>
<tr class="header">
<th>.setActionEventHandler (handler)</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>キーボード内のプライマリキーおよびdismissキーが押下された際のキーボードの動作および鳴動音を、アプリケーションが制御するためのコールバック関数を登録する。</p>
<p>キーがdisable状態の場合にもコールバックは呼ばれる。</p>
<p>キーボードのプライマリキーの設定がreturnの場合にはコールバックは呼ばれない。</p>
<p>コールバックが設定されずにプライマリキーおよびdismissキーが押下された場合、キーボードは非表示になり、操作音validが鳴動する。</p>
<p>ハードウェアキーボードのEnterキーが押下された場合、ソフトウェアキーボードのプライマリキーが押下されたものとしてプライマリキーの表示に応じたtypeがコールバックで通知される</p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>引数の説明</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>name</td>
<td>type</td>
<td>description</td>
</tr>
<tr class="even">
<td>handler</td>
<td>Function</td>
<td>FunctionのI/Fを別途記載する。</td>
</tr>
</tbody>
</table>

-   handlerに設定する関数の定義

<table>
<thead>
<tr class="header">
<th>handler()</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>キーボード内のプライマリキーおよびdismissキーが押下された際にコールされるコールバック関数。</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>引数の説明</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>name</td>
<td>type</td>
<td>description</td>
</tr>
<tr class="even">
<td>type</td>
<td>String</td>
<td><p>押下されたキーの種別を表す文字列。</p>
<p>“dismiss”, “enter”, “ok”, “search”, “done”, “next”のいずれか</p></td>
</tr>
<tr class="odd">
<td>id</td>
<td>String</td>
<td>現在入力中のWidgetに付与されたid文字列。</td>
</tr>
<tr class="even">
<td>戻り値</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>type</td>
<td>description</td>
</tr>
<tr class="even">
<td></td>
<td>String</td>
<td><p>”okClose”, “ngClose”, “okContinue”, “ngContinue”, Deferred Objectのいずれか。(obsolete： “ok”, “ng”, “continue”)</p>
<p>プライマリキーおよびdismissキーを押下した後のキーボードの動作および鳴動音を指定する。</p>
<p>戻り値を返さない場合/上記以外の文字列が返却された場合、”okClose”返却時と同様のふるまいとなる。</p>
<p><strong>“okClose”</strong>：入力完了と判断し、プライマリキーまたはdissmissの動作を行う。(typeが‘next’の場合は、次の入力可能領域にフォーカスが移動し、他のtypeの場合は、現在の入力可能領域からフォーカスがはずれ、キーボードが非表示になる。)操作音validが鳴動する。</p>
<p><strong>“ngClose”</strong>：”okClose”同様にフォーカスがはずれ、キーボードが非表示になる。操作音invalidが鳴動する。</p>
<p><strong>“okContinue”</strong>： フォーカス、キーボードの表示状態は不変。操作音validが鳴動する。</p>
<p><strong>“ngContinue”</strong>：フォーカス、キーボードの表示状態は不変。操作音invalidが鳴動する。</p>
<p><strong>Deferred Object</strong>： resolveする際の引数には”okClose”, “ngClose”, “okContinue”, “ngContinue”, (obsolete： “ok”, “ng”, “continue”)を指定する。
<p>互換性維持のため"ok", "continue", "ng"は残す。それぞれ"okClose", "okContinue", "ngContinue"と同等。</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th>.setFocusEventHandler (handler)</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>キーボードの表示/非表示の際の画面構成等をアプリケーションが制御することを目的とする。</p>
<p>キーボードと連携するTextField, TextArea, およびTextFieldList内の入力可能領域へのフォーカスイン/アウトが発生した場合に実行されるコールバック関数を登録する。</p>
<p>キーボードの表示/非表示とコールバックが呼ばれるタイミングは以下の通り。</p>
<p>フォーカスイン時： キーボード表示前</p>
<p>フォーカスアウト時： キーボード非表示前</p>
<p>本メソッドを複数回呼び出した場合、設定したすべてのhandlerに対して通知される。</p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>引数の説明</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>name</td>
<td>type</td>
<td>description</td>
</tr>
<tr class="even">
<td>handler</td>
<td>Function</td>
<td>FunctionのI/Fを別途記載する。</td>
</tr>
</tbody>
</table>

-   handlerに設定する関数の定義

<table>
<thead>
<tr class="header">
<th>handler()</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>キーボードと連携するTextField, TextArea, およびTextFieldList内の入力可能領域へのフォーカスイン/アウトが発生したときに実行されるコールバック関数。</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>引数の説明</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>name</td>
<td>type</td>
<td>description</td>
</tr>
<tr class="even">
<td>type</td>
<td>String</td>
<td><p>入力可能領域に発生したフォーカスイン/フォーカスアウトを区別する文字列。</p>
<p>フォーカスイン: “focus”が設定される</p>
<p>フォーカスアウト: “blur”が設定される</p></td>
</tr>
<tr class="odd">
<td>id</td>
<td>String</td>
<td>フォーカスイン/フォーカスアウトが発生したWidgetのid文字列が設定される。Widgetにidが設定されていない場合は空文字列が設定される。</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th>.setFaxGroupButtonEventHandler (handler)</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Fax種別指定グループキーがユーザにより選択された際に実行されるコールバック関数を登録する</p>
<p>Keyboardパラメータtype:ewb, typeForEwb:faxAllのキーボードを利用する場合に呼び出す。</p>
<p>押下されたグループキーがDisableであった場合にはコールバック関数は呼ばれない。</p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>引数の説明</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>name</td>
<td>type</td>
<td>description</td>
</tr>
<tr class="even">
<td>handler</td>
<td>Function</td>
<td>FunctionのI/Fを別途記載する。</td>
</tr>
</tbody>
</table>

-   handlerに設定する関数の定義

<table>
<thead>
<tr class="header">
<th>handler()</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Fax種別指定グループキーが選択された際にコールされるコールバック関数。</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>引数の説明</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>name</td>
<td>type</td>
<td>description</td>
</tr>
<tr class="even">
<td>type</td>
<td>String</td>
<td><p>選択された<strong>Fax種別指定グループキー</strong>種別を表す文字列。</p>
<p>“fax_line”, “ext”, “ip”のいずれか。</p>
<p>“fax_line”：FaxまたはLineが選択された</p>
<p>“ext”:：Extが選択された</p>
<p>“ip”：IP Faxが選択された</p></td>
</tr>
<tr class="odd">
<td>id</td>
<td>String</td>
<td>現在入力中のWidgetに付与されたid文字列。</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th>.setKbdHeight (height)</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アプリケーションが独自キーボードを表示する際に利用する。</p>
<p>アプリケーションがキーボードのtypeをelseに設定して独自キーボードを表示する場合、表示するキーボードの高さ(px)を指定する。設定された時点で必要に応じてスクロール位置の調整を行う。</p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>引数の説明</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>name</td>
<td>type</td>
<td>description</td>
</tr>
<tr class="even">
<td>height</td>
<td>Integer</td>
<td>独自キーボードの高さ(px)</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th>.setSuggestionPanelHeight (height)</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Suggestion Panelの高さ(px)を指定する。設定された時点で必要に応じてスクロール位置の調整を行う。Suggestion Panel Widgetからの利用を想定しており、アプリケーションは本関数を明示的に利用する必要はない。</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>引数の説明</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>height</td>
<td>Integer</td>
<td>Suggestion Panelの高さ(px)</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th>.getKbdHeight()</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>現在表示しているキーボードの高さ(px)を返却する。</p>
<p>キーボードが非表示の状態で呼ばれた場合には-1を返却する。</p>
<p>Suggestion Panel Widgetからの利用を想定しており、アプリケーションは本関数を明示的に利用する必要はない。</p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>戻り値</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td><strong>type</strong></td>
<td><strong>description</strong></td>
</tr>
<tr class="even">
<td></td>
<td>Integer</td>
<td>現在表示しているキーボードの高さ(px)。</td>
</tr>
</tbody>
</table>

7.1 keyboardパラメータ
------------------

-   概要

> TextField、TextArea、TextFieldListなどテキスト入力系ウィジェットの生成パラメータkeyboardの共通仕様を記述する。
>
> 独立したユーティリティではないが、KbUtilとの関係性が深いので、ここに記述する。

-   keyboardで使用するObjectの定義

<table>
<thead>
<tr class="header">
<th>property</th>
<th>Type</th>
<th>内容</th>
<th>Default</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>type</td>
<td>String</td>
<td><p>text　テキスト入力用キーボード</p>
<p>email　メールアドレス用キーボード</p>
<p>phoneNum　phoneNumキーボード</p>
<p>sipAddress sipアドレスキーボード</p>
<p>faxAll　phoneNumとsipアドレスの切り替え可能キーボード</p>
<p>number　数値入力用のキーボード</p>
<p>serverFax serverFax用のキーボード</p>
<p>ewb　ブラウザ組み込みのキーボード(詳細種別はtypeForEwbで指定)</p></td>
<td>text</td>
</tr>
<tr class="even">
<td>typeForEwb*6</td>
<td>String</td>
<td><p>text　テキスト入力用キーボード</p>
<p>phoneNum　phoneNumキーボード</p>
<p>faxAll　FAX番号とsipアドレスの切り替え可能キーボード</p>
<p>serverFax　serverFax宛先番号入力用キーボード</p>
<p>serverFaxReg　serverFax宛先番号登録用キーボード</p>
<p>sipFax　IP Fax宛先入力用キーボード</p>
<p>iFax　Internet Fax宛先入力用キーボード</p>
<p>auth 　認証情報入力用キーボード</p>
<p>faxLocalName FAX自局名用キーボード</p>
<p>specialNum　特殊数字/記号用キーボード</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>layer</p>
<p>*4</p></td>
<td><p>String</p>
<p>もしくは</p>
<p>Integer</p></td>
<td><p>Keyboardの表示階層を示す値。数字が大きいものほど前面に表示される。</p>
<p>700～799</p></td>
<td>700</td>
</tr>
<tr class="even">
<td>upperMargin</td>
<td><p>String</p>
<p>もしくは</p>
<p>Integer</p></td>
<td><p>-1 スクロール動作OFF</p>
<p>0　デフォルト値を利用</p>
<p>1以上の値 　スクロール可能コンテンツ最上位点からのドット数</p></td>
<td>0</td>
</tr>
<tr class="odd">
<td>primaryKey</td>
<td>String</td>
<td><p>プライマリキー種別(動作)指定</p>
<p>return 改行</p>
<p>enter / ok / search / done / next :アプリ通知(コールバック仕様参照)。コールバック未設定時はキーボードはクローズする。</p></td>
<td>enter</td>
</tr>
<tr class="even">
<td>primaryKeyStatus</td>
<td>String</td>
<td><p>プライマリキーの状態</p>
<p>disable　無効</p>
<p>auto　有効/無効判断を自動で行う</p></td>
<td>auto</td>
</tr>
<tr class="odd">
<td>empty</td>
<td>String</td>
<td><p>文字未入力時のdisableキー指定</p>
<p>none　disableキーなし</p>
<p>primary　プライマリキー(returnを除く)をdisable</p>
<p>primaryAndDismiss　プライマリキー(returnを除く)とdismissキーをdisable</p></td>
<td>none</td>
</tr>
<tr class="even">
<td>maxReturns</td>
<td>String</td>
<td><p>Return(改行)の最大入力数を指定する。</p>
<p>プライマリキーがreturnのときのみ有効で、最大入力数に達した場合は、disable表示となる。<br />
null:制限なし</p>
<p>0以上の値　入力可能return 文字数</p></td>
<td>null</td>
</tr>
<tr class="odd">
<td><p>lang</p>
<p>*5</p></td>
<td>String</td>
<td><p>キーボード言語直接指定（キーボード言語設定画面用個別機能）</p>
<p><strong>[type:ewbを指定した場合]</strong></p>
<p>JA_ROMAJI　日本語ローマ字</p>
<p>JA_KANA"　日本語50音</p>
<p>JA_EISU　日本語英数</p>
<p>EN　英語　KO　韓国語</p>
<p>ZH_TW　中国繁体字</p>
<p>ZH_CN　中国簡体字　TH　タイ語,</p>
<p>VI　ベトナム語　ID　インドネシア語</p>
<p>CA　カタロニア語CS　チェコ語</p>
<p>DA　デンマーク語　DE　ドイツ語</p>
<p>ES　スペイン語　FR　フランス語</p>
<p>HR　クロアチア語　IT　イタリア語</p>
<p>HU　ハンガリー語　NL　オランダ語</p>
<p>NO　ノルウェー語　PL　ポーランド語PT　ポルトガル語　RO　ルーマニア語</p>
<p>FI　フィンランド語　SV　スウェーデン語　TR　トルコ語　EL　ギリシャ語</p>
<p>RU　ロシア語　UK　ウクライナ語</p>
<p>AR　アラビア語</p>
<p><strong>[type:ewb以外を指定した場合]</strong></p>
<p>EN 英語　　CA カタロニア語</p>
<p>CS チェコ語 　DA デンマーク語</p>
<p>NL オランダ語　SV スウェーデン語</p>
<p>FR フランス語　　DE ドイツ語,</p>
<p>EL ギリシャ語　 HU ハンガリー語</p>
<p>IT　イタリア語　　PL　ポーランド語</p>
<p>PT_BR　ポルトガル語</p>
<p>RO　ルーマニア語　RU　ロシア語</p>
<p>ES　スペイン語　　TR　トルコ語</p>
<p>NO ノルウェー語　FI　フィンランド語</p>
<p>HR クロアチア語 UK ウクライナ語</p>
<p>AR アラビア語</p></td>
<td><p>null</p>
<p>(カレントキーボード言語)</p></td>
</tr>
<tr class="even">
<td><p>modefirst</p>
<p>*1*3</p></td>
<td>String</td>
<td><p>キーボード表示時の入力モード</p>
<p>ascii　ASCII入力可能モード</p>
<p>number　数値入力可能モード,</p>
<p>symbol　記号入力可能モード</p>
<p>default キーボードのデフォルト</p>
<p>katakana　カタカナ入力モード</p>
<p>指定されたキーボードタイプがサポートしていないモード指定時は無効。</p></td>
<td>defult</td>
</tr>
<tr class="odd">
<td><p>ascii</p>
<p>*1*3</p></td>
<td>String</td>
<td>ascii入力モードおよびtypeForEwbがspecialNumの場合における、入力文字列制限<br />
空文字列(“”)　ascii(7bit)のみ入力可能<br />
ASCII文字内で制限を付ける場合は、有効文字を正規表現で記述。*2</td>
<td><p>null</p>
<p>(制限なし)</p></td>
</tr>
<tr class="even">
<td><p>shiftfirst</p>
<p>*1</p></td>
<td>Boolean</td>
<td>入力文字列が0文字時のシフトキー状態<br />
true シフトオン状態<br />
false シフトオフ状態</td>
<td>true</td>
</tr>
<tr class="odd">
<td>moveBG</td>
<td>Boolean</td>
<td>ディスプレイサイズwvgaで入力領域にフォーカスが入った際に背景をずらす共通処理を許容するか否か。</td>
<td>true</td>
</tr>
<tr class="even">
<td><p>prediction</p>
<p>*6</p></td>
<td>Boolean</td>
<td><p>IMを利用するキーボード利用時に、予測変換を行うか否か</p>
<p>true 利用する</p>
<p>false　利用しない</p></td>
<td>true</td>
</tr>
<tr class="odd">
<td><p>color</p>
<p>*6</p></td>
<td>String</td>
<td>キーボードの色彩</td>
<td>darkGray</td>
</tr>
<tr class="even">
<td><p>faxTypeFirst</p>
<p>*6 *7</p></td>
<td>String</td>
<td><p>FAX宛先種別グループボタンの選択状態</p>
<p>faxall以外のキーボードに適用した場合は無効。</p>
<p>※faxとlineは機能的には同等</p>
<p>fax ファクス</p>
<p>ext 　内線</p>
<p>line　外線</p>
<p>sip IP Fax</p>
<p>未指定の場合は、未選択状態になる。</p></td>
<td>null</td>
</tr>
<tr class="odd">
<td><p>acceptableFaxType</p>
<p>*6 *7</p></td>
<td>Array(String)</td>
<td><p>選択可能なFAX宛先種別グループボタン</p>
<p>指定された順に、グループボタンの上から配置される。faxall以外のキーボードに適用した場合は無効。値がnullの場合はFAX宛先グループボタン自体が表示されない。</p>
<p>詳細は、9.9節を参照。</p></td>
<td>null</td>
</tr>
<tr class="even">
<td><p>faxAddButton</p>
<p>*6</p></td>
<td>visible/hide/none</td>
<td><p>「次宛先」ボタンの表示制限</p>
<p>該当キーが存在しないキーボードに適用した場合は無効。</p></td>
<td>visible</td>
</tr>
</tbody>
</table>

> \*1　keyboardのtypeがphoneNumのときは、該当する機能が存在しないため無効。\*2
> 正規表現の詳細については後述。
>
> \*3
> 例えば**メールアドレス入力フィールドに対してAscii(7bit)入力をさせたい場合、modefirst:”asci”,
> asci:””を設定する**
>
> **\*4　typeがewbのときは無効。**
>
> **\*5　typeがtypeForEwbの場合とそうでない場合で値域が異なる**
>
> **\*6 typeがewbのときのみ有効**
>
> **\*7　typeForEwbがfaxAllのときのみ有効**

-   正規表現記述方法

> ascii(7ビット)入力モードにおける、
> ascii(7bit)内で入力文字制限を行うために利用する。
>
> 指定方法は、（１）入力可能文字を指定する方法と（２）入力不可文字を指定する方法(先頭に’^’付与)がある。
>
> 数字、アルファベットは、’-’で連続指定可能（a-gは、abcdefgが入力可能）
>
> 正規表現は文字セットの記法に従うため、特殊文字は、以下のように記述する必要がある。

-   バックスラッシュ \\\\\\\\

-   ハイフン \\\\-

-   ブラケット \\\\\[ \\\\\]

-   ダブルクォート \\”

-   シングルクォート \\’

-   ハット \\^ (先頭に記述しない場合は^で可能)

> （１）入力可能文字を指定する例における表現
>
> ascii: “ 0-9a-zA-Z ~\`|^\*+=&lt;&gt;’,!?”
>
> （２）入力禁止文字を指定する例(先頭文字’^’の場合)における表現
>
> ascii: “^0-9a-zA-Z“

-   keyboardに対する設定について  
    キーボードに対する設定は、事前にコンストラクタオプションkeyboardで設定を推奨する。  
    動作時に設定を変更したい場合は、ファーカスIN前か、フォーカスIN時に、keyboardメソッドを利用して設定変更する。設定項目が変更されるとキーボードを初期化し再表示するため、1文字入力ごとの設定変更等には、対応していない。
