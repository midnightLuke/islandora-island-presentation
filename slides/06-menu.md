# What happened to hook_menu?


## The Drupal 7 Way

```php
function lukes_module_menu() {
  $items = array();
  $items['lukes-custom/list'] = array(
    'page callback' => 'lukes_module_list_page',
    'file' => 'includes/lukes_module.pages.inc',
    'access arguments' => array('access content'),
    'title' => 'Listing of stuff',
    'type' => MENU_NORMAL_ITEM,
  );
  return $items;
}
```

Notes:

- "MENU_NORMAL_ITEM" is default, but included to talk about difference in D8
- Talk about why this is bad
- Defining a page callback AND a menu item
- Hard to predict and difficult to debug


## Here comes some YAML

`.routing.yml` file example.

```yaml
lukes_custom.list:
  path: '/lukes-custom/list'
  defaults:
    _controller: '\Drupal\lukes_custom\Controller\LukesCustomController::listThings'
    _title: 'Listing of stuff'
  requirements:
    _permission: 'access content'
```

` .links.menu.yml` file example.

```yaml
lukes_module.list:
  route_name: lukes_custom.list
  title: Hey my list
  description: 'List some things.'
  parent: system.admin
  weight: 10
```

There is a [LOT of documentation](https://www.drupal.org/node/2118147) on this.

Notes:

- Talk about advantages
- Separation of "MENU_CALLBACK" vs "MENU_NORMAL" vs "MENU_DEFAULT_ACTION"
- There are disadvantages
  - Menu active trail issues

