# File structure

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
