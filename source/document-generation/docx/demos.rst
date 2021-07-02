Demos for DOCX templates
========================

.. contents:: List of demos
   :local:
   :depth: 1

Sales invoice
-------------
This demo demonstrates how to create a template for an invoice document.

You can find the description  of this case in the `create DOCX document from template <../../user-guide/processes/examples/create-docx-from-template-processes.html>`_ article.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/invoice-template.docx>`_
         
          .. image:: ../../_static/img/document-generation/invoice-template.png
                :alt: invoice template
        - `Download result document <../../_static/files/document-generation/demos/invoice-result-document.docx>`_
         
          .. image:: ../../_static/img/document-generation/invoice-result-document.png
                :alt: invoice result                    

.. rubric:: Template data

.. code:: json

    {
        "invoiceNumber": "432",
        "company": {
            "email": "sales@sample.com",
            "address": "3 Main St.New York NY 97203 USA",
            "phone": "202-555-0131"
        },
        "date": "2018-05-21",
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
                    "name": "Stepler",
                    "price": 12.44
                },
                "quantity": 1000,
                "cost": 12440
            },
            {
                "product": {
                    "name": "Fridge",
                    "price": 4219.99
                },
                "quantity": 1,
                "cost": 4219.99
            },
            {
                "product": {
                    "name": "Microwave",
                    "price": 99.99
                },
                "quantity": 5,
                "cost": 499.95
            },
            {
                "product": {
                    "name": "Pen",
                    "price": 7.23
                },
                "quantity": 100,
                "cost": 723
            }
        ],
        "total": 18872.94
    }

.. _tables:

Regular table
-------------

This demo shows how to create a table based on an array of objects. You can find the description of this case in the `tables <tables.html#table>`_ documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/table-template.docx>`_

          .. image:: ../../_static/img/document-generation/table-template.png
                :alt: Table template
        - `Download result document <../../_static/files/document-generation/demos/table-result.docx>`_

          .. image:: ../../_static/img/document-generation/table-result.png
                :alt: Table template result

.. rubric:: Template data

.. code:: json

    {
        "company": {
            "name": "Plumsail",
            "email": "contact@plumsail.com"
        },
        "employees": [
            {
                "name": "Derek Clark",
                "jobTitle": "Marketing director",
                "department": "Marketing Department",
                "office": "Room 18",
                "phone": "(206) 854-9798"
            },
            {
                "name": "Xue Li",
                "jobTitle": "Financial director",
                "department": "Financial Department",
                "office": "Room 19",
                "phone": "(206) 598-1259"
            },
            {
                "name": "Jessica Adams",
                "jobTitle": "Marketing manager",
                "department": "Marketing Department",
                "office": "Room 23",
                "phone": "(206) 789-1598"
            },
            {
                "name": "Katsuko Kawakami",
                "jobTitle": "Analyst",
                "department": "Financial Department",
                "office": "Room 26",
                "phone": "(206) 784-1258"
            }
        ]
    }

.. _dynamic-table:

Dynamic table
-------------

This demo shows how to create dynamic tables from arrays by just adding a single tag into the template document. You can find the description of this case in the `tables <tables.html#dynamic-table>`_ documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/table-from-array-template.docx>`_

          .. image:: ../../_static/img/document-generation/table-from-array-template.png
                :alt: Table from array template
        - `Download result document <../../_static/files/document-generation/demos/table-from-array-result.docx>`_

          .. image:: ../../_static/img/document-generation/table-from-array-result.png
                :alt: Table from array result

.. rubric:: Template data

.. code:: json

    {
        "myArray": [
            [
                "Meaning",
                "Latin prefix",
                "Greek prefix"
            ],
            [
                "between",
                "inter-",
                "epi-"
            ],
            [
                "above, excess",
                "super-, ultra-",
                "hyper-"
            ],
            [
                "inside",
                "intra-",
                "endo-"
            ],
            [
                "outside",
                "extra-, extro-",
                "ecto-, exo-"
            ]
        ]
    }

Repeat multiple table rows
--------------------------

This demo shows how to occupy multiple table rows by properties of a single object from your source array. You can find the description of this case in the `tables <tables.html#repeat-multiple-table-rows>`_ documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/repeat-multiple-table-rows-template.docx>`_

          .. image:: ../../_static/img/document-generation/repeat-multiple-table-rows-template.png
                :alt: Repeat multiple table rows template
        - `Download result document <../../_static/files/document-generation/demos/repeat-multiple-table-rows-result.docx>`_

          .. image:: ../../_static/img/document-generation/repeat-multiple-table-rows-result.png
                :alt: Repeat multiple table rows result

