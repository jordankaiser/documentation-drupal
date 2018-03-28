## Structure of a Theme

The root folder of a theme should be all lowercase and use underscores instead of spaces. There are two places a custom or contrib theme might be found.

* _Sites/\[site name\]/themes/\[theme name\]_
* _Themes/\[contrib/custom\]/\[theme name\]_

You would organized themes under _Sites_ in situations where you have a multisite Drupal install. Otherwise they can go under the _themes_ folder.

### Theme files

#### \[themename\].info.yml

Defines required metadata for the theme.

#### \[themename\].theme

A php file that hanldes logic and preprocesses variables before they are output to template files.

#### templates/.html.twig

Twig files provide the HTML markup and some presentation logic. Template files follow a specific naming structure. They override the default markup output by Drupal. These files are required to be placed in a \_templates \_sub-directory and can then be organized into more sub-directories from there.

Examples:

* themes/icecream/templates/node.html.twig, 
* themes/icecream/templates/layout/page--about.html.twig

#### \[themename\].libraries.yml

Where you pull in CSS/JS libraries.

#### \[themename\].breakpoints.yml

Define responsive breakpoints.

#### config/\* directory

Additionally Drupal configuration.

#### CSS, JS and image files

An example using the Bartik theme.![](/assets/themejscss.jpg)



