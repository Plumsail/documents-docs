.. title:: Auto populate fillable PDF form fields on web form submission

.. meta::
   :description: Automatically apply form submission data to fillable PDFs using Automate (Microsoft Flow), Azure Logic Apps, and PowerApps

How to auto-populate fillable PDF on Plumsail Forms submission
==============================================================

In this article, you will learn how to automate the generation of documents in your company. For example, applications, orders, invoices, cards and others. We’ll show you how to automatically populate fillable PDF on `Plumsail Forms <https://plumsail.com/forms/>`_ submission by its integration with `Processes <../../../user-guide/processes/index.html>`_.

**Processes** are a `Plumsail Documents <https://plumsail.com/documents/>`_ feature with an intuitive interface for creating documents from templates. 

By means of **Plumsail Forms**, you can design elegant, responsive, and highly customizable forms for SharePoint Modern UI or any web page. In our example, we will collect data from a *Web Form*, apply it to a fillable PDF with the help of *Processes*.

.. contents::
    :local:
    :depth: 2

Create a fillable PDF
---------------------

Follow `this instruction <../../../document-generation/fillable-pdf/index.html>`_ to create a fillable PDF. `Download the template file <../../../_static/files/flow/how-tos/fill-in-pdf-form-template.pdf>`_ for this article.


.. image:: ../../../_static/img/flow/how-tos/fill-in-pdf-form-template.png
    :alt: fill in pdf form template

Create a Form
-------------

We have already designed an application for employment form. Here it is:

.. image:: ../../../_static/img/flow/how-tos/application-employment-form.png
    :alt: Plumsail Form image

You can use our ready form template for an employment application. `Download the file <../../../_static/files/flow/how-tos/Application-for-employment.xfds>`_ and import it to the Plumsail Forms designer. 

To create such a form yourself, follow `this link <https://plumsail.com/docs/forms/design.html>`_ to learn more about how to design Plumsail Web Forms. 

**Understanding Internal Names of Form's fields**

It’s crucial to understand the **internal names** of Form's fields. They must correspond to fields' names in a fillable PDF. You can set internal names for Form’s fields in its general propeties:

.. image:: ../../../_static/img/flow/how-tos/internalname.png
    :alt: Internal names of form's fields

Data from this field will fill in the corresponding field in our fillable PDF. Its name is **FirstName** as well.

.. image:: ../../../_static/img/flow/how-tos/field-name-fillable-pdf.png
    :alt: Fillable PDF field and its name

SingleChoice fields in our Plumsail Form correspond to radio buttons in the fillable PDF. So, they should have not only the same general name but the same options. 

**Example**: We have a SingleChoice in the Plumsail form with **Yes** and **No** options. Its internal name is **CurrentlyWorking**. 

.. image:: ../../../_static/img/flow/how-tos/single_choice.png
    :alt: single choice in Form

In fillable PDF we create **two** radio buttons. The general name is the same for two of them – **CurrentlyWorking**. 

.. image:: ../../../_static/img/flow/how-tos/general_name_rudiobutton.png
    :alt: name of radiobutton in PDF form

In properties options, we set a radio button choice – **Yes** for one and **No** for another radio button.

.. image:: ../../../_static/img/flow/how-tos/radiobutton_choice.png
    :alt: name of radiobutton in PDF form

Configure the Process
-----------------------

When our fillable PDF and Plumsail Form are ready, we proceed to configure the Process. It will apply data from the form submission to the fillable PDF. 

Create a new process
~~~~~~~~~~~~~~~~~~~~

To create a new process, go to `the Processes section <https://auth.plumsail.com/account/Register?ReturnUrl=https://account.plumsail.com/documents/processes/reg>`_ in your Plumsail account. 

Click on the *Add process* button.

.. image:: ../../../_static/img/user-guide/processes/how-tos/add-process-button.png
    :alt: add process button

Set the Process name. Select a Fillable PDF for a template type. 

.. image:: ../../../_static/img/flow/how-tos/create-new-process-plumsail-forms.png
    :alt: generate PDF from Plumsail Forms 

Click the *Next* button. You'll be offered to upload a fillable PDF template. 

.. image:: ../../../_static/img/user-guide/processes/upload-fillable-pdf-template.png
    :alt: upload PDF form template

Configure a template
~~~~~~~~~~~~~~~~~~~~~
After you've provided the template file, you'll jump to the next step - **Configure template**.

