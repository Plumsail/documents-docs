How to create a document from a template in Microsoft Flow and sign it using SignNow
####################################################################################

In this article, we will show you how easy is to create any document from a template using `Plumsail documents connector`_ for `Microsoft Flow`_ and sign the ready document with the help of `SignNow connector`_. 

`SignNow`_ is an electronic signature cloud-based software, which makes it easy to sign and manage documents on any device. The modern world looks for quick and paperless solutions. You may want too. If you use an AdobeSign system for e-signs or just want to compare SignNow with an alternative variant, read our article `How to create a document from a template and sign it using AdobeSign`_.

So, in this article, we will automate creating a contract from a template. Then the contract will be sent to our customer via SignNow for signing.

Here is how our completed Flow will look:

|sign_now_flow|

We will show you how to create such a Flow step by step.

**Flow trigger**

After you’ve opened `My Flows`_, create a new one and select a trigger. Actually, you can pick any, for example, trigger a Flow when an opportunity in CRM is closed, or a new item is added to SharePoint list, or some others. We will pick *'Manually trigger a Flow'* just for demonstration purposes. 

**Get file content**

This action takes the content of the specified files from a document library. We store our files in a SharePoint library, but also it might be another file storage system like OneDrive or Dropbox. 

In our case, we need to specify the URL of the SharePoint site and path to our agreement template.

|get_content|

**Create DOCX document from template**

With Plumsail documents connector for Microsoft Flow, it’s very simple to generate documents from a template.  Assign *'Create DOCX from template'* after the *'Get file content'* step. You can find more information about this action by visiting `this page`_.

It has two parameters:

1.	Document content.
2.	Template data.

|docx_from_template|

Mind, If you use the Plumsail documents action for the first time, you’ll be asked for *'Connection Name'* and *'Access Key'*. You can type any name for the connection. For example, *'Plumsail Documents'*.

Then `create an API key in your Plumsail Account page`_, copy and paste it to the *'Access Key'* field.

We’re moving on. For *'File content'*, select an output of the previous step.

To fill in the *'Template data'* field use JSON data, it will be applied to our agreement template, which you can download by clicking `here`_. 

If you have a look at our template, you will see that all the variables are put between :code:`{{ }}` brackets. Once we specify it with JSON, these fields will be automatically filled. 

You can create your own templates using this approach. It’ very simple. How the whole process works read `here.`_

Here is JSON for our current Flow:

.. code:: json

    {
        "Number": "432",
        "Execution.date":"2020-05-25",
        "delivery.date":"2020-05-30",
        "buyer.name":"LUCKY LLC",
        "buyer.address":"3 Main St.New York NY 97203 USA",
        "company": {
           "email": "sales@sample.com",
           "address": "3 Main St.New York NY 97203 USA",
           "phone": "202-555-0131",
           "name": "Plumsail LLC"
        },
        "items": [
            {
                "product": {
                   "name": "Monitor",
                   "price": 99
                 },
                "quantity": 10,
                "cost": 990
                },
                {
                "product": {
                    "name": "Fridge",
                    "price": 4219.99
                },
                "quantity": 1,
                "cost": 4219.99
              }
        ],
        "total": 5209.99
    }


With Plumsail Documents, you can generate documents in different formats from a template:

- `DOCX`_
- `XLSX`_
- `HTML`_
- `TXT`_

**Create file**

For further use, our ready-for-sign agreement has to be stored somewhere. For that, select *'Сreate file'* action. In this example, we store files in the SharePoint document library. So, specify the SP site URL and path to the folder, to which the file will be saved. 

Don’t miss :code:`.DOCX` extension in the *'File name'* field. 

'File content' will be the result file of 'creating DOCX from a template' step.

|create_file|

**Upload document**

This action is from the SignNow connector for Microsoft Flow. It will upload the resulting contract to the SignNow account, after that we can send the document for signature. In the 'File' field put :code:`Result file` – Dynamic content output of the 'Create DOCX from template' step.

|upload_document|

**Invite to sign**

The last action is from the SignNow connector too. It sends the contract for signing. Just type in an e-mail address of a recipient and select :code:`Document ID` in Dynamic content.

|invite_to_sign|

Once the agreement has been signed, you will receive a notification e-mail with the signed document attached. 

|signed_contract|

Now you have an idea how to automate your workflow with the help of Plumsail Documents connector for Microsoft Flow. Find more simple solutions on creating Flows for your operational processes amoung our `Flow examples`_. If you are new to Plumsail Documents, feel free to `sign up for an account`_ and get a 30-Day free trial. It’s easy `to get started`_. 




.. |sign_now_flow| image:: /_static/img/flow/how-tos/sign_now_flow.png
.. |get_content| image:: /_static/img/flow/how-tos/get_content_signnow.png
.. |docx_from_template| image:: /_static/img/flow/how-tos/docx_from_template_sn.png
.. |create_file| image:: /_static/img/flow/how-tos/create_file_sn.png
.. |upload_document| image:: /_static/img/flow/how-tos/upload_doc_sn.png
.. |invite_to_sign| image:: /_static/img/flow/how-tos/invite_to_sign.png
.. |signed_contract| image:: /_static/img/flow/how-tos/notification_sn.png





.. _SignNow connector: https://docs.microsoft.com/en-us/connectors/signnow/
.. _Plumsail documents connector: https://plumsail.com/documents/
.. _Microsoft Flow: https://flow.microsoft.com/en-us/
.. _How to create a document from a template and sign it using AdobeSign: https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/create-a-document-from-template-and-sign-Abobesign.html
.. _SignNow: https://www.signnow.com/
.. _My Flows: https://emea.flow.microsoft.com/manage/flows
.. _this page: https://plumsail.com/docs/documents/v1.x/flow/actions/document-processing.html#create-docx-document-from-template
.. _create an API key in your Plumsail Account page: https://plumsail.com/docs/documents/v1.x/getting-started/sign-up.html
.. _here: https://plumsailonline.sharepoint.com/:w:/s/Anjelika/EWJQZezSnjNJtrX5CkhDZ4oB6yHZ3bsxZfcO3nbYzwqleA?e=0eD1iR
.. _here.: https://plumsail.com/docs/documents/v1.x/document-generation/docx/how-it-works.html
.. _DOCX: https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/create-docx-from-template.html
.. _XLSX: https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/create-xlsx-from-template.html
.. _HTML: https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/create-html-from-template.html
.. _TXT: https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/create-text-from-template.html
.. _to get started: https://plumsail.com/docs/documents/v1.x/getting-started/sign-up.html
.. _sign up for an account: https://account.plumsail.com/
.. _Flow examples: https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/index.html
