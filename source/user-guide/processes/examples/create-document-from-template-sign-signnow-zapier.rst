How to create documents from a template in Zapier and sign them using SignNow
#############################################################################

In this article, we will show you how to create documents from a template using `Processes <../../../user-guide/processes/index.html>`_ and sign them with the help of `SignNow <https://www.signnow.com/>`_.

**Processes** are a `Plumsail Documents <https://plumsail.com/documents/>`_ feature with an intuitive interface for creating documents from templates.

**SignNow** is an electronic signature cloud-based software, which allows to sign and manage documents on any device.

We'll connect these tools in `Zapier <https://zapier.com/apps/plumsail-documents/integrations>`_ to automize the documents exchange and signing.

.. contents::
    :local:
    :depth: 2

Configure the Process
---------------------

Before creating an automated connection of apps in Zapier, we need to set a Process, which will create a PDF purchase agreement from a DOCX template.

Create a new process
~~~~~~~~~~~~~~~~~~~~

Go to `the Processes section <https://account.plumsail.com/documents/processes>`_ in your Plumsail account. 

Click on the *Add process* button.

.. image:: ../../../_static/img/user-guide/processes/how-tos/add-process-button.png
    :alt: add process button

Set the Process name. 

.. image:: ../../../_static/img/flow/how-tos/purchase-agreements-process.png
    :alt: create a new process

Upload the template you're gonna use. In this example, we'll create a PDF purchase agreement from a DOCX template. And below is our template's screenshot. You can download it by `this link <../../../_static/files/flow/how-tos/CONTRACT_TEMPLATE.docx>`_.

.. image:: ../../../_static/img/flow/how-tos/agreement-template.png
    :alt: Agreement DOCX template

When creating your own templates, mind the templating language. Plumsail Word DOCX templates use a different approach than most other templating solutions. It uses a minimal amount of syntax to make your work done.

In short, the templating engine thinks that everything between curly :code:`{{ }}` brackets is variables where it will apply your specified data. 
Read `this article <../../../document-generation/docx/how-it-works.html>`_ to get familiar with the templating engine.

Configure a template
~~~~~~~~~~~~~~~~~~~~

Once you're done with the first step *Create Process*, press the *Submit* button, and you’ll proceed to the next – *Configure Template*:

- Fill in the name of the result file
- Select PDF format for the output file
- `Protect the result PDF <../../../user-guide/processes/create-process.html#add-watermark>`_ if you wish


.. image:: ../../../_static/img/flow/how-tos/configure-template-signNow.png
    :alt: Configure template

You can test a template as well, to see how it will look at the end. After clicking on the *Test template* button, you’ll need to ‘feed’ a template with your data in JSON format. In our case, it might be the following:

JSON data
*********

.. code:: json

    {
        "Number": "432",
        "execution.date": "2020-05-25",
        "delivery.date": "2020-05-30",
        "buyer.name": "LUCKY LLC",
        "buyer.address": "55 Main St.New York NY 97203 USA",
        "company": {
           "email": "sales@sample.com",
           "address": "3 Main St.New York NY 97203 USA",
           "phone": "202-555-0131",
           "name": "Plumsail LLC"
        },
        "items": [
            {
                "product": {
                   "name": "Monitor",
                   "price": 99
                 },
                "quantity": 10,
                "cost": 990
                },
                {
                "product": {
                    "name": "Fridge",
                    "price": 4219.99
                },
                "quantity": 1,
                "cost": 4219.99
              }
        ],
        "total": 5209.99
    }


.. image:: ../../../_static/img/flow/how-tos/test-template-sign-now.png
    :alt: test template

Delivery
~~~~~~~~

The next step is delivery. For demonstrating purpose, we’ll store the result file in `OneDrive <../../../user-guide/processes/deliveries/one-drive.html>`_. But there are `other options <../../../user-guide/processes/create-delivery.html#list-of-available-deliveries>`_.

After you've connected to OneDrive from the Plumsail account, select the folder where to store the ready document. 

.. image:: ../../../_static/img/flow/how-tos/onedrive-signnow.png
    :alt: onedrive-delivery

You can configure as many deliveries as you need.

Start the Process
~~~~~~~~~~~~~~~~~
We will start our Process from Zapier. 

Create a Zap
------------
Zap is an automated connection between web services in Zapier. This is how our Zap looks:

.. image:: ../../../_static/img/flow/how-tos/signnow-zap.png
    :alt: Zap create contract and sign 

Check out the Zap steps described below.

Zap trigger
~~~~~~~~~~~

After you’ve opened `My Zaps <https://zapier.com/app/zaps>`_, create a new one, and select a trigger. You can pick any, for example, trigger a Zap when an opportunity in your CRM is closed, or a web form is submitted, or some others. We will pick `Push by Zapier <https://zapier.com/apps/push>`_ just for demonstration purposes. This kind of trigger enables you to start Zaps manually by Zapier extension for Google Chrome.

Start process in Plumsail Documents
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Once the trigger is set, search for Plumsail Documents and add an action *Start process*.

.. image:: ../../../_static/img/user-guide/processes/how-tos/start-process-zapier.png
    :alt: start process from Zapier action

Click Continue. If this is your first Zap, at this point, you'll need to Sign in to your Plumsail Account from Zapier to establish a connection between the app and your account. If you already have a Plumsail account tied to the app, you can add another one at this step, and use it instead.

Customize Start Process
***********************

Choose the process you want to start by this Zap from the dropdown. 
Then, you need to specify the data in JSON. This data will be applied to the template to personalize documents.

.. important:: Properties from the JSON object should correspond to tokens used in your template. Learn more about templates `here <../user-guide/processes/create-template.html>`_.

You can use the JSON object `which we applied to the template for testing <../../../user-guide/processes/examples/create-document-from-template-and-SignNow-zapier.html#json-data>`_.

.. image:: ../../../_static/img/flow/how-tos/json-data-signnow.png
    :alt: json in zap to create document and sign with SignNow

.. note:: Don't skip testing the Start process action. It's necessary to do to be able to use the output further in the Zap.

.. image:: ../../../_static/img/flow/how-tos/test-start-process.png
    :alt: json in zap to create document and sign with SignNow

Upload document
~~~~~~~~~~~~~~~

This action is from the SignNow integration for Zapier. It will upload the agreement to the SignNow account. After that, we can send the document for signature. In the 'File' field put :code:`File (Exists but not shown)` – output of the 'Start process in Plumsail Documents' step.
Give a name to the document uploaded to SignNow and press *Continue*.

.. image:: ../../../_static/img/flow/how-tos/customize-signnow-document.png
    :alt: Upload document action

Invite to sign
~~~~~~~~~~~~~~
The last action is from the SignNow integration too. It sends the contract for signing.

.. image:: ../../../_static/img/flow/how-tos/invite_to_sign_zapier.png
    :alt: invite_to_sign

Once the agreement has been signed, you will receive a notification e-mail with the signed document attached. 

.. image:: ../../../_static/img/flow/how-tos/notification_sn.png
    :alt: email notification cotract was signed