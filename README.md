# Laravel Redis Mock




This Laravel package provides a Redis mock for your tests. It depends on [Redis PHP Mock](https://github.com/M6Web/RedisMock).


## Installation & Usage


To get started, use Composer to add the package to your project's dependencies:

    composer require spiria-digital/laravel-redis-mock


This package adds a new `mock` Redis client.

In `config/database.php`, make the Redis client configurable via environment variable:

```php
    'redis' => [

        'client' => env('REDIS_CLIENT', 'predis'),

        ...
        
    ],
```

Now, you can switch to the `mock` client in your `.env.testing`:
```
REDIS_CLIENT=mock
```
Alternatively, you can switch to the mock in your `phpunit.xml`:
```
<env name="REDIS_CLIENT" value="mock"/>
```
Done! Your tests should work without a local redis server running.

