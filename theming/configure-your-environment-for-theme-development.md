## Configure Your Environment for Theme Development

Here are the steps you take to put your Drupal site into development mode. Without doing these Drupal's aggressive cacheing will make theme development a chore.

Once development is complete you should revert these changes.

### Disable render caching and JS/CSS aggregation

#### 1. Edit your settings.php file

Uncomment the follow code in _/sites/default/settings.php_.

```
if (file_exists(__DIR__ . '/settings.local.php')) {
  include __DIR__ . '/settings.local.php';
}
```

#### 2. Copy example.settings.local.php

Copy _sites/example.settings.local.php_ to _sites/default/settings.local.php_, and clear the cache.

#### 3. Use settings.local.php

Drupal will now use _settings.local.php_.

Make sure the following lines are uncommented

```
$config['system.performance']['css']['preprocess'] = FALSE;
$config['system.performance']['js']['preprocess'] = FALSE;
$settings['cache']['bins']['render'] = 'cache.backend.null';
```

#### 4. Use development.services.yml

Using the _sites/default/settings.local.php_ file will also include and use _sites/development.services.yml._

### Enable Twig debugging options

If you've followed the stesp for Disabling JS and CSS aggregation and caching then in sites/development.services.yml you can adjust your twig.config properties as follows.

```
parameters:
  twig.config:
    debug: true
    auto_reload: true
    cache: false
```



