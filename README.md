# PHPStan shim

The prefixed `.phar` distribution of [PHPStan](https://github.com/phpstan/phpstan) is built using [phpstan-compiler](https://github.com/fprochazka/phpstan-compiler)

## Usage

Install the package

```bash
composer require --dev xificurk/phpstan-shim
```

and use it like the original executable

```bash
vendor/bin/phpstan.phar analyse src
```

Check out the main repo for more options https://github.com/phpstan/phpstan

## Configuration

It is recommended, that you set a `tmpDir` in your `phpstan.neon`, otherwise it uses the system temp directory.

```
parameters:
    tmpDir: var/cache/phpstan
```

## Extensions

Contrary to [phpstan/phpstan-shim](https://github.com/phpstan/phpstan-shim) this distribution contains several PHPStan extensions:

* [Doctrine](https://github.com/phpstan/phpstan-doctrine)
* [Nette Framework](https://github.com/phpstan/phpstan-nette)
* [Dibi - Database Abstraction Library](https://github.com/phpstan/phpstan-dibi)
* [PHPStan rules for checked & unchecked exceptions](https://github.com/pepakriz/phpstan-exception-rules)

You can enable them, by including their config with a `phar://phpstan.phar/` prefix.

```
includes:
	- phar://phpstan.phar/vendor/phpstan/phpstan-doctrine/extension.neon
```
