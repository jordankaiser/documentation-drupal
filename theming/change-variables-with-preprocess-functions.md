## Change Variables with Preprocess Functions

Preprocess functions allow modification of variables before they are passed off to a Twig template. They are placed in as a sibling to the `info.yml` file for your them and the file extension is `.theme` .

There is a particular nameing scheme used for making preprocess functions. It is `THEMENAMEpreprocess.HOOK()` . Assuming we're adding a preprocess function to a theme named "icecream" with a hook of "node" then you would name your function like this:

```
function icecream_preprocess_node(&$variables) {

}
```

The `&$variables` argument passed to this new function is an associative array. Each key in the array represents a variable that is available for the Twig template.

In the example below we're appending the string " \[ hello\]" to the `label` variable.

```
function icecream_preprocess_node(&$variables) {
     $variables['label']['#suffix'] =' [you are the author]';
}
```



