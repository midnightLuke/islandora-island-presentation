# My first controller


## What are controllers?

- Come from the MVC framework paradigm
- They "glue" together your business and display logic
- In Drupal 8 they replace page callbacks


## Sample controller

```php
namespace Drupal\lukes_module\Controller;

use Drupal\Core\Controller\ControllerBase;

class DefaultController extends ControllerBase {
  public function showPageAction() {
    return [
      '#markup' => $this->t('My awesome page callback'),
    ];
  }
}
```


Extending `ControllerBase` gives us access to some helper functions and common
services.

```php
// Redirect to a different route.
return $this->redirect('system.admin');

// Get the form builder service.
$fb = $this->formBuilder();
```
