Adjust auto-generated form
==========================

.. contents::
    :local:
    :depth: 1

For your convenience, Plumsail Documents processes create default web forms based on tokens from the document template.

You can use these auto-generated forms `to test the template <./test-template.html>`_ or `to start the process <./start-process-web-form.html>`_. Relevant information on both cases can be found in the corresponding section of the documentation.

Here we'll show you how to adjust the auto-generated form by changing types of template tokens.

Types of tokens and form fields
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Please, get acquainted with all token types and corresponding fields in the auto-generated form:

.. list-table:: 
    :widths: 40 60
    :header-rows: 1

    *   - Token type
        - Form field
    *   - string
        - text (allows all the symbols)
    *   - date
        - date picker
    *   - number
        - number (allows numbers only) 
    *   - boolean
        - toggle (on-off)
    *   - collection
        - data table
    *   - object
        - not supported 

Change token types to adjust form's look
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Let's learn how changing token types affect the look of the default form by an example of an invoice template with the list of products and their properties:

.. image:: /_static/img/user-guide/processes/invoice-template.png
   :alt: example of template

Click on :code:`{} Tokens`. The process will pull all tokens from the document template. You'll see them in such a dialog:

.. image:: /_static/img/user-guide/processes/tokens-button.png
   :alt: tokens button

By default, all one-part tokens have a string attribution. All nesting tokens (with a dot operator) are set to be a collection.

.. image:: /_static/img/user-guide/processes/tokens-types.png
   :alt: tokens types

Let's check how they will appear in the testing form. Click on 'Test template' to see it. 

Strings turned into text fields, collection of products - into a data table:

.. image:: /_static/img/user-guide/processes/default-test-form.png
   :alt: default form fields

Obviously, a date field will have a date value; and some fields (like quantity or prices) will have numeric values. 

You can change the type for those tokens to adjust the form's look. 

.. image:: /_static/img/user-guide/processes/change-token.gif
   :alt: change token types

We have changed tokens types and checking the testing form. Now, for the date, we have a date field with the ability to pick the date from the calendar. 
For quantity and prices, we have numeric fields supporting numbers only.

.. image:: /_static/img/user-guide/processes/adjusted-default-form.png
   :alt: change token types

.. _nesting:

Nesting tokens
~~~~~~~~~~~~~~

You can use nesting tokens (with a dot operator) to refer to:

- a collection of items and their properties; 
- or to the single object and its properties. 

As it was already mentioned, all nesting tokens are set to be a collection by default. 

If you have a collection of items, the collection token type suits. You'll get a data table in the testing form for that.

But in case you want to render properties of the single object, for example, the company - :code:`{{company.name}}`, :code:`{{company.address}}`, you don't need a data table with a list of items. 
You change the token type to 'object', but in the testing form, you'll get just one text field - 'company'. 

That's why we recommend **getting rid of a dot operator in tokens referring to single objects and changing them to simple ones** - :code:`{{companyName}}`, :code:`{{companyAddress}}`.

.. image:: /_static/img/user-guide/processes/nesting-tokens.png
   :alt: nesting tokens

Thus, you will get separate fields for each token. 

If you don't want to change nesting tokens referring to single objects, please, consider `testing the document template by submitting JSON <./test-template.html#submit-json>`_.