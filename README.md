# このリポジトリについて
このリポジトリは論文解説サービスであるsitell(https://sitell.me)のdocker開発環境のためのものとなります。

# 使用技術
- Docker v20.10.5
- docker-compose v1.29.0
- PHP v7.4
- Laravel v6.20.26
- Composer v1.10.9

# 環境構築のやり方
1. このリポジトリをgit clone

```
$ git clone git@github.com:centerRyo/sitell-docker.git
```

2. sitellのリポジトリをroot直下にgit clone

```
$ cd sitell-docker/
$ git clone git@github.com:centerRyo/sitell.git
```

3. docker-compose up

```
$ docker-compose up -d
```

4. composer install

```
$ docker-compose exec app bash
$ composer install
```

5. .env作成

.env.exampleをコピーして.envを作成し、以下の値に変更する

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=db
DB_DATABASE=sitell
DB_USERNAME=root
DB_PASSWORD=root
```

6. app key作成

```
$ docker-compose exec app bash
$ php artisan key:generate
```

7. DB マイグレーション

```
$ php artisan migrate
```

8. アクセス

http://localhost にアクセスする
