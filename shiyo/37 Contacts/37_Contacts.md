# 目次

[1. はじめに 1-2](#はじめに)

[2. 機能概要 2-3](#機能概要)

[3. 機能詳細 3-4](#機能詳細)

[3.1. 宛先一覧表示 3-4](#宛先一覧表示)

[3.1.1. Table
Index 3-4](#table-index)

[3.1.2. 宛先種別のフィルタリング
3-5](#宛先種別のフィルタリング)

[3.2. 宛先検索 3-5](#宛先検索)

[3.2.1. Intelligent Search 3-5](#intelligent-search)

[3.2.2. Full
Search 3-5](#full-search)

[3.3. 個人宛先(Contact)詳細
3-5](#個人宛先contact詳細)

[3.4. グループ宛先(Group)詳細
3-6](#グループ宛先group詳細)

[3.5. 個人宛先(Contact)の追加/編集/削除
3-6](#個人宛先contactの追加編集削除)

[3.6. グループ宛先(Group)の追加/編集/削除
3-7](#グループ宛先groupの追加編集削除)

[3.7. Favorite/Contact一覧(AddressBookUtility)
3-7](#favoritecontact一覧addressbookutility)

[3.7.1. Favoriteリスト 3-7](#favoriteリスト)

[3.7.2. Contactリスト 3-7](#contactリスト)

[3.7.3. 宛先選択 3-7](#宛先選択)

[3.8. Add
Contact一覧(Personalize Favorites)
3-7](#add-contact一覧personalize-favorites)

[4. AddressBookアプリ機能提供条件
4-8](#addressbookアプリ機能提供条件)

[5. LDAPアドレス帳(リモートアドレス帳)
5-9](#ldapアドレス帳リモートアドレス帳)

[5.1. 機能提供条件 5-9](#機能提供条件)

[5.2. 検索上限数 5-9](#検索上限数)

[6. AddressBookの権限 6-10](#addressbookの権限)

[6.1. アドレス帳アクセス権限
6-10](#アドレス帳アクセス権限)

[6.2. 宛先作成権限 6-10](#宛先作成権限)

[6.3. 宛先編集権限 6-10](#宛先編集権限)

[7. 宛先登録上限値 7-11](#宛先登録上限値)

[7.1. 個人宛先(Contact) 7-11](#個人宛先contact)

[7.2. グループ宛先(Group) 7-11](#グループ宛先group)

[8. 宛先種別提供条件 8-12](#宛先種別提供条件)

[8.1. Email 8-12](#email)

[8.2. Fax
8-12](#fax)

[8.3. IP(SIP)Fax 8-12](#ipsipfax)

[8.4. InternetFax 8-12](#internetfax)

[8.5. SMB
8-12](#smb)

[8.6. FTP
8-12](#ftp)

[8.7. SFTP
8-12](#sftp)

[8.8. Email
Group 8-12](#email-group)

[8.9. Fax
Group 8-12](#fax-group)

[9. S/MIME判定条件 9-13](#smime判定条件)

[10. One and Done
/ Multiple Selection 10-14](#one-and-done-multiple-selection)

[11. 宛先一覧仕様 11-15](#宛先一覧仕様)

[12. 宛先ソート仕様 12-16](#宛先ソート仕様)

[12.1. Contactリスト 12-16](#contactリスト-1)

[12.2. Favoriteリスト・Search(Intelligent Search / Full
Search)
12-16](#favoriteリストsearchintelligent-search-full-search)

[13. 宛先検索仕様 13-17](#宛先検索仕様)

[13.1. 個人宛先の検索属性 13-17](#個人宛先の検索属性)

[13.2. グループ宛先の検索属性
13-17](#グループ宛先の検索属性)

[14. 他アプリ起動条件 14-18](#他アプリ起動条件)

[15. 入力文字数上限 15-19](#入力文字数上限)

[16. Fax二度入力オプション
16-20](#fax二度入力オプション)

[17. 変更履歴 17-21](#変更履歴)

# はじめに

TOKIWA-PF2.2以降のContacts(AddressBook / AddressBookUtility / Contact /
Group / Search)における機能仕様を記載する。

<img src="image\37_Contacts/media/image1.png" />

# 機能概要

AddressBookは、ドキュメントの配布先となるContactや、複数のContactをまとめたGroupを取り扱うためのアプリケーション及びUtilityである。
下記の機能を提供する。
- デバイス内のアドレス帳(ローカルアドレス帳)に格納されているContact/Groupの一覧を表示する。
- LDAPサーバ内のアドレス帳(リモートアドレス帳)に格納されているContactを表示する。
- Contact/Groupを作成、編集、削除する。
- ローカルアドレス帳またはリモートアドレス帳から宛先を検索する。

- 各アプリの送信先としてアドレス帳内の宛先を選択する機能(AddressBookUtility)

# 機能詳細

AddressBookApp、AddressBookUtilityが提供する機能について記載する。

## 宛先一覧表示

ローカルアドレス帳に登録されているContactおよびGroupの一覧を表示する。

ContactとGroupは混在する。

デバイスから各ContactおよびGroupの情報が取得できるまでは、宛先表示部に"Loading"相当のメッセージを表示する。

このメッセージが表示されている状態では、宛先に対する操作は受け付けない。

-   表示されるContactおよびGroupの最大数

|**種別**|**最大数**|
|---|---|---|
|Contact|「FF(TBD)」参照|
|Group|「FF(TBD)」参照|


宛先が未登録の場合には、その旨を表示する。

-   ソート順序について

Contact/Groupの一覧は、ソートされて表示される。

ソートの詳細は「[Contactリスト](#contactリスト-1)」参照。

ソート順序を変更するための機能は提供しない。

-   一覧リスト上の表示項目

一覧リストの各Rowに表示する名前は、宛先名(DisplayName)使用する。宛先名は、FX/IBGとMNで仕様が異なる。下記参照。

【FX/IBG】

宛先登録時に入力された宛先名。

【MN】

宛先名に任意の文字列を入力することは出来ず、以下の優先順位で自動的に定められる。

1.  FirstName LastName

2.  FirstName

3.  LastName

4.  Company

上記、FirstName、LastName、Companyが未入力の場合は、下記の優先順位に従って宛先名を決定する。

1.  Email Address

2.  Fax Number

3.  FTP Address

4.  SFTP Address

5.  SMB Address

6.  GroupName

宛先名はBoldで表示される。ただし、FirstNameとLastNameが両方入力されている場合は、FirstNameのみBoldで表示する。

-   表示に用いられる文字数

上記Rowに用いられる宛先名(DisplayName)の最大文字列長については「[入力文字数上限](#入力文字数上限)」を参照。

画面上に表示される文字列長については規定しない。宛先名がRowの領域を超過する場合には、省略形(truncate)を使用する。

### Table Index

Indexバーから特定の文字を選び出す機能。

文字が選択されると、連動して選択された文字の宛先の位置までTableをスクロールする。

Tableに表示すべき宛先がない場合には、Disableで表示する。
Index選択時のスクロール位置の算出方法を記載する。
TableIndex操作時のキー: 【FX/IBG】 よみがなの一文字目
【MN】 DisplayNameの一文字目
WAMP I/F:SearchCount
###### queryオブジェクト addrtypeプロパティ
Queryのaddrtypeの指定は、『[宛先一覧仕様](#宛先一覧仕様)』参照

###### sortオブジェクト

Sortの指定は、『[Contactリスト](#contactリスト-1)』参照
###### filterオブジェクト

|対象属性(keys)|大文字・小文字区別(insensitive)|条件のパターン(matchtype)|検索文字列(keywords)|
|---|---|---|---|---|
|【FX/IBG】<br/>索引(よみがな)<br/>|区別しない|より小さい(less)|Indexワード|
|【MN】<br/>DisplayName<br/>||||


SearchCountで取得したcontact件数+1件目のContactの位置にスクロールする。

【参考】
例)「な」でジャンプ (TableRow=5行とする)
Case1: 登録数が5以下のとき  
Index Jumpしない。→Indexは出すか?
Case2: 「た」までしか登録されていないとき  
最後の5行を表示する。
Case3: 「な」行に登録がある。
Case3-1: 「な」行以降のデータが5以下  
最後の5行を表示する。  
Case3-2: 「な」行以降のデータが6以上
「な」行の最初の宛先が先頭に来るように表示する。
Case4: 「は」行以降に登録があるとき  
Case4-1: 「は」行以降のデータが5以下  
最後の5行を表示する。
Case4-2: 「は」行以降のデータが6以上
「は」行以降の最初の宛先が先頭に来るように表示する。

### 宛先種別のフィルタリング

ローカルアドレス帳に対して、特定の宛先種別を含むContact/Groupでフィルタリングすることができる。

フィルタリング可能な宛先種別(※)は下記の通り。

- All

- Email

- Fax

- IP Fax(SIP) <FX/IBGのみ>

- Internet Fax

- SMB(Scan)

- FTP

- SFTP

※デバイスが提供していない機能の宛先種別は表示しない。機能提供の判別は「[宛先種別提供条件](#宛先種別提供条件)」参照。

## 宛先検索

ローカルアドレス帳、リモートアドレス帳から所望の宛先を検索するための機能。

リモートアドレス帳の機能が無効の場合、またはPersonalizeFavoritesのAdd
Contact画面から開かれた検索画面では、ローカルアドレス帳からのみ検索を行う。

リモートアドレス帳の機能判定は、「[機能提供条件](#機能提供条件)」参照。

キーワードを入力して、キーワードが含まれるContactおよびGroupのみを抽出して一覧表示する。

AddressBookApp/AddressBookUtilityから宛先検索を使うことが出来る。

|**対象**|**検索対象**|
|---|---|---|
|AddressBookApp|全宛先種別のContact/Group|
|AddressBookUtility|呼び出し元アプリケーションに応じた宛先種別のContact/Group。|


検索方法は、「[Favoriteリスト・Search(Intelligent Search / Full
Search)](#favoriteリストsearchintelligent-search-full-search)」参照。

AddressBookAppの検索で、リモートアドレス帳から検索した宛先は、詳細画面からローカルアドレス帳に登録することができる。

宛先検索機能には、Intelligent SearchとFull Searchがある。

それぞれ、宛先表示の上限数が異なる。

|**検索方法**|**ローカルアドレス帳**|**リモートアドレス帳**|
|---|---|---|---|
|Intelligent Search|10|10|
|Full Search|無制限|可変。<br/>Default:50<br/>Min:5 / Max:100<br/>上限数のシステムデータは、「検索上限数」参照<br/>|


機能詳細は、「[Intelligent
Search](#intelligent-search)」、「[Full
Search](#full-search)」参照。

### Intelligent Search

Searchフィールド内の値が更新(追加・削除・変換)された時に自動的に検索を開始し、検索結果を表示する機能。

具体的な動作は以下のとおり。

1.  Searchフィールド内の値が更新されたタイミングで、その時、入力されている文字列をキーとして検索を開始する。

2.  検索結果が返る前にSearchフィールド内の値が更新された場合、検索を中断し、入力されている文字列をキーに検索を開始する。

### Full Search

キーボードのSearchが押下された時に、その時入力されている文字列をキーに検索を行う。

## 個人宛先(Contact)詳細

個人宛先(Contact)の情報として表示される項目は、下記の通り。

|**項目**|**型・選択肢**|**新規作成時**<br/>**デフォルト**<br/>|**備考**|
|---|---|---|---|---|
|宛先名(DisplayName) 【FX/IBGのみ】|文字列|空文字|【FX/IBG】では、入力必須。<br/>【MN】では、宛先名は入力不可。ただし、他の入力項目のうち最低1つは入力が必要。<br/>|
|読み方(Phonetic) 【FX/IBGのみ】|文字列|空文字||
|名(FirstName)|文字列|空文字||
|姓(LastName)|文字列|空文字||
|会社名(Company)|文字列|空文字||
|Global Favorite|ON/OFF|OFF||
|Photo|選択不可|ユーザアイコン||
|Email Address|文字列|空文字|最大1件|
|Email Favorite|ON/OFF|OFF||
|電子証明書状態|無/有効/無効|無||
|Email Address削除ボタン||||
|Email Parameter|||詳細は「TBD」参照|
|Fax番号|文字列|空文字|最大1件|
|Fax Favorite|ON/OFF|OFF||
|Fax番号削除ボタン||||
|Fax Parameter|||詳細は「TBD」参照|
|SMBサーバアドレス|文字列|空文字|SMB/FTP/SFTPは排他。<br/>SMB/FTP/SFTPのどちらか最大1件。<br/>各パラメータはBrowseUtility経由で取得する。LUIから直接入力することも可能。<br/>|
|SMB Favorite|ON/OFF|OFF||
|SMBサーバアドレス削除ボタン||||
|SMB Parameter|||詳細は「TBD」参照|
|FTPサーバアドレス|文字列|空文字|SMB/FTP/SFTPは排他。<br/>SMB/FTP/SFTPのどちらか最大1件。<br/>各パラメータはBrowseUtility経由で取得する。LUIから直接入力することも可能。<br/>|
|FTP Favorite|ON/OFF|OFF||
|FTPサーバアドレス削除ボタン||||
|FTP Parameter|||詳細は「TBD」参照|
|SFTPサーバアドレス|文字列|空文字|SMB/FTP/SFTPは排他。<br/>SMB/FTP/SFTPのどちらか最大1件。<br/>各パラメータはBrowseUtility経由で取得する。LUIから直接入力することも可能。<br/>|
|SFTP Favorite|ON/OFF|OFF||
|SFTPサーバアドレス削除ボタン||||
|SFTP Parameter|||詳細は「TBD」参照|


使用できる文字列最大長については「[入力文字数上限](#入力文字数上限)」参照。

文字列が表示領域を超える場合には、省略形(truncate)で表示する。

登録/修正時にUIから入力可能な文字種類についてはTBD。

デバイス側で機能が無効化されていても、ローカルアドレス帳から取得した送信先は表示する。

表示されている詳細項目のうち、送信先(Email/Fax/IP
Fax(SIP)/SMB/FTP/SFTP)を選択したときには、当該送信先を使用するアプリケーションを起動し、起動先で選択された送信先を表示する。

候補となるアプリケーションが複数ある場合は、その中から1つを選択させ、選択されたアプリケーションを起動する。

|**選択した項目**|**起動するアプリケーション※**|
|---|---|---|
|Email Address|Email , ScanTo|
|Fax番号|Fax、InternetFax|
|IP Fax(SIP)|Fax、InternetFax|
|InternetFax|Fax、InternetFax|
|SMB/FTP/SFTP|ScanTo|


※デバイスの状態によってアプリケーションが起動出来ない場合がある。起動条件は、「[他アプリ起動条件](#他アプリ起動条件)」参照。

Email
address等に対応する電子証明書アイコンを選択すると、当該電子証明書の詳細情報が表示される。

表示項目は以下のとおり。

|**項目**|**内容**|
|---|---|---|
|証明書状態|有効/無効|
|発行元|文字列|
|発行対象者|文字列|
|有効期間|証明書有効期間 (yyyy/mm/dd～yyyy/mm/dd)|
|鍵長|XXXbit, ...|
|暗号化方式||


## グループ宛先(Group)詳細

グループ宛先(Group)として表示される項目は、下記の通り。

|**項目**|**型・選択肢**|**新規作成時デフォルト**|**備考**|
|---|---|---|---|---|
|グループ名(GroupName)|文字列|空文字||
|サービス種別|Email Group/Fax Group||PF2.2では、Server Groupは未対応<br/>【FX/IBG】のFax Groupには、Fax/IP Fax(SIP)/InternetFaxを混在させることができる。<br/>|
|Favorite|ON/OFF|OFF||
|Photo|選択不可|グループアイコン||
|Members|サービス種別に対応する宛先を持ったContactのリスト|なし||


GroupNameは入力必須である。

使用できる文字列最大長については「[入力文字数上限](#入力文字数上限)」参照。

登録/修正時にUIから入力可能な文字種類については 3.3利用可能な文字種類
を参照。

1つのGroupが保持できるContacts(宛先メンバ)の最大数は下記の通り

|**種別**|**件数**|
|---|---|---|
|Email Group|200|
|Fax Group|600|


## 個人宛先(Contact)の追加/編集/削除

AddressBookアプリから宛先追加/編集/削除を行うことができる。

また、送信機能を有するアプリケーション(Email, Fax,
ScanTo,等)にてKeyboardやKeypadから入力されている送信先を、当該アプリケーションからの操作でアドレス帳に登録することができる。

登録方法は下記の2つから選択可能。

- 新規登録

- 既存の宛先に登録

既存の宛先に登録する場合、同じ種別の送信先が登録されていない宛先に限り登録することが出来る。

Contactに設定できる項目は「[個人宛先(Contact)詳細](#個人宛先contact詳細)」を参照。

-   Favoriteに関する補足

ContactのFavoriteには、Contactに対して設定できるGlobal
Favoriteと、Contact内の各宛先毎に設定できるIndividual Favoriteがある。

Contactの編集操作時、Global FavoriteとIndividual
Favoriteは以下のとおり連動する。

1.  Global FavoriteをONからOFFにすると、Individual
    FavoriteはすべてOFFになる。

2.  Global FavoriteをOFFからONにすると、Individual
    FavoriteはすべてONになる。

3.  Individual
    FavoriteがすべてONの状態からいずれか1つをOFFにすると、Global
    FavoriteはOFFになる。

4.  Individual Favoriteの1つ以上がOFFの状態から全てをONにすると、Global
    FavoriteはONになる。

-   編集/削除の際のアプリケーションリセットについて

Contactを編集あるいは削除した際には、動作中のアプリケーションのリセットを実施する。

これは、FaxやEmailアプリが宛先表から送信先設定した状態を保ったたまで宛先表項目の編集や削除が実施されると誤送信の原因となるためである。

新規作成時または各アプリケーションからアドレス帳の宛先に対して送信先が追加された場合は、リセットを実施しない。

-   Email暗号化(強制)が有効な場合のEmailアドレスに関する補足

TBD

-   その他補足

デバイス側で無効化された機能(宛先種別)に対する送信先の登録は不可。編集、削除は可。判定条件は、「[宛先種別提供条件](#宛先種別提供条件)」を参照。

## グループ宛先(Group)の追加/編集/削除

Groupに設定できる項目は「[グループ宛先(Group)](#グループ宛先group)」を参照。

-   編集/削除の際のアプリケーションリセットについて

Groupを編集あるいは削除した際には、動作中のアプリケーションのリセットを実施する。

これは、FaxやEmailアプリが宛先表から送信先設定した状態を保ったたまで宛先表項目の編集や削除が実施されると誤送信の原因となるためである。

新規作成時は、リセットを実施しない。

-   Email Groupに関する補足

Email
GroupにContactを追加する際、Email暗号化(強制)が有効であっても証明書の状態はチェックしない。

-   その他補足

1Group内で重複するContactを登録することは出来ない。

Groupのメンバに登録できるのは、ローカルアドレス帳に登録されたContactのみである。リモートアドレス帳のContactを直接Groupメンバに登録することは出来ない。

デバイス側で無効化された機能に対するGroupは登録不可。編集、削除は可。判定条件は、「[宛先種別提供条件](#宛先種別提供条件)」を参照。

## Favorite/Contact一覧(AddressBookUtility)

起動元アプリケーションが送信元としてアドレス帳内の宛先を指定したい場合に使用される。

Favoriteリスト/Contactリストには、起動元アプリケーションによって指定されたサービスでフィルタリングしたローカルアドレス帳の宛先を表示し、ユーザによって選択された宛先情報を起動元に返す。

リモートアドレス帳の宛先は表示しない。リモートアドレス帳の宛先を表示する場合、検索操作をする必要がある。

起動元アプリケーションは適切にサービスを指定する必要がある。

各アプリケーションに応じたフィルタ条件(参考値)は、「[宛先一覧仕様](#宛先一覧仕様)」参照。

宛先名は、Boldで表示する。(【MN】のBold表示仕様はTBD)

### Favoriteリスト

起動元アプリケーションに対応したDestination/Groupの中で、Favoritesに指定されている宛先を表示する。ただし、PersonalizeFavoritesに登録がある場合は、PersonalizeFavoritesの宛先リストを表示する。

FavoritesとPersonalizeFavoritesはどちらか片方しか表示されない。排他仕様。

Favoritesリストの個人宛先用のRowには、1行目に宛先名(DisplayName)、2行目にEmailAddressやFax番号などの送信先が表示される。グループ宛先用のRowは1行でグループ名とグループメンバ数を表示する。詳細は「Dialog仕様書(02.51.02
Address Book Utility)」参照。

1つの宛先の個々の送信先に対してFavoritesが指定されている場合(例えば、起動元がScanToアプリで宛先にEmailAddressとFTPサーバが登録されているケース)、それぞれを別のRowに分けて表示する。

### Contactリスト

起動元アプリケーションによりフィルタリングされた結果としてのContact/Groupの一覧が表示される。

詳細は「Dialog仕様書(02.51.02 Address Book Utility)」参照。

### 宛先選択

一覧表示されているContactあるいはGroupから1つを選択し、起動元アプリケーションが使用する送信先として追加することができる。

宛先選択時に起動元のアプリケーションが選択可否判断を行う。

選択不可の場合は、起動元アプリケーションがバナーメッセージを表示する。

###### 起動元アプリケーションでS/MIME暗号化が有効の場合

- 【FX/IBG】ではGroup宛先を表示しない。

- 証明書を持たない宛先はDisableで表示する。

- 宛先選択時に証明書の有効性をチェックし、無効な証明書の場合は、AddressBook側でエラー処理を行う。

## Add Contact一覧(Personalize Favorites)

PersonalizeFavoritesに宛先を追加するための宛先選択画面。

宛先選択画面には、起動元アプリケーションによりフィルタリングされたローカルアドレス帳のContactおよびGroupが表示される。

Add
Contact画面から宛先を検索する場合、ローカルアドレス帳からのみ検索を行う。リモートアドレス帳の宛先は検索しない。

宛先選択画面のリスト上には、個人の宛先であれば1行目に宛先名(DisplayName)、2行目にEmailAddressやFax番号などの送信先を表示する。複数の送信機能を持つアプリケーションで、送信先は異なるが同一の宛先の場合は、リスト上に1つの宛先として表示し、その宛先を選択すると、それぞれの送信先が表示される。グループの宛先であれば、Group名とGroupメンバ数を表示する。

宛先または送信先を選択すると、PersonalizeFavoritesの一覧に追加される。PersonalizeFavoritesに追加するときは、証明書の有効性チェックは行わない。

詳細な表示内容は、「Dialog仕様書(02.51.02 Address Book Utility)」参照。

# AddressBookアプリ機能提供条件

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFV_SELECTION_SERVICE_FAX_ADDRESS_BOOK|PFV_SERVICE_STATUS_ACTIVE|FAX用アドレス帳||
|Configuration|PFV_SELECTION_SERVICE_SCAN_ADRESS_BOOK|PFV_SERVICE_STATUS_ACTIVE|SCAN用アドレス帳||

どれか一つでもActiveの場合、機能を提供する。

# LDAPアドレス帳(リモートアドレス帳)

LDAPサーバが設定済みかつLDAPアドレス帳の検索機能が有効な場合、LDAPアドレス帳の宛先データをLUIに表示、宛先追加することができる。

## 機能提供条件

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFV_SELECTION_SERVICE_REMOTE_ADDRESS_BOOK_SERVICE|PFV_SERVICE_STATUS_ACTIVE|||
|Configuration|PFRID_ABL_LDAP_CONFIG(AblLdapCfgValid)|1(許可)|840-080:リモート・メールアドレス帳利用許可||

両方が有効な場合、LDAPアドレス帳の検索を許可する。

## 検索上限数

Intelligent SearchとFull Searchで宛先表示の上限数が異なる。

|**検索方法**|**ローカルアドレス帳**|**リモートアドレス帳**|
|---|---|---|---|
|Intelligent Search|10|10|
|Full Search|無制限|可変。<br/>Default:50<br/>Min:5 / Max:100<br/>上限数のシステムデータは、下記参照<br/>|


リモートアドレス帳の宛先検索上限数

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFRID_ABL_LDAP_CONFIG(AblLdapCfgMaxHitCnt)|件数(5～100)|840-091:最大ヒット件数||


# AddressBookの権限
AddressBookには、Access/Create/Editのそれぞれ権限が存在する。
Access権がHideの場合は、Create/Editの権限は無効。
AddressBookUtilityの利用条件は、AddressBookの権限の他に各アプリ側の利用条件にも依存する。

## アドレス帳アクセス権限
AddressBookアプリ/AddressBookUtilityを起動する権限

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|権限|Address Book App &gt; Access|Allow|アクセス可||
|||Restrict|アクセスするには権限を持つユーザで認証が必要。未認証ユーザのみ設定可。||
|||Hide|アクセス不可||


## 宛先作成権限
宛先(Contact/Group)を作成する権限

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|権限|Address Book App &gt; Create Contacts and Groups|Allow|作成可||
|||Hide|作成不可||


## 宛先編集権限
宛先(Contact/Group)を編集・削除する権限

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|権限|Address Book App &gt; Edit Contacts and Groups|Allow|編集可||
|||Hide|編集不可||


# 宛先登録上限値
個人宛先(DestinationContact)とグループ宛先(GroupContact)でそれぞれ上限値を持つ。

## 個人宛先(Contact)

|種別|URI|Property|説明||
|---|---|---|---|---|---|
|WAMP I/F|ui.contact.getLimit|destinationcontact|個人の宛先の登録上限数||


Destinationに対しても上限値はあるが、UIが意識する必要はない。

## グループ宛先(Group)

Groupは、宛先種別毎に上限値を持つ。

|種別|URI|Property|説明||
|---|---|---|---|---|---|
|WAMP I/F|ui.contact.getLimit|mailgroup|EmailGroupの登録上限数||
|WAMP I/F|ui.contact.getLimit|faxgroup|FaxGroupの登録上限数||


# 宛先種別提供条件
各宛先種別(Email/Fax/IP(SIP)Fax/InternetFax/SMB/FTP/SFTP)およびグループ毎の提供条件を記載する。

## Email

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFV_SELECTION_SERVICE_SCAN_TO_EMAIL|PFV_SERVICE_STATUS_ACTIVE|有効||


## Fax

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFV_SELECTION_SERVICE_FAX|PFV_SERVICE_STATUS_ACTIVE|有効||
|Configuration|PFV_SELECTION_SERVICE_SERVER_FAX|PFV_SERVICE_STATUS_ACTIVE|有効||

どれか一つでもActiveの場合、Faxの宛先機能を提供する

## IP(SIP)Fax

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFV_SELECTION_SERVICE_SIP_FAX|PFV_SERVICE_STATUS_ACTIVE|有効||


## InternetFax

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFV_SELECTION_SERVICE_IFAX|PFV_SERVICE_STATUS_ACTIVE|有効||


## SMB

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFV_SELECTION_SERVICE_SCAN_TO_SERVER|PFV_SERVICE_STATUS_ACTIVE|有効||
|Configuration|PfRscSysIfStatusEntry[PFIFID_SMB]|PFRSC_SYS_STATUS_ACTIVE|有効||

両方がActiveの場合、SMBの宛先機能を提供する

## FTP

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFV_SELECTION_SERVICE_SCAN_TO_SERVER|PFV_SERVICE_STATUS_ACTIVE|有効||
|Configuration|PfRscSysIfStatusEntry[PFIFID_FTP]|PFRSC_SYS_STATUS_ACTIVE|有効||

両方がActiveの場合、FTPの宛先機能を提供する

## SFTP

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFV_SELECTION_SERVICE_SCAN_TO_SERVER|PFV_SERVICE_STATUS_ACTIVE|有効||
|Configuration|PfRscSysIfStatusEntry[PFIFID_SFTP]|PFRSC_SYS_STATUS_ACTIVE|有効||

両方がActiveの場合、SFTPの宛先機能を提供する

## Email Group

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFV_SELECTION_SERVICE_SCAN_TO_EMAIL|PFV_SERVICE_STATUS_ACTIVE|有効||


## Fax Group

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFV_SELECTION_SERVICE_FAX|PFV_SERVICE_STATUS_ACTIVE|有効||
|Configuration|PFV_SELECTION_SERVICE_SERVER_FAX|PFV_SERVICE_STATUS_ACTIVE|有効||
|Configuration|PFV_SELECTION_SERVICE_SIP_FAX|PFV_SERVICE_STATUS_ACTIVE|有効||
|Configuration|PFV_SELECTION_SERVICE_IFAX|PFV_SERVICE_STATUS_ACTIVE|有効||


どれか一つでもActiveの場合、Faxの宛先機能を提供する

# S/MIME判定条件
S/MIME機能の有無に応じて、振る舞いが変わるケースがある。詳細はDialog仕様書参照。
\[対象\]
- Emailアドレス
- InternetFaxアドレス

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFV_SELECTION_SERVICE_SMIME|PFV_SERVICE_STATUS_ACTIVE|有効||


# One and Done / Multiple Selection
各アプリからアドレス帳(AddressBookUtility)の宛先を選択する際、1件ずつ宛先を指定するか複数の宛先をまとめて指定するかをシステムデータにて切り替えることができる。但し、アプリから明示的にOne
and
Doneモードが指定された場合は、システムデータではなく、アプリの指定を優先する。
One and Done:宛先を選択すると呼び出し元アプリに戻る。
Multiple
Selection:宛先を選択すると、宛先にチェックマークが付与される。確定またはキャンセル操作をした時に呼び出し元アプリに戻る。

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFRID_UI_DEFAULT_DISPLAY_DESCRIPTION|0|One and Doneモード|791-166<br/>宛先表宛先選択方法<br/>|
|||1|Multiple Selectionモード||


# 宛先一覧仕様
アドレス帳の呼び出し元に応じて、リストアップする宛先が異なる。
呼び出し元アプリと呼び出し元に応じたターゲットの基本ケースを記載する。(呼び出し元がAddressBook以外のターゲットは、呼び出し元が指定するため、この限りではない)
【FX/IBG】 <queryオブジェクト addrtypeプロパティ>

|呼び出し元アプリ|メールアドレス|ファクス番号|IPファクス番号(SIP)|インターネットファクス|SMB|FTP|SFTP|
|---|---|---|---|---|---|---|---|---|
|AddressBook(ALL)|○|○|○|○|○|○|○|
|AddressBook(Email)|○|×|×|×|×|×|×|
|AddressBook(Email Group)|○(Groupは非表示)|×|×|×|×|×|×|
|AddressBook(Fax)|×|○|×|×|×|×|×|
|AddressBook(Fax Group)|×|○(Groupは非表示)|○|○|×|×|×|
|AddressBook(IP Fax)|×|×|○|×|×|×|×|
|AddressBook(IFax)|×|×|×|○|×|×|×|
|AddressBook(SMB)|×|×|×|×|○|×|×|
|AddressBook(FTP)|×|×|×|×|×|○|×|
|AddressBook(SFTP)|×|×|×|×|×|×|○|
|Email|○|×|×|×|×|×|×|
|ScanTo|○|×|×|×|○|○|○|
|Fax|×|○|○|○|×|×|×|
|InternetFax|×|○|○|○|×|×|×|

【MN】 <queryオブジェクト addrtypeプロパティ>

|呼び出し元アプリ|メールアドレス|ファクス番号|IPファクス番号(SIP)|インターネットファクス|SMB|FTP|SFTP|
|---|---|---|---|---|---|---|---|---|
|AddressBook(ALL)|○|○|×|○|○|○|○|
|AddressBook(Email)|○|×|×|×|×|×|×|
|AddressBook(Email Group)|○(Groupは非表示)|×|×|×|×|×|×|
|AddressBook(Fax)|×|○|×|×|×|×|×|
|AddressBook(Fax Group)|×|○(Groupは非表示)|×|×|×|×|×|
|AddressBook(SMB)|×|×|×|×|○|×|×|
|AddressBook(FTP)|×|×|×|×|×|○|×|
|AddressBook(SFTP)|×|×|×|×|×|×|○|
|Email|○|×|×|×|×|×|×|
|ScanTo|○|×|×|×|○|○|○|
|Fax|×|○|×|×|×|×|×|
|InternetFax|×|×|×|○|×|×|×|


# 宛先ソート仕様
UI表示言語に応じて、ソート順を変更する。

## Contactリスト
リスト対象: ローカルアドレス帳
ソートの並び順: 昇順
ソート対象の属性: 【FX/IBG】 索引(よみがな) &gt; 宛先名
【MN】 宛先名(displayname)
大文字・小文字の区別: 区別しない
ソート言語(UI表示言語): 日本語/韓国語/ハンタイ中国語/英語/その他
###### sortオブジェクト

|ソート方式<br/>(type)<br/>|ソートの並び順<br/>(order)<br/>|ソート対象の属性<br/>(keys)<br/>|大文字・小文字区別<br/>(insentive)<br/>|ソート言語<br/>(lang)<br/>|ソート言語に応じた文字種(ひらがな/カタカナ、アルファベットなど)のソート順(UI側では指定不要)<br/>各文字種内のソートは文字コード(UTF-8)<br/>|
|---|---|---|---|---|---|---|
|normal|昇順|【FX/IBG】<br/>索引(よみがな) &gt; 宛先名<br/>|区別しない|日本語|ひらがな/カタカナ &gt; アルファベット &gt; 数値 &gt; その他 &gt; 空白|
|||||韓国語|ハングル字母 &gt; アルファベット &gt; 数値 &gt; その他 &gt; 空白|
|||【MN】<br/>宛先名<br/>||ハンタイ中国語|注音字母 &gt; アルファベット &gt; 数値 &gt; その他 &gt; 空白|
|||||英語・その他|アルファベット &gt; 数値 &gt; その他 &gt; 空白|


## Favoriteリスト・Search(Intelligent Search / Full Search)
Favoriteリストのリスト対象は、ローカルアドレス帳のみ。
Searchの場合は、ローカルアドレス帳の検索結果とリモートアドレス帳の検索結果はそれぞれソートし、マージしない。ローカルアドレス帳とリモートアドレス帳の表示順序は保証しない。
ソートの並び順: 昇順
ソート対象の属性: 宛先名
大文字・小文字の区別: 区別しない
ソート言語(UI表示言語): 文字コード(UTF-8)
###### sortオブジェクト

|ソート方式<br/>(type)<br/>|ソートの並び順<br/>(order)<br/>|ソート対象の属性<br/>(keys)<br/>|大文字・小文字区別<br/>(insentive)<br/>|ソート言語<br/>(lang)<br/>||
|---|---|---|---|---|---|---|
|normal|昇順|宛先名|区別しない|文字コード(UTF-8)||


# 宛先検索仕様

## 個人宛先の検索属性
検索時に使用する属性を記載する。(○:検索キーに含める、×:検索キーに含めない)
【FX/IBG】<filterオブジェクト>

|対象属性(keys)|ローカル|リモート|大文字・小文字区別(insensitive)|条件のパターン(matchtype)||
|---|---|---|---|---|---|---|
|宛先名(DisplayName)|〇|〇|区別しない|前方一致||
|索引(よみがな)|○|○||||
|姓|〇|〇||||
|名|〇|〇||||
|会社名|〇|×||||
|送信先|Emailアドレス|〇|〇|||
||Serverアドレス|〇|×|||
||FAXアドレス|〇|○|||
||InternetFaxアドレス|〇|〇|||
||SipFaxアドレス|〇|〇|||

【MN】<filterオブジェクト>

|対象属性(keys)|ローカル|リモート|大文字・小文字区別(insensitive)|条件のパターン(matchtype)||
|---|---|---|---|---|---|---|
|宛先名(DisplayName)|〇|〇|区別しない|前方一致||
|索引(よみがな)|×|×||||
|姓|〇|〇||||
|名|〇|〇||||
|会社名|〇|×||||
|送信先|Emailアドレス|〇|〇|||
||Serverアドレス|〇|×|||
||FAXアドレス|〇|○|||
||InternetFaxアドレス|〇|〇|||
||SipFaxアドレス|×|×|||


## グループ宛先の検索属性
検索時に使用する属性を記載する。(○:検索キーに含める、×:検索キーに含めない)

リモートのグループ検索はサポート対象外。
【FX/IBG】<filterオブジェクト>

|対象属性(keys)|ローカル|リモート|大文字・小文字区別(insensitive)|条件のパターン(matchtype)|
|---|---|---|---|---|---|
|宛先名(DisplayName)|〇|-|区別しない|前方一致|
|索引(よみがな)|○|-|||


【MN】<filterオブジェクト>

|対象属性(keys)|ローカル|リモート|大文字・小文字区別(insensitive)|条件のパターン(matchtype)|
|---|---|---|---|---|---|
|宛先名(DisplayName)|〇|-|区別しない|前方一致|
|索引(よみがな)|×|-|||


デバイス側の仕様により、検索対象に個人宛先とグループ宛先の両方を指定した際、それぞれに対して対象属性(keys)を指定することは出来ない。対象属性の指定は、個人宛先の対象属性を優先する。

# 他アプリ起動条件
AddressBookアプリからHome画面を経由せずに宛先に対応するアプリを起動することができる。
起動できるアプリと起動条件を記載する。
起動不可の場合は、AddressBook側でエラー処理を行う。起動できるアプリが一つも無い場合は、バナーメッセージを表示する。
起動後のエラー処理(NotConfiguredなど)は各アプリ側で行う。また、エラーによりアプリ画面に遷移出来ない場合は、Home画面を表示すること。

|起動可能アプリ|起動条件|
|---|---|---|
|Email||
|ScanTo||
|Fax||
|InternetFax||
|EasyFax||
|||


# 入力文字数上限
Contacts内で使用する属性や検索フィールドの**入力文字数上限値**を記載する。

|共通属性||
|---|---|---|
|宛先名|128|
|よみがな(索引)|128|
|姓|32|
|名|32|
|会社名|64|
|FAX属性||
|宛先(電話番号)|128|
|送信用ヘッダ|18|
|SIPFax属性||
|宛先(SIPアドレス)|128|
|送信用ヘッダ|18|
|InternetFax属性||
|宛先(アドレス)|128|
|Email属性||
|宛先(メールアドレス)|128|
|補助項目1|20|
|補助項目2|40|
|補助項目3|60|
|Server属性||
|宛先(サーバアドレス)|64|
|ユーザ名|97|
|パスワード|32|
|共有名|64|
|転送先のパス名|128|
|検索||
|検索フィールド|128|
|||
|||
|||
|||


# Fax二度入力オプション
二度入力要否のシステムデータに応じて、画面遷移を変える必要がある。画面遷移の詳細は、「02.51.01.01
Contact Popup」、「02.51.01.04 Group Popup」参照。
判定に必要なシステムデータを記載する。
【個人宛先のFax番号二度入力規制】

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFRID_UI_DEFAULT_FAX_DESCRIPTION_BIT|1|二度入力が必要。Chain-Link:790-680||

※個人のFax宛先に対するシステムデータ
【Faxグループ宛先の二度入力規制】

|種別|参照先|値|説明||
|---|---|---|---|---|---|
|Configuration|PFRID_UI_DEFAULT_FAX_DESCRIPTION|1|二度入力が必要。Chain-Link:790-177||

※Faxグループに対するシステムデータ
