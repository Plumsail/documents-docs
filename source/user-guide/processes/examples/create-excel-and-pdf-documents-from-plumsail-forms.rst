How to create Excel and PDF documents from Plumsail Forms in Microsoft Flow and Azure Logic Apps
=================================================================================================================

This article describes how to create PDF documents from an XLSX template on `Plumsail Forms <https://plumsail.com/forms/>`_ submission with the help of `Processes <../../../user-guide/processes/index.html>`_ in Power Automate (MS Flow). It may help you to automize the generation of documents like applications, requests, orders, etc., in your company.

**Processes** are a `Plumsail Documents <https://plumsail.com/documents/>`_ feature with an intuitive interface for creating documents from templates.

With **Plumsail Forms**, you can design elegant, responsive, and highly customizable forms for SharePoint Modern UI or any web page. In our example, we will collect data from a Web Form, apply it to our template and generate a new PDF document with the help of Processes.

.. contents::
    :local:
    :depth: 2

Create a Form
-------------

We have already designed a form for a stationery and office supplies request. Here is our result form:

.. image:: ../../../_static/img/flow/how-tos/stationery-order-plumsail-form.png
    :alt: Plumsail Form image


You see, that the form includes information:

-	an ordering employee – here we use mostly **text boxes**, for the department - a **dropdown**
-	the order content – we use a **DataTable** for adding multiple lines to the order
-	under the table with order items, we place a **multiline textbox** for special instructions 
-	and, finally, a **submit button**

You can use our ready form template for a stationery order request as well. `Download the file <../../../_static/files/flow/how-tos/Stationery-Order-Form.xfds>`_ and import it to the Plumsail Forms designer. 

To create such a form yourself, follow `this link <https://plumsail.com/docs/forms/design.html>`_ to learn more about how to design Plumsail Web Forms. 

**Understanding Internal Names of Form's fields**

It’s crucial to understand the **Internal Names** of Form's fields. They must correspond to tokens in a template. You can set internal names for Form’s fields in its general propeties:

.. image:: ../../../_static/img/flow/how-tos/name-of-PlumsailForms-field.png
    :alt: setting of the form's fields

Our data table’s name is **items**. And its columns have their names as well - **Product** and **Quantity**. 

In our XLSX template, we'll put such tokens :code:`{{items.Product}}` and :code:`{{items.Quatity}}`. The templating engine will iterate through all objects in the array to render them and add the rows automatically. 


Configure the Process
---------------------

Now we need to create and configure the Process which will generate stationary requests in PDF format based on data from our Plumsail Form submission. 

Create a new Process
~~~~~~~~~~~~~~~~~~~~

Go to `the Processes section <https://account.plumsail.com/documents/processes>`_ in your Plumsail account.

Click on the *Add process* button.

.. image:: ../../../_static/img/user-guide/processes/how-tos/add-process-button.png
    :alt: add process button

Set the Process name. 

.. image:: ../../../_static/img/flow/how-tos/create-new-process-plumsail-forms.png
    :alt: generate PDF from Plumsail Form

Upload the template you will use. In this example, we are going to generate requests for stationery and office supplies. And below is our template for it. You can download it by `this link <../../../_static/files/flow/how-tos/Create-Word-and-XLSX-template.xlsx>`_.

.. image:: ../../../_static/img/flow/how-tos/Cognito-Forms-XLSX-PDF-Template.png
    :alt: Template

When creating your own templates, mind the templating language. Plumsail Excel XLSX templates use a different approach than most other templating solutions. It uses a minimal amount of syntax to make your work done.

In short, the templating engine thinks that everything between curly :code:`{{ }}` brackets is variables where it will apply your specified data. 
Read `this article <../../../document-generation/xlsx/how-it-works.html>`_ to get familiar with the templating engine.

Configure a template
~~~~~~~~~~~~~~~~~~~~

Once you're done with the first step *Create Process*, press the *Submit* button, and you’ll proceed to the next – *Configure Template*:

- Fill in the name of the result file
- Select PDF format for the output file
- `Protect the result PDF <../../../user-guide/processes/create-process.html#add-watermark>`_ if you wish

.. image:: ../../../_static/img/flow/how-tos/configure-template-stationery-order.png
    :alt: Configure template

You can test a template as well, to see how it will look at the end. After clicking on the *Test template* button, you’ll need to ‘feed’ a template with your data in JSON format. 

To understand what JSON to feed, you need to look at tokens in your template. In our template we have :code:`{{name}}`, :code:`{{department}}`, etc, that's how the sample JSON for testing might look in our case:


.. code:: json

    {
      "name": "John Doe",
      "department": "IT",
      "email": "j.doe@contoso.com",
      "items": [
        {
          "Product": "Pen",
          "Quantity": 10
        },
        {
          "Product": "Pencil",
          "Quantity": 10
        }
      ],
      "instructions": "Delivery before Thursday",
      "phone": "(206)-564-96-97",
      "date": "25/02/2020"
    }

