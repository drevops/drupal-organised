# Hooks

Comments with description of hook functionality **SHOULD** NOT go into the hook comment.
Instead, it **SHOULD** start just before a part of the code within hook implementation.

This is due to the fact that hooks are not generic functions, which are supposed to handle specific logic, but more of a wrappers or 'gatherers' of another functions and business logic, each piece of which should be extensively commented separately.

**Incorrect**
```php
/**
 * Implements hook_form_alter().
 *
 * - Overriding some awesome fields because of super creative design.
 * - Handling summary visibility for different user roles.
 */
function MYMODULE_form_alter(){
  // code goes here
}
```

**Correct**
```php
/**
 * Implements hook_form_alter().
 */
function MYMODULE_form_alter(){
  // Overriding some awesome fields because of super creative design.
  // code goes here

  // Handling summary visibility for different user roles.
  // code goes here
}
```
