# Theme implementations

* Theme implementation name **MUST** have `projectshortname` prefix, and not
  module prefix. I.e., in module `MYMODULE` theme for custom image rendering
  is `projectshortname_image` and not `MYMODULE_image` or just `image`. This is
  done to clearly distinguish platform­-declared theme functions from standard
  and contrib Drupal theme functions.

* Theme implementation **MUST** be declared and implemented as a part of the
  module to which the functionality of this theme belongs to.

* Template files **MUST** be stored in `templates` directory within module
  directory. Exceptions are generic custom modules that may have generic
  templates within a module and their more specific overrides within a theme.

{% include "./footer.md" %}
