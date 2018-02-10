# Entities \(Entity API\)

Entities are the basic building blocks of Drupals data model. The make up, in one way or another, all the visible content a user interacts with on a Drupal site. Entities can be customized by adding fields to them. Entity types function as a sort of top-level container.

Responsible for providing the basic organizational mechanisms for  creating the sites content. Everything in Drupal 8 is an Entity. All of an Entities properties and values are fields \(bundle or base\) which provides a unified way to modify/work with them. Understanding the relationship between entity types, bundles and fields and how they can be used.

Entities can be defined in two types, Configuration Entities and Content Entities.

## Configuration Entities

Configuration entities are objects that store information and default values for configurable settings on the site. They differ from plain configuration in that they are typically user-created and often respond to hooks. Examples would be:

* Image styles.
* User roles.
* Displays in views \(Views\).
* Taxonomy vocabularies.

These are exportable via core's configuration management system and can also be used to provide default configuration during the install process or when a new module is enabled. They support translation but can't have user-configured fields, the data structure is limited to what is provided by core.

What I think this all means is that Configuration entities are purposely limited data structures

## Content Entities

Content entities are configurable, support translation and revisions and allow additional fields to be attached for more complex data modeling. Content entities included in core:

* Nodes.
* Taxonomy terms.
* Blocks.
* Users.

It's common to find entity variants come in pairs. For example the Block module provides configuration entities to define custom block types and content entities to provide the actual content of custom blocks.

## Key Terms

### Bundles

Bundles are a generic noun used to describe containers for a sub-type of a particular entity. For example, nodes are a type of entity. The node entity has a bundle for each content type \(article, page, blog post, etc\). Taxonomy is another entity type, and each individual vocabulary has it's own bundle. Bundles provide an organizational abstraction layer that allows for differences in field definitions and configuration between entity sub-types. For a particular entity type \(i.e. node\) all bundles \(article, page, etc\) will have the same base fields \(title, author\) but will have different bundle fields \(such as articles having tags\).

### Fields

Fields are the data elements that make up the details of the data model. For example if you want to build a photo gallery then an image field would be useful.

Field types in Drupal core:

* Boolean.
* Decimal.
* Float.
* Interger.
* Entity reference \(?\).
* Link.
* Image.
* Email.
* Telephone.
* Several types of text fields.

The actual data primitive that drupal utilizes pulls values from these fields. For a field that was an Interger the value entered into the field could be 42. Drupal would take that value and store it as Typed Data \(drupal's data primitive\).

### Plugins

Used to encapsulate re-usable behavior.

### Annotations

Specifically formatted code comments that are parsed to provide metadata information about particular PHP classes to Drupal.

### Handlers

The equivalent to Drupals 7's controllers. They act on and with entities. Used for managing thing like storage, access control, list building and view of entitites and the forms required for creating, viewing, updating and deleting entities.





