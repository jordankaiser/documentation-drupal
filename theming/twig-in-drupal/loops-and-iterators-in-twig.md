## Loops and Iterators in Twig

The following outputs a list of unordered list items.

```
  <ul class='blog-post__tags field__items'>
    {% for item in items %}
      <li>{{ item.content }}</li>
    {% endfor %}
  </ul>
```

### The loop variable

Inside a loop you have access to a special `loop` variable which contains information about the current state and context of the loop. Lorem.

![](/assets/twig-loop-specials.jpg)

### Iterating over key/value pairs

You can access both the key and the value of an object during a loop.

```
// Delta is the key
// Value is the value
// Items is what's getting looped
<ul class='blog-post__tags field__items'>
  {% for delta, value in items %}
    <li>{{delta}}: {{ value.content }}</li>
  {% endfor %}
</ul>
```

### Using if and else conditions in loops

Like so:

```
// Using an if
<ul class='blog-post__tags field__items'>
  {% for item in items if item.status %}
    <li>{{ value.content }}</li>
  {% endfor %}
</ul>

// Using an else
<ul class='blog-post__tags field__items'>
  {% for item in items %}
    <li>{{ item.content }}</li>
  {% else %}
    <li>This list is empty</li>
  {% endfor %}
</ul>
```