.. image:: ../../../_static/img/flow/how-tos/test-template-cognito-xlsx.png
    :alt: test template

It’s testing. We’re going to apply the data from the Plumsail stationery request form to our template.

Delivery
~~~~~~~~

The next step is delivery. For demonstrating purpose, we’ll store the result file in `OneDrive <../../../user-guide/processes/deliveries/one-drive.html>`_. But there are `other options <../../../user-guide/processes/create-delivery.html#list-of-available-deliveries>`_.

Just set the folder's name where the ready document will be saved.

.. image:: ../../../_static/img/flow/how-tos/onedrive-forms.png
    :alt: create pdf from template on form submission

You can configure as many deliveries as you need.

Start the Process
~~~~~~~~~~~~~~~~~
We will start our Process from Microsoft Flow.

Create a Flow
-------------

This is how our Flow looks:

.. image:: ../../../_static/img/flow/how-tos/excel-pdf-plumsail-forms-flow.png
    :alt: xlsx to pdf from Plumsail Forms flow

Below is a step-by-step description.

Form is submitted
~~~~~~~~~~~~~~~~~

We need to start the Flow every time somebody submits our stationery request form. For that, search for  *Plumsail Forms* in Power Automate and add *Plumsail Forms - Form is submitted* as a trigger.

If this is your first Flow with Plumsail Forms, on this step, sign in to your Plumsail Account from MS Flow to use your forms inside Flows.

You'll need to add the form ID to track it. 

.. image:: ../../../_static/img/flow/how-tos/PlumsailForm-trigger.png
    :alt: Plumsail Forms trigger

Find and copy it in **General** settings in Forms Designer.

.. image:: ../../../_static/img/flow/how-tos/Form-ID.gif
    :alt: How to find Plumsail Form ID

Current time
~~~~~~~~~~~~

It's a simple action to get the current date. We'll use its output in the next step.

.. image:: ../../../_static/img/flow/how-tos/current_time.png
    :alt: current time action

Start document generation process
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This is the action from `Plumsail Documents connector <../../../getting-started/use-from-flow.html>`_. This action is suitable for starting the Process of generating documents from a template. You can find more information about this action by visiting `this page <../../../flow/actions/document-processing.html#start-document-generation-process>`_.

Using the action for the first time, you’ll be asked for *''Connection Name''* and *''Access Key''*. 

.. image:: ../../../_static/img/getting-started/create-flow-connection.png
    :alt: create flow connection

You can type any name for the connection. For example, *''Plumsail Documents''*. 

Then `create an API key in your Plumsail Account page <https://plumsail.com/docs/documents/v1.x/getting-started/sign-up.html>`_, copy and paste it to *''Access Key''* field.

The action has two parameters:

.. image:: ../../../_static/img/user-guide/processes/how-tos/start-generation-docs-action.png
    :alt: start generation documents action

- *Process name*. Select the process you need from available ones. 
- *Template data*. Specify source data in JSON format:

.. image:: ../../../_static/img/flow/how-tos/JSON-data-Plumsail-Forms.png
    :alt: dynamic content of Plumsail form is submitted

This object contains information from our form. We selected the dynamic content from the output of *Plumsail Forms - Form is submitted* and *Current time* action.

.. image:: ../../../_static/img/flow/how-tos/dynamic-content-excel-plumsail.png
    :alt: dynamic content of Plumsail Form is submitted


Use the ready document in Flow
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can stop on the step **Start document generation process**. 

Steps described above are enough for generating PDFs from an XSLX template based on the Plumsail Form submission. Your result file will be saved to OneDrive in this case. See how it will look:

.. image:: ../../../_static/img/flow/how-tos/result-file-cognito-xlsx.png
    :alt: Final document

But if you need an advanced logic, it's possible to work with the result file right in the Flow. 

Here is an example of how you can send the ready document for approval. 

Add an action *Create an approval* from the *Approvals* connector. Select an output of the previous step for an attachment.

.. image:: ../../../_static/img/user-guide/processes/how-tos/create-an-approval.png
    :alt: send pdf for approval

Sign up for Plumsail Documents
-------------------------------

As you can see, it's simple to automize the generation of documents on Plumsail Forms submission. If you're new to Plumsail Documents, `register an account <https://auth.plumsail.com/Account/Register>`_ and follow the steps described in the article to set the process for automatic creation of PDFs from Plumsail Forms.

.. hint:: Check out one more example of creating PDF documents from templates on Plumsail Forms submission - `How to generate PDF documents from a DOCX template on Plumsail Forms submission <../../../flow/how-tos/documents/create-word-and-pdf-documents-from-plumsail-forms-processes.html>`_. 