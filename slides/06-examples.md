<!-- .slide: data-background="http://i.giphy.com/bip95zRzXg8q4.gif" -->
# <!-- .element: style="text-shadow: -5px 0 black, 0 5px black, 5px 0 black, 0 -5px black;" --> What Can Islandora Do?


# Not a lot!

Notes:

- Almost nothing without some help, the basic stack provides APIs for solution
packs to provide extra functionality


## Solution Packs

- <!-- .element: class="fragment" --> Solution packs add "_cmodels_" and "_viewers_" for specific types of archival objects
- <!-- .element: class="fragment" --> Solution Packs typically have extra dependencies for ingesting/viewing/derivative generation

Notes:

- Extra dependencies can be a pain to install/manage


## Object Model

- <!-- .element: class="fragment" --> Typically presented as a "tree" structure
- <!-- .element: class="fragment" --> Really a graph structure (objects can have multiple parents)
- <!-- .element: class="fragment" --> RELS-EXT datastream defines relationships

Notes:

- Think of a file system, where a directory can have files and sub-directories


## Metadata

- <!-- .element: class="fragment" --> Islandora uses [MODS](https://en.wikipedia.org/wiki/Metadata_Object_Description_Schema) records extensively
- <!-- .element: class="fragment" --> DC datastreams can be automatically crosswalked automatically from MODS
- <!-- .element: class="fragment" --> Citations can be generated from MODS with Islandora Scholar Solution Pack

Notes:

- Metadata is a librarians dream
- MODS stands for **M**etadata **O**bject **D**escription **S**chema


## Versioning

- <!-- .element: class="fragment" --> All datastreams keep version histories


## Image Archiving

- <!-- .element: class="fragment" --> Large Image Solution Pack for JP2000, tiffs, etc
- <!-- .element: class="fragment" --> Basic Image Solution Pack for png, jpg, gifs, etc


## And a lot more...

- PDFs
- Websites
- Documents
- Citations
- Entities (People/Places/Organizations)
- etc...


## Sites Using Islandora

#### [York University](https://digital.library.yorku.ca)

#### [Metropolitan New York Library Council (METRO)](http://dcmny.org/)

#### [Florida Gulf Coast Univeristy](http://fgcu.digital.flvc.org/islandora/object/fgcu%3Aroot)

#### [Canadian Writing Research Collaboratory](http://beta.cwrc.ca)

#### [... and many others](http://islandora.ca/islandora-installations)

