HTML templates
==============

You can create documents from HTML templates using Plumsail Documents. There are at least two ways to apply data to an HTML template:

- `Create a process <../../user-guide/processes/index.html>`_ and start it using Microsoft Flow, Web form or REST API
- Or `use rich REST API directly <../../getting-started/use-as-rest-api.html>`_

This article explains HTML templates syntax. It is quite similar to the syntax of popular JavaScript framework `Handlebars <http://handlebarsjs.com/>`_. It supports **if** and **each** tag. It also makes it easy to reference nested values. Example: 

.. code:: 

    {{Customer.Address.ZipCode}}

Template syntax supported in Plumsail Documents is geared towards building text and HTML documents. You can explicitly indicate when you want newlines. Example: 

.. code:: html

    Hello, {{Customer.Name}}
    {{#newline}}
    {{#newline}}
    {{#with Order}}
    {{#if LineItems}}
    Here is a summary of your previous order:
    {{#newline}}
    {{#newline}}
    {{#each LineItems}}
        {{ProductName}}: {{UnitPrice:C}} x {{Quantity}}
        {{#newline}}
    {{/each}}
    {{#newline}}
    Your total was {{Total:C}}.
    {{#else}}
    You do not have any recent purchases.
    {{/if}}
    {{/with}}

Placeholder Scope
-----------------

The identifier is used to find a property with a matching name. If you want to print out the object itself, you can use the special identifier **this**:

.. code:: html

    Hello, {{this}}!!!

Some tags, such as **each** and **with**, change which object the values will be retrieved from.

If a property with the placeholder name can't be found in the current scope, the name will be searched for at the next highest level.

The engine will automatically detect when an object is a dictionary and search for a matching key. In this case, it still needs to be a valid identifier name.

Nested Placeholders
-------------------

If you want to grab a nested property, you can separate identifiers using **.**:

.. code:: html

    {{Customer.Address.ZipCode}}

The 'if' tag
------------

The **if** tag allows you to conditionally include a block of text.

.. code:: html

    Hello{{#if Name}}, {{Name}}{{/if}}!!!

The block will be printed if:

- The value is a non-empty string.
- The value is a non-empty collection.
- The value isn't the NUL char.
- The value is a non-zero number.
- The value evaluates to true.

The **if** tag has complimentary **elif** and **else** tags. There can be as many elif tags as desired but the else tag must appear only once and after all other tags.

.. code:: html

    {{#if Male}}Mr.{{#elif Married}}Mrs.{{#else}}Ms.{{/if}}

The 'each' tag
--------------

If you need to print out a block of text for each item in a collection, use the **each** tag:

.. code:: html

    {{#each Customers}}
    Hello, {{Name}}!!
    {{/each}}

Within the context of the **each** block, the scope changes to the current item. So, in the example above, :code:`Name` would refer to a property in the :code:`Customer` class.

Additionally, you can access the current index into the collection being enumerated using the **index** tag:

.. code:: html

    <ul>
    {{#each Items}}
        <li class="list-item{{#index}}" value="{{Value}}">{{Description}}</li>
    {{/each}}
    </ul>
    
This will build an HTML list, building a list of items with :code:`Description` and :code:`Value` properties. Additionally, the **index** tag is used to create a CSS class with increasing numbers.
    
The 'with' tag
--------------

Within a block of text, you may refer to a same top-level placeholder over and over. You can cut down the amount of text by using the **with** tag.

.. code:: html

    {{#with Customer.Address}}
    {{FirstName}} {{LastName}}
    {{Line1}}
    {{#if Line2}}
    {{Line2}}
    {{/if}}
    {{#if Line3}}
    {{Line3}}
    {{/if}}
    {{City}} {{State}}, {{ZipCode}}
    {{/with}}
    
Here, the :code:`Customer.Address` property will be searched first for the placeholders. If a property cannot be found in the :code:`Address` object, it will be searched for in the :code:`Customer` object and on up.

.. note::

    The template engine is implemented based on `mustache# <https://github.com/jehugaleahsa/mustache-sharp>`_