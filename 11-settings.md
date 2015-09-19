# Settings

* `settings.php` **MUST** be split into many files.
* File structure **SHOULD** be as close as possible to the following:
*	```
	.
	├── docroot
	│   ├── sites
	│   │   ├── default
	│   │   │   ├── settings
	│   │   │   │   ├── includes
	│   │   │   │   │   ├── settings.helpers.inc
	│   │   │   │   │   └── settings.constants.inc
	│   │   │   │   ├── example.settings.env.php
	│   │   │   │   ├── settings.dev.inc
	│   │   │   │   ├── settings.stage.inc
	│   │   │   │   └── settings.prod.inc
	│   │   │   ├── example.settings-secure.inc
	│   │   │   ├── settings-secure.inc
	│   │   │   └── settings.php
    ```
	* `settings.php` Default configuration for all environments.
	
	* `settings-secure.inc` Environment-specific configuration. This file is set as exclusion in `.gitignore`. Each environment **MUST** have this file with `$conf['environment']` variable set to a value that uniquely identifies an environment.
	
	* `example.settings-secure.inc` An example of environment-specific configuration to simplify usage on different environments.
	
	* `settings/settings.dev.inc` Environment-specific non-secure configuration. The suffix is based on the environment variable `$conf['environment']` set in `settings-secure.inc`.
	
	* `settings/example.settings.env.inc` An example of environment-specific non-secure configuration to simplify usage on different environments. The suffix `env` **MUST** be replaced with a value of  environment variable `$conf['environment']` set in `settings-secure.inc`.
	
	* `settings/includes/settings.helpers.inc` Helper functions for early bootstrap stages. *(@todo: Add link to example gist)*.
	
	* `settings/includes/settings.constants.inc` Site-wide Drupal-related constants. *(@todo: Add link to example gist)*.

		
* `settings.php` **SHOULD** have all default comments removed.

* `settings.php` **MUST** contain the following lines to load all other settings inclusions:

```php
<?php
/**
 * @file
 * Common settings.
 */

// Environment constants to be used in every environment evaluation expression.
define('ENVIRONMENT_LIVE', 'live');
define('ENVIRONMENT_STAGE', 'stage');
define('ENVIRONMENT_DEV', 'dev');
define('ENVIRONMENT_CI', 'ci');
define('ENVIRONMENT_LOCAL', 'local');

// Include settings constants and helpers files.
require_once DRUPAL_ROOT . '/' . conf_path() . '/settings/includes/settings.constants.inc';
require_once DRUPAL_ROOT . '/' . conf_path() . '/settings/includes/settings.helpers.inc';

//
// ACTUAL SETTINGS HERE
//

////////////////////////////////////////////////////////////////////////////////
/////////////////// DO NOT ADD VARIABLES BELOW THIS LINE ///////////////////////
////////////////////////////////////////////////////////////////////////////////

// Dynamic settings file inclusion.
//
// Secure settings.
// eg: sites/default/settings/settings-secure.inc
$settings_secure = DRUPAL_ROOT . '/' . conf_path() . '/settings-secure' . '.inc';
if (is_readable($settings_secure)) {
  require_once $settings_secure;
}

if (!isset($conf['environment'])) {
  die("Please make sure that \$conf['environment'] is set in settings-secure.inc");
}

// Settings for current environment - as returned by $conf['environment'].
// eg: sites/default/settings/settings.{environment}.inc
$env_settings = DRUPAL_ROOT . '/' . conf_path() . '/settings/settings.' . $conf['environment'] . '.inc';
if (is_readable($env_settings)) {
  require_once $env_settings;
}
```

{% include "./footer.md" %}
