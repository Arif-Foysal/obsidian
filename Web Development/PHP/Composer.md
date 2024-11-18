#PHP 

# Video tutorials
<iframe width="560" height="315" src="https://www.youtube.com/embed/FNa5heI6BD8?si=4fM74H0pN0aumbnU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


**Composer** is a dependency manager for PHP that allows you to manage libraries, packages, and other dependencies required by your projects. It automates the process of installing, updating, and loading the necessary files, ensuring that your project runs smoothly.

**Why use composer**
- **Dependency Management:** Easily manage and install third-party libraries and frameworks.
- **Autoloading:** Automatically load classes without needing to include or require files manually.
- **Version Control:** Ensure that specific versions of packages are used, avoiding conflicts and bugs.


## Default package repository for composer
https://packagist.org/



# Installation
You can follow the official instructions:
https://getcomposer.org/installer

Or you can run
```bash
sudo apt install composer
```

>[!Note]
>Apt might not have the latest version of composer

# Initializing a project with composer

To initialize a project with composer,

**`cd into your project directory`**
then,
```bash
composer init
```
This command will prompt you to fill in details about your project (name, description, license, etc.). You can accept the defaults or modify them as needed.

>[!Note]\
>You can skip the initialization part only care about adding dependencies quickly and you don’t need to provide additional metadata about your project.
# Adding dependencies

**Syntax**
```
composer require vendor/package
```

For example, to add the **Guzzle** HTTP client:
```php
composer require guzzlehttp/guzzle
```

**This command will:**
- Download the package.
- Update the `composer.json` file with the new dependency.
- Create a `composer.lock` file to lock the dependencies to specific versions.
- Generate the `vendor/` directory, where all the dependencies are stored.

# Autoloading

Composer provides an autoload feature that automatically loads classes without needing manual `include` or `require` statements.

```php
<?php

require 'vendor/autoload.php';

// Now you can use any class from your installed packages.
use GuzzleHttp\Client;

$client = new Client();
$response = $client->get('https://api.github.com/users/arif-foysal');
echo $response->getBody();
?>
```

# Installing your dependencies on a new machine

With the `composer.json` and `composer.lock` files from your project, just run
```bash
composer install
```
on your project directory and composer will install all your dependencies automatically.

# Updating your dependencies

Update all dependencies:
```bash
composer update
```

Update specific dependencies:
```bash
composer update vendor/package
```


# Removing packages
```bash
composer remove vendor/package
```
This will:

- Remove the package from `composer.json`.
- Delete the package files from the `vendor/` directory.
- Update the autoload files.


# Composer Scripts
You can define custom scripts in your `composer.json` that run certain commands, making it easier to manage repetitive tasks:
```bash
{
    "scripts": {
        "test": "phpunit"
    }
}
```

Run the script with:
```bash
composer test
```

# Install packages globally
Composer also allows you to install packages globally on your system. For example, to install the Laravel installer globally:
```bash
composer global require laravel/installer
```

Make sure that the Composer global bin directory is in your `PATH` so that you can run global commands from anywhere.


# Composer list arguments
used to list all the composer arguments
```bash
composer list
```

















