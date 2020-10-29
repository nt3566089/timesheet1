# Overview

本ドキュメントはMF-UIの機能仕様書として位置づけられるものである。MF-UIの機能について定義し、Char-UIについては原則として言及しない。



## M/C Configuration

本章においては、M/Cコンフィギュレーション(オプション)、及び、MF-UIにおいて動作制御に関係するシステムデータのみについて記述する。

MF-UIにおいては、オプションは全て何らかのシステムデータラベルを持つように設計される(実際にはNVMがアサインされず、コンパイル時に一意に値が決定するものも同じように扱う)。

M/Cコンフィギュレーションに関しては、システム基本仕様書(System
Overview編)のSystem
Overviewの章に記載されるものがあるが、ここでは特にMF-UIに関連するオプションについて記述する。

### Configuration

1) Imari Family構成

|オプション|MF30<br/>(2001/11)<br/>CP30 4T/TTM<br/>|MF30<br/>(2001/11)<br/>CPF30 4T/TTM<br/>|MF40<br/>(2001/11)<br/>CP40 4/TTM<br/>|MF40<br/>(2001/11)<br/>CPF40 4/TTM<br/>|AP|Carrera|Allagash|備考|
|---|---|---|---|---|---|---|---|---|---|
|1Tray(2Tray Model)|||||||なし|1Tray構成あり。1Tray,3Tray,TTMからオプションを追加選択可。<br/>工場出荷時オプション。<br/>|
|3Tray(4Tray Model)||||||||1Tray構成あり。1Tray,3Tray,TTMからオプションを追加選択可。<br/>工場出荷時オプション。<br/>|
|TTM||||||||1Tray構成あり。1Tray,3Tray,TTMからオプションを追加選択可。<br/>工場出荷時オプション。<br/>|
|Side Tray (Face Up)|||||||||
|Light Finisher (Light Staple Finisher)|||||||||
|DADF||||||||工場出荷オプション|
|OCT||||||||工場出荷オプション|
|DM||||||||工場出荷オプション|
|PostScript3(J2/J5)+HPGL|||||||-|Main ROMに含まれる。|
|ART/Emulation|||||||-|Main ROMに含まれる。|
|HDD||標準||標準|||標準|EPC Copy、EPC Print Scan To Server, Scan To MB,セキュリティプリントに必要|
|Page Memory(64M)||||||||CP/CFPは、64M標準装備。|
|Page Memory(256M)||||||||同上|
|Buffer Memory(128M)|||||||標準|CPでは64Mが標準装備。CFPでは128Mが標準装備。Scan To Server、Scan To Mailbox機能を使用するには128M以上が必要であり、CPの場合メモリ増設が必要。|
|Buffer Memory(256M)||||||||同上|
|結合ジョブ機能の有無||||||||SWスイッチ。デフォルトは無効(表示しない)で出荷される。CEによる変更が可能であり、結合ジョブコピー機能の有効(表示する)、無効(表示しない)を切り替える。ポストロンチ以降有功。|
|Network Scan(Scan機能設定)||||||||SWスイッチ。デフォルトは有効で出荷され、KO設定で変更可能。Scan機能を使用するためには、他にHDDオプション、ページメモリ64M以上、ワークメモリ128以上が必須。|
|Scan to Email<br/>(Scan to Email機能有無)<br/>|||||||無|SWスイッチ。デフォルトは有効で出荷され、EWSからのKO設定で変更可能。Scan To Email機能。インターネットファクスのScan To Email機能とは独立したオプション。ポストロンチ。|
|Internet Fax<br/>(インターネットファクス Scan to Email機能有無、Email to Fax機能有無)<br/>|||||||無|SWスイッチ。デフォルトは機能なし。CE設定。Internet Fax機能を使用するためには、HDDオプション必須。CPに対してFaxオプション併用時、CPFのインターネットファクスと同等機能が提供できる。|
|Fax Main Board||標準||標準|||無|G3通信基盤(G3PSTN)としての機能をもつファックスメインボード。オプションスロット1とオプションスロット2を持つ。内線Ch0、外線Ch1として識別される。内線を機能的に有効にするためには別途SWスイッチがある。|
|G3通信基盤(PSTN)|||||||無|オプションスロット1、2、あるいは両方同時装着可能。|
|G4/G3通信基盤(ISDN)|||||||無|オプションスロット1、2、あるいは両方同時装着可能。|
|ハンドセット|||||||無|CPにはFaxオプション必要|
|コピーPGS1035SGP||||||||SWスイッチ(Default OFF)|
|FV管理キット|なし||なし||||無|関連商品のライザーに統合。SWスイッチ(Default OFF)。|
|コピーライザーS/SD/SD-Ⅱ|||||||無|従来関連商品。PGS1103SGP経由で接続|
|コピーライザー510N|||||||無|従来関連商品。PGS1103SGP経由で接続<br/>仮性能仕様書には記載なし。<br/>|
|コピーライザーⅡ/Ⅲ/Ⅳ/Ⅴ|||||||無|従来関連商品。PGS1103SGP経由で接続|
|コピーライザー610N/650N|||||||無|EP関連商品。直結又はPGS1103SGP経由で接続|
|入金装置/Ⅳ|||||||無|従来関連商品。PGS1103SGP経由で接続|
|入金装置Ⅴ|||||||無|従来関連商品。EP関連商品。直結又はPGS1103SGP経由で接続|
|コピーディスペンサー|||||||無|従来関連商品。PGS1103SGP経由で接続|
|コピーディスペンサーⅡ|||||||無|EP関連商品。直結又はPGS1103SGP経由で接続|
|フットスイッチ|||||||無|その他の関連商品。PGS1103SGP経由で接続|
|キースイッチ|||||||無|その他の関連商品。PGS1103SGP経由で接続|
|リセッタブルカウンター|||||||無|従来関連商品。PGS1103SGP経由で接続|
|キーコーダー/キーカウンター|||||||無|従来関連商品。PGS1103SGP経由で接続|
|新方式減算入金装置|||||||無|新方式アクセサリー。直結又はPGS1103SGP経由で接続<br/>仮性能仕様書には記載なし。<br/>|
|新方式減算ディスペンサー|||||||無|新方式アクセサリー。直結又はPGS1103SGP経由で接続<br/>仮性能仕様書には記載なし。<br/>|
|PGS1103SGP|||||||無||
|EP-DX|||||||無|CPにはFaxオプション必要|
|PSW|||||||無||
|英文キット||||||||言語切り替え機能で対応。|
|ワンタッチパネル|||||||無|Faxオプションとセットで装着される。ワンタッチは90個(ジョブ目メモリボタンはなし)|
|PGS1101SGP|||||||無||


