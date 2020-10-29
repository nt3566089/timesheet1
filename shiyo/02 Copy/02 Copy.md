# Copy

本章では、Copy機能について定義する。

Copy 機能とは、IITで読み込んだ原稿画像をIOTに出力するサービスである。

個々の機能については、2.2Functions、機能間などで発生する各種制限/コンフリクトについては、2.3
Conflictを参照。

## Overview

### Function List

Copy Service Functions編 1.1機能一覧参照。

#### プロダクト対応リスト

各機能の項目を参照。

#### 機能と関連するオプション

各機能の項目を参照。

-   <Imari>両面プリントを行うには、Duplex
    > Moduleと増設メモリのセットが必要。以降、これらのオプションを総称してDuplex
    > Moduleと記す。

-   <Imari>先読み動作を行うには、Hard
    > Diskと増設メモリのセットが必要。以降、これらのオプションを総称してEPC
    > Moduleと記す。
※<PGS7018SGP> EPC Moduleの定義はOverview編で確認中(TBD)。

-   Duplex Module

両面プリントを実施するために必要なオプション一式。

######  Imari  Duplex + メモリ 192M以上

###### PGS7018SGP Duplex + HDD

###### Fuhjin 標準装備

-   EPC Module

先読み動作を実施するために必要なオプション一式。

######  Imari  HDD + メモリ 128M以上

######  PGS7018SGP  RamEPCが標準装備。+HDD で、HDD
EPCオプションとなる。

######  Fuhjin  標準装備

### Function Matrix

2.3 Conflict へ移動。