# Docker Backend

## Clone

```
git clone --recurse-submodules --remote-submodules git@github.com:Ujian-Online/docker-backend.git
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

Pada folder **CODE**, Copy dan rename file **.env.example** menjadi **.env**

### First Command

```
docker-compose exec app composer install
docker-compose exec node yarn install && yarn dev
docker-compose exec app php artisan key:generate
docker-compose exec app php artisan migrate
```
