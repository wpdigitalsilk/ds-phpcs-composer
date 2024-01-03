# Digital Silk PHPCS Configuration

> Composer library to provide drop in installation and configuration of [WPCS](https://github.com/WordPress-Coding-Standards/WordPress-Coding-Standards) and [PHPCompatibilityWP](https://github.com/PHPCompatibility/PHPCompatibilityWP), setting reasonable defaults for WordPress development with nearly zero configuration.

## Installation

Install the library via Composer:

```bash
$ composer require --dev wpdigitalsilk/phpcs-composer:dev-master
```

That's it!

## Usage

Lint your PHP files with the following command:

```bash
$ ./vendor/bin/phpcs .
```

If relying on Composer, edit the `composer.json` file by adding the following:

```json
	"scripts": {
		"phpcs": "phpcs .",
		"phpcbf": "phpcbf ."
	}
```

Then lint via:

```bash
$ composer run phpcs
```

### Continuous Integration

PHPCS Configuration plays nicely with Continuous Integration solutions. Out of the box, the library loads the `DigitalSilk-Default` ruleset, and checks for syntax errors for PHP 7.4 or higher.

To override the default PHP version check, set the `--runtime-set testVersion 7.2-` configuration option.
Example for PHP version 7.2 and above:

```bash
$ ./vendor/bin/phpcs --runtime-set testVersion 7.2-
```

See more [information about specifying PHP version](https://github.com/PHPCompatibility/PHPCompatibility#sniffing-your-code-for-compatibility-with-specific-php-versions).

Note that you can only overrule PHP version check from the command-line.

### IDE Integration

Some IDE integrations of PHPCS fail to register the `DigitalSilk-Default` ruleset. In order to rectify this, place `.phpcs.xml.dist` at your project root:

```xml
<?xml version="1.0"?>
<ruleset name="Project Rules">
	<rule ref="DigitalSilk-Default" />
</ruleset>
```
