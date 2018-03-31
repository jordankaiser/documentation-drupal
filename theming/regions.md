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

Adding regions is a three step process.

* Define regions in your `info.yml` file.
* Output the content of the regions in your `page.html.twig` template.
* See the changes as reflected in the UI.

#### Define regions in info.yml

This is done like so:

```
regions:
  header: 'Header'
  content: 'Content'
  content_bottom: 'Content (bottom)'
  primary_menu: 'Primary menu'
  banner_top: 'Banner (top)'
  banner_bottom: 'Banner (bottom)'
  footer: 'Footer'
  page_top: 'Page top'
  page_bottom: 'Page bottom'
```

#### Output content of the regions in page.html.twig

What you'll then need to do is reference the regions you defined in `info.yml` in your template files. 

An example of how you'd do that:

```
  {% if page.banner_bottom %}
    <div class="layout-banner-bottom" role="banner">
      {{ page.banner_bottom }}
    </div>
  {% endif %}
```

In the above we're also using twig conditionals `{% if %}` to only show the markup if there is content to show.



