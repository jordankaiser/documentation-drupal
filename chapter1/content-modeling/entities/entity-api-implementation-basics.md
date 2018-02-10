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

