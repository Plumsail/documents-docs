You can insert data from you data using tokens. Let us assume, your data has property "invoiceNumber". In this case you can include it using token :code:`{{invoiceNumber}}`. 

.. We use global URLs here to guarantee they are not broken when rst is included in other files.

Those tokens work the same way as in `document templates <https://plumsail.com/docs/documents/v1.x/document-generation/docx/index.html>`_ including `value formatters <https://plumsail.com/docs/documents/v1.x/document-generation/common-docx-xlsx/formatters.html>`_. Additionally, you can use :code:`{{@date}}` token to include current date:

- :code:`{{@date}}` - full current date with time.
- :code:`{{@date}:format(dd.MM.yyyy hh:mm)}` - formatted current date.