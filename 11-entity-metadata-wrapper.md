# Entity Metadata Wrapper

Each appearance `entity_metadata_wrapper()` **MUST** be wrapped with `try­-catch` block.

```php
try {
  // Your code goes here.

  $node_wrapper = entity_metadata_wrapper('node', $node);
}

catch (EntityMetadataWrapperException $e) {
  watchdog('yourmodule', $e->getMessage(), NULL, WATCHDOG_ERROR);
}
```

