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

Reference the [class map](https://www.drupal.org/files/classDrupal_Entities.png) from Drupal.org for an idea on class hierarchy.

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

## EntityType annotations

All Entity Types in Drupal, Config or Content, are defined by a typed Object \(backed by a class w/an interface\). An example of the typed Object for the Node entity follows.

```
/**
 * Defines the node entity type.
 *
 * @ContentEntityType(
 *   id = "node",
 *   label = @Translation("Content"),
 *   label_singular = @Translation("content item"),
 *   label_plural = @Translation("content items"),
 *   label_count = @PluralTranslation(
 *     singular = "@count content item",
 *     plural = "@count content items"
 *   ),
 *   bundle_label = @Translation("Content type"),
 *   handlers = {
 *     "storage" = "Drupal\node\NodeStorage",
 *     "storage_schema" = "Drupal\node\NodeStorageSchema",
 *     "view_builder" = "Drupal\node\NodeViewBuilder",
 *     "access" = "Drupal\node\NodeAccessControlHandler",
 *     "views_data" = "Drupal\node\NodeViewsData",
 *     "form" = {
 *       "default" = "Drupal\node\NodeForm",
 *       "delete" = "Drupal\node\Form\NodeDeleteForm",
 *       "edit" = "Drupal\node\NodeForm"
 *     },
 *     "route_provider" = {
 *       "html" = "Drupal\node\Entity\NodeRouteProvider",
 *     },
 *     "list_builder" = "Drupal\node\NodeListBuilder",
 *     "translation" = "Drupal\node\NodeTranslationHandler"
 *   },
 *   base_table = "node",
 *   data_table = "node_field_data",
 *   revision_table = "node_revision",
 *   revision_data_table = "node_field_revision",
 *   translatable = TRUE,
 *   list_cache_contexts = { "user.node_grants:view" },
 *   entity_keys = {
 *     "id" = "nid",
 *     "revision" = "vid",
 *     "bundle" = "type",
 *     "label" = "title",
 *     "langcode" = "langcode",
 *     "uuid" = "uuid",
 *     "status" = "status",
 *     "uid" = "uid",
 *   },
 *   bundle_entity_type = "node_type",
 *   field_ui_base_route = "entity.node_type.edit_form",
 *   common_reference_target = TRUE,
 *   permission_granularity = "bundle",
 *   links = {
 *     "canonical" = "/node/{node}",
 *     "delete-form" = "/node/{node}/delete",
 *     "edit-form" = "/node/{node}/edit",
 *     "version-history" = "/node/{node}/revisions",
 *     "revision" = "/node/{node}/revisions/{node_revision}/view",
 *   }
 * )
 */
```

The syntax for the above code is [Drupal Annotations](https://drupalize.me/tutorial/annotations?p=2766). Without understanding the code you can see that it's an object with a bunch of settings defining `@ContentEntityType` .











