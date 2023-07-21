# Laravel Database Logger

This package provides a driver to store log messages in the database.

Tested on Laravel 8.

```php
use Illuminate\Support\Facades\Log;

Log::channel('db')->info('Your message');
```

## Installation

You can install the package via composer:

```bash
composer require jeetenkumarsingh/laravel-log-action-to-mysql
```

You can publish and run the migrations with:

```bash
php artisan vendor:publish --tag="log-db-migrations"
php artisan migrate
```

Now add a new channel to `config/logging.php`.

```php
use Jeter\LaravelLogDb\DatabaseLogger;

return [
    'channels' => [
        'db' => [
            'driver' => 'custom',
            'via'    => DatabaseLogger::class,
        ],
    ]   
]
```

## Usage

You could add the `db` channel to the `stack` channel and then log the normal way.

You could also explicitly log to the database:

```php
use Illuminate\Support\Facades\Log;

Log::channel('db')->info('Your message');
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Contributing

Please see [CONTRIBUTING](https://github.com/spatie/.github/blob/main/CONTRIBUTING.md) for details.

## Credits

- [Jitendra Kumar Singh](https://jitendrakumarsingh.com)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
