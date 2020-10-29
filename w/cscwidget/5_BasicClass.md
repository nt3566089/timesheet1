5.0. Basic Class
===========

CSCWidgetの基本クラス群を定義する。

5.1. Basic Class List
----------------

基本クラス群の概要について述べる。

5.2. 共通関数
----------

cscWidgetを使う上で共通に利用する関数。

<table>
<thead>
<tr class="header">
<th>$.cscw.beginInit()</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>初期化開始を宣言することで、初期化処理を最適化する。</p>
<p>この関数を呼んでからendInit()を呼ぶまでは、各種ウィジェットのコンストラクタ以外のメソッドを呼んではならない</p>
<p>※このメソッドを呼ばなくても、cscWidgetは使うことができるが、各ウィジェットのコンストラクタ呼び出しをbeginInit～endInitではさむことにより、通常よりも初期化処理が高速化される。</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th>$.cscw.endInit()</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>初期化を終了する。</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th>$.cscw.exists(name)</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>指定されたnameのウィジェットがあるかどうかを判定する</td>
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
<td>name</td>
<td>String</td>
<td>ウィジェット名</td>
</tr>
<tr class="odd">
<td>戻り値</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>boolean</td>
<td>存在するかどうか</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th>$.fn.cscw(name, option)</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>各ウィジェットのコンストラクタを呼び出す。</p>
<p>通常、ウィジェットのコンストラクタ呼び出しは</p>
<p>$("#foo").cscwToggleSwitch(options)</p>
<p>のようにウィジェット名が関数名の一部となっているが、本メソッドを使うと</p>
<p>$("#foo").cscw("ToggleSwitch", options)</p>
<p>のようにウィジェット名をパラメータに取ることができる</p></td>
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
<td>name</td>
<td>String</td>
<td>ウィジェット名</td>
</tr>
<tr class="odd">
<td>options</td>
<td>Object</td>
<td>ウィジェットの初期化オプション。詳細は各ウィジェットの仕様を参照。</td>
</tr>
</tbody>
</table>

5.3. Widget
--------

全てのWidgetの基底となる親クラスである。

本クラスに定義されるプロパティは、全てのWidgetの共有プロパティである。

-   クラス定義

> $.cscw.Widget

-   共通機能とプロパティ

<!-- -->

-   $.cscw.Settings … 共通設定

-   <span class="underline">ログ出力機能</span>

> Widgetのデバッグログをブラウザ上に出力する。
>
> ブラウザがEWBの場合はシステムのログ出力機能を用いる。本機能は以下のプロパティにより制御可能である。

<table>
<thead>
<tr class="header">
<th>Property</th>
<th>Type</th>
<th>Description</th>
<th>Default</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>logLevel</td>
<td>String</td>
<td><p>ログ出力のレベル設定</p>
<p>off　 ログ出力しない</p>
<p>error　errorレベルのログのみ出力</p>
<p>warn　warnレベル以上のログのみ出力</p>
<p>info infoレベル以上のログのみ出力</p>
<p>debug　debugレベル以上のログのみ出力</p>
<p>trace　traceレベル以上のログのみ出力</p>
<p>all　全てのログを出力(traceと同じ)</p>
<p>※2103SGPのEWB上ではdebug, traceは表示上infoとして出力される。それぞれprefixとして[d], [t]を付与する。</p></td>
<td>info</td>
</tr>
<tr class="even">
<td>windowPrefix</td>
<td>String</td>
<td><p>ログ情報として出力するiframe識別子</p>
<p>null以外の場合は、ログとして出力される内容に、指定したiframe識別子が含まれる。</p></td>
<td>null</td>
</tr>
</tbody>
</table>

-   <span
    class="underline">ウインドウ/フレーム管理機構からのイベント登録機能</span>

> ウインドウ/フレーム管理機構から挙がるイベントを登録する。

