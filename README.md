# 基礎学習ターム 確認テスト_もぎたて
## 環境構築
**Dockerビルド**
1.`git clone git@https://github.com/shino-ym/shinobu.yamaguchi-kadai2`
2.DockerDesktopアプリを立ち上げる
3.`docker-compose up -d --build`
> MySQLは、OSによって移動しない場合があるので、それぞれのpcに合わせてdocker-compose.ymlファイルを編集してください。

**Laravel環境構築**
1. `docker-compose exec php bash`
2. `composer install`
3. `cp .env.example .env`
4. 「.env」に以下の環境変数を追加
```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel_db
DB_USERNAME=laravel_user
DB_PASSWORD=laravel_pass
```

5. アプリケーションキーの作成
`php artisan key:generate`
6. マイグレーションの実行
`php artisan migrate`
7. docker-cpmpose.ymlの「volume」に以下を追加
```
- ./storage:/var/www/storage
```
8. ストレージリンクの作成
`php artisan storage:link`
9. シーディングの実行
`php artisan db:seed`

## 使用技術
- PHP 8.4.10
- laravel 8.75
- MySQL 8.0.36

## ER図

## URL
- 開発環境：http://localhost/products
- phpMyAdmin:：http://localhost:8080/