###### 制限・注意事項/備考

-   内外線切り替えはオプションではなく標準。デフォルトでは内外線切り替えが出来ない。(KO設定で内線(Ch0)が有効にすれば可能となる)

-   IIT/Platen、Network Cardは標準。

-   Faxサービスのボタンを出すかどうかはFaxオプションが存在するかどうかで判断する。CP、CFPの区別はFaxオプションの有無で区別するのではない。コンフィギュレーションのシステムデータで判断する。

-   MF30とMF40の区別はしない(実装を変えない)。

-   EPCオプションとは、HDD+メモリ128MB以上の組み合わせとなり、この条件がクリアされた場合にのみEPCオプションを必要とする機能がEnableされる。

-   Copy高画質オプションは、ページメモリ=128MByte以上で、システムメモリ=512MByte以上が装着され、かつ、システムデータの\[Copy写真画質の動作モード\]が、"画質優先"に設定されている場合にのみ有効となる。

-   Fax部門管理キットは、従来はMF-UIに接続されていたが、ImariからはPGS2038SGPに統合。上記ではFV管理キットとして項目を記述している。

-   Page MemoryとBuffer
    Memoryは、汎用(市販)のSO-DIMMで、同じ物である。実装位置が異なるだけ。

-   認証/集計機能はCV管理のみを対象とする。

-   EP-DX=Alart発呼+EP-Tressである。

-   MDS/MDSSについてはMF-UIでの対応項目はない。

-   言語切り替えはシステムデータによる切り替えの言語切り替えは実施する。FXテリトリでは、日本語と英語、韓国語と英語、中国語と英語の組み合わせのみ対応する。

-   M/NはISO8859で定義される言語の組み合わせに対応可能だが、ImariではM/Nはドロップした。

-   認証/集計機能とPGS2038SGPの併設はない。(システムデータが同時に設定された場合、MF-UIではPGS2038SGPが優先される)

-   PGS1101SGPへの対応はPGS1102SGPと全く同じUI-Service
    I/Fを使用する。カラー制限機能はジョブ起動後に動作する。(これはPGS1101SGPで使用するカードのカラー制限情報が現状のUI-Service
    I/Fでは取得できないため、ユーザ選択でのカラー制限ができないことを指している.)

-   ハンドセットがオプションのため、手動受信モードのときの着信表示対策が必要。ハンドセットは自動検知できない。

-   Scan To Server、Scan To Mailboxの機能がDevice
    UI上に表示されるためには、HDD、ワークメモリ128以上、Scan機能設定が有効である必要がある。さらに、ScanToMailboxはSalutation、EWSのいずれか一種類以上が有効になっていることが条件。ScanToServerは、FTP及び、TCP/IP(IPアドレス)が有効になっていることが条件。

-   EP関連商品、従来関連商品、その他の関連商品、新方式アクセサリの併設については、旧来より、EP関連商品の加算型アクセサリ+{キースイッチ|フットスイッチ}、EP関連商品の減算型アクセサリ+{キースイッチ|フットスイッチ}、EP関連商品の加算型アクセサリ+EP関連商品の減算型アクセサリの併設が存在し、新方式でも3つの併設パターンが存在する。

2) B-MF(PGS7018SGP)構成

･市場出荷構成として以下のコンフィギュレーションがある。

･フィールドアップグレードとしてDC→CF、CP→CPF(FAX
Unit設置)、DC→CP、CF→CPF(Printer
Unit設置)が可能となる。オプション構成によりS(Scan)構成も可能となる。

･表中の「SS」、「DS」、「DD」はDuplexを示す。「-」は出荷形態として存在しない構成を示す。

･PGS2003SGPへの出荷構成はない。

|マーケット|DC|CF|CPF|CP|
|---|---|---|---|---|---|
|国内(FX)|SS/DD|DS/DD(*)|DS/DD(*)|-|
|AP E圏|DD|-|-|DD|
|AP KO|DD|-|-|DD|
|AP TC|DD|-|-|DD|
|GCO China|S/DD|-|-|DD|
|GCO HK|S/DD|-|-|DD|
|PGS1002SGP|DD(*)|-|-|DD(*)|
|PGS2003SGP|-|-|-|-|


