# TinymceFastloadBundle

This bundle extends https://github.com/stfalcon/TinymceBundle so
https://github.com/stfalcon/TinymceBundle/blob/master/README.md must be readed first

## Installation

Add bundle as a dependency to the composer.json of your application

```php
    "require": {
        ...
        "gwinn/tinymce-fastload-bundle": "dev-master"
        ...
    },
```

## Add bundle to your application kernel.

```php
// app/AppKernel.php
<?php
    // ...
    public function registerBundles()
    {
        $bundles = array(
        // ...
            new Gwinn\TinymceFastloadBundle\GwinnTinymceFastloadBundle(),
        );
    }

```

## Copy resources to web folder

```bash
    php app/console assets:install web/
```

## Include in template

```twig
    {{ tinymce_init() }}
```

```html
    <textarea class="tinymce"></textarea>
```

## Configuration

Similar to tinymce-bundle, just add to stfalcon_tinymce section in config.yml

```yaml
stfalcon_tinymce:
    ...
    tinymce_buttons:
        image_uploader:
        title: "Upload Image"
        image: "asset[bundles/gwinntinymcefastload/images/upload.png]"
    ...
    theme:
        simple:
            toolbar: "... | image_uploader | ..."
```
