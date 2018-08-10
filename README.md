[![Laravel 5.3](https://img.shields.io/badge/Laravel-5.3-orange.svg?style=flat-square)](http://laravel.com) [![Latest Stable Version](https://poser.pugx.org/spotonlive/laravel-facebook-ads/v/stable)](https://packagist.org/packages/spotonlive/laravel-facebook-ads) [![Total Downloads](https://poser.pugx.org/spotonlive/laravel-facebook-ads/downloads)](https://packagist.org/packages/spotonlive/laravel-facebook-ads) [![Latest Unstable Version](https://poser.pugx.org/spotonlive/laravel-facebook-ads/v/unstable)](https://packagist.org/packages/spotonlive/laravel-facebook-ads) [![License](https://poser.pugx.org/spotonlive/laravel-facebook-ads/license)](https://packagist.org/packages/spotonlive/laravel-facebook-ads) [![Build Status](https://travis-ci.org/spotonlive/laravel-facebook-ads.svg?branch=master)](https://travis-ci.org/spotonlive/laravel-facebook-ads) [![Code Climate](https://codeclimate.com/github/spotonlive/laravel-facebook-ads/badges/gpa.svg)](https://codeclimate.com/github/spotonlive/laravel-facebook-ads) [![Test Coverage](https://codeclimate.com/github/spotonlive/laravel-facebook-ads/badges/coverage.svg)](https://codeclimate.com/github/spotonlive/laravel-facebook-ads/coverage)

## Facebook Ads API for Laravel 5.*

This package is an integration of [`facebook/facebook-php-ads-sdk`](https://github.com/facebook/facebook-php-ads-sdk) in Laravel 5.*.

### Composer
- Run `$ composer require spotonlive/laravel-facebook-ads`

## Examples

### Client

```php
<?php

namespace App\Http\Controllers;

use LaravelFacebook\Clients\Facebook;

class AdsController
{
    /** @var Facebook */
    protected $facebookClient;

    public function __construct(Facebook $facebookClient)
    {
        $this->facebookClient = $facebookClient;
    }

    /**
     * Show ads
     *
     * @return \Illuminate\Contracts\View\Factory|\Illuminate\View\View
     */
    public function ads()
    {
        $client = $this->facebookClient;

        $accountId = 'act_12345678';

        return view('ads', [
            'ads' => $client->account($accountId)->ads(),
        ]);
    }
}
```

### Credits
- [`SpotOn Marketing`](https://spotonmarketing.dk/)
- [`nikolajlovenhardt`](https://github.com/nikolajlovenhardt)