*2002.9.30 開発全体MTG配布資料「B-MF
config020830PM16.xls」にて変更されている。

表中記号:
「●」標準構成、「○」オプション構成、「◎」工場出荷時のDD構成で標準となる、「-」構成なし。

<img src="image\01 Overview/media/image1.png" style="width:9.88194in;height:6.85417in" />

<img src="image\01 Overview/media/image2.png" style="width:9.88194in;height:4.69444in" />

###### 制限・注意事項/備考

-   内外線切り替えはオプション。

-   PGS7018SGPではページメモリは32MB固定である。(Imariではオプション増設が可能である)

-   Faxサービスのボタンを出すかどうかは、Faxオプションが存在するかで判断する。CP、CFPの区別はFaxオプションの有無で区別しない。コンフィギュレーションのシステムデータで判断する。

-   EP-DX=Alart発呼+EP-Tressである。

-   MDS/MDSSについてはMF-UIでの対応項目はない。

-   言語切り替えはKO設定による言語切り替えを実施する。FXでは、日本語と英語、韓国語と英語、中国語(TC)と英語、中国語(SC)と英語の組み合わせを対応する。

-   認証/集計機能とPGS2038SGPの併設はない。(システムデータが同時に設定された場合、MF-UIではPGS2038SGPが優先される)

-   ハンドセットがオプションのため、手動受信モードのときの着信表示対策が必要。Imari同様ハンドセットの自動検知はないが、モジュラに接続すればそのまま使用可能となっている。

-   FAX UNIT(FAX Card
    > Mainボード)にはハンドセット/外付け電話が接続される。チャンネル0～1と接続する。オプション基盤(G3通信/G3G4通信基盤)が実装されている場合、オフフック(受話器を取った)を検出できなくなる。FAX
    > Motherにはハンドセットが接続される。チャンネル0～Nと接続する。オプション基盤(G3通信/G3G4通信基盤)が実装されている場合のみ動作する。

-   EP関連商品、従来関連商品、その他の関連商品、新方式アクセサリの併設については、旧来より、EP関連商品の加算型アクセサリ+{キースイッチ|フットスイッチ}、EP関連商品の減算型アクセサリ+{キースイッチ|フットスイッチ}、EP関連商品の加算型アクセサリ+EP関連商品の減算型アクセサリの併設が存在し、新方式でも3つの併設パターンが存在する。

-   以下のコピー機能に関しては、システムメモリ(EPC RAM/Option
    > RAM)の総量およびHDDオプションあり/なしにより機能制限を行う。システムメモリにて機能を行う場合はシステムデータの設定を参照して決定する。(注1)
    > Printingエリアに+36MB、Decomposeエリアに+10MBの計+46MBの余裕がなければ128MB以上でも増設が必要。  
    > <img src="temp\01 Overview\image\01 Overview/media/image3.png" style="width:8.97917in;height:3.00694in" />

-   サポートPDL(Page Description Language)の対応を以下に示す。  
    > ●:標準、○:オプション  
    > <img src="temp\01 Overview\image\01 Overview/media/image4.png" style="width:10.04167in;height:1.61111in" />

-   

1.  C2DCC(Tarzan)構成

|オプション|CC55<br/>DC<br/>|CC55<br/>CP<br/>|CC65<br/>DC<br/>|CC65<br/>CP<br/>|CC75<br/>DC<br/>|CC75<br/>CP<br/>|MN<br/>CC65<br/>|MN<br/>CC75<br/>|AP|備考|
|---|---|---|---|---|---|---|---|---|---|---|---|
||||||||||||
||||||||||||
|プラテン(PF1)|標準|標準|標準|標準|標準|標準|||||
|DADF(PF1)<br/>Daimajin(IISS拡張メモリ1面含む)<br/>|||||||||||
|DADF(PF1)<br/>反転両面<br/>|標準|標準|標準|標準|標準|標準|||||
|Print||標準||標準||標準|||||
|BW Scan||標準||標準||標準|||||
|カラースキャナオプション(IISS拡張メモリ3面化, JPEGチップ, Cont DAM256MB化)||||||||||スキャン自動(PGS0081SGP)を行うためには、本オプションが必要。<br/>Tarzanはカラー機であるが、カラースキャナ機能はオプション。<br/>|
|Scan生産性200%オプション(IISS拡張メモリ2面化)||||||||||スキャンボタン不要。|
|BW Fax||||||||||Post launch。|
|USB2.0|||||||||||
|128MB RAM(ESS)|||||||||||
|256MB RAM(ESS)|||||||||||
|512MB RAM(ESS)|||||||||||
|Media Print|||||||||||
|BlueTooth Adapter|||||||||||
|HCF1(2250sht)||||||||||HCF2と同時装着不可。|
|HCF2(4500sht)||||||||||Post launch。HCF1と同時装着不可。2つのトレイからなる。|
|Finisher C||||||||||他の排出装置とは同時装着不可。|
|Finisher D||||||||||Post launch。他の排出装置とは同時装着不可。|
|Booklet(Finisher C&amp;D option)|||||||||||
|Mailbox(Finisher C option)||||||||||PrinterOption装着時のみ。|
|Interposer(Finisher D option)||||||||||Post launch。|
|Folder Unit(Finisher D option)||||||||||Post launch。|
|SCT||||||||||他の排出装置とは同時装着不可。|
|OCT||||||||||他の排出装置とは同時装着不可。|
|拡張親展Box|||||||||||
|DGS|||||||||||
|Print Kit S|||||||||||
|Print Kit H|||||||||||
|Foot Switch|||||||||||
|Wing Table|||||||||||
|CopylLzer|||||||||||
|Coin Kit|||||||||||
|Copy Dispenser|||||||||||
|PGS1103SGP|||||||||||
|PSW|||||||||||
|英文キット||||||||||言語切り替え機能で対応。|


