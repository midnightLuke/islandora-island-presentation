
## What is module development?

Drupal is like an onion.  
<!-- .element: class="fragment" --><img src="images/onion.png" alt="An onion" width="256" height="256" />  
It's got layers!

Notes:

- "Layers" in drupal
  - Theme
  - Module
  - Core
- Often talk about working in the "theme" layer or "module"
layer.
  - Depends on what you want to do
- Module "layer" is _extremely_ flexible, you can change almost
anything.
  - Migrations
  - Features
  - Configuration
  - Custom entities
  - Tweaks to core


## <img src="images/hook.png" alt="Hook" width="96" height="96" style="border: none; box-shadow: none; position: relative; top: 35px" />Drupal 7 module development

- Built on the "hook" system <!-- .element: class="fragment" -->
- Hooks allow you to change behaviour of Drupal <!-- .element: class="fragment" -->
- Largely uses procedural programming <!-- .element: class="fragment" -->
- Very similar to Drupal 6 <!-- .element: class="fragment" -->

Notes:

- "Rigid", meaning if something didn't provide a hook to alter it's behaviour
you were reduced to recreating the whole module to replace it (or hacking it
:P).
- So many hooks could be confusing
  - The field widget API is unwieldy
  - Hooks for different things


## <img src="images/plug.png" alt="Hook" width="72" height="72" style="border: none; box-shadow: none; position: relative; top: 25px" /> Drupal 8 module development

- New plugin system (but hooks are still a thing) <!-- .element: class="fragment" -->
- Uses the Symfony components (which are awesome) <!-- .element: class="fragment" -->
- Built on solid object-oriented techniques <!-- .element: class="fragment" -->
- Uses YAML files instead of info files <!-- .element: class="fragment" -->
- Extremely different than Drupal 7 <!-- .element: class="fragment" -->
