.. title:: How to create PDF documents from template and send them for e-signature with Adobe Sign in Power Automate (Microsoft Flow), Azure Logic Apps, and PowerApps

.. meta::
   :description: Automate your document generation and signing with Adobe Sign in Power Automate (Microsoft Flow), Azure Logic Apps, and PowerApps

Create document from template in Power Automate and sign it using Adobe Sign
=================================================================================

This article is a ready-to-use solution on how to create a PDF document from a template and sign it using `Adobe Sign <https://acrobat.adobe.com/us/en/sign.html>`_.

With the help of `Processes <../../../user-guide/processes/index.html>`_, we will create a purchase agreement from a DOCX template, save in SharePoint document library and send for signing using the **Adobe Sign** connector for Power Automate (Flow). 

This is how the result document will look after signing:

.. image:: ../../../_static/img/flow/how-tos/signed_contract.png
    :alt: signed contract

.. contents::
    :local:
    :depth: 2

Configure the Process
~~~~~~~~~~~~~~~~~~~~~

Before creating the Flow, we need to set a Process, which will create our purchase agreement in PDF format from a DOCX template.


Create a new process
--------------------

First, go to `the Processes section <https://auth.plumsail.com/account/Register?ReturnUrl=https://account.plumsail.com/documents/processes/reg>`_ in your Plumsail account. 

Click on the *Add process* button.

.. image:: ../../../_static/img/user-guide/processes/how-tos/add-process-button.png
    :alt: add process button

Set the Process name. As we're going to create a PDF purchase agreement from a DOCX template, select DOCX for the template type.

.. image:: ../../../_static/img/flow/how-tos/purchase-agreements-process.png
    :alt: create a new process

Configure a template
--------------------

Once you're done with the first step *Create Process*, press the *Next* button, and you’ll jump to the next step – *Configure Template*. 

There you'll find two substeps:

- Editor;
- and Settings.

In `Editor <../../../user-guide/processes/online-editor.html>`_, you can work out the template online, or upload the pre-made template and modify it in case of need. 

You can `download a DOCX template for a purchase agreement <../../../_static/files/flow/how-tos/CONTRACT_TEMPLATE.docx>`_ that we have already prepared. 

.. image:: ../../../_static/img/flow/how-tos/agreement-template.png
    :alt: Agreement DOCX template

And then upload it to the process. 

Templating syntax
*****************

When creating your own templates, mind the templating language. Plumsail Word DOCX templates use a different approach than most other templating solutions. It uses a minimal amount of syntax to make your work done.

In short, the templating engine thinks that everything between :code:`{{curly}}` brackets is variables where it will apply your specified data. 
Read `this article <../../../document-generation/docx/how-it-works.html>`_ to get familiar with the templating engine.

Test template
*************

After you've uploaded the template to the process, you will see the template preview. To get a sight of the resulting document, click the *Test template* button. 
You will see the dialog where you can fill in the auto-generated testing form. 
Form fields are created based tokens from your document template. You can `adjust the look of the testing form by changing token types <../custom-testing-form.html>`_.

.. image:: ../../../_static/img/flow/how-tos/test-template-sign-now.png
    :alt: test template

Once you've tested the template, press *Save&Next* to proceed further - to the **Settings** substep.

- Fill in the name of the result file.
- Select PDF format for the output file
- `Protect the result PDF <../configure-settings.html#add-watermark>`_ if you wish

.. image:: ../../../_static/img/flow/how-tos/configure-template-signNow.png
    :alt: Configure template

Delivery
--------

The next step is delivery. For demonstrating purpose, we’ll store the result file in `OneDrive <../../../user-guide/processes/deliveries/one-drive.html>`_. But there are `other options <../../../user-guide/processes/create-delivery.html>`_.

Select the folder where the ready document will be saved. 

.. image:: ../../../_static/img/flow/how-tos/onedrive-signnow.png
    :alt: onedrive-delivery

You can configure as many deliveries as you need.

Start the Process
-----------------

We will start our Process from Power Automate (Flow). 

Create a Flow
~~~~~~~~~~~~~

This is how our Flow looks:

