# Laravel Configurable Cache

[![Latest Version on Packagist](https://img.shields.io/packagist/v/salehhashemi/laravel-configurable-cache.svg?style=flat-square)](https://packagist.org/packages/salehhashemi/laravel-configurable-cache)
[![Total Downloads](https://img.shields.io/packagist/dt/salehhashemi/laravel-configurable-cache.svg?style=flat-square)](https://packagist.org/packages/salehhashemi/laravel-configurable-cache)
[![GitHub Actions](https://img.shields.io/github/actions/workflow/status/salehhashemi1992/laravel-configurable-cache/run-tests.yml?branch=main&label=tests)](https://github.com/salehhashemi1992/laravel-configurable-cache/actions/workflows/run-tests.yml)
[![StyleCI](https://github.styleci.io/repos/557792567/shield?branch=main)](https://github.styleci.io/repos/557792567?branch=main)

Laravel Configurable Cache is a package that provides a configurable cache management system for your Laravel application.

## Features
- Provides configurable cache settings with dedicated ttl and prefix for each
- Supports all main cache operations provided by Laravel, such as put, get, increment, and delete

## Installation
You can install the package via composer:
```bash
composer require Salehhashemi/configurable-cache
```

Next, from the command line type:
```bash
php artisan vendor:publish --provider="Salehhashemi1992\ConfigurableCache\ConfigurableCacheServiceProvider"
```

Finally, adjust the settings in the published configuration file located in `config/configurable-cache.php` as per your 
requirements.

## Usage
To use the package, you can use the `ConfigurableCache` class methods. Here's an example:
```php
use Salehhashemi\ConfigurableCache\ConfigurableCache;
    
// Storing an item in the cache
ConfigurableCache::put('testKey', 'Hello World!', 'default');
    
// Retrieving an item from the cache
$value = ConfigurableCache::get('testKey', 'tiny');

// Delete a cache item
ConfigurableCache::delete('testKey', 'short');
```

## Default configuration
You can change these configurations in your cache.php config file:

    'configs' => [
        'default' => [
            'prefix' => '_default_',
            'duration' => '+1 Year',
        ],
        'tiny' => [
            'prefix' => '_tiny_',
            'duration' => '+15 minutes',
        ],
        'short' => [
            'prefix' => '_short_',
            'duration' => '+1 hour',
        ],
        'otp' => [
            'prefix' => '_otp_',
            'duration' => '+3 minutes',
        ],
    ]

### Testing

```bash
composer test
```

### Changelog

Please see [CHANGELOG](changelog.md) for more information what has changed recently.

## Contributing

Please see [CONTRIBUTING](contributing.md) for details.

## Credits

- [Saleh Hashemi](https://github.com/salehhashemi1992)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](license.md) for more information.