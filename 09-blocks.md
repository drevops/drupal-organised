# Blocks

* Declared using `hook_block_info()` within a module to which the functionality of this block belongs to.
* Module name ****MUST** NOT** be specified in delta. I.e. instead of `mymodule_myblock` name it `myblock`:

```php
/**
 * Implements hook_block_info().
 */
function MYMODULE_block_info() {
  $blocks = array(
    'myblock' => array(
      'info' => t('My awesome block'),
    ),
  );

  return $blocks;
}
```

* Block output should use `hook_block_view()` and the following snippet:

```php
/**
 * Implements hook_block_view().
 */
function MYMODULE_block_view($delta = '') {
  $block = array();

  switch ($delta) {
    case 'myblock':
      $block['subject'] = t('Myblock title');
      $block['content'] = _MYMODULE_myblock_output();

      break;
  }

  return $block;
}
```

* Block content output **SHOULD** use output function named as `<MYMODULE>_<delta>_output()`. I.e. `_ MYMODULE_myblock_output()`. Note the leading underscore as this is a Drupal 'private' function.

* Blocks **SHOULD** be placed on the page using context module. Context configuration is stored in a separate feature (`projectshortname_contexts`).

* Them templates **SHOULD** be used for each block output. Render arrays are less preferable option. HTML in PHP should be avoided by all means.

* If used in blocks, theme templates **MUST** be stored in the subdirectory of a module named `templates`.

{% include "./footer.md" %}
