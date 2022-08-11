## Requirement
* php
* composer
* mysql

## Setup

Setup laravel

```bash
composer install
composer post-root-package-install
composer post-create-project-cmd
```

Setup mysql for create database

```bash
mysql -u root -e 'CREATE DATABASE IF NOT EXISTS bug_report;'
```

Run migration

```bash
php artisan migrate
```

##

Start service

```bash
php artisan serve
```

Create a user and set refreshed_at is "2022-01-02T00:00:00Z"

```bash
curl --data '{"name": "test", "email": "test@example.com", "password": "password", "refreshed_at": "2022-01-02T00:00:00Z"}' --header 'Content-Type: application/json' localhost:8000/api/user
```

Get user

```bash
curl localhost:8000/api/user/1
```

Expect refreshed_at is "2022-01-02T00:00:00Z"

Actual refreshed_at is "2022-01-02T05:00:00Z"
