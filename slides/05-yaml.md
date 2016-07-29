# From info to YAML


## The Drupal 7 Way

`.info` files example.

```info
name = "Lukes module"
description =  "This is a simple custom module for Drupal 7."
core = "7.x"
package = "Custom"

dependencies[] = node
```


## The Drupal 8 Way

`.info.yml` files example.

```yaml
name: Lukes module
description:  This is a simple custom module for Drupal 8.
core: 8.x
package: Custom
type: module

dependencies:
  - node
```

Notes:

- "type" indicates the type of extension, ie:
  - module
  - theme
  - profile
  - etc.


## YAML vs Info
  
- <!-- .element: class="fragment" -->Probably looks very similar
- <!-- .element: class="fragment" -->More focus on "readability"
- <!-- .element: class="fragment" -->YAML is a [standard](http://yaml.org/)
- <!-- .element: class="fragment" -->Drupal 8 uses it everywhere (brace yourself)
  
