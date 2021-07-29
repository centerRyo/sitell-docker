# このリポジトリについて

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
DB_PORT=3306
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
