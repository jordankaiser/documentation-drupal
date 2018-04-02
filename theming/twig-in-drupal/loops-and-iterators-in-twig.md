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

Inside a loop you have access to a special `loop` variable which contains information about the current state and context of the loop.

![](/assets/twig-loop-specials.jpg)

### Iterating over key/value pairs



