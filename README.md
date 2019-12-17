## Introduction

Horizon Horizon is based on the official [Laravel Horizon](https://github.com/laravel/horizon) package.The web UI is also included.

If you prefer a pure restful api and want to customize the UI, you can refer to [Lumen-horizon](https://github.com/servocoder/lumen-horizon) by servocoder.

## Installation

<p align="center">
<img src="https://res.cloudinary.com/dtfbvvkyp/image/upload/v1551286550/HorizonLight.png" width="430">
<img src="https://res.cloudinary.com/dtfbvvkyp/image/upload/v1551286550/HorizonDark.png" width="430">
</p>

All of your worker configuration is stored in a single, simple configuration file, allowing your configuration to stay in source control where your entire team can collaborate.

```
composer require kinsolee/horizon-lumen
```

2.Add the vendor:publish command dependency and publish its assets and config file. 

```text
composer require "laravelista/lumen-vendor-publish" --dev
```

3. Add `Laravelista\LumenVendorPublish\VendorPublishCommand` to `app/Console/Kernel.php` file.

4. Add `$app->register(\Laravel\Horizon\HorizonServiceProvider::class);` in your `boorstrap/app.php` file.

5. Publish horizon vendor
```text
php artisan vendor:publish --provider="Laravel\Horizon\HorizonServiceProvider"
``` 

## Problems
* If you get the follow errors when you run vendor:publish:
```
Type error: Argument 1 passed to Laravel\Horizon\Repositories\RedisMasterSupervisorRepository::__construct() must implement interface Illuminate\Contr
  acts\Redis\Factory, instance of Redis given
```
Make sure you register `Illuminate\Redis\RedisServiceProvider::class` in your `boorstrap/app.php` file.

* If you deploy horizon-lumen on sub-directory, please specific `base_path` in config/horizon.php
## Official Documentation

Documentation for Horizon can be found on the [Laravel website](https://laravel.com/docs/horizon).

## Contributing

Thank you for considering contributing to Horizon! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

Please review [our security policy](https://github.com/laravel/horizon/security/policy) on how to report security vulnerabilities.

## License

Laravel Horizon is open-sourced software licensed under the [MIT license](LICENSE.md).
