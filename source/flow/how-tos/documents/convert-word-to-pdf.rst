Convert DOCX to PDF
==================================

This article demonstrates how to convert DOCX Word document to PDF with the help of `Microsoft Flow <https://flow.microsoft.com>`_. 

Before starting, ensure that you `added Plumsail Documents connector to Microsoft Flow <../../../getting-started/use-from-flow.html>`_.

We will take a hiring contract as a sample Word document:

.. image:: ../../../_static/img/flow/how-tos/docx-sample-doc.png
   :alt: Select fields

Use `this link <../../../_static/files/flow/how-tos/Hiring%20Contract.docx>`_ to download it.

Our document has to be stored somewhere. Microsoft Flow has a lot of connectors for different systems. Here are just a few of them:

- SharePoint
- Salesforce
- Box
- OneDrive
- Google Drive
- Dropbox
- SFTP
- File System

You can store your source file anywhere. In this example, we will store our document in SharePoint. Our Flow will get a file from a SharePoint document library, convert it to PDF and store generated file back to SharePoint document library. 

This is how complete flow looks:

.. image:: ../../../_static/img/flow/how-tos/convert-docx-to-pdf-flow.png
   :alt: Select fields

Here is step by step description for the flow.

**Flow trigger**

You can actually pick any trigger. For example, you can start Flow on file creation in a SharePoint document library. We use "Manually trigger a flow" trigger here to simplify the Flow.

**Get file content**

This action gets file content of the specified file from a SharePoint document library. You just specify SharePoint site URL and path to your file.

You can use any other connector to get files from your system.

**Convert DOCX to PDF**

This is an action from Plumasail Documents connector, which is a part of `Plumsail Actions <https://plumsail.com/actions>`_.

Just put DOCX file content from the output of the previous action and receive PDF file content as an output of this action.

You can find more information about this action `here <../../actions/document-processing.html#convert-docx-document-to-pdf>`_.

**Create file**

Now you need to store PDF file somewhere. In our example, we use "Create file" action from SharePoint connector to store the PDF document into SharePoint document library.

.. image:: ../../../_static/img/flow/how-tos/generated-pdf-sp-library.png
   :alt: Select fields

You can use any other connector to store PDF document into your system.

.. hint:: There is also `Create document from DOCX template <../../actions/document-processing.html#create-document-from-docx-template>`_ action available. You can use it in conjunction with `Convert DOCX to PDF <../../actions/document-processing.html#convert-docx-document-to-pdf>`_ action to `create PDF documents from a template <create-pdf-from-docx-template.html>`_.