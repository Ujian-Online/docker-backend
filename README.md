# Docker Backend

## Clone

```
git clone --recurse-submodules git@github.com:Ujian-Online/docker-backend.git
```

## Start Docker

```
docker-compose up -d
```

## Stop Docker

```
docker-compose down
```

## MySQL Database

- Agar file Database tidak hilang, docker akan membuat folder data, sehingga ketika di stop, data tidak hilang

## Laravel Install

### ENV File

Pada folder **CODE**, Copy dan rename file **.env.example** menjadi **.env**, dan ubah data mysql, cache dan redis seperti dibawah ini.

```
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel_dock
DB_USERNAME=laravel
DB_PASSWORD=laravel

BROADCAST_DRIVER=redis
CACHE_DRIVER=redis
QUEUE_CONNECTION=redis
SESSION_DRIVER=redis
SESSION_LIFETIME=120

REDIS_HOST=redis
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_MAILER=smtp
MAIL_HOST=mail
MAIL_PORT=1025
MAIL_USERNAME=testuser
MAIL_PASSWORD=testpassword
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS="noreply@admin-staging.lsp-mpsdm.com"
MAIL_FROM_NAME="${APP_NAME}"
```

### First Command

```
docker-compose exec app composer install
docker-compose exec app php artisan key:generate
docker-compose exec app php artisan migrate
docker-compose exec app php artisan passport:install
```


### JS & CSS Update (Optional)

Karena disini menggunakan laravel mix, untuk install package nodejs, maka jalankan command berikut:

```
docker-compose exec node yarn install && yarn dev
```
