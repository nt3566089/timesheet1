# M/C Status

機械に関する情報を表示する。下記の内容について記述する。

1.  機械情報

2.  トレイ情報

3.  レポート・リスト出力/メーター確認

4.  消耗品情報

5.  光疲労警告

## 機械情報

###  機械情報(DMP6-1まで)

###### 概要

コントロールパネルから機械の情報を確認することが出来る。

###### 内容

下記の機械情報を確認することが出来る。

機械構成コード : M/C本体(IOT)のSerial
No.のみを、半角(Ascii)10文字で表示する。

機械の構成 :
商品コード(半角(Ascii)Max8文字)とOptionの有無の表示をする。サポートしない項目は表示しない。表示する機械構成項目を

  以下の表に示す。

###### 機械構成表示項目

|項目|内容|備考|
|---|---|---|---|
|DADF|有無|-|
|原稿通過スタンプ|有無|PGS7018SGP/Kutani/Nausicaaのみ|
|Tray段数|1、2、3、4段、5、6、7段|5段以降はFujin/Raijin/Tarzan/Nausicaaのみ|
|TTM|有無|Fujin/Raijin/Tarzan は無し。|
|HCF|なし、HCF、HCF2|Fuhjin/Raijin/Tarzan/Nausicaaのみ|
|Interposer Tray|有無|D Finisher装着時。<br/>Fuhjin/Raijin/Tarzanのみ<br/>|
|Side Tray|有無|Tarzanは無し。|
|センター排出トレイ|1段、2段|PGS7018SGP/Nausicaa/Varenne。自動検知不可。|
|両面|有無|Optionをサポートしない場合は表示しない *1|
|Output装置|無し、Finisher、Mailbox|Mailboxは/Raijinのみ<br/>A Finisher:Varenne<br/>B Finisher:Kutani/PGS7018SGP/Nausicaa/Varenne<br/>C Finisher:Raijin/Tarzan/Nausicaa/Kutani<br/>D Finisher :Fuhjin/Raijin/Tarzan。<br/>※'05.12時点<br/>|
|Folder Unit|有無|D Finisher装着時。|
|Booklet|有無|C Finisher/D Finisher装着時。<br/>Kutani・Fuhjin/Raijin/Tarzan<br/>|
|SCT|有無|Raijin/Tarzanのみ(表示しない)|
|OCT|有無|PGS7018SGP/Nausicaaは常に有り。Raijin/Tarzanは有り|
|OCT2|有無|PGS7018SGP/Nausicaa/Varenne。自動検知不可。|
|EXIT2|無し、タイプA,タイプB|PGS7018SGP/Nausicaa/Varenne。自動検知不可。|
|トナー回収ボトルのタイプ|標準タイプ、大容量タイプ|Fuhjin のみ。<br/>CH7171によりKutani以降は非表示<br/>|
|HDD|有無(故障含む)||
|Page Memory|Byte表現||
|Buffer Memory|Byte表現||
|高圧縮ボード<br/>(S2Xボード)<br/>|有無(故障もあり)|CH7423、Optionをサポートしない場合は表示しない *1、|
|PostScript|有無|Optionをサポートしない場合は表示しない *1|
|ART Ⅳ|有無|Optionをサポートしない場合は表示しない *1|
|ESC/P|有無|Optionをサポートしない場合は表示しない *1|
|HPGL/2|有無|Optionをサポートしない場合は表示しない *1|
|PCL|有無|Optionをサポートしない場合は表示しない *1|
|PC-PR201H|有無|Optionをサポートしない場合は表示しない *1|
|PDF|有無|Optionをサポートしない場合は表示しない *1|
|KS5843|有無|Optionをサポートしない場合は表示しない *1|
|KSSM|有無|Optionをサポートしない場合は表示しない *1|
|KS5985|有無|Optionをサポートしない場合は表示しない *1|
|USB|有無|USB2.0が実装されない場合は表示しない*2|
|FAX Main Board|実装の有無と回線種別|Optionをサポートしない場合は表示しない|
|FAX Card Slot 1|実装の有無と回線種別|Optionをサポートしない場合は表示しない|
|FAX Card Slot 2|実装の有無と回線種別|Optionをサポートしない場合は表示しない|
|ITオプションMACアドレス|6 Byte Data|CH6529、Optionをサポートしない場合は表示しない|
|ITオプションIPアドレス|4 Byte Data|CH6530、Optionをサポートしない場合は表示しない|
|外部コントローラ|正常、故障、初期化中|Allagashのみ|


上記の機械構成表示項目の中に、Optionをサポートしない場合は項目が表示しない。
上記の機械構成表示項目の中に、内容が"有無"の項目に関しては、Standardとして扱う場合は項目が表示しない。

\*1 サポート情報は、FF「Ⅰ.Ⅲ.Ⅰ デコンポーザ」を参照。

     \*2USBは、ここでUSB2.0のこと、オプションの位置付けで、プリンタボートに利用。 USB1.1は標準でついているが、プリンタボートとしては使用不可。
(Kutani/PGS7018SGP PL対応)

ソフトウエアバージョン : 各Sub SystemのROM Versionを表示する。

表示 :各Sub System
のROMのバージョン情報は、コントローラより文字列データとして取得し表示する。 また、表示する順序は取得したデータの順に表示する。

保守・操作の問い合わせ先
:「貼り付けカードを見る。または、買い上げ販売店に連絡する。」 という内容の表示をする。

表示項目(参照システムデータ)

|項目|設定範囲|備考|
|---|---|---|---|
|機械構成コード|最大10桁の文字列|Ascii Code "0"～"9"、Nullの文字列|
|商品コード|最大8桁の文字列|Ascii Code "0"～"9"、Nullの文字列|
|IIT ROMバージョン|3 Byte Data|Major : 1 Byte (0～254)<br/>Minor : 1 Byte (0～254)<br/>Revision : 1 Byte (0～254)<br/>の3 Byteの情報で構成されている。<br/>|
|IISS ExtensionボードROM バージョン|↑|↑|
|IOT ROMバージョン|↑|↑|
|Controller System ROMバージョン|↑|↑|
||||
|Mailbox|↑|↑|
|Finisher|↑|↑|
|Feeder(HCF)|↑|↑<br/>オプション給紙装置のこと<br/>HCF1、HCF2のVersionとなる<br/>|
|その他の後処理装置ROM バージョン(T.B.D.)|↑|↑|
|DADF ROMバージョン|↑|↑|
|高圧縮ボード(IPS Accelerator )ROMバージョン|↑|↑|
|Fax Main Boardバージョン|↑|↑|
|Fax Card Slot 1バージョン|↑|↑|
|Fax Card Slot 2バージョン|↑|↑|
|SJFI(SESAMI ジョブフローインタフェース)|↑|↑|
|SSMI(SESAMI マネージャ関連)|↑|↑|


###### 制限・注意事項/備考

Option有無表示に関連商品は、表示しない。(Option表示は、PGS1002SGP市場からの要求であり、M/Nでは関連商品が付かない為。)

Optionのシステムデータは、UI DFD 1.1.2 Overviewシステムデータの項参照

Channel
0は、Channelの実装状況の他に内線を有効にするシステムデータが有効に設定されている場合に表示される。

CH5268により、「機械の構成」 及び 「ソフトウェアバージョン」 の表示は、オプション未実装の場合、オプション名の表示はしない。

CH5246により、<Kutani/PGS7018SGP以降共通>「ROM表記文字列を各表示サブで保持せず、新規共通Lib=ROM情報Libから取得する。

(表示項目やROM名の表記や表示順はすべてLib=ROM情報により決まる)

Kutani/PGS7018SGP以降では、表示するソフトウェアバージョンの項目およびその内容はすべてControllerから通知される。Panel-UIでは、通知された情報を表示するのみ.項目の表示・非表示判定はしない。。

###### 機種固有情報

Imari: PostScriptはPostScript
Optionの有無、ART、HPGL2、ESC/PはART/Emuraltion
Optionの有無、KS5843、KSSM、KS5985はKS
Optionの有無として表示される

###### 参考資料

UI Dialogue

CH2074、CH2075

F.F. : 「Ⅲ.Ⅵ Device Management」、「Ⅰ.Ⅰ IOT Device Functions」、「Ⅰ.Ⅱ IIT
Device Functions」  
 「Ⅰ.Ⅲ.Ⅰ デコンポーザ」

### 機械情報(DMP6-2以降)

#### Serial Number

M/C本体の表示用Serial No. (ASCII Code最大10桁の文字列) を表示する。[1]

#### 商品コード

商品コード(ASCII Code最大8桁の文字列)を表示する。

#### 機械の構成

