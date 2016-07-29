# Composer, PSR-4, namespaces and autoloading


You've probably used the `files[]` key in an info file before:

```info
name = "Luke's module"
description = "Hey this is my custom module."
core = "7.x"

files[] = includes/lukes_module_helpers.inc
files[] = includes/lukes_module_pages.inc

dependencies[] = node
```

Or if you're a real rebel maybe even this at the top of a `.module` file (don't do this):

```php
module_load_include('inc', 'lukes_module', 'includes/lukes_module_helpers');
```


## Namespacing your work

Drupal 8 has **no** `files[]` key, instead we use PHP namespaces to autoload
classes right when we need them.

```php
namespace Drupal\lukes_module\Utility;

class LukesUtility {
  [...]
}
```

- Everything lives in your module folder under src.
- This file would be located at `lukes_modules/src/Utility/LukesUtility.php`


## Sample file tree

<img style="width: auto; height: 15em" src="images/sample-tree.png" alt="Sample file tree" />

Notes:

- The `.module` file is now completely optional, you may find that you rarely
have one moving forward.


## Using namespaced code

To then use this class in another file we need to tell PHP to `use` it.

```php
namespace Drupal\lukes_module\Controller;

use Drupal\Core\Controller\ControllerBase;

class LukesController extends ControllerBase {
  public function showAction() {
    [...]
  }
}
```

We could also simply refer to the class above by its fully qualified name and
omit the use statement, but that goes against Drupal coding standards (and is
generally bad practice).

Notes:

- Don't need to `use` LukesUtility because it lives in the same namespace


## Composer and Drupal

```json
{
    "name": "drupal/example",
    "description": "This is an example composer.json for example module.",
    "type": "drupal-module",
    "license": "GPL-2.0+"
    "require": {
        "commerceguys/addressing": "~0.8.1"
    }
}
```

- <!-- .element: class="fragment" -->Drupal
[recommends](https://www.drupal.org/node/2514612) including a composer.json
with modules now
- <!-- .element: class="fragment" -->[Composer manager](https://www.drupal.org/project/composer_manager)
module allows you to define composer dependencies in your module
- <!-- .element: class="fragment" -->Opens up Drupal to the greater PHP
community

Notes:

- Important because we used to only be able to rely on Drupal modules
- We now have access to the entire world of PHP
