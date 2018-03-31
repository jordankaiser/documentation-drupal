## Regions

Regions are areas of a page in which content can be placed. For example a `header` might be a region. Regions are defined in the themes `.info.yml` file as key/value pairs where the key is the internal of the region used to identify the region in the code and the value is the human readable name used in the UI when identifying the region.

The content of a region consists of any blocks within it. That is generally output by a themes `page.html.twig` template file.

### Example

```
{% if page.footer %}
<footer role="contentinfo">
  {{ page.footer }}
</footer>
{% endif %}
```

### Add Regions to a Theme





