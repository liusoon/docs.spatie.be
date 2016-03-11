---
title: Introduction
---

Medialibrary is a Laravel 5.1 package that can associate all sorts of files with Eloquent models. It provides a simple, fluent API to work with. Here's a quick example:

```php
$newsItem = News::find(1);
$newsItem->addMedia($pathToFile)->toCollection('images');
```

It can also directly handle your uploads:

```php
$newsItem->addMedia($request->file('image'))->toCollection('images');
```

Want to store some large files on another filesystem? No problem:

```php
$newsItem->addMedia($smallFile)->toCollectionOnDisk('downloads', 'local');
$newsItem->addMedia($bigFile)->toCollectionOnDisk('downloads', 's3');
```

The storage of the files is handled by [Laravel's Filesystem](http://laravel.com/docs/5.1/filesystem),  so you can plug in any compatible filesystem.

The package can also generate derived images such as thumbnails for images and pdf's. Once you've [set up your model](/laravel-medialibrary/v3/converting-images/defining-conversions/), they're easily accessible:

```php
$newsItem->getMedia('images')->first()->getUrl('thumb');
```

## We have badges!

<section class="article_badges">
    <a href="https://github.com/spatie/laravel-medialibrary/releases"><img src="https://img.shields.io/github/release/spatie/laravel-medialibrary.svg?style=flat-square" alt="Latest Version"></a>
    <a href="LICENSE.md"><img src="https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square" alt="Software License"></a>
    <a href="https://travis-ci.org/spatie/laravel-medialibrary"><img src="https://img.shields.io/travis/spatie/laravel-medialibrary/master.svg?style=flat-square" alt="Build Status"></a>
    <a href="https://insight.sensiolabs.com/projects/27cf455a-0555-4bcf-abae-16b5f7860d09"><img src="https://img.shields.io/sensiolabs/i/27cf455a-0555-4bcf-abae-16b5f7860d09.svg?style=flat-square" alt="SensioLabsInsight"></a>
    <a href="https://scrutinizer-ci.com/g/spatie/laravel-medialibrary"><img src="https://img.shields.io/scrutinizer/g/spatie/laravel-medialibrary.svg?style=flat-square" alt="Quality Score"></a>
    <a href="https://packagist.org/packages/spatie/laravel-medialibrary"><img src="https://img.shields.io/packagist/dt/spatie/laravel-medialibrary.svg?style=flat-square" alt="Total Downloads"></a>
</section>
