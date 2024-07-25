# CatcHe
CatcHe: A Simple, Effective, Basic, Flexible, Secure, and Faster File-Based Caching System for PHP (v8.3+)

## Support Me

This software is developed during my free time and I will be glad if somebody will support me.

Everyone's time should be valuable, so please consider donating.

[https://buymeacoffee.com/oxcakmak](https://buymeacoffee.com/oxcakmak)

### Introduction

The CatcHe class offers a straightforward file-based caching mechanism for PHP applications, prioritizing performance, efficiency, and maintainability. It provides a user-friendly interface for:
* Storing and retrieving cached data
* Setting expiration times (time-to-live)
* Removing specific cache entries
* Clearing the entire cache directory

### Installation
No installation is required. You can directly include the `CatcHe.php` file in your project:
```php
require_once 'path/to/CatcHe.php';
```

## Usage
### Create a CatcHe instance:
```php
$cache = new CatcHe('/path/to/cache/directory');
```
Replace `/path/to/cache/directory` with the desired location for the cache files. The directory will be created automatically if it doesn't exist.

### Store and retrieve data:
```php
$value = 'This is cached data!';
$cache->set('my_key', $value, 600);  // Store with 10-minute TTL

$cachedValue = $cache->get('my_key');

if ($cachedValue) {
    echo 'Retrieved from cache: ' . $cachedValue;
} else {
    // Generate or fetch data if not cached
    $dataToCache = /* ... */;
    $cache->set('my_key', $dataToCache);
}
```

### Delete a specific cache entry:
```php
$cache->delete('my_key');
```

### Clear the entire cache:
```php
$cache->clear();
```
