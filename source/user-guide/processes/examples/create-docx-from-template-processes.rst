.. title:: Generate Word DOCX documents from a template using Zapier and Power Automate Flow

.. meta::
   :description: Use Plumsail Documents processes to generate customized documents from Word templates in a few simple steps.



How to create Word DOCX document from a template in Zapier, Power Automate (Microsoft Flow), Azure Logic Apps, and PowerApps
============================================================================================================================
Let’s suppose you want to automate the process of generating invoices in your company. This article will describe how to create a DOCX document from a template with the help of `Processes <../../../user-guide/processes/index.html>`_, a `Plumsail Documents <https://plumsail.com/documents/>`_ feature. 

The Processes are a user-friendly intuitive interface for creating documents from templates, converting them, and delivering to different systems for further management. 

With its help, we'll create an invoice from a template, and this is how the result document will look:

.. image:: ../../../_static/img/user-guide/processes/how-tos/invoice-result-document.png
    :alt: create docx from template

Let’s go through each step from the very beginning:

.. contents::
    :local:
    :depth: 2

Configure Process
~~~~~~~~~~~~~~~~~

First, register or login to your `Plumsail account`_.

Create new process
--------------------

Click on the *Add Process* button.

.. image:: ../../../_static/img/user-guide/processes/how-tos/add-process-button.png
    :alt: add process button

Give a name to the Process to recognize it later. Select DOCX for a template type. 

.. image:: ../../../_static/img/user-guide/processes/how-tos/create-new-process.png
    :alt: create docx from template

Configure template
--------------------

Once you've created the Process, you'll proceed to its first step - **Configure template**.

It includes two substeps:

- Editor;
- Settings.

In `Editor <../../../user-guide/processes/online-editor.html>`_, you can compose the template from scratch or upload a pre-made one. It's also possible to modify the uploaded template online.

Feel free to `download an invoice DOCX template <../../../_static/files/user-guide/processes/template-invoice.docx>`_ we have already prepared. Then upload it to the process.

.. image:: ../../../_static/img/user-guide/processes/how-tos/upload-template.png
    :alt: upload template file

Templating syntax
*****************

When creating your own templates, mind the templating language. Plumsail Word DOCX templates use a different approach than most other templating solutions. It uses a minimum of syntax to make your work done.

To learn more about the templating engine, check out `the documentation article`_.

In short, the templating engine thinks that everything between such curly :code:`{{ }}` brackets is variables where it will apply your specified data. In our case the most basic example would be :code:`{{invoiceNumber}}` and :code:`{{date}}` tags. They let the engine know that we want to render the invoice number and its date.

But, of course, we can implement a more complex scenario. In our template, we refer to properties inside a collection of products. For that, we use nested tags with a dot operator:

- The :code:`{{product.name}}`, :code:`{{product.price}}` tags get the name, description, and price properties in the product's object.

The templating engine is smart enough to identify what content to duplicate. It will iterate through all objects in the array to render them and add rows automatically.

.. image:: ../../../_static/img/user-guide/processes/how-tos/table-render.png
    :alt: tables in DOCX templates

You can learn more about table rendering in `the tables section`_ of the documentation.

Test template
*************

To check how the document will look at the end, click on the *Test template* button. You will see the dialog where you can fill in the auto-generated testing form. 
Form fields are created from tokens of your document template. You can `adjust the look of the testing form by changing token types <../custom-testing-form.html>`_.

.. image:: ../../../_static/img/user-guide/processes/how-tos/test-template.png
    :alt: create docx from template

Click on the 'Create document', and the resulting invoice will appeat in a new tab.
Once you're satisfied with it, press *Save&Next* to proceed further - to the **Settings** substep.

Here you set the following parameters. Descriptions are under the picture.

.. image:: ../../../_static/img/user-guide/processes/how-tos/configure-template.png
   :alt: configure DOCX template

**Template mode**

It is *Testing* by default. It means you won't be charged for this process runs, but result documents will have a Plumsail watermark. Change it to *Active* to remove the watermark.

**Output filename**

Use tokens to make it personalized. They work the same way as in the template. For instance, we use the following tokens to define the output file name - :code:`{{invoiceNumber}}`. As a result, we'll receive an invoice marked with its number - *Invoice 432*.

**Output type**

By default, it is the same as your template's format. In this particular case, it's DOCX. And we kept it to create the DOCX Word document from a template.

**Test template**

Once you've customized all the settings, you can test the template to see the result as we did it before. 

When everything is done here, click on Save & Next to set up deliveries.


Delivery
--------
The next step is delivery. For demonstrating purpose, we’ll store the result file in `OneDrive <../../../user-guide/processes/deliveries/one-drive.html>`_. But there are `other options <../../../user-guide/processes/create-delivery.html>`_.

You need to connect to your OneDrive from the Plumsail account. After that, set the folder's name where to save the ready document. Here you can use tokens as well. 

.. image:: ../../../_static/img/user-guide/processes/how-tos/store-onedrive.png
    :alt: create docx from template

You can configure as many deliveries as you need.

Start Process
~~~~~~~~~~~~~

Now everything is ready, and you can start generating Word DOCX documents. The step **Start process** will show available options with a description for each.

.. image:: ../../../_static/img/user-guide/processes/how-tos/start-docx-process.png
    :alt: start process to create Word from template

You can start the process :

- `from web form <../start-process-web-form.html>`_;
- `submitting JSON <../start-process-manually.html>`_ corresponding to template tokens;
- `using Power Automate (former Microsoft Flow) <../start-process-ms-flow.html>`_;
- `using Zapier <../start-process-zapier.html>`_
- `using REST API <../start-process-rest-api.html>`_;

.. hint:: Use `Power Automate Flow <../../../getting-started/use-from-flow.html>`_ and `Zapier <../../../getting-started/use-from-zapier.html>`_ to connect the process with other apps. It enables you to gather data from one app and pass on to the process to populate a DOCX template. Thus, you can populate the DOCX template from various web forms, CRM systems, SharePoint lists, and thousands of other web applications. 

.. note:: There is another - a little bit more complicated - way to create DOCX documents from a template. Check `the article <../../../flow/how-tos/documents/create-docx-from-template.html>`_.



.. _Plumsail account: https://auth.plumsail.com/account/Register?ReturnUrl=https://account.plumsail.com/documents/processes/reg
.. _the documentation article: ../../../document-generation/docx/how-it-works.html
.. _the tables section: ../../../document-generation/docx/tables.html