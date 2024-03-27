Tips for PHP Composer
---------------------

### Init Composer for PHP Project

    composer init

### **Create Project**

    composer create-project laravel/laravel --prefer-dist --profile --verbose

Composer install will install all the packages you have defined in your composer.lock file.

Composer update will fetch the newest possible version defined in your composer.json. That means the versions of the packages can change based on your rules. If you put in a \* for the version it could install a new version with breaking changes.

    composer install
    composer update

**Use to search for a package**

    composer search ****
    // to search for a package 

**Remove a Package**

 You can remove the package from composer.json file and run

    composer update

OR

    composer remove vendor/packagename

**Something is not working**

    composer diagnose

**Rewrite your autoloading files**

Sometimes it happens that you get an error some class is not available. But in your code, you see the class …  
There is a chance the class isn’t just added to your autoloading files

    composer dump-autoload

**Keep Composer up to date**

    composer self-update

**Use composer command line to get new packages**

    composer require 42coders/document-templates

**Only update what you want**

    composer update 42coders/document-templates

### **List all the installed dependencies of the project**

Using the `show` command of the Composer, you can get the list of all the packages installed in the project or all your repositories in the following format.

    composer show 
    # List the packages that are installed (this is enabled by default, and deprecated).
    composer show --all 
    # List all packages available in all your repositories.

    composer show --installed

### Get information about a certain package

Using the same `show` command you can get the information about a certain package. For instance, if you want to get information about `spatie/laravel-web-tinker` package, you can do it like so.

    $ composer show spatie/laravel-web-tinker
    $ composer show spatie/laravel-web-tinker 1.0.0

### Navigate to package’s GitHub repository/Homepage

Using the `browse` command, you navigate to the package’s repository URL or homepage in your browser.

    $ composer browse spatie/laravel-web-tinker 
    # Navigate to package's repository URL
    
    $ composer browse spatie/laravel-web-tinker --homepage 
    # Navigate to package's homepage
    
    $ composer browse spatie/laravel-web-tinker --show
    # Only show the homepage or repository URL
    

### Validate

You can validate your project’s `composer.json` which helps find issues with your `composer.json` (if there are any).

    $ composer validate

### Find outdated packages

If you’re keeping all your dependencies latest, you can keep a check on outdated dependencies using an `outdated` command like so.

    composer outdated

*   **green (=)**: Dependency is in the latest version and is up to date.
*   **yellow (~)**: Dependency has a new version available that includes backward compatibility breaks according to semver, so upgrade when you can but it may involve work.
*   **red (!)**: Dependency has a new version that is semver-compatible and you should upgrade it.

Install a package globally
--------------------------

The most common use of Composer is to install and manage a library within a given project. There are however, times when you want to install a given library globally so that all of your projects can use it without you having to specifically require it in each project. Composer is up to the challenge with a modifier to the require command we discussed above, global. The most common use of this is when you are using Composer to manage packages like PHPUnit.  
  
`$ composer global require "phpunit/phpunit:^5.3.*"`