# Counter

## Overview
コントロールパネルより、Billing
Counter(課金対象の枚数)の値を確認することが出来る。

## Billing

### Billing Counter

###### 概要
正確で公正な課金を行う為の電子Billing CounterのCount Upが行われる。
M/Cは、カラーモード毎、サービス毎に、複数のBilling Counterを装備する。

###### 内容
M/Cは以下の電子Billing
CounterのCountを行い、UIでは、Counterの表示を行う。(System
Dataにより表示内容は異なる。)

-   Copy Billing Counter : Copy JobのBillingがCountされる。

-   FAX Billing Counter : Fax Print JobのBillingがCountされる。

-   Print Billing Counter : Printer JobのBillingがCountされる。

-   Large Size Billing Counter : Large Size用紙でのCopy/ Fax/ Printer
    JobのBillingがCountされる。

-   Modal Billing Counter : Copy/ Fax/ Printer
    Jobについて、一定部数まではCountし、一定部数を超えた部分はCountしない。
各Billing CounterでのCountする種類は下記に示す。

||Full Color|Color - 1|Color - 2|BW|
|---|---|---|---|---|---|
|Copy Billing Counter|O<br/><ul><li>Full Color Copy<br/></li></ul>(4色Color)<br/>|-|O<br/><ul><li>単色Color Copy<br/></li><li>2色Color Copy<br/></li></ul>|O<br/><ul><li>白黒Copy<br/></li></ul>|
|Fax/Internet Fax Billing Counter|O<br/><ul><li>Colorをサポートしない為、現状FaxのFull Colorは使用されない。(Internet Fax受信Printは全て白黒で印刷する。)<br/></li></ul>|-|-|O<br/><ul><li>Fax受信Print<br/></li><li>Internet Fax受信による白黒Print<br/></li><li>Polling予約文書の確認Print<br/></li><li>Fax親展受信文書<br/></li><li>インターネットファクス親展受信文書<br/></li></ul>|
|Print Billing Counter|O<br/><ul><li>Full Color Print<br/></li><li>Full Color Report<br/></li><li>Diag Modeでの全てのColor印刷(Copyも含む)<br/></li></ul>|O<br/><ul><li>Toner Save ModeのColor Print<br/></li></ul>|O<br/><ul><li>ART/Emulationを使用したColor Print<br/></li></ul>|O<br/><ul><li>白黒Print<br/></li><li>Toner Save Modeの白黒Print<br/></li><li>白黒Report<br/></li><li>Diag Modeでの全ての白黒印刷(Copyも含む)<br/></li></ul>|


AP/MNで使用する

|Large Size Color Billing Counter<br/>(All Service)<br/>|<ul><li>上記のColor(Full Color、Color-1、Color-2)と判断され、且つ279mm以上x400mm以上の用紙に印刷した場合。<br/></li><li>Tray 1-4の場合、Trayに設定された用紙Sizeから判断する。<br/></li><li>SMHの場合、UI指示された用紙Sizeから判断する。<br/></li></ul>|
|---|---|---|
|Large Size BW Billing Counter<br/>(All Service)<br/>|<ul><li>上記のBWと判断され、且つ用紙SizeがLarge Size Colorと同じ基準の用紙に印刷した場合。<br/></li><li>Tray毎の判断基準もLarge Size Colorと同じ。<br/></li></ul>|


|Modal Color Billing Counter<br/>(All Service)<br/>|<ul><li>上記のColor(Full Color、Color-1、Color-2)と判断される。<br/></li><li>Countする部数はDiag Modeにて指定する。<br/></li></ul>|
|---|---|---|
|Modal BW Billing Counter<br/>(All Service)<br/>|<ul><li>上記のBWと判断される。<br/></li><li>Countする部数はDiag Modeにて指定する。<br/></li></ul>|

※1 : Color - 1とは、Full Color料金を若干割引したもの
※2 : Color - 2とは、Full Color料金とBW料金の中間のもの。
※3 : Report Serviceは、Print Billing Counterに含まれる。
※4 : Internet Fax Serviceは、Fax Billing Counterに含まれる。
※5 :
APで使用するCounterは、上記Service毎のCounterと重複してCountされる。
M/Cでは、13種類のBilling Counterを持つ。
Total Billing Counterは持たないので、UIにTotal
Counterを表示する時は、UIで各Billing Counterを合計してから表示する。
各Billing Counterの値は、Diag Modeにて修正することが可能である。

