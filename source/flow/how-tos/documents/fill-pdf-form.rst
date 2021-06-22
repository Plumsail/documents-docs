.. title:: How to auto populate fillable PDF forms from a SharePoint list using Power Automate (Microsoft Flow), Azure Logic Apps, or Power Apps

.. meta::
   :description: Automatically fill PDF forms from database using Automate (Microsoft Flow), Azure Logic Apps, and PowerApps


Populate PDF forms from SharePoint in Power Automate
====================================================

.. note:: 

  One of our customers voluntarily recorded an overview of a business case for collecting data from PDF forms and for automatic filling them. You can watch the video in addition to reading the article.

  .. raw:: html

    <iframe width="560" height="315" src="https://www.youtube.com/embed/7jTq-kRClhM" frameborder="0" allowfullscreen></iframe>

In this article, you will learn how to automatically populate fillable PDF forms in Power Automate (Microsoft Flow) or Azure Logic Apps. We will use `Fill in PDF Form`_ action from `Plumsail Documents connector`_.

In our case, we will fill in an Application for Employment form based on the data from a SharePoint list. Actually, you can get data from any other source. We use SharePoint list here as an example.

For example, you could place `Plumsail Form`_ on your website and trigger your flow on `form submission`_. Also, you could `extract data from incoming email messages`_ and use this data to fill in your form.

This is how the final PDF document with the form will look in our case:

|fill-in-pdf-form-result|

Our template and result document have to be stored somewhere. Power Automate (Microsoft Flow) has a lot of connectors for different systems. Here are just a few of them:

- SharePoint
- Box
- OneDrive
- Google Drive
- Dropbox
- SFTP
- File System

In this example, we will store the initial fillable PDF form and filled PDF documents in a SharePoint document library.

Create fillable PDF
~~~~~~~~~~~~~~~~~~~

Follow `this instruction <../../../document-generation/fillable-pdf/index.html>`_ to create a fillable PDF. `Download the template file`_ for this article.

|fill-in-pdf-form-template|

Create Power Automate (Microsoft Flow)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Now let us review the flow and learn how it is implemented:

|fill-in-pdf-form-flow|

Flow trigger
~~~~~~~~~~~~
You can actually pick any trigger. For example, you can start Flow on `form submission`_. We use “When an item is created” trigger to get the newest created item from the SharePoint list.

Our SharePoint list has the same columns as fields in our fillable PDF file.

Get file content action
~~~~~~~~~~~~~~~~~~~~~~~
This action gets file content of the source fillable PDF file from a SharePoint document library. You can just specify SharePoint site URL and path to the fillable PDF that we created earlier.

|fill-in-pdf-form-flow-get-file|

You can use any other connector to get files from your system.

Fill in PDF form action
~~~~~~~~~~~~~~~~~~~~~~~
`Fill in PDF form`_ is the action from `Plumsail Documents connector`_. You can use this action to fill PDF forms.

There are two parameters:

1. Content of the PDF document
2. JSON data

In the first parameter 'Content of the PDF document', you can put file content from some other action. In our case, we specified the output of the previous action as a source fillable PDF.

In the second parameter ‘JSON data’ you can put a JSON object as a source data to fill in your form. Please make sure that you specified the same property names as you used in your fillable PDF. Thus, the action will match properties to fields in PDF and fill them.

Send an Email action
~~~~~~~~~~~~~~~~~~~~
Now you need to send the PDF file with filled in form. In our example, we used 'Send an Email' action from Office 365 Outlook connector.

Please notice how we specified the PDF file. It is essential to specify attachment name with the correct extension.

|fill-in-pdf-form-flow-create-file|

You can use any other connector to send or store documents in your system.

Conclusion
~~~~~~~~~~
Now you should have an idea how to use Fill in PDF form action from `Plumsail Documents connector`_ for Power Automate (Microsoft Flow). If you haven’t used it yet, `registering an account`_ would be the first step. It is quite easy to get started.

.. hint:: There is also `Get Form from PDF`_ action available. You can use it to `collect data from fillable PDF`_.

.. _Fill in PDF form: ../../actions/document-processing.html#fill-in-pdf-form
.. _Plumsail Documents connector: https://plumsail.com/documents/
.. _Plumsail Form: https://plumsail.com/forms/public-forms/
.. _form submission: https://plumsail.com/docs/forms/microsoft-flow.html
.. _extract data from incoming email messages: use-regex-match-to-extract-values.html
.. _Download the template file: ../../../_static/files/flow/how-tos/fill-in-pdf-form-template.pdf
.. _registering an account: https://auth.plumsail.com/account/Register?ReturnUrl=https://account.plumsail.com/documents/processes/reg
.. _Get Form from PDF: ../../actions/document-processing.html#get-form-from-pdf
.. _collect data from fillable PDF: collect-data-pdf-form.html

.. |fill-in-pdf-form-result| image:: ../../../_static/img/flow/how-tos/fill-in-pdf-form-result.png
.. |fill-in-pdf-form-template| image:: ../../../_static/img/flow/how-tos/fill-in-pdf-form-template.png
.. |fill-in-pdf-form-flow| image:: ../../../_static/img/flow/how-tos/fill-in-pdf-form-flow.png
.. |fill-in-pdf-form-flow-get-file| image:: ../../../_static/img/flow/how-tos/fill-in-pdf-form-flow-get-file.png
.. |fill-in-pdf-form-flow-create-file| image:: ../../../_static/img/flow/how-tos/fill-in-pdf-form-flow-send-email.png