> THIS VERSION IS DEPRECATED! PLEASE USE [sven/unique-hashids](https://github.com/svenluijten/unique-hashids) INSTEAD.

# Unique Hashids

[![Latest Version on Packagist][ico-version]][link-packagist]
[![Total Downloads][ico-downloads]][link-downloads]
[![Software License][ico-license]](LICENSE.md)

This is a simple trait for [Laravel](http://laravel.com) models to generate
unique ids for them. It uses [vinkla](https://github.com/vinkla)'s wonderful
[Hashids](https://github.com/vinkla/hashids) package and is configurable within
the model itself.

## Installation

You may install this package via [composer](http://getcomposer.org):

```bash
$ composer require juggl/unique-hashids
```

## Configuration

This will install both this package and [Hashids](https://github.com/vinkla/hashids).
Please see the documentation over there to install & configure the hashids. This package
will use the default Hashids driver.

## Usage

To start generating unique ids for your models, all you need to do is use a trait,
like so:

```php
namespace App;

use Juggl\UniqueHashids\GeneratesUnique;
use Illuminate\Database\Eloquent\Model;

class YourModel extends Model
{
    use GeneratesUnique;

    // The rest of your model
}
```

By default, this package assumes you have a `unique_id` column on you database
to store the unique id in. Optionally, you may override this by setting a
static property `$uniqueColumn` on your model:

```php
namespace App;

use Juggl\UniqueHashids\GeneratesUnique;
use Illuminate\Database\Eloquent\Model;

class YourModel extends Model
{
    use GeneratesUnique;

    public static $uniqueColumn = 'my_column'; // this will assume 'unique_id' by default.

    // The rest of your model
}
```

## Credits

This package depends on [vinkla](https://github.com/vinkla)'s excellent Hashids
package, found [here](https://github.com/vinkla/hashids).

## License

`juggl\unique-hashids` is licenced under the MIT License (MIT). Please see the
[license file](LICENSE.md) for more information.

[ico-version]: https://img.shields.io/packagist/v/juggl/unique-hashids.svg?style=flat-square
[ico-license]: https://img.shields.io/badge/license-MIT-green.svg?style=flat-square
[ico-downloads]: https://img.shields.io/packagist/dt/juggl/unique-hashids.svg?style=flat-square

[link-packagist]: https://packagist.org/packages/juggl/unique-hashids
[link-downloads]: https://packagist.org/packages/juggl/unique-hashids