.. image:: ../../../_static/img/flow/how-tos/Adobe-sign-flow.png
    :alt: Create an agreement and sign with Adobe Sign flow

Check out the Flow steps described below.

Flow trigger
------------

After you’ve opened `My Flows <https://emea.flow.microsoft.com/manage/flows>`_, create a new one, and select a trigger. You can pick any, for example, trigger a Flow when an opportunity in CRM is closed, or a new item is added to SharePoint list. We will pick *'Manually trigger a Flow'* just for demonstration purposes.

Start document generation process
---------------------------------

This is the action from `Plumsail Documents connector <../../../getting-started/use-from-flow.html>`_. This action is suitable for starting the Process of generating documents from a template. You can find more information about this action by visiting `this page <../../../flow/actions/document-processing.html#start-document-generation-process>`_.

Mind, If you use the Plumsail documents action for the first time, you’ll be asked for *'Connection Name'* and *'Access Key'*. You can type any name for the connection. For example, *'Plumsail Documents'*.

Then `create an API key in your Plumsail Account page <https://account.plumsail.com/documents/api-keys>`_, copy and paste it to the *'Access Key'* field.

The **Start document generation process** action has two parameters:

- *Process name*. Select the process you need from available ones. 
- *Template data*. Specify source data in JSON format as we did on `the step of testing <../../../flow/how-tos/documents/create-a-document-from-template-and-sign-Abobesign-processes.html#json-data>`_ the template. 


.. image:: ../../../_static/img/flow/how-tos/template-data-signnow.png
    :alt: Template data

Create file
-----------

Use this action to store the completed agreement in SharePoint document library. Specify a SharePoint site URL, a library, the name of the document with :code:`.PDF` extension, and for *File content* choose :code:`Result file` – an output from the *Start document generation* step.

.. image:: ../../../_static/img/flow/how-tos/create_file_as.png
    :alt: create_file

Create sharing link for a file or folder
----------------------------------------

We will need to share our contract with Adobe Sign, that’s why a sharing link is needed. Pay attention to choose the right link type and scope – they should be *'View and edit'* and *'Anyone with the link, including anonymous'* respectively. 


.. image:: ../../../_static/img/flow/how-tos/create_share_link.png
    :alt: sharing_link

There is a tricky moment for SharePoint site collection – you may be not allowed to share files from libraries of your SP site. In the case of such a setting, the Flow will fail on this step. We need to change the settings.

For that, go to SharePoint Admin Center, navigate to Active sites, choose yours and click on the button *'Sharing'* to edit the settings. 

.. image:: ../../../_static/img/flow/how-tos/sharing_button.png
    :alt: active_sites

For our purpose, the site content can be shared with anyone.

.. image:: ../../../_static/img/flow/how-tos/anyone_can_edit.png
    :alt: Site content can be shared with anyone

You may be worried about sensitive information while sharing files, but there is no reason for it; nobody can use the link, but the Adobe Sign application for getting content to create an agreement for further usage in Adobe Sign. 

Moreover, there is another action in Adobe Sign connector for Power Automate (Microsoft Flow) to upload documents directly, but unfortunately, it doesn’t work now because of a lack of code integration. We believe that it will be fixed in the future.

Create an agreement from a document URL, and send for signature
---------------------------------------------------------------

This action creates an agreement, saves it in the AbobeSign account and sends it to your partner for signature. 

You can put any name for *'Agreement name'*. 

For Document URL field select an output from the previous step, and add :code:`?download=1` to make the link direct. Otherwise, it won’t work.

Don’t forget to specify a file extension with :code:`.PDF`

.. image:: ../../../_static/img/flow/how-tos/adobe_sign_action.png
    :alt: adobesign_action

The Flow is ready. Now you know how to simplify your workflow processes with the help of Processes by Plumsail Documents and its connector for Power Automate (Flow). If you haven't a Plumsail account yet, `sign up <https://auth.plumsail.com/Account/Register?ReturnUrl=https://account.plumsail.com/documents/processes/reg>`_ to get started.

.. hint:: If you use a SignNow system for e-signs or just want to compare Adobe Sign with an alternative, read our article `How to create a document from a template and sign it using SignNow <./create-document-from-template-sign-signnow.html>`_.