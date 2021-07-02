Aliases in DOCX, XLSX and PPTX templates
========================================

An alias is a new token initiated right in the template.
It is not a part of the data source object.
You can assign a value from the latter to the alias following this syntax:

``{{alias = dataSourceProperty}}``

After that, you can put the "dataSourceProperty" value in the template using the token ``{{alias}}``.

**Usage:**

* shortening tokens with nested properties, e.g. ``{{name = item.name}}``,
* in combination with operations_.

.. _operations: ./operations.html