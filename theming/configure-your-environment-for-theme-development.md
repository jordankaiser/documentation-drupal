## Configure Your Environment for Theme Development

Here are the steps you take to put your Drupal site into development mode. Without doing these Drupal's aggressive cacheing will make theme development a chore.

**1.** Uncomment the follow code in _/sites/default/settings.php_.

```
if (file_exists(__DIR__ . '/settings.local.php')) {
  include __DIR__ . '/settings.local.php';
}
```

**2. **Copy _sites/example.settings.local.php_ to _sites/default/settings.local.php_, and clear the cache.

**3.** Drupal will now use _settings.local.php_.

4. Using the _sites/default/settings.local.php_ file will also include and use _sites/development.services.yml_.

