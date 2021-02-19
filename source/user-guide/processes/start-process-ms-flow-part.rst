You can use `Plumsail Documents connector <https://emea.flow.microsoft.com/en-us/connectors/shared_plumsail/plumsail-documents/>`_ for Power Automate (Microsoft Flow) to start a process. Start by `creating an API key <https://plumsail.com/docs/documents/v1.x/user-guide/api-keys.html>`_. You will need it in your Flow.

Then add the `Start process <../flow/actions/document-processing.html#start-process>`_ action to your Flow. You will be asked for *'Connection Name'* and for *'Access Key'*. You can type any name for the connection. For example, *'Plumsail Documents'*. Then paste API key that you created earlier to *'Access Key'*.

.. image:: /_static/img/getting-started/create-flow-connection.png
   :alt: Screen of Plumsail Documents

Optionally, once the action is executed you can get the result document as an output of the action and continue to work with it in your Flow.

Here is an example of a simple Flow that starts a process and then sends the generated document for approval:

.. image:: /_static/img/user-guide/processes/start-process-flow.png
    :alt: Start process flow

The above example of Flow has a manual trigger for simplicity. But you can trigger your Flow on various events - for example, for a selected item in the SharePoint list, or When a new item is created in the SharePoint list, or various Web forms submissions - actually, there are too many cases to list them. Use different triggers to populate document templates with data from your web-services.

.. rubric:: Please, find out examples of Power Automate Flows with processes:

- `Create documents from a template and electronically sign using AdobeSign <https://plumsail.com/docs/documents/v1.x/user-guide/processes/examples/create-document-from-template-and-sign-abobesign.html>`_
- `Create documents from a template and electronically sign using SignNow <https://plumsail.com/docs/documents/v1.x/user-guide/processes/examples/create-document-from-template-sign-signnow.html>`_
- `Create custom documents from Dynamics 365 CRM <https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/create-custom-pdf-invoice-from-d365.html>`_
- `Create Word and PDF documents from Microsoft Forms <https://plumsail.com/docs/documents/v1.x/user-guide/processes/examples/create-word-and-pdf-documents-from-microsoft-forms.html>`_
- `Create Word and PDF documents from Cognito Forms <https://plumsail.com/docs/documents/v1.x/user-guide/processes/examples/create-word-and-pdf-documents-from-cognito-forms.html>`_
- `Create Word and PDF documents from Typeform <https://plumsail.com/docs/documents/v1.x/user-guide/processes/examples/create-word-and-pdf-documents-from-typeform.html>`_
- `Create Word and PDF documents from Jotform <https://plumsail.com/docs/documents/v1.x/user-guide/processes/examples/create-word-and-pdf-documents-from-jotform.html>`_
- `Create Excel and PDF documents from Plumsail Forms <https://plumsail.com/docs/documents/v1.x/user-guide/processes/examples/create-excel-and-pdf-documents-from-plumsail-forms.html>`_
- `Create Excel and PDF documents from Microsoft Forms <https://plumsail.com/docs/documents/v1.x/user-guide/processes/examples/create-excel-and-pdf-documents-from-microsoft-forms.html>`_
- `Create Excel and PDF documents from Cognito Forms <https://plumsail.com/docs/documents/v1.x/user-guide/processes/examples/create-Excel-and-pdf-documents-from-cognito-forms.html>`_
- `Create Excel and PDF documents from Typeform <https://plumsail.com/docs/documents/v1.x/user-guide/processes/examples/create-excel-and-pdf-documents-from-typeform.html>`_
- `Read CSV and batch generate PDF documents <https://plumsail.com/docs/documents/v1.x/user-guide/processes/examples/create-html-and-pdf-from-template-from-csv.html>`_
