How to create Excel and PDF documents from Microsoft Forms in Power Automate and Azure Logic Apps
=================================================================================================

This article shows how to create PDF documents from an XLSX template on a `Microsoft Form <https://forms.office.com/>`_ submission with the help of `Processes <../../../user-guide/processes/index.html>`_ in Power Automate (MS Flow). It may help you to automate the generation of different documents like applications, requests, orders, etc., in your company. 

**Processes** are a `Plumsail Documents <https://plumsail.com/documents/>`_ feature with an intuitive interface for creating documents from templates.

**Microsoft Forms** are an online form builder with themes and question branching that allows you to create surveys, quizzes, polls and collects other information.

In this example, we will collect data from a Microsoft Form, apply the data to our Excel template, and generate a new PDF document with the help of Processes in Power Automate (Microsoft Flow).

.. contents::
    :local:
    :depth: 2

Create a Form
-------------

We have already created a Microsoft Form for a short employee information sheet. We will use data from its submission. If you haven't created MS Forms before, follow `this link <https://support.office.com/en-gb/article/create-a-form-with-microsoft-forms-4ffb64cc-7d5d-402f-b82e-b1d49418fd9d>`_ to learn how to do it.

It's possible to use the form from this example. After you've logged into your Microsoft Forms account, click on `this link <https://forms.office.com/Pages/ShareFormPage.aspx?id=sw17qLgWx0qMVHqdDlcIbmR30TR_6NdLl37R-A7gviRUREdDS0RUQ0pWNVZTSFJOWEJZN1c0UTJZRy4u&sharetoken=myrEdz9F27iuAWGKqSd6>`_ to duplicate the form. After duplicating you'll be able to use the form as your own. 

Below is a screenshot of our form:

.. image:: ../../../_static/img/flow/how-tos/MSform.png
    :alt: Microsoft Form

Configure the Process
---------------------

Before creating the Flow, we need to set a Process, which will generate PDF documents from an XLSX template.

Create a new process
~~~~~~~~~~~~~~~~~~~~

Go to `the Processes section <https://account.plumsail.com/documents/processes>`_ in your Plumsail account. 

Click on the *Add process* button.

.. image:: ../../../_static/img/user-guide/processes/how-tos/add-process-button.png
    :alt: add process button

Set the Process name. 

.. image:: ../../../_static/img/flow/how-tos/create-new-process-plumsail-forms.png
    :alt: generate PDF from Typeform

Upload the template you're gonna use. In this example, we'll create a short employee information sheet. And below is our template for it. You can download it by `this link <../../../_static/files/flow/how-tos/Create-Excel-and-PDF-EmployeesData-template.xlsx>`_.

.. image:: ../../../_static/img/flow/how-tos/MS-Forms-XLSX-PDF-template.png
    :alt: Excel template

When creating your own templates, mind the templating language. Plumsail Excel XLSX templates use a different approach than most other templating solutions. It uses a minimal amount of syntax to make your work done.

In short, the templating engine thinks that everything between curly :code:`{{ }}` brackets is variables where it will apply your specified data. 
Read `this article <../../../document-generation/xlsx/how-it-works.html>`_ to get familiar with the templating engine.

Configure a template
~~~~~~~~~~~~~~~~~~~~

Once you're done with the first step *Create Process*, press the *Submit* button, and you’ll proceed to the next – *Configure Template*:

- Fill in the name of the result file
- Select PDF format for the output file
- `Protect the result PDF <../../../user-guide/processes/create-process.html#add-watermark>`_ if you wish

.. image:: ../../../_static/img/flow/how-tos/Configure-template-employeedata.png
    :alt: Configure template


You can test a template as well, to see how it will look at the end. After clicking on the *Test template* button, you’ll need to ‘feed’ a template with your data in JSON format. To understand what JSON to feed, you need to look at tokens in your template. 
In our template we have :code:`{{name}}`, :code:`{{title}}`, etc, that's how the sample JSON for testing might look in our case:


