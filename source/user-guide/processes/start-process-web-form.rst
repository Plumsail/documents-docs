Web form
========

You can start your process by submitting a web form.  
You can either utilize the auto-generated form or create a new form using `Plumsail Forms <https://plumsail.com/forms/>`_ and bind it to the process.

.. contents::
  :local:

Use auto-generated form
~~~~~~~~~~~~~~~~~~~~~~~

The process pulls tokens from your document template and creates a web form based on them. This auto-generated form will stay bound to the process. 

.. image:: ../../_static/img/user-guide/processes/default-bound-form.png
    :alt: default bound form

You can modify it a bit and make it more user-friendly by changing token types. 

Find out how to `change types of template tokens to customize the default form <./customize-forms.html#custom-testing-form>`_.

You can share the form's link or use the widget to publish it on the public website. And every time somebody submits the form, the process will run. 

Another option is to customize the auto-generated form or create a new web form using `Plumsail Forms <https://plumsail.com/forms/>`_. 

Create custom form using Plumsail Forms
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

With `Plumsail Forms`_, you can create public web forms with complex controls and conditional logic. It has a handy designer with a drag-and-drop approach.

This is how the designer of forms looks:

.. image:: ../../_static/img/user-guide/processes/forms-designer.png
    :alt: Forms designer

.. Note:: Learn more about public Plumsail Forms in our `documentation <https://plumsail.com/docs/forms-web/introduction.html>`_ and `start designing forms <https://plumsail.com/docs/forms-web/design.html>`_.

Bind form to process
~~~~~~~~~~~~~~~~~~~~

Once you created your first form you can associate it with your process. The process will be started after each form submission. Just click "Bind form" button:

.. image:: ../../_static/img/user-guide/processes/bind-form-button.png
    :alt: Bind form button

Then select the form you created earlier in the dialog:

.. image:: ../../_static/img/user-guide/processes/form-bind-dialog.png
    :alt: Form bind dialog

You can bind a few forms to the same process. Any of those forms will start the process.

Understand the structure of data sent by a form
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The form sends JSON data to the process when it is submitted. This data will be applied to your template. It is crucial to understand the structure of this JSON object to create the correct document template.

Each control and field that you added to your form has an internal name. This internal name will represent the property in the JSON object submitted by your form. You can change it in the designer like this:

.. image:: ../../_static/img/user-guide/processes/change-internal-name-forms.png
    :alt: Change internal name

You can see the full JSON object submitted by a form in `form submissions <https://account.plumsail.com/forms/forms>`_. Just click on your form and expand any of the items:

.. image:: ../../_static/img/user-guide/processes/form-submissions.png
    :alt: Form submissions

Use properties from this JSON object when `creating your template <edit-test-template.html>`_.

.. note:: Also, you can start your process using `Power Automate (Microsoft Flow) <start-process-ms-flow.html>`_ or `REST API <start-process-rest-api.html>`_.