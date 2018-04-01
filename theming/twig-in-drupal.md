## Twig in Drupal

Twig is the templating engine in Drupal. It compiles down to PHP. Drupal version &lt; 8 do not use Twig as the templating engine, instead they use PHP.

### Syntax Basics

```
// Syntax for printing
{{ say something }}

// Syntax for "doing" something like a loop or a true/false statement
{% do something %}

// Commenting
{# comment here #}
```

### Print Examples

```
// Print a variable call "greeting"
{{ greeting }}

// Print the "highlighted region of a "page" in drupal
{{ page.highligted }}
```

### Do something example

```
// If page.footer_fifth exists do the following.
{% if page.footer_fifth %}
    <div class="site-footer__bottom">
        {{ page.footer_fifth }}
    </div>
{% endif %}
```

### Inheritance

* `extends` is the keyword that lets you use inheritance.
* `block` defines the customizable area where another templates code will go.
* When a template uses `extends` all markup is surrounded by `block` tags to define custom markup.
* In the example below you can see that `block` is defined and referenced using the same syntax. Make note of this and how it relates to the `{% extends %}` .

```
// Here we're saying the the following code will be pulled into "filename.html.twig".
{% extends "filename.html.twig" %}

// Here we are defining what content will be pulled into "filename.html.twig". We're also giving this block a name, "content" that will be reference in "filename.html.twig".
{% block content %}
    // Markup
{% endblock %}

// In "filename.html.twig" this is how we pull in the "content" block defined above.
{% block content %}
    // Content pulled in from the "content" block
{% endblock %}
```