.. code:: json

    {
      "name": "John Smith",
      "title": "Designer",
      "department": "Marketing",
      "manager": "Amanda Peterson",
      "dateOfHire": "19/02/2020",
      "address": "5th Avenue 5 apt 5",
      "cell": "+789123456",
      "dateOfBirth": "01/08/1980",
      "SIN": "011-022-033-099"
    }

.. image:: ../../../_static/img/flow/how-tos/test-template-plumsail-forms-processes.png
    :alt: test template

It’s testing. We’re going to apply the data from the MS Form to our template. 

Delivery
~~~~~~~~

The next step is delivery. For demonstrating purpose, we’ll store the result file in `OneDrive <../../../user-guide/processes/deliveries/one-drive.html>`_. But there are `other options <../../../user-guide/processes/create-delivery.html#list-of-available-deliveries>`_.

Select the folder where the ready document will be saved. Fill in the file's name. You don't need to put :code:`.extension`, it'll be done automatically based on the output file type you set on the *Configure template* step.

.. image:: ../../../_static/img/flow/how-tos/onedrive-forms.png
    :alt: create pdf from template on form submission

You can configure as many deliveries as you need.


Start the Process
~~~~~~~~~~~~~~~~~
We will start our Process from Power Automate (Microsoft Flow). 

Create a Flow
-------------
This is how our Flow looks:

.. image:: ../../../_static/img/flow/how-tos/MSform-flow-xlsx-pdf.png
    :alt: pdf from MS form flow

Check out the Flow steps described below.

Form is submitted
~~~~~~~~~~~~~~~~~

We need to start the Flow every time somebody submits our form. For that, search for *Microsoft Forms* in Power Automate and set *Microsoft Forms - When a response is submitted* as a trigger.

If this is your first Flow with Microsoft Forms, on this step, sign in to your Microsoft Forms Account from MS Flow to use your forms inside Flows.

Then, you'll need to pick the form you want to track in the dropdown.

.. image:: ../../../_static/img/flow/how-tos/microsoft-form-trigger-xlsx.png
    :alt: Microsoft Form trigger

Get response details
~~~~~~~~~~~~~~~~~~~~
As we want to get the submitted data, we need to add *Microsoft Forms - Get response details* action. On this action, we select the same **Form Id** that we used in the trigger. Then, we click in the **Response Id** text box and pick **List of response notifications - Response Id** in the Dynamic content menu on the right:

.. image:: ../../../_static/img/flow/how-tos/Microsoft-Forms-Response-ID.png
    :alt: Get response details


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

.. image:: ../../../_static/img/flow/how-tos/JSON-msform-xlsx-pdf.png
    :alt: dynamic content of MS Form is submitted

This object contains information from our form. We selected the dynamic content from the output of *Microsoft Forms - Get response details* action:

.. image:: ../../../_static/img/flow/how-tos/msform-dynamic-content.png
    :alt: dynamic content of Microsoft Form is submitted

Use the ready document in Flow
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can stop on the step **Start document generation process**. 

Steps described above are enough for generating PDFs from an XSLX template based on the Microsoft Form submission. Your result file will be saved to OneDrive in this case. See how it will look:

.. image:: ../../../_static/img/flow/how-tos/resultfile-employee-info.png
    :alt: Final document

But if you need an advanced logic, it's possible to work with the result file right in the Flow. 

Here is an example of how you can send the ready document for approval. 

Add an action *Create an approval* from the *Approvals* connector. Select an output of the previous step for an attachment.

.. image:: ../../../_static/img/user-guide/processes/how-tos/create-an-approval.png
    :alt: send pdf for approval

Sign up for Plumsail Documents
------------------------------

As you can see, it's simple to automize the generation of documents on Microsoft Forms submission. If you're new to Plumsail Documents, `register an account <https://auth.plumsail.com/Account/Register>`_ and follow the steps described in the article to set the process for automatic creation of PDFs from Microsoft Forms.

.. hint:: You can generate PDFs from Web Forms even without Power Automate (Microsoft Flow). Check the article `How to generate PDF documents from a DOCX template on Plumsail Forms submission <../../../flow/how-tos/documents/create-word-and-pdf-documents-from-plumsail-forms-processes.html>`_.