.. rubric:: Template data

.. code:: json

    [
        {
            "name": "David Navarro",
            "title": "Head of Marketing",
            "aboutMe": "I like programming \nand good coffee."    
        },
        {
            "name": "Jessica Adams",
            "title": "HR",
            "aboutMe": "I enjoy meeting new people and finding ways to help them have an uplifting experience."    
        },
        {
            "name": "Anil Mittal",
            "title": "Sales manager",
            "aboutMe": "I am a dedicated person with a family of four."    
        } 
    ]      

.. _loops-and-nesting:

Loops and nesting
-----------------

This demo demonstrates how to create complex nested documents based on nested objects and collections. You can find the description of this case in the `loops and nesting <loops-and-nesting.html>`_ documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/loops-nesting-template.docx>`_
         
          .. image:: ../../_static/img/document-generation/loops-nesting-template.png
                :alt: Loops and nesting template
        - `Download result document <../../_static/files/document-generation/demos/loops-nesting-result.docx>`_
         
          .. image:: ../../_static/img/document-generation/loops-nesting-result.png
                :alt: Loops and nesting template                    

.. rubric:: Template data

.. code:: json    

    [
        {
            "name": "David Navarro",
            "companies": [
                {
                    "name": "Plumsail",
                    "projects": [
                        {
                            "name": "Plumsail Actions",
                            "achievement": [
                                {
                                    "description": "Design the hardware"
                                },
                                {
                                    "description": "Design the software"
                                },
                                {
                                    "description": "Implement the software"
                                }
                            ]
                        },
                        {
                            "name": "Plumsail Forms",
                            "achievement": [
                                {
                                    "description": "Design everything"
                                },
                                {
                                    "description": "Implement everything"
                                }
                            ]
                        }
                    ],
                    "managers": [
                        {
                            "name": "Derek clark",
                            "title": "Head of Development",
                            "reference": "he likes programming \nand good coffee"
                        },
                        {
                            "name": "Jessica Adams",
                            "title": "CEO",
                            "reference": "I don't know this guy"
                        }
                    ]
                },
                {
                    "name": "Contoso",
                    "projects": [
                        {
                            "name": "Who knows what it was",
                            "achievement": [
                                {
                                    "description": "R&D"
                                },
                                {
                                    "description": "Bureaucracy"
                                }
                            ]
                        }
                    ],
                    "managers": [
                        {
                            "name": "Lots of people",
                            "title": "Managers",
                            "reference": "I saw this guy once in the cafeteria"
                        }
                    ]
                }
            ]
        },
        {
            "name": "Martin Harris",
            "companies": [
                {
                    "name": "Plumsail",
                    "projects": [
                        {
                            "name": "Plumsail Org Chart",
                            "achievement": [
                                {
                                    "description": "Mentor"
                                },
                                {
                                    "description": "Teach"
                                }
                            ]
                        }
                    ],
                    "managers": [
                        {
                            "name": "Anil Mittal",
                            "title": "Founder",
                            "reference": "I like the way he laughs"
                        }
                    ]
                },
                {
                    "name": "Contoso",
                    "projects": [
                        {
                            "name": "Whatever it was",
                            "achievement": [
                                {
                                    "description": "R&D"
                                },
                                {
                                    "description": "Documentation"
                                }
                            ]
                        },
                        {
                            "name": "Another old project",
                            "achievement": [
                                {
                                    "description": "Research"
                                },
                                {
                                    "description": "Development"
                                }
                            ]
                        }
                    ],
                    "managers": [
                        {
                            "name": "Brenda Coel",
                            "title": "Head of Heads",
                            "reference": "he knows the stuff"
                        },
                        {
                            "name": "Xue Li",
                            "title": "CEO",
                            "reference": "Brenda said he knows the stuff"
                        }
                    ]
                }
            ]
        }
    ]

.. _links-and-endnotes:

Links and endnotes
------------------

This demo shows how to add external links and endnotes to your document. You can find the description of this case in the `links and endnotes <external-links.html>`_ section of the documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/external-links-template.docx>`_

          .. image:: ../../_static/img/document-generation/external-links-template-demo.png
                :alt: Table template
        - `Download result document <../../_static/files/document-generation/demos/external-links-result.docx>`_

          .. image:: ../../_static/img/document-generation/external-links-result-demo.png
                :alt: Table template result

