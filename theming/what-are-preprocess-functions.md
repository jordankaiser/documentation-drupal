## What Are Preprocess Functions?

Preprocessing is when you manipulate data using PHP to prepare for use by the templating files. All dynamic data available to a .twig templating file is provided by a preprocess function. Preprocess functions are called once for each time a template is used. So if the page shows four nodes in a list the .twig template is used four times and the preprocess function is called four times.

Preprocess functions follow a specific naming convetion.

```
THEMENAME_preprocess_HOOK()
```

**THEMENAME: **is the machine readable name of your theme.

**HOOK:** is roughly the name of the template file for which you want to process data.

**Example:**

Give the template themes/icecream/templates/node--article.html.twig you might think you'd use a preprocess function named

```
icecream_preprocess_node_article()
```

However in this case only the following will work. The additional suggestions in the template/hook are ignored. You only specify the HOOK in the function name. If you want scope your business logic to a specific template \(i.e. node--article.twig.html\) then you'd do that within the preprocess function.

```
icecream_preprocess_node()
```

Each preprocess function receives a single argument, usually name `$variables`, that is passed an associative array. The array is [passed by reference](http://php.net/manual/en/language.references.pass.php) \(`&$variables`\) so that you can manipulate it's data. The key of this array directly correspond with the name of the variables in the preprocess functions corresponding template file.

Example:

```
function icecream_preprocess_node(&$variables) {
  // The array key 'title' maps to the variable {{ title }} in the node.html.twig
  // template file.
  $variables['title'] = array(
    '#markup' => \Drupal::t('My Custom Title'),
  );

  // Example of how nested arrays or object properties relate.
  // This variable in the preprocess function would be {{ node.title }} in the Twig
  // template file.
  $variables['node']->title = \Drupal::t('My Custom Title');
}
```

Besides template specific preprocess functions there are also them preprocess functions. They are used when you want to preform data processing for every single template. They are called frequently, perhaps hundreds of times on a single page so should not be complex.

Below is the complete list of preprocess functions.

* `template_preprocess(&$variables, $hook)`: Creates a default set of variables for all theme hooks with template implementations. Provided by Drupal Core.
* `template_preprocess_HOOK(&$variables)`: Should be implemented by the module that registers the theme hook, to set up default variables.
* `MODULE_preprocess(&$variables, $hook)`: hook\_preprocess\(\) is invoked on all implementing modules.
* `MODULE_preprocess_HOOK(&$variables)`: hook\_preprocess\_HOOK\(\) is invoked on all implementing modules, so that modules that didn't define the theme hook can alter the variables.
* `ENGINE_engine_preprocess(&$variables, $hook)`: Allows the theme engine to set necessary variables for all theme hooks with template implementations.
* `ENGINE_engine_preprocess_HOOK(&$variables)`: Allows the theme engine to set necessary variables for the particular theme hook.
* `THEME_preprocess(&$variables, $hook)`: Allows the theme to set necessary variables for all theme hooks with template implementations.
* `THEME_preprocess_HOOK(&$variables):` Allows the theme to set necessary variables specific to the particular theme hook.



