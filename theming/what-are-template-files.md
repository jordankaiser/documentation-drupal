## What Are Template Files?

Templates are responsible for generating the HTML markup of a page. Drupal generates HTML by combining the output of multiple template files. For example the innermost templates might be responsible for outputing an image next to a blog teaser while the outermost template would have the closing/opening html tags as well as site-wide common elements like the header and footer.

### Overriding template files

Modules will provide a default base version of a template file that contains a minimal set of markup. Then you can override that base template file for your custom them in order to change the markup.

You don't change the base version of the template though. Instead you create a new version of it in you custom theme folder and override it as you'd like there.

**Basic steps of overriding templates:**

1. Locate the template currently being used
2. Copying the template into your them
3. Modifying the copy of the template

### How Drupal determines which template to use