###### 機種固有情報
Imari : 各Serviceの電子Billing
Counterの桁数は7桁とし、有効範囲は0000000から1999999まで、1999999を超えると、そのDataは保証されなくなる。
信頼性を高める為にBackup Counterを2 Set装備する。ただしModal
CounterのBackup Counterはない。
Kutani : 各Serviceの電子Billing
Counterの桁数は7桁とし、有効範囲は0000000から9999999まで、9999999を超えると、そのDataは保証されなくなる。
信頼性を高める為にBackup Counterを2 Set装備する。ただしModal
CounterのBackup Counterは1Setである。
PGS7018SGP :各Serviceの電子Billing
Counterの桁数は7桁とし、有効範囲は0000000から9999999まで、9999999を超えると、そのDataは保証されなくなる。
信頼性を高める為にBackup Counterを2
Set装備する。ただしCopy/Fax/Print/Large Size/Modal CounterのColor(Full
Color,Color-1,Color-2)のBackup Counterは1Set
である。
Tarzan : 各Serviceの電子Billing
Counterの桁数は7桁とし、有効範囲は0000000から9999999まで、9999999を超えると、そのDataは保証されなくなる。

信頼性を高める為にBackup Counterを2 Set装備する。
Raijin/Fujin : 各Serviceの電子Billing
Counterの桁数は7桁とし、有効範囲は0000000から9999999まで、9999999を超えると、そのDataは保証されなくなる。
信頼性を高める為にBackup Counterを2
Set装備する。ただしCopy/Fax/PrintのColor(Full
Color,Color-1,Color-2)のBackup Counterは1Setである。

###### 制限・注意事項/備考
Billing Counterの表示については、UI DFD M/C Status 9.3.2.1
Billingメーター確認の項参照。
BillingのCount Timingについては、3.2.8 DV Management-3
ビリングを参照。
Billingの色の判断については、3.2.8 DV Management-3 ビリングを参照。
Billingの修復機能(自動/手動)については、3.2.8 DV Management-3
ビリングを参照。
インターネットファクス受信Printは、全て白黒で印刷する。
Modal Counterの詳細は、3.2.8 DV Management-3.4.5
モーダル・カウント仕様を参照。

###### 参考資料
Imari FF 3.2.8 DV Management 3 ビリング
Common FF 3.2.8 DV Management 3 ビリング

### 締め日Counter

###### 概要
指定した締め日に、Billing
Counterの内容を締め日Counterに格納し、次の締め日まで保持する。

###### 内容
前項のBilling
Counterと同じ種類の締め日Counterを装備する。(9種類。AP使用のCounterとModal
Counterは除く。)
UIでは、締め日Counterの表示を行う。
締め日Counterが表示されるには下記の条件がある。

1.  EPシステム(EP-SV、EP-DX)が接続されていて、電話回線も接続されている時(EP関連商品直結、EP関連商品の接続の為だけにEP-SVをアダプターとして使用している時はCountしない)

2.  システムデータの締め日が"0日"以外の時。(システムデータの締め日カウンターの表示が"実施"になっている時。)

3.  EP-SV時、EPデータ発信タイプが、"EP-DXへ通知"以外の時。

4.  EP-DX時、EPデータ発信タイプが、"EP-SVへ通知"以外、リモートセンターコール機能が、"On"、Fax
    Cardの実装状態が、"正常"の時。

5.  1回以上締め日を経過した時(最初の締め日が発生するまでは、締め日Counterは0で有る。)

###### 機種固有情報
Imari : Billing
Counter同様、各締め日Counterの桁数は7桁とし、有効範囲は0000000から1999999まで、1999999を超えると、そのDataは保証されなくなる。
Kutani : 各Serviceの電子Billing
Counterの桁数は7桁とし、有効範囲は0000000から9999999まで、9999999を超えると、そのDataは保証されなくなる。
PGS7018SGP :
各Serviceの電子Billing
Counterの桁数は7桁とし、有効範囲は0000000から9999999まで、9999999を超えると、そのDataは保証されなくなる。
Tarzan : 各Serviceの電子Billing
Counterの桁数は7桁とし、有効範囲は0000000から9999999まで、9999999を超えると、そのDataは保証されなくなる。
Raijin : 各Serviceの電子Billing
Counterの桁数は7桁とし、有効範囲は0000000から9999999まで、9999999を超えると、そのDataは保証されなくなる。

Fuijin : 各Serviceの電子Billing
Counterの桁数は7桁とし、有効範囲は0000000から9999999まで、9999999を超えると、そのDataは保証されなくなる。

###### 制限・注意事項/備考
本仕様は、国内仕様にのみ適用する。
あらかじめ、締め日のDataを設定する必要がある。
この機能は、EP-DX若しくは、EP-SV機能を使用する場合に有効。
EP-DXを使用する時は、M/Cの締め日Counterが有効となるが、EP-SVを使用する時は、EP-SV側の締め日Counterが有効となる。
締め日Counterの表示については、UI DFD M/C Status 9.3.2.1
Billingメーター確認の項参照。
締め日CounterのCount Timingについては、3.2.8 DV Management-3
ビリングを参照。

###### 参考資料
Imari FF 3.2.8 DV Management 3 ビリング
Common FF 3.2.8 DV Management 3 ビリング