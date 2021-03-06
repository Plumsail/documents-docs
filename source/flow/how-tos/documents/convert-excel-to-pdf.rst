.. title:: How to convert and save Excel to PDF in Power Automate Flow and Azure Logic Apps

.. meta::
   :description: Automatically convert XLSX to PDF format and save using Power Automate and Azure Logic Apps

Convert XLSX to PDF in Power Automate 
=====================================

This article describes how to achieve a pixel-perfect XLSX Excel document to PDF conversion in `Power Automate (Microsoft Flow) <https://flow.microsoft.com>`_. 

We will take a purchase order as a sample Excel document:

.. image:: ../../../_static/img/flow/how-tos/xlsx-sample.png
   :alt: Excel sample to convert to PDF

Use `this link <../../../_static/files/flow/how-tos/Purchase%20Order%20Example.xlsx>`_ to download it.

Our document has to be stored somewhere. Power Automate (Microsoft Flow) has a lot of connectors for different systems. Here are just a few of them:

- SharePoint
- Salesforce
- Box
- OneDrive
- Google Drive
- Dropbox
- SFTP
- File System

You can store your source file anywhere. In this example, we will store our document in OneDrive. Our Flow will get a file from OneDrive, convert it to PDF and store generated file back to OneDrive. 

This is how complete flow looks:

.. image:: ../../../_static/img/flow/how-tos/convert-xlsx-to-pdf-flow.png
   :alt: pixel perfect Excel to PDF conversion flow

Here is step by step description for the flow.

**Flow trigger**

You can actually pick any trigger. For example, you can start Flow on file creation in a SharePoint document library. We use "Manually trigger a flow" trigger here to simplify the Flow.

**Get file content**

This action gets the file content of the specified file from the OneDrive folder.

You can use any other connector to get files from your system.

**Convert XLSX to PDF**

This is an action from `Plumsail Documents connector <https://plumsail.com/documents>`_. It will convert our Excel document, and we'll receive the pixel-perfect PDF output. 

Just put XLSX file content from the output of the previous action and receive PDF file content as an output of this action.

You can find more information about this action `here <../../actions/document-processing.html#convert-xlsx-document-to-pdf>`_.

**Create file**

Now you need to store PDF file somewhere. In our example, we use "Create file" action OneDrive connector to store the PDF document. 

.. image:: ../../../_static/img/flow/how-tos/excel-generated-pdf-onedrive.png
   :alt: the ready pixel perfect pdf in OneDrive

You can use any other connector to store PDF document into your system.

.. hint:: There is also `Create document from XLSX template <../../actions/document-processing.html#create-document-from-xlsx-template>`_ action available. You can use it in conjunction with `Convert XLSX to PDF <../../actions/document-processing.html#convert-xlsx-document-to-pdf>`_ action to `create PDF documents from a template <create-pdf-from-xlsx-template.html>`_.