.. title:: Create PDF documents from SharePoint list and send them for e-signature with eversign

.. meta::
   :description: Generate non-disclosure agreements from the SharePoint list and electronically sign using eversign and Plumsail Documents

How to automatically generate documents from data in SharePoint list and send them for digital signature in eversign using Power Automate Flow
===============================================================================================================================================

From this article, you will learn how to create an eSign document from data in the SharePoint list. Imagine that you have a list of employees on the SharePoint site. 
When you hire a new employee, you need to create and sign a non-disclosure agreement (NDA) with him/her. We will show how you can do it without having to print documents. 

.. image:: ../../../_static/img/user-guide/processes/how-tos/employees-list-eversign.png
    :alt: SharePoint list with employees

A new item in the SharePoint list will trigger the document generation process that will merge the list data into the NDA template and send the resulting document to the employee for digital signature in `eversign <https://eversign.com/>`_.

To automate the process, we'll use the `Plumsail Documents <https://plumsail.com/documents/>`_ connector for `Power Automate <https://flow.microsoft.com/>`_. You'll also need an `eversign account <https://eversign.com/signup>`_. 

.. contents::
    :local:
    :depth: 2

Configure document generation process
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To create a new document generation process in Plumsail Documents, go to `the Processes section <https://account.plumsail.com/documents/processes>`_ in your Plumsail account.

Click on the *Add process* button.

.. image:: ../../../_static/img/user-guide/processes/how-tos/add-process-button.png
    :alt: add process button

Fill in the process name field. 

Select **DOCX** for the template type. In this particular case, we tick the DOCX type because we'll create an NDA from the Word template. As you see, Plumsail Documents supports various template formats.

.. image:: ../../../_static/img/user-guide/processes/how-tos/create-process-eversign.png
    :alt: create a new process

Click *Next* to proceed to the next step - **Configure template**.

Configure document template
---------------------------

The Configure template step includes two substeps:

- Editor;
- Settings.

In `Editor <../../../user-guide/processes/online-editor.html>`_, you can compose document templates online, or upload pre-made ones and modify them. 

`Download the NDA template <../../../_static/files/user-guide/processes/dna-docx-template.docx>`_ we've prepared for this case and upload it to the process.

.. image:: ../../../_static/img/user-guide/processes/how-tos/upload-template-docusign.png
    :alt: upload template file

Once you did it, you'll see the preview of the document template:

.. image:: ../../../_static/img/user-guide/processes/how-tos/eversign-nda-preview.png
    :alt: NDA template preview

Word DOCX templating syntax
***************************

You may notice :code:`{{tokens}}` in the document template. We highlighted them purple to attract your attention and describe how the templating syntax works. 

Everything in :code:`{{curly braces}}` is variable that the templating engine will replace with specified data. 
In our example, :code:`{{employee}}` will turn into the real name, and :code:`{{date}}` token will turn into the agreement effective date. 

We used a value formatter for the date to get the result in a required format:

.. code:: text

    {{date}:format(MM/dd/yyyy)} 

You can find more information about formatters and other features in the `Word DOCX templates documentation <../../../document-generation/docx/index.html>`_.

Insert signing tags into the template
*************************************
At the end of the non-disclosure agreement template, we put special tags to define the location of signatures and other related fields for signers. 
You can't see them as we've changed their font color to white. 

These tags are from eversign; they ease the process of signing. Each signer will see where to place his signature and what fields are required to complete.

This is how tags look in the document template (we highlighted them black to make visible):

.. image:: ../../../_static/img/user-guide/processes/how-tos/eversign-nda-tags.png
    :alt: eversign signature tags

This is what the first signer will see:

.. image:: ../../../_static/img/user-guide/processes/how-tos/first-eversign-signer.png
    :alt: eversign signature tags result 1

the second signer will see:

.. image:: ../../../_static/img/user-guide/processes/how-tos/second-eversign-signer.png
    :alt: eversign signature tags result 2

It's easy to compose such signature tags. The logic is that they include a series of options in a specific order, divided with :code:`|` symbol, and the whole tag is wrapped by :code:`[squire brackets]`.

For instance, the option going first is a field type. In our template, we have such types as :code:`sig` (means signature), :code:`text`, and :code:`date`. 

Learn more about using `eversign signature and other related tags <../deliveries/eversign.html#use-signature-and-other-related-tags>`_. 

Customize output file
*********************

Let's move further - to the **Settings** substep.

.. image:: ../../../_static/img/user-guide/processes/how-tos/configure-template-eversign.png
    :alt: settings substep

Here you can customize the settings of the output file such as:

- **Mode**. It affects whether the resulting file will have a Plumsail watermark or not. In *Testing* mode, it will, but you won't pay for executions. In *Active*, it won't have the Plumsail watermark; each process run will spend one credit.
- **Output filename**. Use tokens from the document template to personalize the document name. They will work exactly the same way as in the template. 
- **Output type**. By default, it's the same as the template. We switched it to PDF. 
- Additionally, it's possible to `protect the resulting PDF file by a watermark or other security settings <../configure-settings.html#add-watermark>`_.

