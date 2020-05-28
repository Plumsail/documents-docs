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