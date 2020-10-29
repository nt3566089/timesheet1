# Memory残量

###### 概要

Userに対してMemoryの残量表示を行う。

###### 動作

Memory残量の通知(Cont.からの通知時)毎に表示を行う。

Copy、Fax、Scanner、Boxの各サービスは、各画面の基本、待機中、実行中画面に表示し、表示単位は%で表示する。

UIが取得可能なパーティション種別(FF参照)と表示対象のサービス、ジョブは以下の通り。

||残量表示するパーティション種別|||
|---|---|---|---|---|
||設定画面|実行中画面||
|CopyService|Copy|コピー|←|
||らくらくコピー|コピー|←|
||Copy&amp;保存、保存|Scan|←|
|FaxService|Fax|Fax|←|
||らくらくファクス|Fax|←|
||インターネットファクス|Fax|←|
||sipFax|Fax|←|
||ServerFax|Scan|←|
|ScanService|ScanToMailBox|Scan|←|
||ScanToPC|Scan|←|
||ScanToEmail|Scan|←|
||ScanToServer|Scan|←|
||ScanToURL|Scan|←|
||ScanToMedia|非表示|←|
|BMLinkSService|BMLinkSScan|Scan|←|
|BoxService|拡張親展ボックス|Scan|非表示|
||再出力用ボックス|Scan|部数変更画面のみScan<br/>その他は非表示<br/>|


###### 制限・注意事項/備考

Memory残量の表示は、Hard Disk装着時、RAMDisk実装時に表示される。

Hard Diskの故障発生後は、Memory残量表示のUpdateは行なわない。又、Power
On時にHard Diskが故障していた場合は、Memory残量の表示は行なわない。

MNではMemory残量表示は行わない(RF1486/CH12310)。

###### 参考資料

FF :システム基本仕様書蓄積装置