機械の構成として表示する項目は「09.1
Appendix-機械構成表示項目一覧」にまとめる。

オプション未実装の場合、オプション名の表示は行わない。[2]

#### ソフトウエアバージョン

各Sub SystemのROM Versionを表示する。  
ROM Version は、

Major : 1 Byte (0～254)  
Minor : 1 Byte (0～254)  
Revision : 1 Byte (0～254)

の3 Byteの情報で構成されている。

表示項目やROM名の表記や表示順はROM Infomation
Library(共通Lib)の実装に従う。[3]

#### 保守・操作の問い合わせ先

「貼り付けカードを見る。または、買い上げ販売店に連絡する。」 という内容の表示を行う。

サポート先URL(PGS1002SGPのURL)を表示する。URLの参照先はPDI
Libより取得する。(PGS1002SGPのみ) <CH12358>

#### IPアドレス

###### 概要

本体のIPアドレス情報を表示する。

###### 内容

システムデータ \[IP動作モード\]
設定やその他により、以下のルールで表示する。

各種表示する場合の優先順位は以下。

1.  IPv4モードの場合
IPv4アドレスを表示する。

|表示項目|IP手動設定|IP自動設定|
|---|---|---|---|
|IPアドレス(カレント)|1|1|

※手動設定、自動設定いずれの場合も、上記には現在有効なIPアドレスが設定される

1.  IPv6モードの場合
IPv6アドレスを表示する。

|表示項目|IP手動設定する|IP手動設定しない|
|---|---|---|---|
|自動設定アドレス-1|1|1|
|自動設定アドレス-2|2|2|
|自動設定アドレス-3|3|3|
|手動設定アドレス|4|-|
|リンクローカルアドレス|5|4|


1.  デュアルスタックモードの場合

IPv6アドレス → IPv4アドレス の順に表示する。
DMP2009-4a以降MNのみ、IPv4アドレス、IPv6アドレスの両方を表示する(CH19271)。

###### 制限・注意事項/備考

-   上記表示項目に対応して参照するべきシステムデータについては、Tools-ネットワーク設定の該当章、および
    UI SystemData Listを参照。


-   DMP-X-PL3 メンテ以降(CH24395:Kisyu2-PL3/Rookie2-
    PL3/Herakles-PL2)、DMP-XI以降(CH24876)
 システムデータで、UIのIPアドレスが「非表示」に設定されている場合は、
   未認証状態、一般ユーザーでは非表示とし、
   機械管理者(KO)、管理者権限ユーザー(SA)、CEでは表示とする。
  

   表示項目(参照システムデータ)

|項目|M/C default|設定範囲|備考|
|---|---|---|---|---|
|IP Address表示を行わないか、行うかの設定|表示する|表示する<br/>表示しない<br/>|「0x0000000X」<br/>1bit目が0:表示する or 1:表示しない で切り替える<br/>|


###### 機種固有情報

-   CH23187(Herakles-PL)、CH24394(Kisyu2-PL2)
個別対応ROMでは、以下のルールでアドレスを隠ぺいする
    未認証状態、一般ユーザでは非表示とし、
    機械管理者(KO)、管理者権限ユーザー(SA)、CEでは表示とする。

#### 製品名

製品名を表示する。表示する製品名はPDI Libより取得する(最大32byte)。
※DMP2009-4a以降、MNのみ表示(CH19271)。

#### ホスト名

本体に設定されているホスト名(KOで設定するホスト名)を表示する(ASCII
Code最大32文字の文字列)。
※DMP2009-4a以降、MNのみ表示(CH19271)。

#### ファクス番号

KO自局情報設定に設定されているG3IDを表示する。
回線の装着状況により、回線1～3、SIP有効時は回線SIPのファクス番号を表示する。

-   DMP2009-4a以降、MNのみ表示(CH19271)。

-   表示する文字種、最大文字数については、「16.3.4.7.3.
    発信元名/回線設定」を参照。

## トレイ情報

###### 概要

コントロールパネルからTrayの状態を確認することが出来る。

###### 内容

下記の項目よりTray毎の情報/状態を確認することが出来る。

Tray状態 :
給紙可(正常)、用紙無し、Tray無し、故障、リフトアップ中、不明の6段階表示

用紙残量 : Full、3/4、1/2、1/4、No Paper、残量不明の6段階表示

用紙サイズと向き :
各Trayの用紙Sizeと用紙の向きを表示する。(用紙Sizeの種類に関しては、FF編
1.1 IOT Device Functionの項参照)

用紙種類(紙質) :
UserがToolsで設定した用紙の種類を表示する。(User定義用紙の場合は、その名称(User設定文字列)も合わせて表示する。\*2)

###### 機種固有情報

- Pinot

用紙種類 :
UserがToolsで設定した用紙の種類を表示する。(カスタム用紙種類の場合は、その名称(User設定文字列)も合わせて表示する。)

用紙質量 : UserがToolsで設定した用紙の質量を表示する。

###### 制限・注意事項/備考

このTray情報から、用紙の紙質設定を行う事はできない。

SMHの状態表示は、用紙サイズは、用紙種類(紙質)は\[KO設定のNVM値\] を表示する。

用紙サイズについては以下ルールで表示する (詳細はDialogue仕様書を参照)

-   MediaPopup無しの場合は「自動サイズ検知」。ただし、自動サイズ検知の能力がないプロダクトでは、表示しない。

-   MediaPopup有りの場合はJRMからの通知に従う
\*2 User定義用紙のデータサイズに関しては、 「FF編 Ⅰ.Ⅰ IOT
Device Function 4.2.3 用紙種類の設定」 の項参照。

###### 参考資料

FD : F-1240、UI-0160、MD-0530 W-3720、

FF : 「Ⅲ.Ⅵ Device Management」、「Ⅰ.Ⅰ IOT Device Functions」

UI Dialogue

## レポート・リスト出力/メーター確認

### レポート・リスト出力

###### 概要

コントロールパネルから各種のレポート/リストを出力(Print
Out)することが出来る。

###### 内容

Report各種の出力/詳細は、UI DFD 15. Report、FF編 2.6 Report
Serviceの項参照。

###### 制限・注意事項/備考

Error履歴Report(Error Log Report)は、COでも出力することが出きる。

CH10109対応にて、DMP5以降では手動レポートはシステムデータ値によて提供するか否か変化する。

システムデータは、「従来どおり提供する」「KOユーザ/CEユーザには提供する」の2値。(システムデータについてはTBD)

上記"KOユーザ"、"CEユーザ"の定義は、UI-DFD「25. 認証」の「25.1.1.
デバイスの管理情報へのアクセス制限」を参照の事。

###### 機種固有情報

Allagash: 外部コントローラがレポートを生成するため、レポート画面はTools
Modeになる。

###### 参考資料

UI Dialogue

### メーター確認

#### Billingメーター確認

###### 概要

コントロールパネルからBillingメーターの情報を確認することが出来る。

###### 内容

下記のBillingメーターの情報を確認することが出来る。

|メーターの種類|内容|表示|
|---|---|---|---|
|Billingメーター|Billingメーターの表示|・表示用のメーター1～メーター3を表示する。<br/>・締め日メーター*3の上記の種類<br/>|
||AP/AllagashでのBillingメーターの表示|・表示用のメーター1～メーター4を表示する。<br/>CH14660(DMP8-1PL以降)より表記が「メーター1」,…ではなく各メーターの意味を示す言葉(例: Black Impressions)で表示する。<br/>|
||<DMP-X以降(RF3779 CH19256)><br/>AP(IBG) でのBillingメーターの表示<br/>|・表示用のメーター1～メーター5を各メーターの意味を示す言葉で表示する。|


メーターNの表示条件は以下とする。

###### CH9441以降

メーター1～5の表示有無は、DVMより提供されるライブラリに依存する。UI内部において、機種/テリトリ等による表示判断は実施しない。

詳細な表示条件については、『FF Document Volume >3.5.3
デバイスUIからのメーター確認』を参照。

###### CH9441対応まで

UI内部において、機種/テリトリ等により、表示するべきメーターを判断する。

UIで表示するメーター番号は、以下。

|テリトリ|機種|メーター1|メーター2|メーター3|メーター4|備考|
|---|---|---|---|---|---|---|---|
|FX|白黒|○|△|△||BillingType = 1 の場合は、メーター2, 3 非表示<br/>BillingType = 3 の場合は、メーター3 非表示<br/>|
||カラー|○|○|○|||
|AP<br/>A<br/>|白黒|○|○|△|△|FAX搭載されない場合は、メーター4 非表示<br/>BillingType = 2 の場合は、メーター3, 4 非表示<br/>|
||カラー|○|○|○|○||
|PGS1002SGP, PGS2003SGP|白黒|○|△|||BillingType = 1 の場合は、メーター2 非表示|
||カラー|○|○|○|○||


