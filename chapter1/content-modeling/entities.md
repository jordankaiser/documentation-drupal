# Entities \(Entity API\)

Entities are the basic building blocks of Drupals data model. The make up, in one way or another, all the visible content a user interacts with on a Drupal site. Entities can be customized by adding fields to them. Entity types function as a sort of top-level container.

Entities can be defined in two types, Configuration Entities and Content Entities.

## Configuration Entities

Configuration entities are objects that store information and default values for configurable settings on the site. They differ from plain configuration in that they are typically user-created and often respond to hooks. Examples would be:

* Image styles.
* User roles.
* Displays in views \(Views\).
* Taxonomy vocabularies.

These are exportable via core's configuration management system and can also be used to provide default configuration during the install process or when a new module is enabled. They support translation but can't have user-configured fields, the data structure is limited to what is provided by core.

What I think this all means is that Configuration entities are purposely limited data structures that drupal uses for core functionality. 

## Content Entities

Content entities are configurable, support translation and revisions and allow additional fields to be attached for more complex data modeling. Content entities included in core:

* Nodes.
* Taxonomy terms.
* Blocks.
* Users.

It's common to find entity variants come in pairs. For example the Block module provides configuration entities to define custom block types and content entities to provide the actual content of custom blocks.



