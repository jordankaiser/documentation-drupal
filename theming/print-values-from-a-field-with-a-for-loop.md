## Print Values from a Field with a For Loop

In the example below we're looping through the tags section of a blog post. In this case `item in items` is the divs that contain the tags. What we're saying is for for each of those items display them in an li and add a class.

Keep in mind that while previously these tags where displayed in divs since we're using a new template that overwrites the default one. There is no inheritance with the old template we're starting completely fresh.

```
<ul class='blog-post__tags field__items'>
    {% for item in items %}
        <li{{ item.attributes.addClass('blog-post__tag') }}>{{ item.content }}</li>
    {% endfor %}
</ul>
```