-   AP白黒機の場合、Optionとして搭載される可能性のないサービスが利用するメーターは非表示にする必要がある。
コピー、プリンターは標準あるいはオプションとして搭載される可能性があるため、FAXのみを対象とし、「搭載予定」ではなく「今のFAX搭載有無」に連動させる。

締め日メーター表示

\*3 :
締め日メーターを表示するには下記の条件がある。(国内仕様のみ表示する)

1.  締め時表示の実施/禁止 が "実施" になっている時。

2.  EPシステムの利用形態により、以下の条件に分かれる。
2.1. EP-SV時、またはEP-SV/EP-DX 併設で通知先が "EP-SV"/"両方へ通知"
の時、  
① 電話回線が接続されている時。
2.2. EP-DX時、またはEP-SV/EP-DX 併設で通知先が "EP-DX"/"両方へ通知"
の時、  
① リモートセンターコール機能が "ON" の時。  
② Fax Card の実装状態が "正常" の時。
3. Tools(仕様設定) Entryでき,Tools Modeに入れること(※Tools
Entry,Modeに関しては16.Tools参照)(Imari BG22060)

\[Yokohama-2a以降(CH13075)\]

1. EP(EP-SV/EP-DX/WEP)設置済みである(共通Libより取得)

2. システムデータ「締め時表示の実施/禁止」が、「実施」になっている

3. 【EP-DX/EP-BBの場合】 締め日の設定
(DXとBBで、それぞれ別々のシステムデータ) が「0」以外に設定されている
(CH21679)

EP-DXの場合:システムデータ「860-014:ビリング締め日」が0以外

EP-BBの場合:システムデータ「920-014:ビリング設定締め日(日)」が「0:動作禁止」以外

上記の1.2.3
の条件を満足したときに、締め時メータの値を取得し、取得できた値を表示する。

EP-SV設置である場合は、締め時メータの値の取得のためにジョブ規制ありのKO
Tools Modeに遷移する。(CH21012)

値が取得できない場合は、枠のみ表示し、値はBlank表示とする。

表示桁数は7桁。上位桁が0の場合は、その桁は表示しない。(0サプレスして表示する。)

表示項目(参照システムデータ)

|項目|設定範囲|備考|
|---|---|---|---|
|EP-SV,EP関連商品の接続有無|なし<br/>あり<br/>||
|電話回線接続の有無|なし<br/>あり<br/>||
|EPデータ発信タイプ|EP-SVへ通知<br/>EP-DXへ通知<br/>両方へ通知<br/>||
|リモートセンターコール機能|ON<br/>OFF<br/>||
|Fax Card の実装状態|正常<br/>エラー<br/>未実装<br/>||
|締め時表示の実施/禁止|禁止<br/>実施<br/>||






|||
|---|---|---|
||<br/><br/><br/>|
||<br/><br/><br/>|
||<br/><br/><br/>|
||<br/><br/><br/>|
||<br/><br/><br/>|
||<br/><br/><br/>|
||<br/><br/><br/>|




|||
|---|---|---|
||<br/><br/><br/>|
||<br/><br/><br/>|
||<br/><br/><br/>|




|||
|---|---|---|
|ケース 1～6|<br/><br/><br/><br/>|


###### システムデータ

|項目|設定範囲|備考|
|---|---|---|---|
|ビリングメータータイプ|ケース1～ケース11|DMP-X RF3779 CH19256より「ケース1～ケース7」から「ケース1～ケース11」に変更(ケース8,9,10,11が追加)。|


###### 制限・注意事項/備考

(1)上記ケースの各Billingメーターは下記のものを指す。

CopyのColor–2 : Copyの単色+Copyの2色Color

PrintのColor-1 : PrintのToner Save Mode

PrintのColor-2 : 少数色プリント、ART/Emulationを使用したColor Print

(2)各メーターに表示するものが無い時は、Blankを表示する。

(3)上記Billingメーターの9種のメーターを合計(1999999×9)すると、17999991の8桁となるが、EPホスト側の制限により、メーターの表示は全て7桁で良い。

(4)Kutani以降Product共通でメーターの表示は全て7桁で良いことになった。マシン側から8桁を通知する時があるときは下7桁のみを表示するようにする。(CH4659)

(5)Billingメーターは、Marketによって表示内容が異なるものがある。

(6)Password無しでメーター確認は出来るが(操作的にはUser
Modeで可能)、Systemとしては、仕様設定Modeに遷移する。

(7)Job処理中は、メーター確認は表示できない。但し、保留ジョブのみの場合は表示できる。

(8)メーター確認表示が指示されてから、メーター確認画面を表示中の間は
ジョブ(プリントやFax送受信など)の起動や処理は制限される。

(9)締め日動作が行われていない場合は、メーター名は表示されるが、締め日メーター値は表示されない。

(10)Billing
Counter及び締め日Counterが0の場合でも、メーター名及びメーター値0を表示する。(締め日Counterに関しては、締め日動作が行われて、且締め日Counterが0の場合)

(11)Billing
Counter読み出しError、締め日Counter読み出しError時は、メーター表示は行わず、System
Failとする。(12)Imariにおいてはメーター1,2,3はUI側がCopyのColor総数などから直接計算して表示していたが、Kutani/PGS7018SGP/Fuhjin以降はJRM I/F通知の数値を参照するのみとなった。

(12) <Fuhjin CSMN以降>
テリトリ=AP&白黒機の場合に、FAX有無により、メーター4
の表示制御を実施する

(13) <Fuhjin CSNM以降> 白黒機の場合、テリトリ =
PGS1002SGP/PGS2003SGPでは、「メーターN」の表現を、種別(コピー、プリント等)で表現する。(CH9352)

(14) <CH9441>
TarzanPL以降、UI内部によるメーターN表示判断は実施せず、DVMライブラリにゆだねる。

    (HB-UI : Hagi～対応。 FCW-UI : TarzanPL～対応。)

(15)<CH10421>DMP5以降共通、PGS1002SGP向けBilling
Meterの表記変更テリトリによる表示。(FCW-UI:CH14660よりDMP-Kobe2より導入)
FX(←CH14660:"AP"を削除):従来どおり"メーター1"、"メーター2"、"メーター3"、"メーター4"
"メーター5" (CH11810で追加)を表示する(FXはメータ3まで)
AP:
メータ毎にそのメータの意味を表示する。表示される可能性のあるメーター種別は該当UI
Dialogue仕様書「04.05
メーター確認Popup」を参照(CH14660より追加)。

-   PGS1002SGP,PGS2002SGP:メータ毎にそのメータの意味を表示する。表示される可能性のあるメーター種別は下記の通り。トータル(Total
    Impressions)

-   トータルカラー(Total Color Impressions)

-   トータル白黒(Total B&W Impressions)

- 03/07/15
DV仕変の確認・調整会で以下のカウンタに関してはUI表示しないことで合意:

1.  CH5325での認証/集計機能 DVカウンタにおける
認証/集計機能 DV Counter(アカウント毎)

(Print)

 ・Print 枚数 (総計)(両面)(裏紙)

(Copy)

 ・Copy 枚数 (総計)(両面)(裏紙)

(Finishing)

 全て

   認証/集計機能 DV Counter (特殊アカウント)

  全て
(2)CH5326でのFax 認証/集計機能 DVカウンタにおける全て
(3)CH5327でのScan 認証/集計機能 DVカウンタにおける
   SCAN Auditoron DV Counter(カウント毎)
    ・Scan To File 面数 (Color)(BW)

- Scan To Mailbox 面数(Color)(BW)

- Scan To EMail 面数 (Color)(BW)
###### 機種固有情報

-   -   PGS7018SGPのみ最大500部門。その他のプロダクトは最大1,000件。(CH9275)

###### 参考資料

共通プラットフォーム FF編 Ⅲ.Ⅱ.Ⅷ.Document Volume Management
4.3.部門(アカウント)情報

#### Document Volume集計カウンターの確認(CH4666)

###### 概要

コントロールパネルからDocument
Volume集計カウンターをリセット,レポート出力することが出来る。

###### 内容

KOモードで上記のすべてのカウンター値を一括してリセットできる。DMP2007-1以降、KOに加え、AA,
SA権限を持つCOもリセットを行うことが出来る。(CH12749)

レポート出力に関してはUI DFD 15.Reportの「Document
Volume集計レポート」参照。どこから出力させるかはUI
Dialogue仕様に任せる。

###### システムデータ

表示項目(参照システムデータ)

|項目|設定範囲|備考|
|---|---|---|---|
||||


