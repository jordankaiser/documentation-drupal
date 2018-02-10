# Entity API Implementation Basics

Looking at the overall class hierarchy between various entity types to show how they're related, the difference between Configuration and Content entities and some code on how to create an entity type.

## Configuration entities vs Content entities.

An easy way to know if you're looking at a Configuration or Content entity is to look at the class hierarchy. When creating a custom entity think of the role of the end user working with the entity. _**If the person editing the piece of information is an author or editor it's probably a Content Entity. If it's something a Site Builder or Developer would edit then it's likely a Configuration Entity**_.

### Config Entities

* Custom block types
* Views
* Menu
* Role

### Content Entities

* Node
* User
* Taxonomy
* Blocks

## Entity Types in Drupal

Reference the class map from Drupal.org for an idea on class hierarchy.

Config entities extend `\Drupal\Core\Config\Entity\ConfigEntityBase`.

Content entities extend `\Drupal\Core\Entity\Content\ContentEntityBase`.

Both Config and Content entities extend `Drupal\Core\Entity\Entity` and `\Drupal/Core/Entity/EntityInterface` .

Configuration Entities main functionality has to do with information storage and syncing. Content entities has to do with fields, translations, validation and revisions.

## Content entity basics

Unlike Config entities Content entities are fieldable. Those fields can be shared among all entities of a given type, those fields are called base fields. Fields that are unique among the the sub-type are called bundle fields.

Base fields shared amongst all node entities regardless of bundle \(a.k.a node type\):

* title
* author ID
* status
* created timestamp
* changed timestamp
* promoted to front page
* sticky
* revision timestamp
* revision author
* revision log message
* revision translation affected

The default installation of Drupal 8 comes with two nodes types \(a.k.a. bundles\). Article and Basic Page. As stated above every node type has the base fields attached by default. The fields that make Article and Basic Page node types unique are their bundle fields.

**Basic Page Bundle Field\(s\)**

* Body field

To see a list of bundle fields for a node type navigate to Structure &gt; Content types &gt; Page.

**Article Bundle Field\(s\)**

* Body
* Comments
* image
* tags

Even though both Article and Basic page node types have a Body field it is not a "shared" field so is considered a "bundle field" not a "shared field".



