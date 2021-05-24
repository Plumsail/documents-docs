.. title:: Populate document templates with Google Forms data automatically with Plumsail Documents in Zapier

.. meta::
   :description: How to create custom PDF, Word, Excel, or PowerPoint documents from templates on Google Forms submission


Generate PDF documents from Google Forms and automatically save results to Google Drive
=======================================================================================

From this article, you will learn how to generate PDF documents with you Google Forms data 
and automatically save the resulting documents to Google Drive. 

`Google Forms <https://forms.google.com>`_ allow you to build online forms that you can publish on your website or anywhere else. 
Otherwise, you can share the link leading to the form.

`Plumsail Documents <https://plumsail.com/documents/>`_ automates generating documents from templates and delivering resulting documents. 

In this example, we’ll create a PDF purchase order from an Excel template and store the result into Google Drive. 
We'll connect Google Forms to Plumsail Documents with the help of the `Zapier platform <https://zapier.com/>`_. 

.. contents::
  :local:
  :depth: 1

Prepare online form in Google Forms
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Using the Google Forms builder, we’ve prepared such an `online form for a purchase order <https://forms.gle/jeYBMXo8bv3qNq3T9>`_. 

The online form builder by Google Forms is easy to use. You add new fields and specify their types. We have a short text type for almost all fields. Also, we added a date field. 

.. image:: ../../../_static/img/user-guide/processes/how-tos/po-google-form.png
  :alt: google form for purchase order

And a dropdown for choosing products.

.. image:: ../../../_static/img/user-guide/processes/how-tos/dropdown-products-google-forms.png
  :alt: google form dropdown for selecting products


Create document generation process in Plumsail Documents
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

`Sign up for a 30-day free Plumsail Documents trial <https://auth.plumsail.com/Account/Register?ReturnUrl=https%3A%2F%2Faccount.plumsail.com%2Fdocuments%2Fprocesses>`_. 
If you already have a Plumsail account, then open the Processes section.

Add a new process and select ‘Start from template’. 

.. image:: ../../../_static/img/user-guide/processes/how-tos/start-process-from-template.png
  :alt: add new process 

Then choose the purchase order template from the document templates library. 

.. image:: ../../../_static/img/user-guide/processes/how-tos/selec-po-template-google-forms.png
  :alt: select purchase order template from document templates library

You can adjust premade document templates to your needs. For editing online, click on 'Edit online'.

.. image:: ../../../_static/img/user-guide/processes/how-tos/edit-template-online-google-forms.png
  :alt: click edit online to edit premade template

Or use the 'Download' and 'Upload' buttons to edit it locally on your PC.

You can create your own document templates and upload them to the document generation process. 
Plumsail Documents templating language is easy to understand and implement.
Everything you enclose in :code:`{{double curly brackets}}` will be replaced by custom data. 
There are many advanced features in Plumsail Documents templates such as lists, tables, charts, and more, and even QR codes and barcodes. 

Please, learn how Plumsail Documents templating language works for various formats:

- `Word <https://plumsail.com/docs/documents/v1.x/document-generation/docx/index.html>`_
- `Excel <https://plumsail.com/docs/documents/v1.x/document-generation/xlsx/index.html>`_
- `PowerPoint <https://plumsail.com/docs/documents/v1.x/document-generation/pptx/index.html>`_
- `Fillable PDF <https://plumsail.com/docs/documents/v1.x/document-generation/fillable-pdf/index.html>`_

For simplicity here, we leave the premade template of the purchase order as-is. 

Only in the Settings, we configure to get the output document in PDF. And enable Active mode to remove the Plumsail watermark from the resulting documents. 

.. image:: ../../../_static/img/user-guide/processes/how-tos/templates-settings-google-forms.png
  :alt: template's settings

Add Google Drive delivery
--------------------------

We proceed to add delivery to our document generation process. We’ll store completed purchase orders in Google Drive. 

For that, select the Google Drive delivery.

.. image:: ../../../_static/img/user-guide/processes/how-tos/google-drive-delivery-google-forms.png
  :alt: adding google drive delivery

Sign in to your Google account from the Plumsail account. Specify the folder where to store the resulting documents. That’s it.

.. image:: ../../../_static/img/user-guide/processes/how-tos/google-drive-delivery-settings-google-forms.png
  :alt: settings of google drive delivery

You can add ad many deliveries as you need. 
For instance, in addition to storing in Google Drive, you can send the resulting documents by Gmail. 

We’re moving further. The next step is to start the process we’ve created. 

Connect Google Forms to Plumsail Documents in Zapier
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
  
We'll trigger our process by Google Forms submission. For that, we need to create a Zapier automated connection of apps. It's called Zap.

Click on the 'Use this zap' button to utilize the zap template.

|Widget|

.. |Widget| raw:: html

    <script type="text/javascript" src="https://zapier.com/apps/embed/widget.js?guided_zaps=134356"></script>

This is how our Zap looks:

.. image:: ../../../_static/img/user-guide/processes/how-tos/zap-google-forms-and-plumsail-documents.png
  :alt: zapier connection between google forms and plumsail documents

Below is a step-by-step description.

Trigger - New Response in Spreadsheet in Google Forms
------------------------------------------------------

To be able to use this trigger in Zapier for a particular form, don't forget to connect the form to the spreadsheet. 
You can do it in Responses by clicking on the Spreadsheets icon.

.. image:: ../../../_static/img/user-guide/processes/how-tos/connect-google-form-to-spreadsheet.png
  :alt: connect google form to spreadsheet

Select 'New Response in Spreadsheet' as a trigger if you're creating the zap from scratch.

.. image:: ../../../_static/img/user-guide/processes/how-tos/new-response-in-spreadsheet-google-forms.png
  :alt: google forms trigger 

To configure it, sign in to your Google account from Zapier. Then select the form you’d like to track and the corresponding spreadsheet.

.. image:: ../../../_static/img/user-guide/processes/how-tos/set-up-google-forms-trigger.png
  :alt: set up google forms trigger

Don't skip testing the trigger. You'll need the testing data further while setting the zap.

.. image:: ../../../_static/img/user-guide/processes/how-tos/test-google-forms-trigger.png
  :alt: test trigger new response in spreadsheet in google forms

Action - Start Process in Plumsail Documents
---------------------------------------------

For an action, select the Plumsail Documents app and its 'Start process' action.

.. image:: ../../../_static/img/user-guide/processes/how-tos/start-process-google-forms.png
  :alt: start process in plumsail documents action

Sign in to your Plumsail account from Zapier to be able to configure the action. 
On the 'Set up action' step, you need to select the document generation process you'd like to start.
Then map data from Google Forms with document template tokens. Fill in each token field with corresponding data from Google Forms.

.. image:: ../../../_static/img/user-guide/processes/how-tos/set-up-start-process-google-forms.png
  :alt: set up action start process in plumsail documents

Now you can turn on your zap. Every time somebody submits the Google form with the purchase order, you'll get a PDF document in your Google drive. 

.. image:: ../../../_static/img/user-guide/processes/how-tos/ready-documents-google-forms.png
  :alt: ready document stored in Google Drive


Hope you'll like this automation. Plumsail Documents works well with lots of other web forms. 

`Check the integrations for more ready-to-use examples <https://plumsail.com/documents/integrations/category/forms-and-surveys>`_. 















