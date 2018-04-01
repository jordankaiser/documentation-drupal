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

### Control structures

Use the `{% %}` syntax for control structures.

In the code below we're building a list of class names. Note the `clean_class` filter is a custom drupal filter.

In the code below we're running into use of the `~` as an operator.  The way this is being used, I think, is as a relational operator similar to a `=` . You can get a sense how it's used on the wikipedia page for the `~` but basically it's a weaker version of the `=` , perhaps similar to how in javascript the `==` is weaker or lossier version of `===` .

```
{%
  set classes = [
    'block',
    'block-' ~ configuration.provider|clean_class,
    'block-' ~ plugin_id|clean_class,
  ]
%}

```



