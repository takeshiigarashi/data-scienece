# 5.2 データ保管

## データの形式

構造化データに対しては、CSVやTSVがよく使われる。

## ストレージ

非構造化データのように形式が統一されていない様々なデータを保管する場合は、ファイルストレージにデータを保存する。

クラウドストレージだとAmazon S3、Google Cloud Storage、IBM Cloud Object Storageなど。

オンプレミス型では、FTPサーバーやファイル共有サーバーなど。

## データベース

リレーショナル・データベースと非リレーショナル・データベースがある。

**RDB**

テーブル形式にデータを保管するデータベース。SQLを用いて操作する。

**NoSQLデータベース**

テーブル形式でない多種多様なデータベースをまとめて非リレーショナルデータベースと呼ぶ。キーバリュー型、階層型、ドキュメント志向型など。

## データベースの分散処理

HadoopとSpark

Hadoopは、分散ファイルシステムHDFSと分散処理フレームワークMapReduceから構成される。巨大なデータを処理するのが得意だが、反復的なデータ処理は不得意

Sparkは、Hadoopの後続の分散技術で、ビッグデータや機械学習など、大規模なデータを扱うことにより長けた分散処理フレームワーク。

## データの流れ

データソース -> データレイク -> データウェアハウス -> データマート

**データレイク** 加工されていない生のデータを一言管理するストレージやデータベース。

**データウェアハウス** データレイクのデータを加工して構造化データとして保存するデータベース。ペダバイト規模のデータに対して高性能なSQLが実行可能。代表的な製品にはOracle Exadata、IBM Integrated Analytics Syste、Teradataなどがある。

**データマート** 具体的な活用目的に特化した形でデータを保存する場所がデータマート。データウェアハウス内に保存されることもあるが、データウェアハウスよりも規模が小さく、目的に特化した集計済みデータが保存される。

クラウドサービスの例

| |Amazon AWS|Google Cloud Platform|Microsoft Azure|
|--|--|--|--|
|データレイク|S3|Cloud Storage|Data Lake Storage|
|データウェアハウス|Redshift|BigQuery|Synapse Analytics|
|データマート|RDS|Cloud SQL|Azure SQL Database|

BIツールを使って、店舗とECサイトのそれぞれの担当者が、売上や顧客層などのデータを確認したいとする。店舗とECサイトでは、取得しているデータの種類や使いたいBIツールが異なることも考えられる。こうした場合、それぞれに特化したデータマートを作成することが適切と考えられる。

