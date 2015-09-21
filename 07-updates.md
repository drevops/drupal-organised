# Updates

* `hook_update_N()` **MUST** be used to deliver DB changes between environments.
* `shortprojectname_updates` module **SHOULD** be used just for all non-schema updates in features and custom modules.
* Update comment **SHOULD** be written in 3rd person pronoun: "enables" instead of "enable".
* Update functions **SHOULD** be suffixed with major version set to zero: 7000, 7001, 7002 and so on.
* Use the following snippet to implement `hook_update_N()`:

```php
/**
 * [PRJ-123] Enables mymodule.
 */
function MYPROJECT_updates_update_7000() {
	// code goes here
}
```

{% include "./footer.md" %}
