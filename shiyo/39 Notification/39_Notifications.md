[1. NotificationPGS2132SGPとNotificationsList
2](#_Toc4664781)

[1.1. LUIの役割 2](#_Toc4664782)

[1.1.1. デバイスの状態を表示する
2](#デバイスの状態を表示する)

[1.1.1.1. DeviceApp>Notifications画面で状態を表示する
2](#deviceappnotifications画面で状態を表示する)

[1.1.1.2. NotificaitonPGS2132SGPPGS2132SGPで自動的に状態を表示する
2](#notificaitonpgs2132sgppgs2132sgpで自動的に状態を表示する)

[1.1.2. 操作を提供する 2](#操作を提供する)

[1.2. Notificationsの対象 2](#_Toc4664787)

[1.3. 表示項目と動作 3](#_Toc4664788)

[1.3.1. 共通の表示項目/動作 3](#共通の表示項目動作)

[1.3.1.1. タイトルについて 3](#タイトルについて)

[1.3.2. NotificationPGS2132SGPの表示項目/動作
3](#notificationpgs2132sgpの表示項目動作)

[1.3.3. リスト画面の表示項目/動作
4](#リスト画面の表示項目動作)

[1.3.4. 詳細画面の表示項目/動作
4](#詳細画面の表示項目動作)

[1.3.5. History画面の表示項目/動作
5](#history画面の表示項目動作)

[1.4. 改訂履歴 6](#_Toc4664795)

# 

1.  NotificationPGS2132SGPとsList

TOKIWA
Local-UI(LUI)における、NotificationPGS2132SGPとNotificationsListの表示・動作について記述する。

仕様書中に表示される正式な名称は、最新のダイアログ仕様書参照の事。

同様に、本書で表記される「イメージ」は、理解を容易するための参考情報であるため、正しい情報は、ダイアログ仕様書またはイメージデータそのものを参照の事。

1.  LUIの役割

NotificationPGS2132SGPとNotificationsListにおけるLUIの役割は、以下の通り。

### デバイスの状態を表示する

デバイスの状態をLUI画面上に表示する。この方法として、(1)Device>Notificationsに表示 (2)NotificationPGS2132SGP(自動的に表示) がある。

#### DeviceApp>Notifications画面で状態を表示する

DeviceApp>Notificationsボタン押下により、リスト画面を表示し、現在の状態を表示する。

リストの具体的な表示内容については、5.3章参照のこと。

DeviceApp>Notificationsは\[FaultHistory\]ボタンを持っており、FaultHistoryを参照することができる。

#### NotificaitonPGS2132SGPPGS2132SGPで自動的に状態を表示する

対象の事象が発生した時、NotificationPGS2132SGPを表示し、現在の状態を表示する。

■共通表示条件は次の通り:

- 対象の事象が発生した時

- 対象の事象が発生している状態で、UIが立ちあがった時

■共通消去条件は次の通り:

- 事象が解除された時

- 閉じるボタンで閉じた時

■共通再表示タイミングは次の通り:

- 事象に変化があったとき(新しいエラーが発生したときなど)

- オートクリア動作発生時(オートクリア動作はUI Basic Bahavior
Specを参照のこと)

■以下のエラーは、NotificationPGS2132SGP表示の対象にしない。

|ChainLink|内容|備考|
|---|---|---|---|
|003-974|次原稿待ち||
|016-426|PGS1085SGP serverと接続不可|CH36441|
|062-400|Platen InterLock Open & DADF Doc OFF|BG237006|
|024-986|ProofPrint時の残り部数Print是非確認||
||||


事象が発生してもNotificationPGS2132SGPを自動表示しない。DeviceApp>Notificationsには表示される。

### 操作を提供する

ユーザーへの操作を提供する。

NotificationPGS2132SGP及びNotificationsListで提供する操作は画面遷移のみ。カウンターリセット操作やUpdate操作、ジョブ中止操作等は、専用の画面で行うためココでは提供しない。

注)Notifications からジョブ削除は出来ない:

ジョブ中に用紙切れ等のエラーが発生した場合、ジョブエラー画面が自動で表示される。

この画面では、エラーの解除ガイドを表示すると共に、ジョブの削除を提供している(OperaionError/Notice)。

仮にこの画面を閉じて、NotificationsListを開くと、用紙切れエラーが発生していることが確認できるが、Notifications画面から表示させたエラー画面からはジョブの削除を行う事はできない。

これは、Notificationsはジョブとの関連付けを持たない為である。

ジョブを削除する場合は、Jobsから削除操作する必要がある。

1.  Notificationsの対象

以下に、Notificationsでの表示対象を示す。

NotificationsListで対象とする事象は、エラーコードを持った事象に限る。

||Notifications<br/>表示対象<br/>|アイコン|備考|
|---|---|---|---|---|
|SystemFail|○|Fault|※実際にはFault画面とNotificaitonPGS2132SGPは共存しないので見ることができない。CE-DiagでSystemFail画面を閉じた場合に見ることが可能。|
|SubSystemFail|○|Fault||
|ServiceFail|○|Fault||
|LocalFail|○|Fault||
|Job|×|||
|Jam(Static)<br/>Jam(Dynamic)<br/>|△|Fault|JamZoneのChainLinkのみが対象となる。|
|DeviceError|○|Fault||
|OperationError|○|Fault||
|Notice|○|Fault||
|Warnning|×|||
|Record|×|||
|Info|○|Alert||


   ※上記アイコンは、基本仕様であり、個々のChainLinkでどのアイコンを採用するかはダイアログ仕様書参照のこと

1.  表示項目と動作

表示項目について記載する。

ChainLink毎の表示内容については、Dialog仕様書「11. Fault」参照の事。

### 共通の表示項目/動作

#### タイトルについて

タイトルは基本的に、バナーもリストも詳細表示も、同じものを使用する。

エラー種別とタイトルにについて:

エラーの種別より、専用/汎用タイトルが使われる。

|種別|タイトル|備考|
|---|---|---|---|
|SystemFail|汎用|汎用タイトルの例:<br/>・故障あるいは異常が発生しています。XXX-XXX<br/>|
|SubSystemFail|汎用| ↑|
|ServiceFail|汎用| ↑|
|LocalFail|汎用| ↑|
|Jam|汎用|汎用タイトルの例:<br/>・ジャムが発生しています。XXX-XXX<br/>|
|DeviceError|専用|専用タイトルの例:<br/>・黒トナー切れです。<br/>・カバーを閉じてください(XXX-XXX)。<br/>|
|OperationError/ Notice|専用・汎用|専用タイトルの例(消耗品と用紙切れのみ):<br/>・イエロートナー切れ。※1<br/>・トレイ1の用紙が無くなりました。<br/>汎用タイトルの例:<br/>・ジョブが停止しています。XXX-XXX<br/>|
|Info|専用・汎用|専用タイトル(消耗品)の例:<br/>・イエロートナーが少なくなっています。※1<br/>汎用タイトル(ネットワーク系エラー等)の例:<br/>・故障あるいは異常が発生しています。XXX-XXX<br/>|


正しい表現は、ダイアログ仕様書参照の事。

※1消耗品の場合、部材名+状態で表現する。

### NotificationPGS2132SGPの表示項目/動作

NotificaitonPGS2132SGPには、タイトルが表示される。複数存在する場合は「他に何件あるのか」という情報も表示する。

■動作:

共通表示条件に書かれている条件で、表示・消去・再表示を行う。

複数発生している場合は、優先度の一番高いものを表示する。

※優先度の低い事象が追加で発生した場合も、バナー上に表示されるのは優先度の高い事象となる。

NotificationPGS2132SGPとリスト画面:

リストを表示する際、NotificationPGS2132SGPを消す。

### リスト画面の表示項目/動作

リスト画面には、「アイコン」「タイトル」「発生日時」を表示する。

発生日時はDATETIME型でシステム設定に従い表示形式を変える。

DeviceApp>NotificationsListでは、FaultHIstoryを確認することができる。

■動作:

- DeviceApp>Notificationsがタップされたとき、DeviceAppNotificationsListを表示する。

- NotificationPGS2132SGPがタップされ且つ複数事象が複数ある場合、NotificationPGS2132SGPListを表示する。

リスト表示中に0個になった時の動作

 -DeviceApp NotificationsList : リスト画面を維持したまま、「No
List」である旨を表示する

 -DevciePGS2132SGP NotificationsList : リスト画面を閉じる

### 詳細画面の表示項目/動作

詳細画面では、「タイトル」「ChainLink」の他に、Additional
Information(ガイドメッセージ)を表示する。

||画面|ガイドメッセージの主旨|詳細画面例|
|---|---|---|---|---|
|SystemFail<br/>SubSystemFail<br/>ServiceFail<br/>LocalFail<br/>|汎用|マニュアルで番号を確認してください。||
|Jam|専用|- (専用画面なので専用メッセージになる)||
|DeviceError|専用|- (専用画面なので専用メッセージになる)||
|OperationError|汎用|(紙切れ )Jobs画面でジョブを確認してください<br/>(消耗品 )専用画面なので専用メッセージ<br/>(上記以外) Jobs画面でジョブを確認してください<br/>| |
|Notice|汎用|Jobs画面でジョブを確認してください||
|Info|汎用|(消耗品) 詳細はSupply画面を確認してください。<br/>(消耗品以外) マニュアルで番号を確認してください。<br/>| |


### History画面の表示項目/動作

FaultHistory画面では、「FaultCode」「日時」「カウンター」を表示する。

■動作

DeviceApp>Notifications &gt;
Historyボタン押下により Historyを参照することができる。

画面表示の対称にするフォルトは以下の通り(CH12407)

- System

- SubSystem

- Local

- Service

- DynamicJam

- JobFail

History画面は、画面表示時点のスナップショットで表示する。動的に変化しない。
