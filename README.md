Laravel JS Localization
=======================

> Laravel Localization in JavaScript.

This is a simple package that convert all your localization messages of your Laravel app to JavaScript, and provides a small JavaScript library to interact with those messages.

For larvel 4.* use https://github.com/rmariuzzo/Laravel-JS-Localization

Support Laravel 5.0.

Installation
------------

Add the following line to you `composer.json` file under `require`.

    "xaoc/laravel-js-localization": "dev-master"

Run:

    composer update

In your Laravel app go to `config/app.php` and add the following service provider:

    'providers' => array(
        ...
        'Mariuzzo\LaravelJsLocalization\LaravelJsLocalizationServiceProvider'
        ...
    )

That's it!

Usage
-----

This project comes with a command that generate the JavaScript version of all your messages found at: `app/lang` directory. The resulting JavaScript file will have the whole bunch of messages and a thin library similar to Laravel's `Lang` class.

**Generating JS messages**

    php artisan lang:js

**Specifying a custom target**

    php artisan lang:js public/assets/dist/lang.dist.js

**Compressing the JS file**

    php artisan lang:js -c

Documentation
-------------

This is the documentation regarding the thin JavaScript library. The library highly inspired on Laravel's `Lang` class.

**Getting a message**

    Lang.get('messages.home');

**Getting a message with replacements**

    Lang.get('messages.welcome', { name: 'Joe' });

**Changing the locale**

    Lang.setLocale('es');

**Checking if a message key exists**

    Lang.has('messages.foo');

**Support for singular and plural message based on a count**

    Lang.choice('messages.apples', 10);

**Calling the `choice` method with replacements**

    Lang.choice('messages.apples', 10, { name: 'Joe' });    

For more detailed information, take a look at the source: [Lang.js](https://github.com/xAockd/Laravel-JS-Localization/blob/master/src/js/lang.js).

