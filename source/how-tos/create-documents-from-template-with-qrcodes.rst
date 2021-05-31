.. title:: How to create PDF, Word, Excel, PowerPoint documents with QR codes from template 

.. meta::
  :description: Quick tips for each type of QR code: URL, phone number, GEO

Generate documents with qr codes from template – 3 quick tips for each type
=============================================================================

In this article, we’ll review a few examples of how you can boost your business processes with `Plumsail document generation <https://plumsail.com/documents/>`_ that supports dynamic QR codes.

QR (stands for “Quick Response”) codes are codes that people can scan with their smartphones to get quick access to something – whatever it be – sign up form, document, location, and so on. 
QR codes in documents can accelerate communication, logistics, marketing, and other business processes at every stage. 

.. contents::
  :local:
  :depth: 1

URL QR code in document templates
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

URL QR codes are the most popular as they can lead to any source. These are just a few common examples:

-	Your company site
-	Sign up form for your product
-	Payment form
-	URL for downloading an app
-	Any document stored in the cloud – contactless menus at restaurants; COVID-19 test results, and more.

The pandemic has made QR codes an integral component of life. 

Let us say, there is a medical laboratory that offers various tests to patients. When test data is ready, the laboratory test report is generated and stored. 
And it should contain a QR code to make the document available for checking online. 

Below are my simple laboratory test report template and the resulting document with the QR code leading to the same document available online.

To get a QR code in the output document, I used a special formatter that lets the templating engine know that I'd like to get a QR code. 

:code:`qrcode(size)` is a formatter for qr codes. For more information, `check the documentation on formatters <../document-generation/common-docx-xlsx/formatters.html>`_.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../_static/files/document-generation/demos/laboratory-test-template.docx>`_           
            .. image:: ../_static/img/document-generation/word-document-template-with-qrcode.png
                :alt: word document template with dynamic qr code

        - `Download result document <../_static/files/document-generation/demos/completed-laboratory-report-with-qrcode.pdf>`_
            .. image:: ../_static/img/document-generation/pdf-document-with-qrcode.png
                :alt: completed pdf document with qr code
           
.. hint:: You can pull data from your system using Power Automate Flow or Zapier, then pass data to populate the document and get the completed document with the QR code generated dynamically. `Check out the integrations of Plumsail Documents <https://plumsail.com/documents/integrations/>`_.

Phone number QR code in document templates
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

It's possible to create a document from a template with phone number QR codes in the output document. For that, you need to insert a token with the :code:`qrcode(size)` formatter as in the previous example. 

The difference is in the data you pass. For a telephone number QR code, value data should be in such format: :code:`tel:+1-234-555-6677`. 

Below are a business card template and the resulting document after merging data. 

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../_static/files/document-generation/demos/employee-card-template.docx>`_           
            .. image:: ../_static/img/document-generation/business-card-template-with-phone-qr-code.png
                :alt: word document template with phine number qr code

        - `Download result document <../_static/files/document-generation/demos/employee-card-phone-qrcode.pdf>`_
            .. image:: ../_static/img/document-generation/completed-pdf-with-phone-qr-number.png
                :alt: completed pdf document with phone number qr code

When someone scans the generated QR code, they will be offered to choose to call, send a text message, or save the contact. 

Geolocation QR code in document template
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Another good option for QR codes in documents is geolocation. As in the previous examples, you indicate that you'd like to get a QR code in the generated document by putting the :code:`qrcode(size)` formatter. 

The data you'll pass to document template should be in this format :code:`geo:40.74018922726678,-74.00869124083648`. 

Use it in documents that are required to include location coordinates. Below is a simple example you can include in your own documents.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../_static/files/document-generation/geo-location-qr-code-template.docx>`_           
            .. image:: ../_static/img/document-generation/docx-template-with-geo-qr-code.png
                :alt: word document template with geo location qr code

        - `Download result document <../_static/files/document-generation/demos/geo-qr-code-result-pdf.pdf>`_
            .. image:: ../_static/img/document-generation/generated-pdf-with-geo-qr-code.png
                :alt: completed pdf document with geo location qr code

Sign up for Plumsail Documents
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If you're new to Plumsail Documents, `sign up for a 30-day free trial <https://auth.plumsail.com/account/Register?ReturnUrl=https://account.plumsail.com/documents/processes/reg>`_ to start your way to document automation.

If you need any help, write us at `support@plumsail.com <mailto:support@plumsail.com>`_

