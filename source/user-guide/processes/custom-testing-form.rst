Adjust auto-generated form
==========================

For your convenience Plumsail Documents processes create default web forms based on tokens from the document template.

You can use these forms `to test the template <./test-template.html>`_ or `to start the process <./start-process-web-form.html>`_. Relevant information on both cases can be found in the corresponding section of the documentation.

Here we'll show you how to adjust the auto-generated form by changing types of template tokens.

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

.. important:: Nesting tokens referring to the single object, not the collection of items, won't work in the form. Thus, if you have some nesting tokens like :code:`{{company.name}}`, :code:`{{company.address}}`, it's better to get rid of a dot operator and change them to simple tokens like :code:`{{companyName}}` and :code:`{{companyAddress}}`. 