# Laravel (PHP)

This CircleCI config is for Laravel apps running on PHP 7.3 and using PostgreSQL database.

## Images

- `circleci/php:7.3-stretch-node-browsers`
- `circleci/postgres:9.6`

## Caveats

- The `bcmath` PHP extension is installed in order to support [Laravel Telescope](https://laravel.com/docs/5.8/telescope)
- The projects must contain an example configuration for CircleCI located in a file called `.env.circleci.example` with the following database environment variables

```
DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=5432
DB_DATABASE=test_database
DB_USERNAME=root
DB_PASSWORD=
```