###### 制限・注意事項/備考

-   言語切り替えはシステムデータによる切り替えの言語切り替えは実施する。FXテリトリでは、日本語と英語、韓国語と英語、中国語と英語の組み合わせのみ対応する。

-   M/NはISO8859で定義される言語の組み合わせに対応可能。

-   HDDは、標準。

-   ColorEPC,BWEPCは、標準。

-   DADFは、標準。

-   M/N,APは、現時点(20021128)で詳細不明。

-   

1.  E-mono(Fuhjin)構成

|オプション|E-mono110<br/>DC<br/>|E-mono110<br/>CP<br/>|E-mono90<br/>DC<br/>|E-mono90<br/>CP<br/>|MN<br/>110/90<br/>DC<br/>|MN<br/>110/90<br/>CP<br/>|AP|検知手段|備考|
|---|---|---|---|---|---|---|---|---|---|---|
|||||||||||
|||||||||||
|プラテン(PF1)|標準|標準|標準|標準||||||
|DADF(PF1)<br/>Daimajin(IISS拡張メモリ1面含む)<br/>|標準|標準|標準|標準||||||
|Print||標準||標準||||||
|BW Scan||標準||標準||||||
|カラースキャナオプション(IISS拡張メモリ3面化, JPEGチップ, Cont DAM256MB化)||||||||||
|Scan生産性200%オプション(IISS拡張メモリ2面化)|||||||||高速スキャンボタン不要。|
|インターネットファクス|||||||||CPSのoption。FAXはない。|
|CopyServer |||||||||Post launch(2004.9)は、標準。|
|CopyServer –外部Media|||||||||CopyServerのOption。|
|プリンタースキャナー|||||||||DC機に対するオプション。|
|- USB2.0||||||||||
|- 増設 RAM|||||||||RAM Sizeは、TBD。|
|||||||||||
|- BlueTooth Adapter||||||||||
|- 802.11b Adapter||||||||||
|Media Print||||||||||
|HCF2||||||||自動検知|2つのトレイからなる。|
|D Finisher|標準|標準|標準|標準||||自動検知|Base Finisher3000, Saddle Staple Finisher|
|Booklet Maker(Finisher D option)||||||||自動検知||
|Interposer(Finisher D option)||||||||自動検知||
|Folder Unit(Finisher D option)||||||||自動検知||
|||||||||自動検知|※Fuhjin/Raijin/Tarzan)IOT DeviceFunctionFF(K1.0.0)には、Fuhjinでは未対応の記載があるが、風神/雷神)仮性能仕様書(パフォーマンス編)K0.02では 対応する旨記載されている。20030207時点では、FFに合わせて記載した。|
|拡張親展Box||||||||||
|DGS|TBD|TBD|TBD|TBD||||||
|Print Kit S||||||||||
|Print Kit H||||||||||
|Foot Switch||||||||||
|DocuLizer||||||||||
|DocuLizer NW||||||||||
|CopylLizer610N/650N|||||||||接続テストが必要。510Nは不要。|
|PGS1103SGP(LT展開キット, EX親と子)||||||||||
|PSW||||||||||
|英文キット|||||||||言語切り替え機能で対応。|
|アテンションライト||||||||||
|Key Switch||||||||||
|関連商品アダプターキット||||||||||
|併設キット||||||||||


###### 制限・注意事項/備考

-   言語切り替えはシステムデータによる切り替えの言語切り替えは実施する。FXテリトリでは、日本語と英語、韓国語と英語、中国語と英語の組み合わせのみ対応する。

-   M/NはISO8859で定義される言語の組み合わせに対応可能。

-   HDDは、標準。

-   ColorEPC,BWEPCは、標準。

-   Copy全面AE,ACCを行うためには、拡張メモリが最低でも1面分必要。Scanカラー自動(PGS0081SGP)を行うためには、3面必要。

-   DADFは、標準。

-   DADF(PF1)反転両面は、ない。

-   トレイ1～トレイ4は、標準。

-   SMH(手差しトレイ)は、標準。

-   Inverterは、標準。

-   HCF1は、ない。

-   C Finisherは、ない。C FinisherにしかないMailBoxもなし。

-   SCTは、ない。

-   OCTは、ない。

-   エディターパッドは、ない。

-   分離IITは、ない。

-   ウイングテーブルは、ない。

-   プラテンキットは、ない。

-   ディスペンサー2は、ない。

-   入金装置5は、ない。

-   入金装置6Nは、ない。

-   M/N,APは、現時点(20021128)で詳細不明。

###  システムデータ

###### 概要
以下では主にUIにボタンを配置すべきかどうかの判断に関係するシステムデータを記述する。
1) Imari/PGS7018SGP

