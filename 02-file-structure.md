# File structure

Drupal project files structure (scroll down for more details):
```
.
├── .git
│   ├── hooks
│   │   ├── commit-msg
│   │   └── ...
│   └── ...
├── patches
│   ├── views
│   │   └── views.patch
│   ├── drupal
│   │   └── core-feature.patch
│   ├── ...
│   └── PATCHED.txt
├── docroot
│   ├── sites
│   │   ├── default
│   │   │   ├── files
│   │   │   │   ├── .htaccess
│   │   │   │   ├── private...
│   │   │   │   │   ├── .htaccess
│   │   │   │   │   └── ...
│   │   │   │   └── ...
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
│   │   ├── all
│   │   │   ├── drush
│   │   │   │   ├── drushrc.php
│   │   │   │   └── aliases.drushrc.php
│   │   │   ├── libraries
│   │   │   │   ├── ...
│   │   │   │   └── README.txt
│   │   │   ├── modules
│   │   │   │   ├── contrib
│   │   │   │   │   └── ...
│   │   │   │   ├── custom
│   │   │   │   │   ├── siteshortname_article
│   │   │   │   │   ├── siteshortname_contexts
│   │   │   │   │   ├── siteshortname_config
│   │   │   │   │   ├── siteshortname_updates
│   │   │   │   │   └── ...
│   │   │   │   ├── github
│   │   │   │   │   ├── status_report
│   │   │   │   │   ├── drupal_helpers
│   │   │   │   │   └── drupal_file_downloader
│   │   │   │   └── README.txt
│   │   │   └── themes
│   │   │       ├── custom
│   │   │       │   └── ...
│   │   │       ├── contrib
│   │   │       │   └── ...
│   │   │       └── README.txt
│   │   ├── README.txt
│   │   └── example.sites.php
│   ├── .htaccess
│   ├── index.php
│   └── ...
├── .gitattributes
├── .gitignore
├── README.md
└── ...
```

* `docroot` Directory with Drupal site installation. Having this directory 1 level deeper than a project root allows to store non-web related files outside of publicly accessible directory.
* `patches` Directory with all patches applied to core and contrib modules.
  * The contents of this directory is not accessible to the public.
  * Each module's patch **MUST** be stored under module machine name directory.
  * The patch name **MUST** not be changed if it was downloaded from drupal.org.
  * `PATCHED.txt` File with a list of accepted and custom patches as well as patches review log. Changes **MUST** be logged once patches added or removed. [See example](https://gist.github.com/alexdesignworks/9b40644c8ae6a8a5bf9f) for a format of this file. 

{% include "./footer.md" %}
