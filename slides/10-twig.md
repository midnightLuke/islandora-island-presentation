# My first Twig template


## What is Twig?

- <!-- .element: class="fragment" -->Templating language
- <!-- .element: class="fragment" -->Extremely flexible &amp; powerful
- <!-- .element: class="fragment" -->Definitely not getting too far into it


## The new hook_theme

It's still a hook (take deep breaths)

```php
/**
 * Implements hook_theme().
 */
function lukes_module_theme($existing, $type, $theme, $path) {
  return array(
    'lukes_template' => array(),
  );
}
```

This template would live in your module folder under "templates" with the
extension ".html.twig" (`lukes_module/templates/lukes-template.html.twig`)


Using the new template in a controller might look like:

```php
namespace Drupal\lukes_module\Controller;

use Drupal\Core\Controller\ControllerBase;

class DefaultController extends ControllerBase {
  public function showPageAction() {
    return [
      '#theme' => 'lukes_template',
    ];
  }
}
```

lukes-template.html.twig

```twig
<div class="lukes-template">
  <p>This is luke's template, it's pretty simple right now.</p>
  <p>If we were printing variables we would escape them like {{ this }}</p>
</div>
```
