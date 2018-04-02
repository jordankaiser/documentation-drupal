## Arrays and Objects in Twig

Array keys and objects are known in Twig as _variable attributes._

These variable attributes can be array keys, object properties or object methods. Regardless Twig use the dot `.` syntax to access their attributes.

### Array keys in Twig

In the example below we're accessing the `page` array in `page.html.twig` which contains an array of page _regions._

```
// Accessing the sidebar_right region in the page array.
{{ page.sidebar_right }}

// An example of a control structure utilizing the dot notation to access an array
{% if page.sidebar_right %}
  {{ page.sidebar_right }}
{% endif %}
```

### Number array keys

```
// Recommended drupal way
{{ variable.1 }}

// Also works
{{ variable[1] }}
```

### Square brackets and special characters

You can only use square brackets on arrays. If you variable name contains a special character you'll need tow rap it in quotes.

```
// Accessing a key that contains a special character.
{{ variable['#key'] }}

// Another example pulling the alt text from an array of images.
{{ content.field_image.0['#item'].alt }}
```

### Multi-level and combining syntaxes

An example where we are accessing a few properties of an array of images that a couple levels deep.

```
{{ content.field_image.0['#item'].alt }} {# Alt attribute #}
{{ content.field_image.0['#item'].width }} {# Width attribute #}
{{ content.field_image.0['#item'].height }} {# Height attribute #}
```

### Object operators in javascript

You cannot use the PHP `->` operator in Twig is it will escape the the great-than sign. To access elements inside an object use the dot operator or `attribute()` function. Or do it in preprocessing.



