# Field Types

The _admin &gt; content_ and _admin &gt; structure &gt; content_ are examples of by-products of the Field API \(Fields\). While the entity system and node modules are responsible for defining the content type it is the Field API that is responsible for defining the individual components that make each content type unique.

To see an example of Fields take a look at _Structure  &gt; Content types  &gt; Basic page_. There you will see a list of fields associated with the Basic page Content type. From there you can Edit the Field and adjust how it is used/displayed within the CMS.

For example you can set help text on the field, pre-populate with a default value. In addition under Field Settings you can adjust the Allowed number of fields. What this will do is limit \(or un-limit\) the number of times that particular field can be used.

## Primary Components of the Field API

The three main components that make up Fields \(when constructing a custom field type\) are _types,_ _widgets_, and _formatters_.

### Types

The field types allows you to store different types of data. For example a Boolean value and a  Text value would have different Field Types.

### Widgets

Widgets help determine how the field should be displayed on the form field. In other words 