.. rubric:: Template data

.. code:: json

    [
        {
            "name": "The Open University",
            "description": "Distance and online courses. Qualifications range from certificates, diplomas and short courses to undergraduate and postgraduate degrees.",
            "linkName": "Go to the site",
            "linkURL": "http://www.openuniversity.edu/courses"
        },
        {
            "name": "Coursera",
            "description": "Online courses from top universities like Yale, Michigan, Stanford, and leading companies like Google and IBM.",
            "linkName": "Go to the site",
            "linkURL": "https://plato.stanford.edu/"
        },
        {
            "name": "edX",
            "description": "Flexible learning on your schedule. Access more than 1900 online courses from 100+ leading institutions including Harvard, MIT, Microsoft, and more.",
            "linkName": "Go to the site",
            "linkURL": "https://www.edx.org/"
        }
    ]

.. _pie-charts:

Pie charts
----------

This demo shows how to build a pie chart in a MS Word document. You can find the description  of this case in the `pie charts <charts.html#pie-charts>`_ documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/pie-chart-template.docx>`_

          .. image:: ../../_static/img/document-generation/pie-chart-template-small-docx.png
                :alt: Pie charts template
        - `Download result document <../../_static/files/document-generation/demos/pie-chart-result.docx>`_

          .. image:: ../../_static/img/document-generation/pie-chart-result-small-docx.png
                :alt: Pie charts result

.. rubric:: Template data

.. code:: json

    [
        {
            "title": "Countries by coffee production",
            "description": "Production in thousand kilogram bags",
            "prod": [
                {
                    "country": "Brazil",
                    "value2017": 51500
                },
                {
                    "country": "Vietnam",
                    "value2017": 28500
                },
                {
                    "country": "Colombia",
                    "value2017": 14000
                },
                {
                    "country": "Indonesia",
                    "value2017": 10800
                },
                {
                    "country": "Honduras",
                    "value2017": 8349
                },
                {
                    "country": "Other countries",
                    "value2017": 61000
                }
            ]
        }
    ]


.. _clustered-column-charts:

Clustered column charts
-----------------------

This demo shows how to build a clustered column chart in a MS Word document. You can find the description of this case in the `clustered column charts <charts.html#clustered-column-charts>`_ documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/clustered-column-template.docx>`_

          .. image:: ../../_static/img/document-generation/clustered-columns-template-small-docx.png
                :alt: Pie charts template
        - `Download result document <../../_static/files/document-generation/demos/clustered-column-result.docx>`_

          .. image:: ../../_static/img/document-generation/clustered-columns-result-small-docx.png
                :alt: Pie charts result

.. rubric:: Template data

.. code:: json

    [
        {
            "title": "Countries by coffee production",
            "description": "Production in thousand kilogram bags",
            "prod": [
                {
                    "country": "Brazil",
                    "value2015": 37600,
                    "value2016": 43200,
                    "value2017": 51500
                },
                {
                    "country": "Vietnam",
                    "value2015": 22000,
                    "value2016": 27500,
                    "value2017": 28500
                },
                {
                    "country": "Colombia",
                    "value2015": 11300,
                    "value2016": 13500,
                    "value2017": 14000
                },
                {
                    "country": "Indonesia",
                    "value2015": 14000,
                    "value2016": 11000,
                    "value2017": 10800
                },
                {
                    "country": "Honduras",
                    "value2015": 7500,
                    "value2016": 5800,
                    "value2017": 8349
                },
                {
                    "country": "Other countries",
                    "value2015": 37358,
                    "value2016": 44229,
                    "value2017": 61000
                }
            ]
        }
    ]

