<!-- .slide: data-background="http://i.giphy.com/TPl5N4Ci49ZQY.gif" -->
# <!-- .element: style="color: black; text-shadow: -5px 0 white, 0 5px white, 5px 0 white, 0 -5px white;" --> What is Islandora?


<!-- .slide: data-background="#fff" -->
<img src="images/islandora.png" alt="Islandora logo" class="img-clear">

It's a suite of software for archiving digital assets! <!-- .element: style="color: black;"-->

...it's a Drupal module!<!-- .element: class="fragment", style="color: black;" -->

Notes:

- "Suite" includes a lot of layers.
- "Islandora" itself is simply a Drupal module.


## <span class="fa fa-cubes"></span> What's in the box?

#### Spoiler: There is no box

- <!-- .element: class="fragment" --> **Fedora Commons** (_Java content repository_)
- <!-- .element: class="fragment" --> **Drupal Filter** (_Fedora authentication plugin_)
- <!-- .element: class="fragment" --> **Apache SOLR** (_Search tool_)
- <!-- .element: class="fragment" --> **Fedora GSearch** (_Java search indexer_)
- <!-- .element: class="fragment" --> **Tuque** (_Fedora client php library_)
- <!-- .element: class="fragment" --> **Islandora** (_Drupal module_)
- <!-- .element: class="fragment" --> **Drupal**
- <!-- .element: class="fragment" --> ...etc 😨

Notes:

- Not the Fedora OS
  - Back end Java content repository
- This is the basic stack required to run Islandora, does not include various 
"Solution Packs", that have their own dependencies
- Islandora leans heavily on java servlets
- Set up is not trivial and debugging can be a pain
- Djakota and Imagemagick are also required for certain things for example...
- Typically all of this lives on a single server
- Drupal has it's own requirements, ie Web server, database, etc...
- Fedora also requires a database


## <span class="fa fa-file"></span> Fedora Commons

- <!-- .element: class="fragment" --> Fedora is a Java Content Repository and implements the [JCR standard](https://en.wikipedia.org/wiki/Content_repository_API_for_Java)
- <!-- .element: class="fragment" --> Typically deployed into a Tomcat servlet container
- <!-- .element: class="fragment" --> Islandora currently uses Fedora 3.x (which is EOL)
- <!-- .element: class="fragment" --> Fedora stores **objects** in "FOXML" (Fedora-Object XML) files
- <!-- .element: class="fragment" --> Objects can have any number of **datastreams**, which can contain anything
- <!-- .element: class="fragment" --> A Fedora Repository can be rebuilt using only the filesystem

Notes:

- PHPCR implements the same standard with different backends (with various 
levels of "feature-completedness" depending on the back-end)
  - Used in the Symfony CMF
- Datastreams typically contain metadata, derivatives (ie images in various 
sizes) and other data about the object
- Popular among archivists
- Has no front-end
  - Islandora is not the only front-end for Fedora, there is also "Hydra" (ruby)
- Drupal analogue is "Entities" (Objects) and "Fields" (Datastreams)


## <span class="fa fa-search"></span> Apache SOLR

- <!-- .element: class="fragment" --> Search tool for Islandora
- <!-- .element: class="fragment" --> Uses **Fedora GSearch** to index FOXML files directly
- <!-- .element: class="fragment" --> FOXML is translated to SOLR documents using XSLT

Notes:

- Drupal is not involved in the indexing process...
  - No runtime modifications


## <span class="fa fa-desktop"></span> Islandora

- <!-- .element: class="fragment" --> Uses **Tuque** to interface with Fedora
- <!-- .element: class="fragment" --> Ingests and displays **objects**
- <!-- .element: class="fragment" --> Uses various **Solution Packs** to define "_content models_"
- <!-- .element: class="fragment" --> Uses **SOLR** index for search and discover-ability
- <!-- .element: class="fragment" --> Commonly referred to as the "front-end" or "interface" for Fedora within Islandora community

Notes:

- Analogue for content models would be content-types
  - Fedora is almost "schema-less" though, similar to SOLR
- Strange to think of Drupal as a "front-end" for something when it is typically
a back-end technology (ie headless Drupal)


<!-- .slide: data-background="http://www.turingfinance.com/wp-content/uploads/2013/11/2Deployment.png" alt="complex system architecture" -->
# <!-- .element: style="color: black; text-shadow: -5px 0 white, 0 5px white, 5px 0 white, 0 -5px white;" --> It's a little complicated
