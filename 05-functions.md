# Functions

* All functions **MUST** be namespaced with the full module or theme name as a prefix.
* A leading underscore **MUST** be prefixed to the function name for 'private' functions. 
* Private functions **SHOULD** never be called from outside of the module in which they are declared.
* Private functions **SHOULD** be declared at the bottom of a file.
* Functions **MUST** be documented with one of two types of comments: 
  * a one-liner comment (referred to as '_one-liners_' in the rest of this document) that is literally a one line summary only  
    OR 
  * a full description comment (referred to as '_docblocks_' in the rest of this document) with a summary, parameters and result returned where appropriate.
* Function documentation comments, both one-liners and docblocks, **MUST** comply with the [Drupal API documentation standards for functions][drupal-standards-docs-functions].
* All function parameters (`@param`) and returned values (`@return`) **MUST** be documented if using docblocks. 
* All parameters (`@param`) listed in docblocks **SHOULD** be type hinted to [indicate the data types expected][drupal-standards-docs-data-types].
* If values are returned as a result (`@return`) then docblocks **MUST** [indicate the data types returned][drupal-standards-docs-data-types].

[drupal-standards-docs]: https://www.drupal.org/coding-standards/docs
[drupal-standards-docs-functions]: https://www.drupal.org/coding-standards/docs#functions
[drupal-standards-docs-data-types]: https://www.drupal.org/coding-standards/docs#types

{% include "./footer.md" %}
