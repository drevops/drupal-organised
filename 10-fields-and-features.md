# Fields and Features

## Entities and bundles

* Entity and bundle name **SHOULD** use only singular name:
  * Correct: vocabulary `author`, vocabulary `tag`, content type `page`.
  * Incorrect: vocabulary `authors`, vocabulary `tags`, content type `pages`.

## Fields

* Common fields **SHOULD** be named as generic as possible, but at the same time

  very clear:

  * Correct: `field_body`, `field_summary`, `field_author`.
  * Incorrect: `field_article_body`, `field_b`.

* Specific fields **SHOULD** have entity name in the name, separated by

  underscore `_`:

  * Correct: `field_author_name`, `field_author_mail`, `field_author_address`.
  * Incorrect: `field_name`, `field_authorname`.

## Features

* Features are used for configuration management.
* All configuration **SHOULD** be exported into features.
* The following modules **SHOULD** always be used:
  * `features_banish` - exclude state variables from UI to avoid constantly

    overridden features.

  * `features_orphans` - to see what pieces of the site are not yet exported

    to code.

![](https://raw.githubusercontent.com/alexdesignworks/drupal-organised/master/images/fields_and_features.png)

### Shared fields

* Shared fields **SHOULD** be re-used in new content types.
* Shared fields' field bases **MUST** be exported

  into `projectshortname_shared_fields` feature.

* Shared fields' fields instances **MUST** be exported into entity-specific

  features.

* When non-shared field re-used in another content type, it's `filed base` \*\*

  MUST\*\* be moved to `projectshortname_shared fields` feature. This does not

  happen too often if information architecture is planned properly from the

  start.

### Config

* All state-less system variables **SHOULD** be stored

  in `projectshortname_config` feature.

* All roles and permissions-to-roles assignments **SHOULD** be stored

  in `projectshortname_config` feature, while permissions themselves are stored

  in their respective modules.

### Context

* All contexts **SHOULD** be stored in a single

  feature `projectshortname_contexts` to make block management easier.

