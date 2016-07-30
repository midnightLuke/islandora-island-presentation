# Drupal-izing Islandora

Notes:

- One of the things we focused on was finding "Drupal" solutions


## The Challenge

- <!-- .element: class="fragment" --> Drupal was chosen as it was a popular open-source CMS platform
- <!-- .element: class="fragment" --> Much of the original development was done by developers who were initially unfamiliar with Drupal
- <!-- .element: class="fragment" --> Drupal contrib has starting solving some of the issues Islandora solved in custom additions
- <!-- .element: class="fragment" --> The current version of Islandora contains a lot of legacy code

Notes:

- ie Drupal was _not_ chosen by folks who used it often
- Islandora 7.x is essentially a port of 6.x


## Example: Islandora Blocks

- <!-- .element: class="fragment" --> Islandora shows a lot of metadata using templates
- <!-- .element: class="fragment" --> Requires a lot of template overrides to change displays
- <!-- .element: class="fragment" --> Much of this data could be put into blocks so site admins could have more control
- <!-- .element: class="fragment" --> Even more control could be given by adding "Islandora" options to blocks (ie _cmodel_ based display options)

Notes:

- Show an example of using blocks instead of templates


## Example: Islandora Facet API

- <!-- .element: class="fragment" --> Islandora uses a custom SOLR integration with custom facets
- <!-- .element: class="fragment" --> Facets are not very configurable, have limited display configurations
- <!-- .element: class="fragment" --> Custom facets are difficult to implement
- <!-- .element: class="fragment" --> More control could be acheived using the powerful [Facet API](https://drupal.org/project/facetapi) module

Notes:

- Show an example of Islandora Facets vs Facet API
- More documentation for using/developing for Facet API


## Other "Drupal"-izing

- <!-- .element: class="fragment" --> Islandora SOLR vs the Search API with Sarnia
- <!-- .element: class="fragment" --> Fedora GSearch vs custom Search API Provider with XSLT
- <!-- .element: class="fragment" --> XACML permissions vs Drupal permissions

Notes:

- Things that _could_ be done, but have not tried/tested
- Given infinite time on a project there are lots of improvements we could make
- XACML a little rigid due to Drupal filter
  - Two scopes: User and role, Drupal modules provide more scopes (like group memberships), but not supported by Drupal filter
