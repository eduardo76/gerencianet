# SDK GERENCIANET FOR PHP - NÃO OFICIAL

== NÃO OFICIAL ==  
Sdk for Gerencianet Pagamentos' API.
For more informations about parameters and values, please refer to [Gerencianet](http://gerencianet.com.br) documentation.

[![Build Status](https://travis-ci.org/gerencianet/gn-api-sdk-php.svg)](https://travis-ci.org/gerencianet/gn-api-sdk-php)
[![Code Climate](https://codeclimate.com/github/gerencianet/gn-api-sdk-php/badges/gpa.svg)](https://codeclimate.com/github/gerencianet/gn-api-sdk-php)
[![Test Coverage](https://codeclimate.com/github/gerencianet/gn-api-sdk-php/badges/coverage.svg)](https://codeclimate.com/github/gerencianet/gn-api-sdk-php/coverage)

## Installation
Require this package with [composer](https://getcomposer.org/):
```
$ composer require eduardo/gerencianet-sdk-php-atualizado
```
Or include it in your composer.json file:
```
...
"require": {
  "eduardo/gerencianet-sdk-php-atualizado": "1.*"
},
...
```
## Requirements
* PHP >= 5.4

## Tested with
```
php 5.4 and 5.5
```
## Getting started
Require the module and namespaces:
```php
require __DIR__ . '/../sdk/vendor/autoload.php';

use Gerencianet\Gerencianet;
```
Although the web services responses are in json format, the sdk will convert any server response to array. The code must be within a try-catch and exceptions can be handled as follow:
```php
try {
  /* code */
} catch(GerencianetException $e) {
  /* Gerencianet's api errors will come here */
} catch(Exception $ex) {
  /* Other errors will come here */
}
```

### For development environment
Instantiate the module passing using your client_id, client_secret and sandbox equals true:
```php
$options = [
  'client_id' => 'client_id',
  'client_secret' => 'client_secret',
  'sandbox' => true
];

$api = new Gerencianet($options);
```

### For production environment
To change the environment to production, just set the third sandbox to false:
```php
$options = [
  'client_id' => 'client_id',
  'client_secret' => 'client_secret',
  'sandbox' => false
];

$api = new Gerencianet($options);
```

## Running tests

To run tests install [PHPUnit](https://phpunit.de/getting-started.html) and run the following command:
```php
$ phpunit -c config.xml
```

## Running examples
Update examples/config.json file with client_id and client_secret of your application.

You can run using any web server, like Apache or nginx, or simple start a php server as follow:

```php
php -S localhost:9000
```

Then open any example in your browser.

:warning: Some examples require you to change some parameters to work, like examples/charge/detail.php where you must change the id parameter.

## Additional Documentation

The full documentation with all available endpoints is in https://dev.gerencianet.com.br/.

## License ##
[MIT](LICENSE)
