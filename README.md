CakePHP 2.10.24 環境
====================

PHP 7.4 + PostgreSQL 14 + CakePHP 2.10.24 の環境を簡単に起動できるようにしたもの


## INSTALL & RUN

0. docker および docker-compose が動作する状態にしておく

1. PostgreSQL データベースのデータ保存ディレクトリを作成
    ``` shellsession
    mkdir Postgres/data
    chmod 700 Postgres/data
    ```

2. 各種 Docker コンテナの作成
    ``` shellsession
    docker-compose build
    ```

3. 環境の起動
    ``` shellsession
    docker-compose up
    ```

4. Web ブラウザでアクセス

    下記 URL にアクセスしてください。
    ``` shellsession
    http://localhost:8084/admin/
    ```


## docker-compose ファイルの修正箇所

1. Web サーバのポートは 8084 にしているが、別のサービスで既に利用している等で違うポートに変更したい場合

https://github.com/smiyabe/docker-cakephp-2.10.24/blob/46a97b7f2e60bc13ff1899f482f18a7fb119394e/docker-compose.yml#L5-L6

2. 最初の起動時にデータベースが作成される。このときのユーザ、パスワード、データベース名を変更したい場合

https://github.com/smiyabe/docker-cakephp-2.10.24/blob/46a97b7f2e60bc13ff1899f482f18a7fb119394e/docker-compose.yml#L16-L19

3. 各コンテナの uid, gid を変更したい場合

https://github.com/smiyabe/docker-cakephp-2.10.24/blob/46a97b7f2e60bc13ff1899f482f18a7fb119394e/docker-compose.yml#L7-L8

https://github.com/smiyabe/docker-cakephp-2.10.24/blob/46a97b7f2e60bc13ff1899f482f18a7fb119394e/docker-compose.yml#L14-L15
