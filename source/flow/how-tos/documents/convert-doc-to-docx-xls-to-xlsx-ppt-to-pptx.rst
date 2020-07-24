.. title:: Batch convert DOC to DOCX, XLS to XLSX, PPT to PPTX in Power Automate Flow

.. meta::
   :description: Bulk convert DOC to DOCX, XLS to XLSX, PPT to PPTX in SharePoint library or other storage using Microsoft Power Automate

How to convert DOC, XLS, PPT documents to DOCX, XLSX, PPTX respectively using Power Automate (Microsoft Flow)
=============================================================================================================

In this article, you will find out how you can easily convert older formats of Microsoft Office documents into modern ones in bulk with the help of `Power Automate (Microsoft Flow)`_ and `Plumsail Documents`_.  Since Microsoft developed new extensions, sooner or later everyone faces a necessity to convert DOC to DOCX, XLS to XLSX and PPT to PPTX. Benefits of new formats are obvious, useful features were added and files weight less so it’s easier to use them online. 

Imagine, you have a SharePoint library (or files storage in any other system) full of DOC, XLS, PPT files which you need to convert to modern extensions.

|lib1_lib2|

In this article we’ll show how you can do it massively using actions from `Plumsail Documents connector`_ for Power Automate (Microsoft Flow):

- `Convert DOC to DOCX`_
- `Convert XLS to XLSX`_
- `Convert PPT to PPTX`_


Convert DOC to DOCX
-------------------

Let’s begin with the most common case – converting DOC to DOCX.
First, open `Power Automate (Microsoft Flow)`_.  In *'My flows'* create a new one and select *'Manually trigger a flow'* as a trigger.
At the end, the flow will look like this. 

|wholeflow|

Here is a step-by-step description.

**Get files (properties only)**

After setting a manual trigger for the flow, add *'A new action'* – for it, search for a SharePoint Connector and the ‘Get files’ action. 

Navigate to the SharePoint library you want to convert documents from. To get only DOC files from there, use a very convenient tool like an `ODATA filter`_ (in advanced options). `Here`_ you can read about its syntax and find some examples how to apply it to query concrete parameters.

In our case, you need to set a value for the files format. SharePoint libraries have a column with extensions. Its name is :code:`File_x0020_Type`. So the query will be :code:`File_x0020_Type` equals (:code:`eq` in ODATA syntax) :code:`'doc'` (value should be put between single quotes).

|ODATA_filter|

For the next steps set up Control **‘Apply to each’** and in the first field you’ll be asked to select an output from the previous step. Choose :code:`Value` from a dynamic content.

**Get file content**

Assign the ‘Get file content’ action for a SharePoint connector. It takes content of the specified files from a document library. Now you need to set a dynamic content :code:`Identifier`.

|identifier|

**Convert DOC to DOCX**

After that, use a `Plumsail Documents connector`_ and the `Convert DOC to DOCX`_ action. When you add an action for the first time, you’ll be asked for *''Connection Name''* and *''Access Key''*. You can type any name for the connection. For example, *''Plumsail Documents''*. 

Then `create an API key in your Plumsail Account page`_, copy and paste it to *''Access Key''* field.

Document content will be the result of the ‘Get file content’ step. 

|convert_doc_to_docx|

**Create file**

The final part is saving your DOCX files into a separate folder. Add an action, search for the SharePoint ‘Create file’. Fill in all required fields like in the image. 

|saving_docx|

The flow is ready, run it and check the target SharePoint library. 


Convert XLS to XLSX
-------------------

To convert all your XLS files into XLSX just build the same flow, but type in :code:`File_x0020_Type eq 'xls'` in the ODATA filter query field to get all XLS files from the SharePoint library.

|query_xls|

Assign `Convert XLS to XLSX`_ instead of ‘DOC to DOCX’ in the Plumsail Documents action. And save the result files with :code:`.xlsx` extension. 

|saving_xls|


Convert PPT to PPTX
-------------------

The same flow works for converting PPT to PPTX. Query all PPT files by using ODATA filter just the same way, but the file type equals PPT – fill in a field with :code:`File_x0020_Type eq 'ppt'`.

|query_ppt|

Assign  `Convert PPT to PPTX`_ in Plumsail Documents step. Save the result files with :code:`.pptx` extension.

|saving_ppt|


Now you know how to use `Plumsail Documents`_ to convert DOC to DOCX, XLS to XLSX, PPT to PPTX. If you haven’t tried it yet, feel free to press `Start trial`_ and see `the documentation`_ for details. You will find a lot of useful `Power Automate (Microsoft Flow) examples`_ which will help you to automate your operational processes. It is quite easy to get started. 



.. |lib1_lib2| image:: /_static/img/flow/how-tos/lib1_lib2.png
.. |wholeflow| image:: /_static/img/flow/how-tos/wholeflow.png
.. |ODATA_filter| image:: /_static/img/flow/how-tos/odata_filter.png
.. |identifier| image:: /_static/img/flow/how-tos/identifier.png
.. |convert_doc_to_docx| image:: /_static/img/flow/how-tos/convert_doc_to_docx.png
.. |saving_docx| image:: /_static/img/flow/how-tos/saving_docx.png
.. |query_xls| image:: /_static/img/flow/how-tos/query_xls.png
.. |saving_xls| image:: /_static/img/flow/how-tos/convert_xls_to_xlsx.png
.. |query_ppt| image:: /_static/img/flow/how-tos/query_ppt.png
.. |saving_ppt| image:: /_static/img/flow/how-tos/saving_pptx.png






.. _Power Automate (Microsoft Flow): https://flow.microsoft.com/en-us/
.. _Plumsail Documents: https://plumsail.com/documents/
.. _Plumsail Documents connector: https://plumsail.com/documents/
.. _Convert DOC to DOCX: https://plumsail.com/docs/documents/v1.x/flow/actions/document-processing.html#convert-doc-to-docx
.. _Convert XLS to XLSX: https://plumsail.com/docs/documents/v1.x/flow/actions/document-processing.html#convert-xls-to-xlsx
.. _Convert PPT to PPTX: https://plumsail.com/docs/documents/v1.x/flow/actions/document-processing.html#convert-ppt-to-pptx
.. _ODATA filter: https://flow.microsoft.com/en-us/blog/advanced-flow-of-the-week-filtering-with-odata/
.. _here: https://flow.microsoft.com/en-us/blog/advanced-flow-of-the-week-filtering-with-odata/
.. _Convert DOC to DOCX: https://plumsail.com/docs/documents/v1.x/flow/actions/document-processing.html#convert-doc-to-docx
.. _Plumsail Documents connector: https://plumsail.com/documents/
.. _create an API key in your Plumsail Account page: https://plumsail.com/docs/documents/v1.x/getting-started/sign-up.html
.. _Convert XLS to XLSX: https://plumsail.com/docs/documents/v1.x/flow/actions/document-processing.html#convert-xls-to-xlsx
.. _Convert PPT to PPTX: https://plumsail.com/docs/documents/v1.x/flow/actions/document-processing.html#convert-ppt-to-pptx
.. _Power Automate (Microsoft Flow) examples: https://plumsail.com/docs/documents/v1.x/index.html
.. _Start trial: https://plumsail.com/documents/
.. _the documentation: https://plumsail.com/docs/documents/v1.x/index.html?_ga=2.255047816.1471117182.1560166578-1778584084.1559557652



