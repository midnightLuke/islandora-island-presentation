<!-- .slide: data-background="images/excited.gif" -->
# <!-- .element: style="color: white;"-->Services and the Dependency Injection Container


## What are services?

Symfony [defines](http://symfony.com/doc/current/book/service_container.html) a
service as:

> [...] any PHP object that performs some sort of "global" task. It's a
purposefully-generic name used in computer science to describe an object that's
created for a specific purpose (e.g. delivering emails).

Notes:

- "It's a class that only get's created when needed and is only created once,
with every other call for the service returning the same object."
- Helper functions


## What is the dependency injection container?

Symfony [defines](http://symfony.com/doc/current/book/service_container.html)
the dependency injection container as:

> [...] a PHP object that manages the instantiation of services (i.e. objects).


## Why do we call it "dependency injection"?

- A service can depend on other services
- The dependency injection container takes responsibility for ensuring all
dependencies for a service are met

Notes:

- This would also create the session service, if it wasn't created yet, and
inject that into the Trello Client (dependency injection).
- Ideally you would declare whatever needs the service as a service itself and
then use dependency injection, but sometimes that is overkill
- Groupings of utility functions
- How many times have you written `_my_module_helper_thing`?
- This is handled by the dependency injection container.
  - Some services depend on other services, these dependencies get "injected"
  (wave of comprehension)


## Defining a service (return of the YAML)

Services are defined in your modules `.services.yml` file.

```yaml
parameters:
  trello_client_key: "d75adcab7f81be6b5f3fcf275d7c88bc"
  trello_client_secret: "secreeeeeeets"

services:
  lukes_module.trello_client:
    class: "\Drupal\lukes_module\Utility\TrelloClient"
    arguments: ['%trello_client_key%', '%trello_client_secret%', '@session']
```

Notes:

- When someone requests this service the container will construct an instance of
TrelloClient if it doesn't exist and return it if it does.
- The `@session` key above indicates that this service should receive the
"session" service as an argument.
- Allows services to depend on each other
- Anything can be a service
- You can override core services and parameters in your
sites/default/services.yml file


## Fetching a service

```php
// Use the shortcut here.
$session = \Drupal::service('lukes_module.trello_client');
```

<!-- .element: class="fragment" -->You can also define controllers
_as services_ and use dependency injection

<img src="images/inception.gif" alt="Inception hallway" class="fragment" />
