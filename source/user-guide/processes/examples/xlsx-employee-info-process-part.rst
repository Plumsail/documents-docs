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