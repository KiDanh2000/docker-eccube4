# docker-eccube4


HOW TO USE
前提として Docker Desktop をインストールして下さい。


プロジェクトのクローン
当プロジェクトをクローンします。

git clone https://github.com/KiDanh2000/docker-eccube4.git
クローンしたプロジェクトディレクトリに移動します。

cd docker-for-eccube4

EC-CUBEのソースを配置
EC-CUBEのバージョンを指定し、ソースコードをダウンロードします。

：例 EC-CUBE 4.2.0 の場合

make EC-CUBE4.2.0
当プロジェクトで提供しているバージョンは下記の通りです。

EC-CUBE4.2.1
EC-CUBE4.2.0
EC-CUBE4.1.2-p2
EC-CUBE4.1.2-p1
EC-CUBE4.1.2
EC-CUBE4.1.1
EC-CUBE4.1.0
EC-CUBE4.0.6-p2
EC-CUBE4.0.6-p1
EC-CUBE4.0.6
EC-CUBE4.0.5-p1
EC-CUBE4.0.5
EC-CUBE4.0.4
EC-CUBE4.0.3
EC-CUBE4.0.2
EC-CUBE4.0.1
EC-CUBE4.0.0

PHPのバージョンを選択
使用するPHPのバージョンを指定します。

：例 PHP 8.1 の場合

make PHP8.1
当プロジェクトで提供しているバージョンは下記の通りです。

PHP8.2
PHP8.1
PHP8.0
PHP7.4
PHP7.3
PHP7.2
PHP7.1

データベースの選択
使用するデータベースとバージョンを指定します。

：例 MySQL 8.0 の場合

make MySQL8.0
当プロジェクトで提供しているデータベースとバージョンは下記の通りです。

MySQL8.0
MySQL5.7
PostgreSQL14
PostgreSQL13
PostgreSQL12
PostgreSQL11
PostgreSQL10
PostgreSQL9

イメージビルド＆コンテナの起動
アプリケーションコンテナのイメージを作成します。

docker-compose build app
全てのコンテナを起動します。

docker-compose up

初期化
下記コマンドで構築した環境を初期化することができます。

make Initialization
内部の処理は下記の通りです。

コンテナ・ボリュームの停止＆削除
ソースコード（eccubeディレクトリ）の削除
永続化されたデータベースの情報を削除
docker-compose.ymlの削除
Dockerfileの削除

実行できるmakeコマンド
下記コマンドで実行可能なmakeコマンドを確認することができます。

make

データベースの設定情報
MySQL	PostgreSQL
database	eccube	eccube
host	db	db
port	3306	5432
user	db_user	db_user
password	db_password	db_password
root password	db_password	
DBMS	phpMyAdmin	Adminer

ブラウジング
Front	Browsing
EC-CUBE	http://localhost
Adminer (PostgreSQL)	http://localhost:8080
phpMyAdmin (MySQL)	http://localhost:8080
MailCatcher	http://localhost:1080

Linux ディストリビューション利用者向けの設定
当プロジェクトでは、appコンテナ初回起動時にファイルの所有者とグループをwww-dataに変更しています。 Linux ディストリビューションの Docker ではホストとコンテナ間のファイルの所有者、グループの切り分けができないため、ホストでファイルを変更する場合はパーミッションの調整が必要です。

eccubeディレクトリのパーミッションを777に変更してください。

sudo chmod -R 777 eccube
※Git 管理する際はパーミッションの差分に注意してください。
