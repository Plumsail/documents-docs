.. title:: How to add image watermarks to PDF documents without Acrobat using Power Automate Flow, Azure Logic Apps, or PowerApps

.. meta::
   :description: Add image watermarks to PDF documents automatically without Acrobat in Power Automate (Microsoft Flow), Azure Logic Apps, or PowerApps

Add image watermark to PDF document using Power Automate
=============================================================

If you find yourself in a need to protect your PDF documents, you may decide to add a watermark to them. It can help you to identify the document owner, to maintain some level of traceability, to classify documents, and to assure confidentiality of the information both inside and outside the organization.

We hope this **first article** from our "How to use Watermarks" series will let you get started with watermarking PDFs using `Plumsail Documents <https://plumsail.com/documents/>`_ in Power Automate (Microsoft Flow).

  **Here is the list of all the articles in the series:**

  1. How to use **an image type watermark** to automatically add a company logo to PDF files and save them in a new folder.

  2. How to use `a text type watermark <../../../flow/how-tos/documents/add-a-text-watermark-to-a-PDF-document.html>`_ to prevent documents dissemination.

  3. How to use `a PDF type watermark <../../../flow/how-tos/documents/add-a-PDF-watermark-to-a-PDF-document.html>`_ to add a watermark with a specific design to PDF documents generated on submitting a form.

*Add watermark to PDF* action supports a few types of watermarks  —  Text, Image, and PDF:

.. image:: ../../../_static/img/flow/documents/add-a-watermark-to-pdf-select-type.png
    :alt: Selection of the watermark type

So, let us have a look at how to add an image watermark to a document.

Use image type watermark to add a company logo
----------------------------------------------

One of the most effective ways to protect PDFs files or to retain corporate identity across documents is to add the company logo to them. Even if a document is spread further than you intended, the watermark will identify you as the owner.

Imagine, you are storing your company files somewhere in a cloud, for example, OneDrive, and want to add an image watermark to new PDF files.

When a new file is added to a folder Files in OneDrive, we will add an image watermark to it and save it in a new folder named *WatermarkedFiles*.

Here is how our flow will look like:

.. image:: ../../../_static/img/flow/how-tos/Watermark-new-files-in-a-folder.png
    :alt: Use image type watermark to add a company logo flow

Let us have a closer look at each step of the flow.

Create the flow
----------------

Flow trigger
~~~~~~~~~~~~

Please navigate to `MS Flow <https://emea.flow.microsoft.com>`_, create a flow and find *OneDrive  —  When a file is created* action. Using this trigger will allow you to start the flow on adding a file into a folder. Set the name of the source folder:

.. image:: ../../../_static/img/flow/how-tos/Watermark-new-files-in-a-folder-source-folder.png
    :alt: OneDrive  —  When a file is created action

Get file content
~~~~~~~~~~~~~~~~

Find *Get file content using path* action from *OneDrive* connector. Put here **File Path** from the output of the previous action:

.. image:: ../../../_static/img/flow/how-tos/Watermark-new-files-in-a-folder-get-file-content.png
    :alt: OneDrive  —  Get file content using path

Get watermark file content
~~~~~~~~~~~~~~~~~~~~~~~~~~

Get the file you are going to use as the watermark. We store it in SharePoint. You can use any other connector to get files from your system.

.. image:: ../../../_static/img/flow/how-tos/Watermark-new-files-in-a-folder-get-watermark-file-content.png
    :alt: SharePoint  —  Get file content

Add a watermark to PDF
~~~~~~~~~~~~~~~~~~~~~~

This is an action from `Plumsail Documents connector <https://plumsail.com/documents>`_.

Choose **Image** type of the watermark. Put **File content** from the output of the *Get file content using path* action into the **Document content** field, and the **File content** from the previous action into the **Image content** field.

We set custom values for **Watermark position, Opacity, Watermark Image** width. You may check detailed information on how to use these and other settings `here <../../../flow/actions/document-processing.html#add-image-watermark-to-pdf>`_.

.. image:: ../../../_static/img/flow/how-tos/Watermark-new-files-in-a-folder-add-watermark.png
    :alt: Plumsail Documents —  Add a watermark to PDF

Create file
~~~~~~~~~~~

Create a file in another folder. We used *Create file* action from *OneDrive* connector, but you can save your file in any other cloud service.

.. image:: ../../../_static/img/flow/how-tos/Watermark-new-files-in-a-folder-create-file.png
    :alt: OneDrive —  Create file

So, here is our result document watermarked with a large Plumsail logotype on the background:

.. image:: ../../../_static/img/flow/how-tos/InternalRulesAndRegulationsResult.png
    :alt: Result document watermarked with an image type watermark

Conclusion
----------

We hope this `series of articles <../../../flow/how-tos/documents/add-an-image-watermark-to-a-PDF-document.html#how-to-add-an-image-watermark-to-a-pdf-document>`_ on using *Add watermark to PDF* action will help you to ascertain the proper use of your PDF documents.  If you haven't used  `Plumsail Documents <https://plumsail.com/documents/>`_ yet, `registering an account <https://plumsail.com/docs/documents/v1.x/getting-started/sign-up.html>`_ would be the first step. It is quite easy to get started.

.. Hint:: For more security options please have a look at `Protects PDF action <https://plumsail.com/docs/documents/v1.x/flow/actions/document-processing.html#protect-pdf-document>`_. It allows you to add passwords, copy-, printing-, and other protections to PDF files with the help of Power Automate (Microsoft Flow) and Azure Logic Apps.