.. hint:: When you have a complex document template and you modify it a lot, it's a good ideas to test the template to see the result. We won't go into detail here, as we have a really simple template. You can find `more information on how to test document templates in the documentation <../test-template.html>`_.

Send document to eversign for eSignatures
-----------------------------------------

When the Configure template step is completed, you'll move on and will be offered to add deliveries.

**Delivery** means the way where to send and save resulting documents. Select the eversign delivery to send non-disclosure agreements to new employees for digital signatures using eversign.

Connect to your eversign account:

.. image:: ../../../_static/img/user-guide/processes/connect-eversign.png
    :alt: connect to eversign

After the connection between Plumsail and eversign accounts is established, you'll be able to customize the eversign delivery settings according to your needs.

Fill in the email subject and message. Here you can use tokens from the document template as well. 

Add recipients. It's possible to add as many as you need. Set their roles - either *Needs to sign* or *Receives a copy*. In our example, we have two signers:

.. image:: ../../../_static/img/user-guide/processes/how-tos/eversign-general-settings.png
    :alt: eversign general settings

To add an extra level of security, you can enable PINs for each signer. Click on the lock button, then set the PIN value.

.. image:: ../../../_static/img/user-guide/processes/how-tos/eversign-pin.png
    :alt: set eversign PIN

Expand **Advanced** to customize more settings. 

We enabled *Sequential signing* to set the strict order in which signers must sign the document. To change the order, drag and drop recipients.

And also, we enabled to *Require all signers to sign to complete the document*. If one of the signers rejects to sign, the document will be canceled.

.. image:: ../../../_static/img/user-guide/processes/how-tos/eversign-advanced-settings.png
    :alt: eversign advanced settings

The eversign delivery is set. It's possible to add as many deliveries as you need. For instance, you can add a SharePoint delivery to store employees' NDA in the SharePoint library.
Check out the `full list of deliveries and how to set them <../create-delivery.html#list-of-deliveries>`_.

Start process to create NDA and send to eversign
-------------------------------------------------

There are several ways of launching the process. We'll start our process from Power Automate:

.. image:: ../../../_static/img/user-guide/processes/how-tos/start-eversign-process.png
    :alt: start process from Power Automate

You can create the Flow from scratch or `utilize this Flow template for starting the document generation process on SharePoint item creation <https://emea.flow.microsoft.com/en-us/galleries/public/templates/e2d159a56b584314b45608be58ef2e3f/when-sharepoint-item-is-created-generate-documents-with-plumsail-documents/>`_. Red-outlined in the above picture.

Follow the steps below to configure the Flow.

Create and configure Power Automate Flow
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The picture of the completed Flow:

.. image:: ../../../_static/img/user-guide/processes/how-tos/eversign-flow.png
    :alt: eversign completed flow

When new employee is added to SharePoint list
---------------------------------------------

The Flow trigger is an automated trigger from the SharePoint connector for Power Automate. It's called *When an item is created*.

You need to specify the SharePoint site address where the list is located. And the SharePoint list itself:

.. image:: ../../../_static/img/user-guide/processes/how-tos/when-item-created-eversign.png
    :alt: flow triggers on SharePoint item creation

Start process of generating agreements
--------------------------------------

The next step is an action from the Plumsail Documents connector for Power Automate. 
It's called *Start document generation process*. And it will start the process we have configured to generate NDAs and send them to employees for digital signatures.

If it's your first time using Plumsail Documents in Power Automate, you'll be asked to create a connection and provide its name and an API key.

.. image:: /_static/img/getting-started/create-flow-connection.png
   :alt: Screen of Plumsail Documents

Type any name for the connection. For example, *Plumsail Documents*. `Create and copy an API key in the Plumsail account <https://account.plumsail.com/documents/api-keys>`_, paste it into the Access key field.

The *Start document generation process* has two fields to complete:
 
- *Process Name*. Select the process we have previously created from the dropdown.
- *Template Data*. Use the JSON format to fill it in. Use dynamic content from the trigger to specify objects. 

.. image:: /_static/img/user-guide/processes/how-tos/start-process-from-flow-eversign.png
   :alt: start document generation process

Save the Flow, and you'll never need to handle NDAs manually. This is an example of how the resulting document will look after signing:

.. image:: /_static/img/user-guide/processes/how-tos/signed-nda-eversign.png
   :alt: resulting document signed

Conclusion
~~~~~~~~~~

We automated the whole process of generating and sending non-disclosure agreements to new employees for e-signing in eversign.
You can use a similar approach to generate and electronically sign any other documents such as contracts, invoices, applications. 

The source data for document templates can come not only from SharePoint lists. You can use your favorite apps to connect to Plumsail Documents, pull data, and populate templates.
See more examples in `the integrations section <https://plumsail.com/documents/integrations/>`_. 

Drop us a line to `support@plumsail.com <support@plumsail.com>`_ in case you encounter any difficulties or get any questions.








