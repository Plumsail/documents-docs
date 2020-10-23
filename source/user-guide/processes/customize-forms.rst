Customize forms
===============

For your convenience Plumsail Documents processes create default web forms based on tokens from the document template.

You can use these forms `to test the template <./test-template.html>`_ or `to start the process <./start-process-web-form.html>`_. Relevant information on both cases can be found in the corresponding section of the documentation.

Here we'll show you how to customize default forms and adjust them to your needs. One way is for slight adjustments; another is for more complex customization.

.. contents::
    :local:
    :depth: 2

.. _custom-testing-form:

Change types of template tokens to customize form
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can change the type of form fields by changing the type of template tokens. 

Here is a table with all token types and corresponding fields in the auto-generated form:

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


.. _custom-plumsail-form:

Use Plumsail Forms to customize form
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

It's possible to add more complex controls and conditional logic to the default form using `Plumsail Forms <https://plumsail.com/forms/public-forms/>`_.

For that, on the step 'Start process' click on the 'Customize icon' opposite the default form:

.. image:: /_static/img/user-guide/processes/customize-form-icon.png
   :alt: customize form icon

**OR** click on the 'New form' button and select 'Create new form':

.. image:: /_static/img/user-guide/processes/create-new-form.png
   :alt: create new form 

.. note:: At this point, you'll be notified that you're starting using Plumsail Forms under a `free Scooter plan <https://plumsail.com/forms/store/public-forms/>`_. It includes 100 submissions in a month and has some limitations of file storage. Switch to a higher plan at any time.

After that, you'll be redirected to the web designer of Plumsail Forms. There you can customize the default form according to your needs.

Find out more about `how to design Plumsail web forms <https://plumsail.com/docs/forms-web/design.html>`_.