###### 制限・注意事項/備考

-   KOモード以外では、カウンターのリセットを行うことはできない。(DMP6-3まで)

-   DMP2007-1以降、KOに加え、AA,
    SA権限を持つCOもリセットを行うことが出来る。(CH12749)


-   プリントジョブ処理中に、カウンターのリセットを行うことはできない。

-   一括リセット指示された場合は、確認画面を表示し誤動作を防止する。

-   カウンター自体削除することはできない。・03/07/15
    DV仕変の確認・調整会で以下のカウンタに関してはUI表示しないことで合意(CH5693):
(1)CH5325でのDV運用カウンタにおける全て
(2)CH5326でのFax DV運用カウンタにおける全て
(3)CH5327でのScan DV運用カウンタにおける全て

-   FXのみ提供。M/N, IBGには提供しない。(CH8023)

###### 参考資料

1) 共通プラットフォーム FF編 Ⅲ.Ⅱ:Management Service機能編 Ⅲ.Ⅱ.Ⅷ:Document
Volume Management 9 Document Volume集計機能

2) 共通プラットフォーム FF編 Ⅲ.Ⅱ:Management Service機能編 Ⅲ.Ⅱ.Ⅵ:Device
Management 3.7 機能詳細

#### 詳細メーター確認(DMP2007-1以降のVarrenne2を除くM/N機のみ)

###### 概要

Billingメーターを含む詳細なメーター情報を参照することができる。
詳細メーター確認では、カテゴリ毎にフィルタリングして表示することが出来る。

###### カテゴリの種類

-   Impression Counters(デフォルト)

-   Sheet Counters

-   Images Sent Counters(Fax Option , インターネットファクス Option,
    Server Fax Option, Scan To E-Mail Option, Distributed Scan
    Opitonの全てのオプションが存在しない時は、選択できない(非表示))

-   Fax Impressions Counters(Fax Option , インターネットファクス Option,
    Server Fax
    Optionの全てのオプションが存在しない時は、選択できない(非表示))
    CH13020により削除。

-   All Usage Counters

###### 内容

各カテゴリに含まれるメータを以下の表で示す。