It includes two substeps:

- Editor;
- Settings.

In `Editor <../online-editor.html>`_, it's possible to upload a new fillable PDF template. And download it to your PC.

Another feature here is testing the template. It helps you to get a sight of the resulting document and decide if you're satisfied with it.

Just click the *Test template*. You'll see the dialog where to put the source data in JSON format. 

.. image:: ../../../_static/img/user-guide/processes/how-tos/test-fillable-pdf-template.png
    :alt: Test fillable PDF template

To test the PDF form template from this example, copy and paste this JSON data:

.. code:: json

    { 
    "FirstName": "David",
    "LastName": "Navarro",
    "Address": "3 Main St.",
    "City": "New York",
    "PostalCode": "972013",
    "PhoneNumber": "202-555-0131",
    "Email": "david@sample.com",
    "Activities": "Sports: football, basketball, volleyball",
    "CurrentlyWorking": true,
    "HistoryCompany": "Acme Corp",
    "HistoryAddress": "123 James St. Miami, USA",
    "HistorySupervisor": "Derek Clark",
    "HistoryPhoneNumber": "555-777-9999",
    "HistoryPosition": "Marketing director",
    "HistoryDuties": "Developing marketing strategy",
    "HistoryLeaving": "Moving to another city",
    "HistoryContact": true,
    "Date": "06/30/2020"
    }

.. note:: It's testing, we'll pass data from Plumsail web forms to the process. See the `Start process section <#start-the-process-on-plumsail-forms-submission>`_. 

In the **Settings** substep, you customize the following settings:

**Template mode**

It is *Testing* by default. It means you won't be charged for this process runs, but result documents will have a Plumsail watermark. Change it to *Active* to remove the watermark.

**Output filename**

Use tokens to make it personalized. They work the same way as in the template. 

.. hint:: You can `protect your final PDF document with a watermark, by setting a password, or disabling some actions <../configure-settings.html#add-watermark>`_. 

**Test template**

You can test the template from the Settings as well - to check how the customized settings will appear in the resulting document. The procedure is the same as we've already described above.

.. image:: ../../../_static/img/flow/how-tos/Configure-template-fillable-pdf1.png
    :alt: Configure template

.. note:: **Lock form fields** option is activated by default. If you want to edit fields in the result PDF file - disable the option.

Delivery
~~~~~~~~

The next step is delivery. For demonstrating purposes, let us set an email delivery. 

Fill-in a recipient email. Add recipients for a copy or blind copy if you need. Define the subject of the letter. And write an email body. 

You can use tokens from your template to specify details in the email subject as we did, or in the body. The submitted data will be applied to them as well. Find out more about `using tokens <../../../user-guide/processes/tokens-in-process-fields.html>`_.

.. image:: ../../../_static/img/flow/how-tos/send-email-populate-pdf.png
    :alt: send email delivery

You can configure as many deliveries as you need. Check all the available options and how to handle them `here <../../../user-guide/processes/create-delivery.html#list-of-available-deliveries>`_.

Start the Process on Plumsail Forms submission
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

We will start our Process by submitting the Plumsail Web Form.

For that, we will bind it. Press the *Bind* button and select the form from the dropdown. 

.. image:: ../../../_static/img/flow/how-tos/bind-the-form.png
    :alt: bind the form

Once we've done it, the Form will appear in the list of Plumsail Forms bound to this Process. 

.. image:: ../../../_static/img/flow/how-tos/binded-forms-list.png
    :alt: auto-populate pdfs on plumsail form submission

Every time somebody submits the form, the Process of population fillable PDF documents will start. It will apply the Form submission data to the fillable PDF and send the result document by email.

See how the result file looks:

.. image:: ../../../_static/img/flow/how-tos/fill-in-pdf-form-result.png
    :alt: fill in pdf form result

Sign up for Plumsail Documents
------------------------------

To fully automize the generation and flow of your documents, `register a Plumsail account <https://auth.plumsail.com/Account/Register?ReturnUrl=https://account.plumsail.com/documents/processes/reg>`_. It's easy to get started and save time with the help of Plumsail Documents.

.. hint:: Check another article on `how to automatically populate fillable PDFs with SharePoint list data in Power Automate <../../../user-guide/processes/examples/fill-pdf-form-processes.html>`_. 