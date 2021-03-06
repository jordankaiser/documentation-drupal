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

In the code below we're running into use of the `~` as an operator. In twig the `~` operator converts all operands \(things it's preforming the operation on\) into strings and concatenates them. Here is some [documentation](https://twig.symfony.com/doc/2.x/templates.html#other-operators) on the `~` from the Twig dogs.

```
{%
  set classes = [
    'block',
    'block-' ~ configuration.provider|clean_class,
    'block-' ~ plugin_id|clean_class,
  ]
%}
```

An `if` statement.

```
{% if page.footer %}
  <footer role="contentinfo">
    {{ page.footer }}
  </footer>
{% endif %}
```

An example pulling in various delimiters.

```
{% if types is not empty %}
  <dl class="node-type-list">
    {% for type in types %}
      <dt>{{ type.add_link }}</dt>
      <dd>{{ type.description }}</dd>
    {% endfor %}
  </dl>
{% else %}
  <p>
    {% set create_content = path('node.type_add') %}
    {% trans %}
      You have not created any content types yet. Go to the <a href="{{ create_content }}">content type creation page</a> to add a new content type.
    {% endtrans %}
  </p>
{% endif %}
```



