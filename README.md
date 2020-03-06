# README

The bundle provides a [KCFinder](http://kcfinder.sunhater.com/) for [CKEditor](http://ckeditor.com/) integration for your Symfony Project

## Migration from KCFinderBundle

You're probably coming here because you updated `mylittleparis/sonata-bundle` to [v3.1](https://github.com/MyLittleParis/SonataBundle/releases/tag/3.1) or [v4.1](https://github.com/MyLittleParis/SonataBundle/releases/tag/4.1).
When migrating from KCFinderBundle, you need to change `config.yml`, `routing.yml` and `AppKernel.php`.

Example:
https://github.com/MyLittleParis/my-little-paris/pull/1402/files

## Documentation

### Installation

Register the bundle:

``` php
// app/AppKernel.php

public function registerBundles()
{
    return array(
        new Ikadoc\KCFinderBundle\IkadocKCFinderBundle(),
        // ...
    );
}
```

Install the bundle:

```
$ composer require mylittleparis/kcfinder-bundle-v2
```

Add routing:

```
// app/config/routing.yml
kcfinder:
    resource: "@IkadocKCFinderBundle/Resources/config/routing.yml"
    prefix: /admin
```


### Configuration

The bundle allow to change base_path to kcfinder folder and you can define as many configs you want. The list of all config options are available
[here](http://kcfinder.sunhater.com/install).

``` yaml
ikadoc_kc_finder:
    base_path : "%kernel.root_dir%/../vendor/sunhater/kcfinder"
    config:
        disabled : false
        uploadURL: "/uploads/"
        uploadDir: "%kernel.project_dir%/web/uploads/"
```


## License

The Ikadoc KCFinder Bundle is under the MIT license. For the full copyright and license information, please read the
[LICENSE](/LICENSE) file that was distributed with this source code.
