# Updates

* `hook_post_update_N()` **MUST** be used to deliver DB changes between environments.
* `shortprojectname_updates` module **SHOULD** be used just for all non-schema

  updates in features and custom modules.

* Update comment **SHOULD** be written in 3rd person pronoun: "enable**s**" instead

  of "enable".

* Use the following snippet to implement `hook_post_update_N()`:

```php
/**
 * Provisions contewnt for About Us page.
 */
function MYPROJECT_updates_post_update_provision_content() {
    // code goes here
}
```

