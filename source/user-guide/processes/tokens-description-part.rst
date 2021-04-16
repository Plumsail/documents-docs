You can insert values from your data using tokens.
Their list is available by clicking ``{ }``.

Let us assume your data has property *invoiceNumber*.
In this case, you can include it using token :code:`{{invoiceNumber}}`. 
The tokens work in the same way as in `document templates`_ including `value formatters`_.
Additionally, you can use :code:`{{@date}}` token to include current date:

- :code:`{{@date}}` - full current date with time.
- :code:`{{@date}:format(dd.MM.yyyy hh:mm)}` - formatted current date.

.. We use global URLs here to guarantee they are not broken when rst is included in other files.

.. _document templates: https://plumsail.com/docs/documents/v1.x/document-generation/docx/index.html
.. _value formatters: https://plumsail.com/docs/documents/v1.x/document-generation/common-docx-xlsx/formatters.html