|項目|M/C default|設定範囲|備考|
|---|---|---|---|---|
|基本コンフィグレーション||||
|機械シリアルNo.|-|ASCII文字列||
|商品コード|-|ASCII文字列||
|装置の種類|-(CFP)|P<br/>SP<br/>CP<br/>CFP<br/>(C)<br/>||
|OEM/個別対応区分|-(Normal)|0:Normal<br/>1:サークルケイ<br/>2:松下OEM<br/>3:(NTTOEM)<br/>||
|コヒーレント区分|<br/>2002.9.10修正<br/>(CH3862)<br/>Imari時:FX<br/>Allagash時:MN<br/>|0:FX (4Tab対応)<br/>1:MN (6Tab対応)<br/>2:Advanced<br/>||
|MNプロダクト区分|<br/>2002.9.10修正<br/>(CH3862)<br/>Imari時:FX<br/>Allagash時:Allagash<br/>|0:FX<br/>1:Carrera<br/>2:Allagash<br/>||
|ロケール||||
|テリトリ情報(FX,PGS1003SGP,PGS2003SGP,AP)|-(FX)|FX<br/>PGS1002SGP<br/>PGS2003SGP<br/>AP<br/>||
|OEM情報|OFF|OFF<br/>ON<br/>||
|言語情報|-(日本語)|日本語<br/>英語<br/>フランス語<br/>ドイツ語<br/>イタリア語<br/>スペイン語<br/>ポルトガル語<br/>ロシア語<br/>中国語<br/>韓国語<br/>タイ語<br/>ベトナム語<br/>台湾語<br/>||
|国コード (ISO3316の値を適用)|-(Japan)|0=未定義<br/>840 =USA(default) , 124=Canada ,<br/>076=Brazil ,<br/>3=Latin America→アサイン不可<br/>826= UK (default) , 276=Germany ,<br/>380=Italy ,<br/>250=France ,<br/>724=Spain ,<br/>528=Holland ,<br/>756=Swiss ,<br/>752=Sweden , 056=Belgium , 040=Austria , 620=Portugal , 246=Finland , 208=Denmark , 578=Norway , 300=Greece , 372=Ireland , 036=Australia ,<br/>554=New Zealands , 360=indonesia , 702=Singapore , 458=Malaysia , 608=Philippin , 764=Thailand ,<br/>344=Hong Kong , 704=Vietnum,<br/>392=Japan,<br/>158=Taiwan,<br/>410=Korea<br/>||
|Device Moduleオプション||||
|DADFの有無|自動検知|なし(Platen)<br/>あり<br/>||
|トレイ段数|自動検知|1Tray<br/>2Tray<br/>4Tray<br/>||
|TTMの有無|自動検知|なし/あり||
|サイドトレイの有無|自動検知|なし/あり||
|Output装置の有無種類|自動検知|装置なし<br/><br/>Light Finisher<br/><br/>||
|OCT|自動検知|なし/あり||
|Exit2|自動検知|なし/あり|PGS7018SGP固有|
|Exit2 Tray|なし|なし/あり|PGS7018SGP固有|
|DM(両面)の有無|自動検知|なし/あり||
|Token Ringボードの有無|自動検知|なし/あり/故障中||
|Memory関連||||
|HDDの有無|自動検知|なし/あり/故障中||
|ページメモリサイズ(容量)|自動検知|bytes|Imariではオプションによる容量増加可能|
|システム(バッファ)メモリサイズ(容量)|自動検知|bytes||
|電子ソートプリント領域の状態|自動検知|無効/有効|HDDなしでEPC機能実施|
|電子ソートコピー領域の状態|自動検知|無効/有効|HDDなしでEPC機能実施|
|親展ボックス領域の状態|自動検知|無効/有効|HDDなしで親展ボックス機能実施|
|Copy関連||||
|結合ジョブ|無効(表示しない)|有効(表示する)<br/>無効(表示しない)<br/>||
|認証/集計機能関連||||
|認証/集計機能 Mode|OFF|OFF/ON||
|Password 認証/集計機能 対象サービスCopy|OFF|OFF/ON|CH3244により追加<br/>「12.2 Password 認証/集計機能」参照<br/>|
|Password 認証/集計機能 対象サービスPrint|OFF|OFF/ON|CH3244により追加<br/>「12.2 Password 認証/集計機能」参照<br/>|
|Password 認証/集計機能 対象サービスScan|OFF|OFF/ON|CH3244により追加<br/>「12.2 Password 認証/集計機能」参照<br/>|
||||(CH4663より削除)|
|Password 認証/集計機能 対象サービスFAX/インターネットファクス|OFF|OFF/ON|CH3244により追加<br/>「12.2 Password 認証/集計機能」参照<br/>|
|Printer関連||||
|搭載しているPDL|自動検知|ART PGS2003SGP(PLW) 0x0001<br/>ART IV 0x0002<br/>PS3 0x0004<br/>HPGL 0x0008<br/>PCL 0x0010<br/>ESCP 0x0020<br/>PCPR(201H) 0x0040<br/>の組み合わせ<br/>||
||||CH3392対応により削除|
||||CH3392対応により削除|
|Scan関連(Mailbox/Server/Email)||||
|Scan機能設定|有効|無効/有効||
|Scan PGS0081SGP Option|OFF|OFF/ON|CH3520対応により追加。「4.2.5.7 カラーモード」を参照する。|
|ScanToMailbox||||
|Salutationポート|停止|起動/停止||
|EWSポート|停止|起動/停止||
|ScanToServer関連||||
|Ftp Clientポート|停止|起動/停止||
|ScanToEmail関連||||
|Scan to Email機能の有無|なし|なし/あり||
|ホスト名(TCPIPホスト名)|NULL|ASCII文字列||
|Fax関連||||
|Fax Cardの実装状態|自動検知|正常<br/>エラー<br/>実装されていない<br/>||
|Ch0用実装の有無|自動検知|なし<br/>内線(PSTN)<br/>外線PSTN (実際はない)<br/>ISDN (実際はない<br/>||
|Ch1用実装の有無|自動検知|なし<br/>内線(PSTN)(実際はない)<br/>外線PSTN<br/>ISDN (実際はない)<br/>||
|Ch2用実装の有無|自動検知|なし<br/>内線(PSTN) (実際はない)<br/>外線PSTN<br/>ISDN<br/>||
|Ch3用実装の有無|自動検知|なし<br/>内線(PSTN) (実際はない)<br/>外線PSTN<br/>ISDN<br/>||
|Ch4用実装の有無|自動検知|なし<br/>内線(PSTN) (実際はない)<br/>外線PSTN<br/>ISDN<br/>||
|Ch5用実装の有無|自動検知|なし<br/>内線(PSTN) (実際はない)<br/>外線PSTN<br/>ISDN<br/>||
|内線機能の有無|無効|無効<br/>有効<br/>||
|インターネットファクス関連||||
|Scan to Email機能の有無|なし|なし/あり||
|||<br/><br/>||
|||<br/><br/>||
|||<br/><br/>||
|SMTP/POP受信起動|SMTP受信|停止<br/>SMTP受信<br/>POP受信<br/>||
|自機メールアドレス|NULL|ASCII文字列||
|管理者メールアドレス|NULL|ASCII文字列||
|Scan To Email/インターネットファクス共通||||
|SMTP送信I/F|起動|停止/起動||
|SMTPサーバアドレス(ホスト名)|NULL|ASCII文字列||
|SMTPサーバアドレス(IPアドレス)NVM|0.0.0.0|各0～255||
|SMTPサーバアドレス(IPアドレス)RAM|0.0.0.0|各0～255|CH3585対応|
|自機ドメイン名(TCPIP DNSホスト名)|NULL|ASCII文字列||
|SMTP AUTO CONFIG(アドレス取得方式)|DHCP|マニュアル<br/>DHCP<br/>|CH3585対応|
|TCP/IP関連(ScanToServer/Email/インターネットファクス共通)||||
|TCP/IP-IPアドレス|0.0.0.0|各0～255||
|TCP/IP-ゲートウエイアドレス|0.0.0.0|各0～255||
|TCP/IP-ネットマスク|0.0.0.0|各0～255||
|EP関連商品||||
|関連商品の種類|なし|なし<br />Copy PGS2038SGP(加算型)、<br/>Copy PGS2038SGP(減算型)、<br/>Dispenser、<br />Coin Kit<br />Copy PGS2038SGPとDispenserの併設<br />Copy PGS2038SGPとCoin Kitの併設<br />DispenserとCoin Kitの併設<br/>||
|||||
|FAX部門管理||<br/><br/>|CH3294により削除|
|PGS1103SGP,EP関連商品の接続有無|なし|なし/あり||
|(PGS1103SGP)電話回線の接続有無|なし|なし/あり||
|その他||||
|CEモード|Normal Mode|Normal Mode<br/>CE Mode<br/>||
|ミリインチ切換え<br/><br/>|(Millimeter)|<br/><br/>5:A4 Millimeter<br/>44:レター Inch<br/>|(参考 Chain-Link No 700-397)|
|デフォルト用紙サイズの指定|(A4)|5:A4<br/>44:レター<br/>|(参考 Chain-Link No 700-397)<br/>備考<br/>自動階調補正で使用する用紙サイズの切換えで、上段ミリインチ切換えと同一システムデータを使用する。ただし対応するラベル定義は別定義とする。<br/>|


###### 制限・注意事項/備考

-   装置の種類において、PはMFに無関係。

-   Output装置の有無と種類のTower MailboxはMFではなし。


###### 参考資料
仮性能仕様書
システム基本仕様書(System Overview編)


2) Fuhjin/Raijin/Tarzan