<table>
<thead>
<tr class="header">
<th>Property</th>
<th>Type</th>
<th>Description</th>
<th>Default</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>windowSuspendEvent</td>
<td>String</td>
<td>自身のフレームより上のレイヤに、別フレームが表示されたことを示すイベント</td>
<td>“cscwWindowSuspend”</td>
</tr>
<tr class="even">
<td>windowResumeEvent</td>
<td>String</td>
<td>自身のフレームより上のレイヤに、別フレームがなくなったことを示すイベント</td>
<td>“cscwWindowResume”</td>
</tr>
</tbody>
</table>

-   <span
    class="underline">Widgetとウィンドウ状態に関する設定機能</span>

> ウィンドウ生成時のWidgetの状態やウィンドウ状態の追跡指示を設定する。

<table>
<thead>
<tr class="header">
<th>Property</th>
<th>Type</th>
<th>Description</th>
<th>Default</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>windowSuspend</td>
<td>Boolean</td>
<td>ウィンドウ(uiFrame)生成時にsuspend状態で始まるか否かを指定する。</td>
<td>false</td>
</tr>
<tr class="even">
<td>trackWindowStatus</td>
<td>Boolean</td>
<td><p>ウィンドウ状態の追跡を開始するか否かを指定する。</p>
<p>2回以上trueが渡された場合、2回目以降は無視される。</p></td>
<td>false</td>
</tr>
</tbody>
</table>

-   <span class="underline">表示言語の共通初期設定の設定機能</span>

> CSCWidgetの利用に先立ち、表示で用いる言語の情報を設定する。設定された情報は生成されるCSCWidgetすべてに適用される。

<table>
<thead>
<tr class="header">
<th>Property</th>
<th>Type</th>
<th>Description</th>
<th>Default</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>lang</td>
<td>String</td>
<td><p>画面表示で用いる言語を指定する。</p>
<p>この設定に従い、具体的なフォントファミリやフォントサイズが決まる。</p></td>
<td>“en”</td>
</tr>
<tr class="even">
<td>dir</td>
<td>String</td>
<td><p>文章の書き進む方向( text direction)を指定する。</p>
<p>“ltr” 左から右へ書き進む。英語など</p>
<p>“rtl” 右から左へ書き進む。アラビア語</p></td>
<td>“ltr”</td>
</tr>
</tbody>
</table>

-   <span class="underline">フレーム間共有データの指定</span>

> CSCWidgetの利用に先立ち、すでに他のフレームでロード済みのデータを再利用する。

<table>
<thead>
<tr class="header">
<th>Property</th>
<th>Type</th>
<th>Description</th>
<th>Default</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>shareWindow</td>
<td>window</td>
<td><p>cscw.all.share.jsをロードしたフレームのwindowオブジェクトを指定する。</p>
<p>指定がない場合は、グローバル変数windowに共有データがあると仮定して動作する</p></td>
<td>null</td>
</tr>
</tbody>
</table>

-   メソッド

<table>
<thead>
<tr class="header">
<th>$.cscw.Settings.set(options)</th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>共通プロパティの値を変更する</td>
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
<td><strong>type</strong></td>
<td><strong>description</strong></td>
</tr>
<tr class="even">
<td>options</td>
<td><strong>Object</strong></td>
<td><strong>共通プロパティのプロパティ名と値をペアで指定する</strong></td>
</tr>
</tbody>
</table>

5.4. CSCWidget Factory
-----------------

jQueryプラグインを作成するための仕組みを提供するクラスである。

Widget
Factoryを用いて作成したjQueryプラグインは、自動的にWidgetクラスを継承する。

-   クラス定義

> $.cscw.defineWidget

5.5. Abstract Button
---------------

抽象ボタンクラス。

本クラスを継承すると、ふるまいが同一でデザインおよびレイアウトの異なるボタンクラスを定義することができる。

-   クラス定義

> $.cscw.AbstractButton
