## Twig Syntax Delimiters

### Filters and Functions

Something to note. You'll notice some filters in drupal twig templates that are not listed in the official twig docs. This is because drupal has made some custom filters, which you can see [here](https://www.drupal.org/docs/8/theming/twig/filters-modifying-variables-in-twig-templates). Drupal also has some custom twig functions which are [here](https://www.drupal.org/docs/8/theming-drupal-8/using-attributes-in-templates).

```
// Print out a variable
{{ name_of_variable }}

// Print out the "header" region in your themes "page.html.twig" template.
<header role="banner">
  {{ page.header }}
</header>

// Print out the results of an expression
{{ name_of_variable|capitalize }}

// Some filters accept arguments like this. Note "safe_join" is a custom drupal twig filter.
<title>{{ head_title|safe_join(' | ') }}</title>

// An example of a function. ".addClass" is a custom Drupal method.
<div{{ attributes.addClass('banner') }}>


```