|項目|M/C default|設定範囲|備考|
|---|---|---|---|---|
|基本コンフィグレーション||||
|機械シリアルNo.|-|'英数字(ASCII)最大10桁)||
|商品コード|-|ASCII文字列||
|装置の種類|TBD|P<br/>SP<br/>CSP<br/>CFSP<br/>(、C)<br/>|(CはM/Nで要求あり) 工場生産時に設定する。 P(rinter), F(ax), C(opy), S(can) にそれぞれ以下のようにビットを割り当て、その論理和で表現する。 P:0x01、F:0x02、C:0x04、S:0x08  尚、SPとMF-CSPを区別するため、SPは 0x09 を割り当てるものとする。|
|Panel表示切り替えスイッチ1(OEM/個別対応表示切り替え用)|0:標準|0:標準<br/>1:サークルK<br/>2:松下OEM<br/>3:NTT<br/>||
|Panel表示切り替えスイッチ2(Coherent表示切り替え用)|'0&lt;--Imari<br/>1&lt;--Allagash<br/>|0:4 Tab Coherent UI<br/>1:6 Tab Coherent UI<br/>2:Advanced UI<br/>|Fuhjin/Raijin/tarzanでの値は、TBD。|
|Panel表示切り替えスイッチ3(表示切り替え用)|0&lt;--Imari<br/>2&lt;--Allagash<br/>1&lt;--CARRERA<br/>|0:FX Behabvior<br/>1:Carrera Behabior<br/>2:Allagash Behavior<br/>|Fuhjin/Raijin/tarzanでの値は、TBD。|
|ロケール||||
|テリトリ情報(FX,PGS1003SGP,PGS2003SGP,AP)|-|1=FX<br/>2=PGS1002SGP<br/>3=PGS2002SGP<br/>4=AP<br/>||
|OEM情報|OFF|OFF<br/>ON<br/>||
|言語情報|1:日本語|1:日本語<br/>2:英語<br/>3:フランス語<br/>4:ドイツ語<br/>5:イタリア語<br/>6:スペイン語<br/>7:ポルトガル語<br/>8:ロシア語<br/>9:中国語<br/>10:韓国語<br/>11:タイ語<br/>12:ベトナム語<br/>13:台湾語<br/>14:オランダ語<br/>15:デンマーク語<br/>16:スウェーデン語<br/>17:フィンランド語<br/>18:ノルウェー語<br/>||
|国コード (ISO3316の値を適用)|0 = 未定義|0 = 未定義<br/>840 =USA<br/>124=Canada<br/>076=Brazil<br/>3=Latin America→アサイン不可<br/>826= UK<br/>276=Germany<br/>380=Italy<br/>250=France<br/>724=Spain<br/>528=Holland<br/>756=Swiss<br/>752=Sweden<br/>056=Belgium<br/>040=Austria<br/>620=Portugal<br/>246=Finland<br/>208=Denmark<br/>578=Norway<br/>300=Greece<br/>372=Ireland<br/>036=Australia<br/>554=New Zealands<br/>360=indonesia<br/>702=Singapore<br/>458=Malaysia<br/>608=Philippin<br/>764=Thailand<br/>344=Hong Kong<br/>704=Vietnum<br/>392=Japan<br/>158=Taiwan<br/>156=China<br/>410=Korea<br/>|複数国に対応されているEPROMにて、システムデータのデフォルト値を目的の国に設定変更するためのキーコード。<br/>本データを設定変更すれば、即目的の国のシステムデータ群に置き換わる。<br/>|
|Device Moduleオプション||||
|DADFの有無|自動検知|0:"無し"<br/>1:"有り"<br/>||
|トレイ段数|自動検知|1:1Tray<br/>2:2Tray<br/>3:3Tray<br/>4:4Tray<br/>5:5Tray<br/>6:6Tray<br/>7:7Tray<br/>|(※1) SMHは、トレイ段数に含めない。|
|HCF1の有無|自動検知|1:あり<br/>0:なし<br/>||
|HCF2の有無|自動検知|1:あり<br/>0:なし<br/>||
|InterposerTrayの有無|自動検知|1:あり<br/>0:なし<br/>||
|両面Printモジュールの有無|自動検知|1:あり<br/>0:なし<br/>||
|Output装置の有無と種類|自動検知|0:Output装置無し<br/>0x0001:Finisher<br/>||
|SCTの有無|自動検知|1:あり<br/>0:なし<br/>||
|OCTの有無|自動検知|1:あり<br/>0:なし<br/>||
|C Finisherの有無|自動検知|1:あり<br/>0:なし<br/>||
|D Finisherの有無|自動検知|1:あり<br/>0:なし<br/>||
|BookletMakerの有無|自動検知|1:あり<br/>0:なし<br/>||
|FolderUnitの有無|自動検知|1:あり<br/>0:なし<br/>||
|MailBoxの有無|自動検知|1:あり<br/>0:なし<br/>||
|Memory関連||||
|HDDの有無|自動検知|0:あり<br/>1:故障中<br/>2:なし<br/>||
|ページメモリサイズ(容量)|自動検知|bytes||
|ページバッファメモリ|自動検知|bytes||
|電子ソートプリント領域の状態???|自動検知|無効/有効|HDDなしでEPC機能実施|
|電子ソートコピー領域の状態???|自動検知|無効/有効|HDDなしでEPC機能実施|
|親展ボックス領域の状態???|自動検知|無効/有効|HDDなしで親展ボックス機能実施|
|Copy関連||||
|結合ジョブの設定メニュー表示有無の切り替え|'0 : 表示しない<br/><CARRERA>は1<br/>|0 : 表示しない<br/>1 : 表示する<br/>||
|認証/集計機能関連||||
|CE 認証/集計機能 Mode|OFF|0 : 表示しない<br/>1 : 表示する<br/>|国内:表示しない<br/>AP:表示するIchiro:表示しない<br/>Ginga:表示しない<br/>|
|認証/集計機能 Color Mode|0 : ALL|0 : ALL<br/>1 : COLOR<br/>2 : FULL COLOR ONLY<br/>||
|認証/集計機能 Mode Copy|0 : OFF|0 : OFF<br/>1 : ON<br/>||
|認証/集計機能 Mode Print|0 : OFF|0 : OFF<br/>1 : ON<br/>||
|認証/集計機能 Mode Scan|0 : OFF|0 : OFF<br/>1 : ON<br/>||
||||CH4663により削除。|
|認証/集計機能 Mode FAX インターネットファクス|0 : OFF|0 : OFF<br/>1 : ON<br/>||
|Printer関連||||
|搭載しているPDL|自動検知|以下の論理和を返却する<br/>ART PGS2003SGP(PLW) 0x00000001<br/>ARTⅣ  0x00000002<br/>PS3  0x00000004<br/>HPGL  0x00000008<br/>PCL  0x00000010<br/>ESCP  0x00000020<br/>PCPR(201H)  0x00000040<br/>KS5843 0x00004000<br/>KSSM 0x00020000<br/>KS5895 0x00040000<br/>||
|Scan関連(Mailbox/Server/Email)||||
|SCAN機能設定|0:有効|0:有効<br/>1:無効<br/>||
|Scan To Email機能設定|0:&quot;無効&quot;|1:&quot;有効&quot;<br/>0:&quot;無効&quot;<br/>||
|ScanToMedia機能設定|TBD:&quot;無効&quot;|TBD:有効<br/>TBD:無効<br/>||
|ScanToFTPサービス|TBD:"起動しない"|TBD:起動する<br/>TBD:起動しない<br/>||
|'ScanToSMBサービス|TBD:"起動しない"|TBD:起動する<br/>TBD:起動しない<br/>||
|SCAN PGS0081SGPメニュー表示設定|0:表示しない|0:表示しない<br/>1:表示する<br/>||
|ScanToMailbox||||
|Salutation起動設定|0 : 停止<CARRERA>は1|0 : 停止<br/>1 : 起動<br/>||
|EWS起動設定|1 : 起動|0 : 停止<br/>1 : 起動<br/>||
|ScanToServer関連||||
|Ftp Client起動設定|0 : 停止<br/><CARRERA/Allagash>は1 : 起動<br/>|0 : 停止<br/>1 : 起動<br/>||
|ScanToEmail関連||||
|ScanToEmail(インターネットファクス送信)機能設定|0:&quot;無効&quot;|1:&quot;有効&quot;<br/>0:&quot;無効&quot;<br/>||
|(TCP/IP)ホスト名<br/>(SMB ポートのホスト名と同じもの)<br/>|TBD|'Shift JIS 1～32バイト||
|Fax関連||||
||||TBD|
|インターネットファクス関連||||
||||TBD|
|Scan To Email/インターネットファクス共通||||
|SMTP送信起動|1:&quot;起動|0:&quot;停止&quot;<br/>1:&quot;起動<br/>||
|SMTPメールサーバホスト名|NULL|ASCII 128文字|SMTPメールゲートウェイIPアドレスが設定されずに、DNSサーバーがあるときのみ|
|SMTPメールサーバIPアドレス|0.0.0.0|00000000～FFFFFFFF||
|SMTPメールサーバIPアドレス(RAM)|0.0.0.0|00000000～FFFFFFFF||
|DNSドメイン名|NULL|DNSドメイン名(通常、表記されない最後の"."(ドット)を含めて255文字以内||
|SMTP Auto Config|0x02:DHCP|0x10:手動設定<br/>0x02:DHCP<br/>||
|TCP/IP関連(ScanToServer/Email/インターネットファクス共通)||||
|TCP/IP-IPアドレス|0.0.0.0|00000000～FFFFFFFF||
|TCP/IP-ゲートウエイアドレス|0.0.0.0|00000000～FFFFFFFF||
|TCP/IP-サブネットマスク|0.0.0.0|00000000～FFFFFFFF||
|EP関連商品||||
|関連商品の種類|なし|0 = なし<br/>1 = Copy PGS2038SGP(加算型)<br/>2 = Copy PGS2038SGP(減算型)<br/>3 = Dispenser<br/>4 = Coin Kit<br/>5 = Copy PGS2038SGPとDispenserの併設<br/>6 = Copy PGS2038SGPとCoin Kitの併設<br/>7 = DispenserとCoin Kitの併設<br/>||
|PGS1103SGP,EP関連商品の接続有無|0=なし|0=なし<br/>1=あり<br/>||
|(PGS1103SGP)電話回線の接続有無|0=なし|0=なし<br/>1=あり<br/>||
|その他||||
|CEモード???|Normal Mode|Normal Mode<br/>CE Mode<br/>|「Power Off前モード(PSWからDiag)の事?|
|MF-UIのミリ/インチ表示切替…<br/>レポートのデフォルト用紙サイズ(及びMF-UIのミリ/インチ表示切替にも使用)<br/>|5:A4 Millimeter|5:A4 Millimeter<br/>44:レター Inch<br/>||
|デフォルト用紙サイズの指定…<br/>レポートのデフォルト用紙サイズ(及びMF-UIのミリ/インチ表示切替にも使用)<br/>|5:A4 Millimeter|5:A4 Millimeter<br/>44:レター Inch<br/>|(参考 Chain-Link No 700-397)<br/>備考<br/>自動階調補正で使用する用紙サイズの切換えで、上段ミリインチ切換えと同一システムデータを使用する。ただし対応するラベル定義は別定義とする。<br/>|


###### 制限・注意事項/備考

-   

###### 参考資料
風神/雷神 仮性能仕様書(パフォーマンス編)
システム基本仕様書(System Overview)
Fuhjin/Raijin/Tarzan) IOT Device Function FF
Fuhjin/Raijin/Tarzan) IIT Device Function FF
☆ 5-グリーンブック コント システムデータ(C2DE).xls20030117版

## Concurrent

本章では、コンカレント仕様について記述する。

システムのコンカレント処理能力については、システム基本仕様書(Architecture編)を、ジョブとジョブ及び、システム状態(故障を含む)詳細なコンカレントマトリックスについてはシステム基本仕様書(Feature
& Function編)に記載されるため、それらを参照のこと。