|カテゴリ|メーター|備考|CH情報等|
|---|---|---|---|---|
|All Usage Counters|A4 Equivalent Impressions|CEモードのときに表示。それ以外は非表示。|CH24668で追加|
||Total Impressions|PGS1045SGP #1||
||Black Impressions|PGS1045SGP #34 先頭に半角スペース(3byte)<br/>3Tierまたは2Tierのときは非表示<br/>||
||Black Copied Impressions|PGS1045SGP #3 先頭に半角スペース(6byte)<br/>3Tierまたは2Tierのときは非表示<br/>||
||Black Printed Impressions|PGS1045SGP #7 先頭に半角スペース(6byte) <br/>3Tierまたは2Tierのときは非表示<br/>||
||Color Impressions|PGS1045SGP #33 先頭に半角スペース(3byte) 白黒機では非表示<br/>3Tierまたは2Tierまたは白黒+2Tierのときは非表示<br/>||
||Color Copied Impressions|PGS1045SGP #25 先頭に半角スペース(6byte) 白黒機では非表示<br/>3Tierまたは2Tierまたは白黒+2Tierのときは非表示<br/>||
||Color Printed Impressions|PGS1045SGP #29 先頭に半角スペース(6byte) 白黒機では非表示<br/>3Tierまたは2Tierまたは白黒+2Tierのときは非表示<br/>||
||Black + Color Level 1 Impressions|PGS1045SGP #33 先頭に半角スペース(3byte)<br/>3Tierもしくは2Tierでは表示<br/>|Kobe-1以降(CH15301)|
||Black + Color Level 1 Copied Impressions|PGS1045SGP #25 先頭に半角スペース(6byte)<br/>3Tierもしくは2Tierでは表示<br/>|Kobe-1以降(CH15301)|
||Black + Color Level 1 Printed Impressions|PGS1045SGP #25 先頭に半角スペース(6byte)<br/>3Tierもしくは2Tierでは表示<br/>|Kobe-1以降(CH15301)|
||Color Level 2 Impressions|PGS1045SGP #33 先頭に半角スペース(3byte)<br/>3Tireもしくは2Tireたは白黒+2Tireのときは表示<br/>|Kobe-1以降(CH15301)|
||Color Level 2 Copied Impressions|PGS1045SGP #25 先頭に半角スペース(6byte)<br/>3Tireもしくは2Tireたは白黒+2Tireのときは表示<br/>|Kobe-1以降(CH15301)|
||Color Level 2 Printed Impressions|PGS1045SGP #25 先頭に半角スペース(6byte)<br/>3Tireもしくは2Tireたは白黒+2Tireのときは表示<br/>|Kobe-1以降(CH15301)|
||Color Level 3 Impressions|PGS1045SGP #33 先頭に半角スペース(3byte)<br/>3Tireもしくは白黒+2Tireのときは表示<br/>|Kobe-1以降(CH15301)|
||Color Level 3 Copied Impressions|PGS1045SGP #33 先頭に半角スペース(6byte)<br/>3Tireもしくは白黒+2Tireのときは表示<br/>|Kobe-1以降(CH15301)|
||Color Level 3 Printed Impressions|PGS1045SGP #33 先頭に半角スペース(6byte)<br/>3Tireもしくは白黒+2Tireのときは表示<br/>|Kobe-1以降(CH15301)|
||Large Impressions|PGS1045SGP #47||
||Black Large Impressions|PGS1045SGP #44 先頭に半角スペース(3byte)||
||Color Large Impressions|PGS1045SGP #43 先頭に半角スペース(3byte) 白黒機では非表示||
||Fax Impressions|PGS1045SGP #71 FAX Option ありのとき表示(Server Faxは関係なし)|CH13020で追加|
||Sheets||CH13020で追加|
||Copied Sheets|先頭に半角スペース(3byte)|CH13020で追加|
||Black Copied Sheets|PGS1045SGP #4 先頭に半角スペース(6byte)|CH13020で階層変化|
||Color Copied Sheets|PGS1045SGP #26 先頭に半角スペース(6byte) 白黒機では非表示|CH13020で階層変化|
||Printed Sheets|先頭に半角スペース(3byte)|CH13020で追加|
||Black Printed Sheets|PGS1045SGP #8 先頭に半角スペース(6byte)|CH13020で階層変化|
||Color Printed Sheets|PGS1045SGP #30 先頭に半角スペース(6byte) 白黒機では非表示|CH13020で階層変化|
||Embedded Fax Sheets|PGS1045SGP #15 先頭に半角スペース(3byte) FAX Option ありのとき表示|CH13020で階層変化|
||2 Sided Sheets||CH13020で追加|
||Copied 2 Sided Sheets|先頭に半角スペース(3byte)|CH13020で追加|
||Black Copied 2 Sided Sheets|PGS1045SGP #5 先頭に半角スペース(6byte)|CH13020で階層変化|
||Color Copied 2 Sided Sheets|PGS1045SGP #27 先頭に半角スペース(6byte) 白黒機では非表示|CH13020で階層変化|
||Printed 2 Sided Sheets|先頭に半角スペース(3byte)|CH13020で追加|
||Black Printed 2 Sided Sheets|PGS1045SGP #9 先頭に半角スペース(6byte)|CH13020で階層変化|
||Color Printed 2 Sided Sheets|PGS1045SGP #31 先頭に半角スペース(6byte) 白黒機では非表示|CH13020で階層変化|
||Embedded Fax 2 Sided Sheets|PGS1045SGP #16 先頭に半角スペース(3byte) FAX Option ありのとき表示|CH13020で階層変化|
||Black Copied Large Sheets|PGS1045SGP #6||
||Color Copied Large Sheets|PGS1045SGP #28 白黒機では非表示||
||Black Printed Large Sheets|PGS1045SGP #10||
||Color Printed Large Sheets|PGS1045SGP #32 白黒機では非表示||
||Embedded Fax Large Sheets|PGS1045SGP #17 FAX Option ありのとき表示||
||Images Sent|Fax Option , インターネットファクス Option, Server Fax Option, Scan To E-Mail Option, Distributed Scan Opitonのいずれかが存在する時に表示|CH13020で追加|
||Fax Images Sent|先頭に半角スペース(3byte)|CH13020で追加|
||Embedded Fax Images Sent|PGS1045SGP #13 FAX Option ありのとき表示|CH13020で階層変化|
||Internet Fax Images Sent|PGS1045SGP #13 インターネットファクス Option ありのとき表示|CH13020で階層変化|
||Server Fax Images Sent|PGS1045SGP #13 先頭に半角スペース(6byte) Server-FAX Option ありのとき表示|CH13020で階層変化,下記と順番変更|
||E-mail Images Sent|PGS1045SGP #12 先頭に半角スペース(3byte) E-Mail Option ありのとき表示|CH13020で階層変化,上記と順番変更|
||Network Scanning Images Sent|PGS1045SGP #11 Network Scanning Option ありのとき表示|CH13020で階層変化|
||Scanned Images Stored|スキャナーオプションありの時に表示|CH13020で追加|
|Impression Counters|A4 Equivalent Impressions|CEモードのときに表示。それ以外は非表示。|CH24668で追加|
||Total Impressions|PGS1045SGP #1||
||Black Impressions|PGS1045SGP #34 先頭に半角スペース(3byte)<br/>3Tierまたは2Tierのときは非表示<br/>||
||Black Copied Impressions|PGS1045SGP #3 先頭に半角スペース(6byte)<br/>3Tierまたは2Tierのときは非表示<br/>||
||Black Printed Impressions|PGS1045SGP #7 先頭に半角スペース(6byte)<br/>3Tierまたは2Tierのときは非表示<br/>||
||Color Impressions|PGS1045SGP #33 先頭に半角スペース(3byte) 白黒機では非表示<br/>3Tierまたは2Tierまたは白黒+2Tierのときは非表示<br/>||
||Color Copied Impressions|PGS1045SGP #25 先頭に半角スペース(6byte) 白黒機では非表示<br/>3Tierまたは2Tierまたは白黒+2Tierのときは非表示<br/>||
||Color Printed Impressions|PGS1045SGP #29 先頭に半角スペース(6byte) 白黒機では非表示<br/>3Tierまたは2Tierまたは白黒+2Tierのときは非表示<br/>||
||Black + Color Level 1 Impressions|PGS1045SGP #33 先頭に半角スペース(3byte)<br/>3Tierもしくは2Tierでは表示<br/>|Kobe-1以降(CH15301)|
||Black + Color Level 1 Copied Impressions|PGS1045SGP #25 先頭に半角スペース(6byte)<br/>3Tierもしくは2Tierでは表示<br/>|Kobe-1以降(CH15301)|
||Black + Color Level 1 Printed Impressions|PGS1045SGP #25 先頭に半角スペース(6byte)<br/>3Tierもしくは2Tierでは表示<br/>|Kobe-1以降(CH15301)|
||Color Level 2 Impressions|PGS1045SGP #33 先頭に半角スペース(3byte)<br/>3Tireもしくは2Tireたは白黒+2Tireのときは表示<br/>|Kobe-1以降(CH15301)|
||Color Level 2 Copied Impressions|PGS1045SGP #25 先頭に半角スペース(6byte)<br/>3Tireもしくは2Tireたは白黒+2Tireのときは表示<br/>|Kobe-1以降(CH15301)|
||Color Level 2 Printed Impressions|PGS1045SGP #25 先頭に半角スペース(6byte)<br/>3Tireもしくは2Tireたは白黒+2Tireのときは表示<br/>|Kobe-1以降(CH15301)|
||Color Level 3 Impressions|PGS1045SGP #33 先頭に半角スペース(3byte)<br/>3Tireもしくは白黒+2Tireのときは表示<br/>|Kobe-1以降(CH15301)|
||Color Level 3 Copied Impressions|PGS1045SGP #33 先頭に半角スペース(6byte)<br/>3Tireもしくは白黒+2Tireのときは表示<br/>|Kobe-1以降(CH15301)|
||Color Level 3 Printed Impressions|PGS1045SGP #33 先頭に半角スペース(6byte)<br/>3Tireもしくは白黒+2Tireのときは表示<br/>|Kobe-1以降(CH15301)|
||Large Impressions|PGS1045SGP #47||
||Black Large Impressions|PGS1045SGP #44 先頭に半角スペース(3byte)||
||Color Large Impressions|PGS1045SGP #43 先頭に半角スペース(3byte) 白黒機では非表示||
||Fax Impressions|PGS1045SGP #71 FAX Option ありのとき表示(Server Faxは関係なし)|CH13020で追加|
|Sheet Counters|Sheets|||
||Copied Sheets|先頭に半角スペース(3byte)|CH13020で追加|
||Black Copied Sheets|PGS1045SGP #4 先頭に半角スペース(6byte)|CH13020で階層変化|
||Color Copied Sheets|PGS1045SGP #26 先頭に半角スペース(6byte) 白黒機では非表示|CH13020で階層変化|
||Printed Sheets|先頭に半角スペース(3byte)|CH13020で追加|
||Black Printed Sheets|PGS1045SGP #8 先頭に半角スペース(6byte)|CH13020で階層変化|
||Color Printed Sheets|PGS1045SGP #30 先頭に半角スペース(6byte) 白黒機では非表示|CH13020で階層変化|
||Embedded Fax Sheets|PGS1045SGP #15 先頭に半角スペース(3byte) FAX Option ありのとき表示|CH13020で階層変化|
||2 Sided Sheets||CH13020で追加|
||Copied 2 Sided Sheets|先頭に半角スペース(3byte)|CH13020で追加|
||Black Copied 2 Sided Sheets|PGS1045SGP #5 先頭に半角スペース(6byte)|CH13020で階層変化|
||Color Copied 2 Sided Sheets|PGS1045SGP #27 先頭に半角スペース(6byte) 白黒機では非表示|CH13020で階層変化|
||Printed 2 Sided Sheets|先頭に半角スペース(3byte)|CH13020で追加|
||Black Printed 2 Sided Sheets|PGS1045SGP #9 先頭に半角スペース(6byte)|CH13020で階層変化|
||Color Printed 2 Sided Sheets|PGS1045SGP #31 先頭に半角スペース(6byte) 白黒機では非表示|CH13020で階層変化|
||Embedded Fax 2 Sided Sheets|PGS1045SGP #16 先頭に半角スペース(3byte) FAX Option ありのとき表示|CH13020で階層変化|
||Black Copied Large Sheets|PGS1045SGP #6|CH13020で順番変化|
||Color Copied Large Sheets|PGS1045SGP #28 白黒機では非表示|↑|
||Black Printed Large Sheets|PGS1045SGP #10|↑|
||Color Printed Large Sheets|PGS1045SGP #32 白黒機では非表示|↑|
||Embedded Fax Large Sheets|PGS1045SGP #17 FAX Option ありのとき表示|CH13020で追加|
|Image Sent Counters|Images Sent|Fax Option , インターネットファクス Option, Server Fax Option, Scan To E-Mail Option, Distributed Scan Opitonのいずれかが存在する時に表示|CH13020で追加|
||Fax Images Sent|先頭に半角スペース(3byte)  Fax Option , インターネットファクス Option, Server Fax Optionのいずれかが存在する時に表示|CH13020で追加|
||Embedded Fax Images Sent|PGS1045SGP #13 FAX Option ありのとき表示|CH13020で階層変化|
||Internet Fax Images Sent|PGS1045SGP #13 インターネットファクス Option ありのとき表示|CH13020で階層変化|
||Server Fax Images Sent|PGS1045SGP #13 先頭に半角スペース(6byte) Server-FAX Option ありのとき表示|CH13020で階層変化|
||E-mail Images Sent|PGS1045SGP #12 先頭に半角スペース(3byte) E-Mail Option ありのとき表示|CH13020で階層変化|
||Network Scanning Images Sent|PGS1045SGP #11 Network Scanning Option ありのとき表示|CH13020で階層変化|


###### 制限・注意事項/備考

-   CH12358により、DMP2007-1以降のM/N機(Varrenne2は除く)のみに導入する機能である。

-   該当Config マシンにどのメーターが存在するか?つまり、All Usage
    > Countersとして表示するメーターは何かを返すAPIは、DVM-Libが提供する。UIはそのAPIを使用して全てのメーターを取得し、指定されたカテゴリに含まれるメーターのみを表示するという制御を実施する。(カテゴリ振りはUIの役割)

-   CH13020(DMP2007-1のSSTフェーズで)により、Fax Impressions
    > Countersカテゴリの削除とカウンターの増減あり。

-   Copy関連メーターは、Copy機能がありの場合のみ表示する。

-   Printer関連メーターは、プリント機能がありの場合のみ表示する。

-   Color Level 1,2,3\*\*\*\*は、Kobe-1以降(CH15301)にBilling
    > Typeの設定次第で表示されることがある。
(表示はDV-Lib次第であるが、Black ImpressionsとColor
ImpressionsはTierであるかどうかUI-Panelが判断し非表示にする。)

## 消耗品確認

### 消耗品確認(DMP7-2A以前)

###### 概要

