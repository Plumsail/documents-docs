.. title:: Create Word DOCX documents from a template in Zapier, Power Automate Flow, Azure Logic Apps, and PowerApps

.. meta::
   :description: Use Plumsail Documents processes to generate customized documents from Word templates in a few simple steps.

Automatically genetate Word document from template 
===================================================
From this article, you will learn how to create a document generation process in `Plumsail Documents <https://plumsail.com/documents/>`_. It will help you to automatically generate any Word DOCX documents from templates, so you can automate document generation in your company. 

Particularly in this article, we'll create invoices. This is how the result document will look:

.. image:: ../../../_static/img/user-guide/processes/how-tos/invoice-result-document.png
    :alt: create docx from template

Let’s go through each step from the very beginning:

.. contents::
    :local:
    :depth: 2

Configure Process
~~~~~~~~~~~~~~~~~

First, register or log in to your `Plumsail account`_.

Create new process
--------------------

Add a new process. You can either create a document generation process from scratch or start from one of premade templates. 
Let's create a process from scratch to follow the steps from this instruction.

After we clicked the *Add Process* button, we need to name our process and select a template type. In our case, it's DOCX:

.. image:: ../../../_static/img/user-guide/processes/how-tos/create-new-process.png
    :alt: create docx from template

Configure template
--------------------

Once we've created the Process, we'll proceed to its first step - **Configure template**.

It includes two substeps:

- Editor;
- Settings.

In Editor, you can compose the template from scratch or upload an existing one. It's also possible to modify the uploaded template online.

Feel free to `download the invoice DOCX template <../../../_static/files/user-guide/processes/template-invoice.docx>`_ we have already prepared. Then upload it to the process.

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