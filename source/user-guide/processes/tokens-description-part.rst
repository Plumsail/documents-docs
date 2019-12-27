Use tokens like :code:`{{invoiceNumber}}`, :code:`{{fullName}}`, :code:`{{companyName}}` to get values from your data. 

Those tokens work the same way as in `document templates <../../../document-generation/docx/how-it-works.html>`_ including `value formatters <../../..document-generation/common-docx-xlsx/formatters.html>`_. Additionally, you can use :code:`{{@date}}` token to include current date:

- :code:`{{@date}}` - full current date with time.
- :code:`{{@date}:format(dd.MM.yyyy hh:mm)}` - formatted current date.