コントロールパネルから消耗品の状態を確認することが出来る。

###### 内容

下記の消耗品の状態を確認することが出来る。

|項目|内容|表示|備考|
|---|---|---|---|---|
|トナーカートリッジ|トナー毎(Y、M、C、K別)に残量の表示<br/>(Tarzanはカラー別(Y、M、C、K1、K2)、PGS7018SGP/Pazu/Nausicaa/Yupa/ Fuhjin/Raijin/Volanteは黒(K)のみ)<br/>|Full、3/4、1/2、1/4、Pre-Near Empty、トナー切れ間近、トナー無し、ミスセット、タイプミスマッチ、故障の9段階表示※<br/>PGS7018SGP/Pazu /Nausicaa/Yupaは残量検知不可<br/><ol start="9" type="1"><li>DMP5以降、MN系では、残量数値[%](丸めなし)とステータスを表示する、FX/APでは、従来通り25%刻み表示とステータスを表示する。(CH10650)<br/></li></ol>|PGS7018SGP/Pazu /Nausicaa/Yupaは残量検知不可のため、良好、まもなく交換、要交換、ミスセット、カートリッジ、故障の6段階表示。<br/>Kutaniはフル、3/4、1/2、1/4、Pre-Near Empty、、Near Empty,Emptyの7段階表示<br/>|
|トナー回収ボトル|状態の表示|良好、満杯間近、満杯、トナー回収ボトルMiss Set、の4段階表示||
|ドラムカートリッジ|ドラム毎(Y、M、C、K別)に状態の表示<br/>PGS7018SGP/Pazu /Nausicaa/Yupa/Fuhjin/Raijin/VolanteはKのみ<br/>|良好、寿命間近が間近、寿命間近、交換、ミスセット、タイプミスマッチ、故障 の7段階表示※Printの継続可能/継続不可はSystem Dataにより制御される<br/><ol start="10" type="1"><li>DMP5以降、MN系では、残量数値[%]とステータスを表示する、FX/APでは、従来通りステータスのみ表示。(CH10650)<br/></li></ol>※DMP6-2以降、「寿命間近が間近」追加(RF1381)<br/>※DMP2007-2a以降<br/><CH12786><br/>TEAKのみテリトリがFX/APの場合でも790-400(消耗品1%残量表示有無)が有効な場合は1%刻み残量表示を行う。<br/>|PGS7018SGP/Pazu /Nausicaa/Yupaは6段階表示。<br/>Kutaniは良好、交換間近、交換、ミスセットの4段階表示。<br/>|
|現像ユニット<br/>(Deve Assy)<br/>|Deve毎(Y、M、C、K別)に状態の表示|良好、寿命近し、寿命(利用不可)の3段階表示<br/>※寿命でもPrintは継続可能<br/>||
|Fuser ユニット<br/>(Fuser Assy)<br/>|状態の表示|良好、寿命間近が間近、寿命間近、寿命、故障の 5段階表示<br/><ol start="11" type="1"><li>寿命でもPrintは継続可能、ただし、Volanteの継続可否はSystem Dataにより制御される<br/></li></ol>※DMP6-2以降、「寿命間近が間近」追加(RF1381)<br/>|<br/><br/>|
|フューザークリーニングウェッブ|状態(寿命情報)の表示|利用可、ウェブ切れ間近、ウェブ切れ、 の3段階表示。<br/>※DMP2007-2a以降<br/><CH12786><br/>TEAKのみテリトリがFX/APの場合でも790-400(消耗品1%残量表示有無)が有効な場合は1%刻み残量表示を行う。<br/>|<br/><br/>|
|CC(Cleaning Colotron) Assy|状態(寿命情報)の表示|<br/>利用可、寿命間近、寿命の3段階表示。<br/>||
|IBT Belt CLN ASSY<br/>(転写ベルトクリーナー)<br/>|状態の表示|良好、寿命近し、寿命(利用不可)の3段階表示<br/>※寿命でもPrintは継続可能<br/>||
|2nd BTR Unit<br/>(第2バイアス転写ロール)<br/>|状態の表示|良好、寿命近し、寿命(利用不可)の3段階表示||
|IBT BTR Unit<br/>(転写ベルト)<br/>|状態の表示|良好、寿命近し、寿命(利用不可)の3段階表示<br/>※寿命でもPrintは継続可能<br/>||
|ホチキス|状態の表示|良好、カートリッジ確認(針残量少/ミスセット)、異常発生、故障 の4段階表示|Finisher装着時。|
|Booklet Front ホチキス|状態の表示|良好、カートリッジ確認(針残量少/ミスセット)、異常発生、故障 の4段階表示|Finisher装着時。<br/>ブックレットオプションがない場合は表示しない。<br/>|
|Booklet Rear ホチキス|状態の表示|良好、カートリッジ確認(針残量少/ミスセット)、異常発生、故障 の4段階表示|Finisher装着時。<br/>ブックレットオプションがない場合,は表示しない。<br/>|
|針カット屑箱|状態の表示|良好、予備を依頼、要交換、未装着または装着不良の4段階表示|D2Finisher装着時。|
|パンチダストボックス|状態の表示|良好、まもなく満杯、満杯、故障、未装着または装着不良の5段階表示|パンチオプション装着時。<br/>CH14265で"まもなく満杯"追加。<br/>|
|Roller ASSY Kit-TTM<br/>(紙送りローラー)<br/>|Tray毎(Tray1～4)に状態の表示|良好、寿命近し、寿命(利用不可)の3段階表示<br/>※寿命でもPrintは継続可能<br/>||
|Roller ASSY Kit-TTM以外<br/>(紙送りローラー)<br/>|Tray毎(Tray1～4)に状態の表示|良好、寿命近し、寿命(利用不可)の3段階表示<br/>※寿命でもPrintは継続可能<br/>||
|臭気フィルター|状態の表示|良好、寿命(利用不可)の2段階表示<br/>※寿命でもPrintは継続可能<br/>|<br/>オプション装着時。<br/>|


\*1 DMP6-1以降のMN(PGS1212SGP)はCRU

###### 制限・注意事項/備考

Imariは、Oil LessなのでFuser Oil残量表示はない。

Tonerは、色単位に交換することが出きる。

ドラムカートリッジは、色単位に交換することが出きる。

PGS7018SGP/Nausicaaはトナーカートリッジ、ドラムカートリッジ、ホチキスのみ表示する。市場で交換可能品としては他にFuser
Module、BTR、FEED ROOLがあるが、ERUかつ状態検知不可のため表示しない。

CC\_AssyおよびFuserユニットは、FX/APテリトリー時、UI上の消耗品リストには表示しない。(CH8928)

Varenneは下記の通り:

トナーカートリッジ:UI上Y,M,C,Kトナーカートリッジの状態表示と該当トナーを交換位置に移動するためのUI操作機能を提供する。
ドラムカートリッジ:UI上状態表示のみ。
Fuser ユニット:UI上状態表示とリセット操作機能を提供する。
(CH10761により、ERUのため、UI上非表示)
転写ベルトクリーナー:UI上状態表示とリセット操作機能を提供する。
第2バイアス転写ロール:UI上状態表示とリセット操作機能を提供する。
臭気フィルター(Option):UI上状態表示とリセット操作機能を提供する。(CH9926)
ホチキスカートリッジ(Option):UI上状態表示のみ。

###### 機種固有情報

機械確認画面での表示有無、及び、CRU/ERU区分を以下に示す