.. _conditionally-hide-blocks:

Conditionally hide blocks
-------------------------
.. note::

  If you use multiple bullet lists or tables, it is better to create a separate alias for each case (``nonDev1`` and ``nonDev2`` of this sample).

This demo shows how to hide table rows, bullet lists items and arbitrary sections of document if there is a specific value in the tag or empty.

You can find the description  of this case in the `conditionally hide blocks <conditionally-hide-blocks.html>`_ documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/conditionally-hide-blocks-template.docx>`_
         
          .. image:: ../../_static/img/document-generation/hide-blocks-demo-template.png
                :alt: hide blocks template
        - `Download result document <../../_static/files/document-generation/demos/conditionally-hide-blocks-result.docx>`_
         
          .. image:: ../../_static/img/document-generation/hide-blocks-demo-result.png
                :alt: hide blocks result

.. rubric:: Template data

.. code:: json    

    {
      "companyName": "Plumsail",
      "site": "http://plumsail.com",
      "contacts": null,
      "employees": [
        {
          "name": "Derek Clark",
          "hireDate": "2012-04-21T18:25:43-05:00",
          "department": "marketing"
        },
        {
          "name": "Jessica Adams",
          "hireDate": "2012-04-21T18:25:43-05:00",
          "department": "sales"
        },
        {
          "name": "Anil Mittal",
          "hireDate": "2016-04-11T14:22:13-02:00",
          "department": "development"
        }
      ]
    }

Watermarks
----------

This demo shows how to add a watermark to a document.

JSON representation of the object:

.. rubric:: Template data

.. code:: json

    {
       watermark: "Classified"
    }

To add a watermark please navigate to the *Design* tab in MS Word, click *Watermark*, then *Custom watermark*, choose *Text watermark* option and simply add :code:`{{watermark}}` tag into the *Text* field.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/watermark-template.docx>`_

          .. image:: ../../_static/img/document-generation/watermark-template.png
                :alt: hide blocks template
        - `Download result document <../../_static/files/document-generation/demos/watermark-result.docx>`_

          .. image:: ../../_static/img/document-generation/watermark-result.png
                :alt: hide blocks result


QR codes
----------

This demo shows how to add QR codes to a document.

JSON representation of the object:

.. rubric:: Template data

.. code:: json

    {
       "OnlineCopyURL": "https://plumsail.com/"
    }

.. code:: json

    {
       "employeePhone": "tel:+1-234-555-6677"
    }

.. code:: json

    {
       "officeAddress": "geo:40.74018922726678,-74.00869124083648"
    }

To add a QR code add :code:`qrcode(size)` tag into your docx template. Find some examples below:

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/laboratory-test-template.docx>`_           
            .. image:: ../../_static/img/document-generation/word-document-template-with-qrcode.png
                :alt: word document template with dynamic qr code

        - `Download result document <../../_static/files/document-generation/demos/completed-laboratory-report-with-qrcode.pdf>`_
            .. image:: ../../_static/img/document-generation/pdf-document-with-qrcode.png
                :alt: completed pdf document with qr code

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/employee-card-template.docx>`_           
            .. image:: ../../_static/img/document-generation/business-card-template-with-phone-qr-code.png
                :alt: word document template with phine number qr code

        - `Download result document <../../_static/files/document-generation/demos/employee-card-phone-qrcode.pdf>`_
            .. image:: ../../_static/img/document-generation/completed-pdf-with-phone-qr-number.png
                :alt: completed pdf document with phone number qr code

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/geo-location-qr-code-template.docx>`_           
            .. image:: ../../_static/img/document-generation/docx-template-with-geo-qr-code.png
                :alt: word document template with geo location qr code

        - `Download result document <../../_static/files/document-generation/demos/geo-qr-code-result-pdf.pdf>`_
            .. image:: ../../_static/img/document-generation/generated-pdf-with-geo-qr-code.png
                :alt: completed pdf document with geo location qr code