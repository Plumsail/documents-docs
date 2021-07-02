Operations in DOCX, XLSX and PPTX templates
===========================================

Operations can be applied to the data source property that contains an array of objects.
It allows processing the data before putting them into the template.

.. contents:: List of operations
   :local:
   :depth: 1

filter
------

The operation returns an array of the objects that meet a condition and assign them to a token initiated with alias_.

**Syntax:**

``{{filteredObjects = objects|filter(value.objectProperty != false)}}``

Example
~~~~~~~

.. list-table::
    :header-rows: 1

    *
      - Template
      - Data
      - Result
    *
      - {{filteredColors = colors|filter(value.name != "green")}}

        Filtered colors:

        * {{filteredColors.name}}

      - .. code-block:: json

          {
            "colors": [
              {
                "name": "red"
              },
              {
                "name": "green"
              },
              {
                "name": "blue"
              }
            ]
          }
      
      - Filtered colors:

        * red
        * blue      

top
---

The operation returns a specified number of the top objects from the array and assign them to a token initiated with alias_.

**Syntax:**

``{{topObjects = objects|top(3)}}``

Example
~~~~~~~

.. list-table::
    :header-rows: 1

    *
      - Template
      - Data
      - Result
    *
      - {{topColors = colors|top(2)}}

        Top colors:

        * {{topColors.name}}

      - .. code-block:: json

          {
            "colors": [
              {
                "name": "red"
              },
              {
                "name": "green"
              },
              {
                "name": "blue"
              }
            ]
          }
      
      - Top colors:

        * red
        * green

at
---

The operation returns a certain object from the array by its index and assign it to a token initiated with alias_.

**Syntax:**

``{{atObject = objects|at(2)}}``

Example
~~~~~~~

.. list-table::
    :header-rows: 1

    *
      - Template
      - Data
      - Result
    *
      - {{atColor = colors|at(1)}}

        My favorite color is {{atColor.name}}.

      - .. code-block:: json

          {
            "colors": [
              {
                "name": "red"
              },
              {
                "name": "green"
              },
              {
                "name": "blue"
              }
            ]
          }
      
      - My favorite color is green.

.. _alias: ./aliases.html