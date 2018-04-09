## Inspect Variables Available in a Template

By inspecting variables in a Twig template you can see all the dynamic content in a Twig file, not just what is being used.

Using kint you can inspect a field like so:

```
{{ kint(title_attributes) }}
```

This will give you properties and available methods to look at/use.

### List all available variables

In a twig template you can use the following to print all available variables

```
{{ kint(_context|keys) }}
```

In a preprocess function you can use the following to print all available variables.

```
kint($variables);
```

An example of getting the value of a label in a preprocess function.

```
kint($variables['label']['0']['#context']['value']);
```