|項目|Imari|Allagash|Kutani/Hagi<br/>/SanRemo<br/>|PGS7018SGP<br/>/Pazu<br/>|Nausicaa<br/>/Yupa<br/>|Fuhjin|Tarzan<br/>FX/AP<br/>|Tarzan<br/>MN<br/>|Varenne|PGS1212SGP|Volante|
|---|---|---|---|---|---|---|---|---|---|---|---|---|
|トナーカートリッジ|○|○|○|○|○|○|○|○|○|○|○|
||CRU|CRU|CRU|CRU|CRU|CRU|CRU|CRU|CRU|CRU|CRU|
|トナー回収ボトル|○|○|○|-|-|○|○|○|○|○|○|
||CRU|CRU|CRU|-|-|CRU|CRU|CRU|CRU|CRU|CRU|
|ドラムカートリッジ|||○|○|○|○|○|○|○|○|○|
||ERU|CRU|ERU|CRU|CRU|ERU|ERU|CRU|CRU|CRU|ERU|
|現像ユニット|||×|-|-|-|-|-|×|×|-|
|(Deve Assy)||ERU|ERU|-|-|-|-|-|ERU|ERU|-|
|Fuser ユニット|||×|-|-|-|×|○|○|○|○|
|(Fuser Assy)|CRU|ERU|ERU|-|-|-|スペアパーツ|CRU|CRU|CRU|ERU|
|Fuser Cleanning Web|-|-|-|-|-|○|-|-|-||-|
||-|-|-|-|-|ERU|-|-|-|-|-|
|CC Assy|-|-|-|-|-|-|×|○|-||-|
||-|-|-|-|-|-|ERU|CRU|-|-|-|
|IBT Belt CLN ASSY|||×|-|-|-|-|-|○|×|-|
||ERU|ERU|ERU|-|-|-|-|-|CRU|ERU|-|
|2nd BTR Unit|||×|-|-|-|-|-|○|×|-|
||ERU|ERU|ERU|-|-|-|-|-|CRU|ERU|-|
|IBT BTR Unit|||×|-|-|-|-|-|×|×|-|
||ERU|ERU|ERU|-|-|-|-|-|ERU|ERU|-|
|ホチキスカートリッジ|○|○|○|○|○|○|○|○|○||○|
||CRU|CRU|CRU|CRU|CRU|CRU|CRU|CRU|CRU|CRU|CRU|
|針カット屑箱|-|-|-|-|-||○|○|-|-|○|
||-|-|-|-|-|CRU|CRU|CRU|-|-|CRU|
|パンチダストボックス|-|-|○|-|○|○|○|○|-|○|○|
||-|-|CRU|-|CRU|CRU|CRU|CRU|-|CRU|CRU|
|Roller ASSY Kit|-||×|-|-|-|-|-|×|×|-|
||-|ERU|ERU|-|-|-|-|-|ERU|ERU|-|
|臭気フィルター|-|-|-|-|-|-|-|-|○|-|-|
||-|-|-|-|-|-|-|-|CRU|-|-|


\*1 FuhjinEnhance(2005年10月)からリリース

\*2 Tarzan3rdからリリース

\*3 DMP6-1以降のMN(PGS1212SGP)はCRU

\*4 DMP2007-2c以降のプロダクトについては IOT FF
4.6.6消耗品、定期交換部品の状態を参照のこと。

(CH10761) Varenne Roller ASSY Kit は ERU

B-MF(PGS7018SGP/Nausicaa/Yupa) … Fuser module, BTR, FeedRool
は状態検知できない

###### CH8928 Tarzan
CC\_Assy及びFuserスペアパーツ扱い化に伴い、Tarzan FX/APではFuser非表示。

###### CH9859 表示項目の明確化

###### CH14053CRU消耗品については、EP設置済み、かつ、以下の条件を満足するときにPreNearEmpty
/ PreNearLifeEnd 表示を行わない。

- EP-SV/DX設置時(Legacy)

850-012:「CRUワーニング通知の許可/禁止」= 1(許可)の場合

- EP-WEB設置時

920-021:「CRU NearEmpty通知設定」= 1(通知する)または

920-022:「CRU NearFull通知設定」= 1(通知する)の場合

###### プロダクト固有

- Pinot

###### CH13096DRUM、CC ASSY、Fuser
ASSYについてはNVM(CE)にてERU/CRU切り替え可。

- PGS2122SGPPL

###### CH21201 トナーカートリッジの状態として、以下の個別キーが有効な時には、"(Pre)
Near Emtpty" を "Ready" として扱う。

    →PFRSC\_SYS\_UNIQUE\_FUNC1\_LOW\_TONER\_DISABLE

###### 参考資料

Allagash FF編 Device Management 4.3.3.6 消耗品、定期交換部品の状態

共通プラットフォーム FF編 Device Management 4.3.3.6
消耗品、定期交換部品の状態

#### 消耗品確認(SPARS)

###### 概要

9.4.1に加え、SPARSではコントロールパネルから印刷可能枚数を確認することが出来る。

###### 内容

  「40.02.00 消耗品確認 Tab Frame(MN仕様).doc」を参照。

###### 備考

  RF2329対応。

### 消耗品確認(DMP7-2C以降)

###### 概要

コントロールパネルから消耗品の状態を確認することが出来る。

###### 内容

表示する消耗品の項目、状態は「09.3
Appendix-消耗品表示項目一覧.xls」を参照のこと。

###### 参考資料

共通プラットフォーム FF編 1-1 IOT Device Function 4.6.6
消耗品、定期交換部品の状態

#### 消耗品確認(PGS1217SGP-08)

###### 概要

9.4.2に加え、PGS1217SGPでは、トナー以外のCRU部品に関し、ラダーから詳細画面を表示することが出来る。

###### 内容

表示する消耗品の項目、状態は「09.3
Appendix-消耗品表示項目一覧.xls」を参照のこと。

詳細画面の表示形式は、「04.04.01.01
(FCW)消耗品状態とメッセージ.xls」を参照のこと。

###### 備考

CH14967対応

### 消耗品確認(Kobe1以降)

###### 概要

- コントロールパネルから消耗品の状態を確認することが出来る。

###### 内容

- 表示する消耗品の項目、状態、項目に対して実施可能な操作は「09.3
Appendix-消耗品表示項目一覧.xls」を参照のこと。

- FX限定: 消耗品配送日を表示することが出来る(Dialogue仕様書「04.04
消耗品確認 Tab Frame.doc」)を参照のこと。(CH14688)

###### 参考資料

- 共通プラットフォーム FF編 1-1 IOT Device Function 4.6.6
消耗品、定期交換部品の状態

###### 備考

- 消耗品配送日表示はKobe1で機能導入するが、センター側が未対応のため機能しない。

#### HFSIカウンタリセット

###### 概要

消耗品の詳細確認画面において、

定期交換部品の交換時にユーザーによるHFSIカウンターリセットを実施可能にする。

機能を提供する条件は、機種や消耗品の項目により異なるため、

詳細は、IOT FF 及び 「09.3 Appendix-消耗品表示項目一覧.xls」 を参照。

###### 制限・注意事項/備考

-   HFSIカウンターリセットにはDC1003を利用する

-   状態が良好な場合には、カウンターリセットを提供しない (CH17228)

###### 機種固有情報

-   リセット操作等を実施する詳細画面(消耗品Popup)は、CH17228対応によりDMP2009-2以降は機種共通で導入
(DMP2009-1以前は、PGS1217SGP・Varenneのみ導入)

#### マーキングリフレッシュ

###### 概要

ドラム/現像機が一体型のプロダクトでは、低AC/低生産性(はがき等)を多用すると、現像機内の劣化トナーが増え「低濃度」・「逆極かぶり」が発生する場合がある。

IOTデバイスがその可能性を検知/判断した場合に、

ユーザーにより、(劣化トナーを用紙に転写して機外に排出するための)べた黒プリントを実施可能にする。

###### 動作内容

1.  マーキングリフレッシュの必要有無をUI画面に表示する
以下の条件を全て満たす場合に機能を提供する
 - ドラム状態 : 有効 (Ready)
 - マーキングリフレッシュ : 可能 (true)

1.  マーキングリフレッシュ機能を選択する
機能の選択時は、ToolsMode(ジョブ規制)に遷移する。
実行中あるいは保留中のジョブが存在する場合には、マーキングリフレッシュ画面に遷移できない。
機能選択後(機能画面の表示中)は、
マーキングリフレッシュの開始/中止以外のUI操作/画面遷移を禁止する。
(例)
 - メニューやPGS1318SGPキー押下による画面遷移
 - Auto Clear Timerタイムアップ動作
 - 認証ボタン/キー操作

1.  画面の指示に従い、リフレッシュ(プリント)実施に必要なパラメータを選択/用紙をセットして実行する
このとき、SMHに用紙をセットしても、SMH
MediaPopup動作は実施しない。(ToolsMode中)
プリントを行う場合の起動パラメータは以下とする
 - 用紙トレイ : 手差しトレイ (固定)
 - 用紙紙質 : 普通紙 (固定)
 - 用紙サイズ : A3 SEF、A4LEF、Letter LEF、Ledger(11x17)
SEF、のいずれか
 - 必要な用紙枚数 : IOTより取得 ※制限/備考欄を参照
以下の場合には、マーキングリフレッシュ動作(プリント)を起動不可とする。
 - プリント用紙のサイズが選択されていない場合
 - SMHトレイに用紙がセットされていない場合

1.  リフレッシュ(プリント)を開始したら、実行中の旨を表示する
終了時は、実行結果として以下の旨を表示する
 - 正常終了
 - ユーザーによる中止
 - 異常終了(用紙不足に伴う終了)
 - 異常終了(上記以外)

###### 制限・注意事項/備考

-   マーキングリフレッシュには、DC1218を利用する

