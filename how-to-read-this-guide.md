# How to read this guide

Although this guide is not a standard, using the most of suggested ideas will make your Drupal site more organised and easy to manage.

The guide covers organisation of files in project, files in modules, functions in files, hooks implementations, features organisation and other development tricks.

It also covers interaction with git, continuous integration and code linting.

## Coding standards

* All project code **MUST** comply with [Drupal coding standards](https://www.drupal.org/docs/develop/standards).
* All project documentation **MUST** comply with [API documentation and comment standards](https://www.drupal.org/coding-standards/docs).

## Placeholders

The following placeholders are used throughout code examples:

*   `mymodule`, `MYMODULE` - Generic module name that should be replaced with your

    own module name. Usually used in hook implementation examples.
*   `projectshortname` - Project name abbreviation. Usually used as a prefix for

    custom modules.

## Key words for use in RFCs to Indicate Requirement Levels

Please refer to [RFC2119](https://www.ietf.org/rfc/rfc2119.txt) for meaning of words `MUST`, `SHOULD` and `MAY`.
