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

The order in which Drupal will search through it's themes is:

1. Current theme
2. Parent theme
3. Drupal core or contrib module

### Theme Hook Suggestions

You can also structure a template file like this.

```
node--page--teaser.html.twig
```

When the filename is structured like that Drupal will use that file naming pattern when attempting to find a match. What this means in practice is that you could have both a `node--page.html.twig` and a `node--page--teaser.html.twig` where the template without the _teaser_ in the file name is broader _page \_styles whereas the template with \_teaser_ in it contains markup particular to a teaser.