-   リフレッシュ(プリント)に必要な用紙の枚数として、IOTから以下の情報を取得できる。
リフレッシュの実施状態により必要な枚数は変化するため、必要の都度、最新の情報を取得すること。
 - 大サイズ時(用紙のプロセス長が216mmより長い)の枚数 : A3
SEF、Ledger(11x17) SEF に適用
 - 小サイズ時(用紙のプロセス長が216mm以下)の枚数 : A4LEF、Letter
LEF に適用

-   

###### 機種固有情報

-   CH19550 Sangoh に導入

-   CH20529 Howl4-FXに導入

## 光疲労警告(CH8113)

###### 概要

感光体交換時に警告画面を表示し、警告音を鳴動する事で、なるべく短時間に交換作業を実施してもらうように促す。

###### 内容

MarkingDrawerを引き出した状態が続くと、感光体の能力が低下し、転写時に色のムラが発生する。

色のムラを回復させるには時間が掛かる為、感光体交換時には、素早い交換作業をしてもらうように画面表示をし、異常警告音を鳴らす。

\*光疲労:光が当たった部分のみ濃度が出なくなり、感材ピッチの濃淡として現れる。これが起きた場合の復帰目安として、500LUXで2分間照射された場合で約3日かかる。

## Maintenance Assistant

本節では、Maintenance Assistant について記述する。

###### 動作

1.  UIは Machine Status の基本画面に"Maintenance Assistant" の WBB
    を配置する。

2.  "Maintenance Assistant" の WBB をユーザが押下すると "Maintenace
    Assistant" の Window を UI に表示する。

3.  "Maintenace Assistant" の Window からユーザが "Send Diagnostic
    Information to PGS0387SGP" のボタンを押下すると  
    Maintenace Data を Edget Server へ通知する。

4.  "Send Diagnostic Information to PGS0387SGP"
    のボタン押下を受け付けると、"Sending Diagnostics Information" Pop-up
    Windowを UI に表示する。

5.  Maintenace Data の Edge Server へ通知終了後、Confirmation Report
    を出力する。

6.  Maintenance Data の Edge Server
    への送信中は、次の要求を受け付けない。

7.  "Sending Diagnostics Information" Pop-up
    Windowは、以下の事象が発生するまで UI に表示する。

-   ユーザが画面を閉じる操作を行う

-   オートクリアが発生する

DMP-XI-1b以降: "Send Diagnostic Information to
PGS0387SGP"のボタンは、PGS1082SGP通信が無効となっているときにはDisableとし、押下できない。

###### 表示条件:DMP-XI-1aまで

-   "Maintenance Assistant" の WBB は MN 機、かつ、P機以外で表示する。  
    > 表示有無の判定には、PGS1084SGPの起動状態を参照し、PGS1084SGPモジュールが活性状態(起動)のときに表示を行う。

###### 表示条件:DMP-XI-1b

-   "Maintenance Assistant" の WBB は MN 機で表示する。
DMP-XI-1bにおいてはPGS1082SGPモジュールの起動状態を得ることができないため他の条件によらず表示する。

###### 表示条件:DMP-XI-1c以降

-   "Maintenance Assistant" の WBB は MN
    > 機で、かつ、PGS1082SGPサービスサポート情報のシステムデータ(930-043)が「利用可能」になっているときに表示する。

###### 制限・注意事項

-   "Maintenance Assistant" の WBB
    はステップ記憶型ジョブメモリに登録することはできない。

###### 機種固有情報

-   特記事項なし

###### 備考

-   特記事項なし

###### 参照情報

RF4395: eSolutionの残項目対応(DMP2009-3aドロップ項目の対応)

CH20168: <DMP2009-4a以降共通&gt;&lt;SMeS>
UIからのMaintenanceData通知指示

BS 22 100 Maintenance Assistant

PGS1084SGP FF 7.3デバイス使用状況の通知 (UI起動)

ダイアログ仕様書(04.02 機械状態(Machine Information、04.02.06
Maintenance Assistant Popup、04.02.06 Maintenance Assistant Run Popup)

CH25348 :<PGS1082SGP> ユーザによるデータ通知

CH27372 : <PGS1082SGP> DMP-XI-1c向けUI対応

## ファクス認定番号

本節では、ファクス認定番号 について記述する。

公衆回線に接続するためには、技術基準に適合した認定番号を表示する必要があり、国内機では、FaxMiniでの認定番号、PCC
Faxでの認定番号、NGN使用時の認定番号をそれぞれ取得する。

これまでは、ラベルにより認定番号を表示してきたが、法令改訂により、現状の規定である、  
「特定端末機器の見やすい箇所に付す方法」に加え、  
「特定端末機器に電磁的方法により記録し、当該特定端末機器の映像面に直ちに明瞭な状態で表示することができるようにする方法」  
が追加されたことにより、UI上での表示も可能となった。

###### 動作

-   機械確認画面>機械状態 レポート出力画面に、ファクス認定番号を確認する画面を開くためのWBBを配置する。  
    > -WBBの表示条件  
    > KO設定「国コード=日本」が設定されている  
    > かつ  
    > PCC装着時 or FaxMini装着時 or NGNあり  
    > の場合表示する。

-   ファクス認定番号を確認する画面には、以下の要領で、マークと認定番号を表示する。  
    > -認定番号は、PDI Libraryにより取得する。  
    > -認定番号は、ASCII文字列でMax18文字とし、初期状態(認定番号未取得の場合)は、0が18桁設定されている。  
    > -認定番号は、PDI
    > Libraryからの取得状態(例えば取得失敗など)に関わらず、取得できた文字列をそのまま表示する。  
    > -装着されているFaxカードにより、PCC or
    > FaxMini用の認定番号をマークとともに表示する。  
    > -NGNありの場合は、NGN用の認定番号を表示する。このとき、Faxカードが装着されていなければ、NGN用の認定番号のみ表示する(上記マークは表示しない)。

###### 制限・注意事項

-   CH20960対応により、DMP-X以降表示。

-   

###### 機種固有情報

-   特記事項なし

###### 備考

-   特記事項なし

###### 参照情報

Dialog仕様書 04.02 機械状態(Machine Information)

## 無線LAN

本節では、無線LAN について記述する。

DMP-XI-3a/3bからWLAN Converter(外付けWiFiアダプター、Silex社製の
SX-BR-4600WAN)の提供が行なわれるようになった。

本節で「無線LAN」と記述している場合、上記「WLAN
Converter」を示し、「無線LANの状態」は「WLAN Converterの状態」を示す。

###### 動作

-   機械確認画面>機械状態 レポート出力画面に、無線LANの状態を確認する画面を開くためのWBBを配置する。  
    > -WBBの表示条件  
    > Controller(JRM経由)で通知される、デバイスとWLAN
    > Converterの有線接続状態が「接続がされている」である  
    > 場合表示する。

-   状態表示  
    > -「無線LAN接続状態 通信品質」に応じて、状態の表示を行なう。  
    > -「無線LAN接続状態
    > チャネル」に応じて、「チャネル」の表示を行なう。ただし、「無線LAN接続状態
    > 通信品質」が「未接続」の場合、「チャネル」表示しない。  
    > -「無線LAN
    > GO固定動作」が「GO固定動作有効」であれば、下記の情報の表示を行なう。  
    > -「無線LAN GO固定時SSID」に応じて、「SSID(Wi-Fi
    > Direct)」の表示を行なう。  
    > -「無線LAN GO固定時Pre-Shared Key」に応じて、「パスフレーズ(Wi-Fi
    > Direct)」の表示を行なう。

###### システムデータ

|項目|関連機能|設定範囲|備考|
|---|---|---|---|---|
|無線LAN接続状態 通信品質||未接続<br/>弱<br/>普通<br/>良好<br/>||
|無線LAN接続状態 チャネル||0～255||
|無線LAN GO固定動作||GO固定動作無効<br/>GO固定動作有効<br/>||
|無線LAN GO固定時SSID||ASCII:最大32文字+終端NULL||
|無線LAN GO固定時Pre-Shared Key||ASCII:最大64文字+終端NULL||


###### 制限・注意事項

-   RF8156/CH30697およびRF9145対応により、DMP-XI-3a以降表示。

-   

###### 機種固有情報

-   特記事項なし

###### 備考

-   特記事項なし

###### 参照情報

Dialog仕様書 04.02 機械状態(Machine Information)

[1] CH9568:Serial No.MN要求表示対応

[2] CH5268:<Kutani/PGS7018SGP以降共通&gt;&lt;HB/FCW>機械の構成、ソフトウエアバージョン表示ルールの変更

[3] CH5246:<Kutani/PGS7018SGP以降共通>
ROMバージョン表記文字列の仕様確定(含:DownLoadUtility)