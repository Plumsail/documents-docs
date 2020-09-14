Demos for XLSX templates
========================

.. contents:: List of demos
   :local:
   :depth: 1

Purchase Order
--------------
This demo demonstrates how to create a template for a Purchase Order document.

You can find description of this case in `Create XLSX from template </flow/how-tos/documents/create-xlsx-from-template.html>`_  article.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document </_static/files/document-generation/demos/purchase-order-template.xlsx>`_
         
          .. image:: /_static/img/document-generation/purchase-order-template.png
                :alt: purchase order template
        - `Download result document </_static/files/document-generation/demos/purchase-order-result.xlsx>`_
         
          .. image:: /_static/img/document-generation/purchase-order-result.png
                :alt: purchase order result

.. rubric:: Template data

.. code:: json

    {
      "Order": {
        "Date": "2018-05-21",
        "Number": "432"
      },
      "Vendor": {
        "CompanyName": "Acme Corp",
        "Address": "123 James Street, Miami, USA",
        "Email": "sample@acme.com",
        "Phone": "555-777-9999"
      },
      "ShipTo": {
        "CompanyName": "Contoso Inc.",
        "Address": "1234 North Expressway, Arizona, USA",
        "Email": "sample@contoso.com",
        "Phone": "111-222-8900"
      },
      "items": [
        {
          "product": {
            "name": "Monitor",
            "price": 99
          },
          "quantity": 10
        },
        {
          "product": {
            "name": "Stepler",
            "price": 12.44
          },
          "quantity": 1000
        },
        {
          "product": {
            "name": "Fridge",
            "price": 4219.99
          },
          "quantity": 1
        },
        {
          "product": {
            "name": "Microwave",
            "price": 99.99
          },
          "quantity": 5
        },
        {
          "product": {
            "name": "Pen",
            "price": 7.23
          },
          "quantity": 100
        }
      ]
    }

.. _tables:

Regular table
-------------

This demo shows how to create a table based on an array of objects. You can find the description of this case in the `tables <tables.html#table>`_  documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document </_static/files/document-generation/demos/table-template.xlsx>`_

          .. image:: /_static/img/document-generation/table-template-xlsx.png
                :alt: Table template
        - `Download result document </_static/files/document-generation/demos/table-result.xlsx>`_

          .. image:: /_static/img/document-generation/table-result-xlsx.png
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

Dynamic table from an array
~~~~~~~~~~~~~~~~~~~~~~~~~~~

This demo shows how to create dynamic tables from arrays by just adding a single tag into the template document. You can find the description of this case in the `tables <tables.html#dynamic-table>`_  documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document </_static/files/document-generation/demos/table-from-array-template.xlsx>`_

          .. image:: /_static/img/document-generation/table-from-array-template-xlsx.png
                :alt: Table from array template
        - `Download result document </_static/files/document-generation/demos/table-from-array-result.xlsx>`_

          .. image:: /_static/img/document-generation/table-from-array-result-xlsx.png
                :alt: Table from array result

.. rubric:: Template data

.. code:: json

    {
        "myArray": [
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

.. _dynamic-table-columns:

Dynamic table from a number of arrays
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This demo shows how to create dynamic tables from several objects with nested arrays. You can find the description of this case in the `tables <tables.html#dynamic-table-columns>`_  documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document </_static/files/document-generation/demos/dynamic-table-columns-template.xlsx>`_

          .. image:: /_static/img/document-generation/dynamic-table-from-a-number-of-arrays-template-full.png
                :alt: Dynamic table from a number of arrays template
        - `Download result document </_static/files/document-generation/demos/dynamic-table-columns-result.xlsx>`_

          .. image:: /_static/img/document-generation/dynamic-table-from-a-number-of-arrays-result.png
                :alt: Dynamic table from a number of arrays result

.. rubric:: Template data

.. code:: json

    {
        "company": "Plumsail",
        "contacts": {
            "website": "http://plumsail.com",
            "support": "contacts@plumsail.com",
            "sales": "sales@plumsail.com"
        },
        "employees": [
            {
                "name": "Derek Clark",
                "metadata": [
                    [
                        "Marketing director",
                        "Room 18",
                        "(206) 854-9798"
                    ]
                ]
            },
            {
                "name": "Xue Li",
                "metadata": [
                    [
                        "Financial director",
                        "Room 19",
                        "(206) 598-1259"
                    ]
                ]
            },
            {
                "name": "Jessica Adams",
                "metadata": [
                    [
                        "Marketing manager",
                        "Room 23",
                        "(206) 789-1598"
                    ]
                ]
            },
            {
                "name": "Katsuko Kawakami",
                "metadata": [
                    [
                        "Analyst",
                        "Room 26",
                        "(206) 784-1258"
                    ]
                ]
            }
        ]
    }

.. _repeat-multiple-table-rows:

Repeat multiple table rows
--------------------------

This demo shows how to occupy multiple table rows by properties of a single object from your source array. You can find the description of this case in the `tables <tables.html#repeat-multiple-table-rows>`_  documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document </_static/files/document-generation/demos/repeat-multiple-table-rows-result.xlsx>`_

          .. image:: /_static/img/document-generation/repeat-multiple-table-rows-template-xlsx.png
                :alt: Repeat multiple table rows template
        - `Download result document </_static/files/document-generation/demos/repeat-multiple-table-rows-template.xlsx>`_

          .. image:: /_static/img/document-generation/repeat-multiple-table-rows-result-xlsx.png
                :alt: Repeat multiple table rows result

.. rubric:: Template data

.. code:: json

    [
        {
            "name": "David Navarro",
            "phone": "(206) 854-9798",
            "title": "Head of Marketing"
        },
        {
            "name": "Jessica Adams",
            "phone": "(206) 789-1598",
            "title": "Financial director"
        },
        {
            "name": "Anil Mittal",
            "phone": "(206) 784-1258",
            "title": "Sales manager"
        }
    ]

.. _loops-and-nesting:

Loops and nesting
-----------------

This demo demonstrates how to create complex nested documents based on nested objects and collections. You can find the description of this case in the `loops and nesting <loops-and-nesting.html>`_  documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document </_static/files/document-generation/demos/loops-and-nesting-template.xlsx>`_

          .. image:: /_static/img/document-generation/xlsx-loops-and-nesting-template.png
                :alt: Loops and nesting template
        - `Download result document </_static/files/document-generation/demos/loops-and-nesting-result.xlsx>`_

          .. image:: /_static/img/document-generation/xlsx-loops-and-nesting-result.png
                :alt: Loops and nesting result

.. _loops-and-nesting-data:

.. rubric:: Template data

.. code:: json

    {
        "reports":[
            {
                "quarter": "Q1",
                "sales": [
                    {
                        "month": "Jan",
                        "products": [
                            {
                                "name": "Television set", 
                                "total": 63225.81
                            },
                            {
                                "name": "Fridge",                            
                                "total": 15500
                            },
                            {
                                "name": "Microwave",                            
                                "total": 29032.26
                            }
                        ]
                    },
                    {
                        "month": "Feb",
                        "products": [
                            {
                                "name": "Television set", 
                                "total": 47419.35
                            },
                            {
                                "name": "Fridge",                            
                                "total": 20500
                            },
                            {
                                "name": "Microwave",                            
                                "total": 23467.74
                            }
                        ]
                    },
                    {
                        "month": "Mar",
                        "products": [
                            {
                                "name": "Television set", 
                                "total": 48548.39
                            },
                            {
                                "name": "Fridge",                            
                                "total": 12500
                            },
                            {
                                "name": "Microwave",                            
                                "total": 19354.83
                            }
                        ]
                    }
                ]
            },
            {
                "quarter": "Q2",
                "sales": [
                    {
                        "month": "Apr",
                        "products": [
                            {
                                "name": "Television set", 
                                "total": 54193.55
                            },
                            {
                                "name": "Fridge",                            
                                "total": 14500
                            },
                            {
                                "name": "Microwave",                          
                                "total": 35080.65
                            }
                        ]
                    },
                    {
                        "month": "May",
                        "products": [
                            {
                                "name": "Television set", 
                                "total": 44032.25
                            },
                            {
                                "name": "Fridge",                            
                                "total": 17500
                            },
                            {
                                "name": "Microwave",                            
                                "total": 24435.48
                            }
                        ]
                    },
                    {
                        "month": "Jun",
                        "products": [
                            {
                                "name": "Television set", 
                                "total": 42903.23
                            },
                            {
                                "name": "Fridge",                            
                                "total": 11500
                            },
                            {
                                "name": "Microwave",                            
                                "total": 36290.32
                            }
                        ]
                    }
                ]
            }
        ]
    }

.. _formulas:

Formulas
--------

This demo shows how to use formulas to your document. You can find a description of these case in the `formulas <./formulas.html>`_  section of the documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document </_static/files/document-generation/demos/formulas-template.xlsx>`_

          .. image:: /_static/img/document-generation/formulas-template.png
                :alt: Formulas template
        - `Download result document </_static/files/document-generation/demos/formulas-result.xlsx>`_

          .. image:: /_static/img/document-generation/formulas-result.png
                :alt: Formulas result

.. rubric:: Template data

.. code:: json

    {
        "currentWeek": [
            {
                "description": "May, 14 - May, 18",
                "currentRate": "1.1767",
                "fruits": [
                    {
                        "type": "Apples",
                        "number": {
                            "Monday": 15,
                            "Tuesday": 8,
                            "Wednesday": 1,
                            "Thursday": 17,
                            "Friday": 7
                        },
                        "price": 0.5
                    },
                    {
                        "type": "Oranges",
                        "number": {
                            "Monday": 14,
                            "Tuesday": 20,
                            "Wednesday": 22,
                            "Thursday": 8,
                            "Friday": 19
                        },
                        "price": 0.5
                    },
                    {
                        "type": "Bananas",
                        "number": {
                            "Monday": 17,
                            "Tuesday": 24,
                            "Wednesday": 31,
                            "Thursday": 9,
                            "Friday": 22
                        },
                        "price": 0.4
                    },
                    {
                        "type": "Pears",
                        "number": {
                            "Monday": 11,
                            "Tuesday": 25,
                            "Wednesday": 6,
                            "Thursday": 18,
                            "Friday": 13
                        },
                        "price": 0.6
                    },
                    {
                        "type": "Peaches",
                        "number": {
                            "Monday": 27,
                            "Tuesday": 19,
                            "Wednesday": 23,
                            "Thursday": 17,
                            "Friday": 5
                        },
                        "price": 0.3
                    }
                ]
            }
        ]
    }

.. _pie-and-clustered-column-charts:

Pie and clustered column charts
-------------------------------

This demo shows how to create charts in your document. You can find a description of these cases in the `pie charts <./charts.html#pie-charts>`_  and `clustered column charts <./charts.html#clustered-column-charts>`_  sections of the documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document </_static/files/document-generation/demos/charts-template.xlsx>`_

          .. image:: /_static/img/document-generation/charts-template.png
                :alt: Table template
        - `Download result document </_static/files/document-generation/demos/charts-result.xlsx>`_

          .. image:: /_static/img/document-generation/charts-result.png
                :alt: Table template result

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
                    "value2015": 37358
                    "value2016": 44229,
                    "value2017": 51000,
                }
            ]
        }
    ]


.. _charts-on-multiple-worksheets:

Charts on multiple worksheets
-----------------------------

This demo shows how to create charts on multiple worksheets in one file. You can find a description of this case in the `charts on multiple worksheets <./charts.html#charts-on-multiple-worksheets>`_  section of the documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document </_static/files/document-generation/demos/charts-multiple-sheets-template.xlsx>`_

          .. image:: /_static/img/document-generation/chart-worksheets-template-small.png
                :alt: Charts on multiple worksheets template
        - `Download result document </_static/files/document-generation/demos/charts-multiple-sheets-result.xlsx>`_

          .. image:: /_static/img/document-generation/chart-worksheets-result-small.png
                :alt: Charts on multiple worksheets result

.. rubric:: Template data

.. code:: json

    [
        {
            "title": "Coffee production by country",
            "description": "Production in thousand kilogram bags",
            "prod": [
                {
                    "Brazil": {
                        "value1": 25600,
                        "value2": 32200,
                        "value3": 34500
                    },
                    "Vietnam": {
                        "value1": 28500,
                        "value2": 18500,
                        "value3": 17500
                    },
                    "Colombia": {
                        "value1": 11300,
                        "value2": 13500,
                        "value3": 14000
                    },
                    "Indonesia": {
                        "value1": 14000,
                        "value2": 11000,
                        "value3": 19800
                    },
                    "IvoryCoast": {
                        "value1": 4100,
                        "value2": 1600,
                        "value3": 8000
                    },
                    "OtherCountries": {
                        "value1": 37358,
                        "value2": 44229,
                        "value3": 51000
                    }
                }
            ]
        },
        {
            "title": "Cocoa production by country",
            "description": "Production in 1000 tonnes",
            "prod": [
                {
                    "Brazil": {
                        "value1": 256,
                        "value2": 140,
                        "value3": 180
                    },
                    "Vietnam": {
                        "value1": 34,
                        "value2": 12,
                        "value3": 6
                    },
                    "Colombia": {
                        "value1": 0,
                        "value2": 0,
                        "value3": 0
                    },
                    "Indonesia": {
                        "value1": 777,
                        "value2": 600,
                        "value3": 500
                    },
                    "IvoryCoast": {
                        "value1": 1345,
                        "value2": 1200,
                        "value3": 1448
                    },
                    "OtherCountries": {
                        "value1": 1834,
                        "value2": 1789,
                        "value3": 1085
                    }
                }
            ]
        },
        {
            "title": "Another commodity production",
            "description": "Production in some units",
            "prod": [
                {
                    "Brazil": {
                        "value1": 106,
                        "value2": 158,
                        "value3": 80
                    },
                    "Vietnam": {
                        "value1": 34,
                        "value2": 56,
                        "value3": 10
                    },
                    "Colombia": {
                        "value1": 33,
                        "value2": 48,
                        "value3": 65
                    },
                    "Indonesia": {
                        "value1": 98,
                        "value2": 105,
                        "value3": 80
                    },
                    "IvoryCoast": {
                        "value1": 23,
                        "value2": 30,
                        "value3": 41
                    },
                    "OtherCountries": {
                        "value1": 151,
                        "value2": 184,
                        "value3": 216
                    }
                }
            ]
        }
    ]


.. _multiple-worksheets:

Multiple worksheets
-------------------

This demo shows how to create multiple worksheets in one file. You can find the description of this case in the `multiple worksheets <multiple-worksheets.html>`_  section of the documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document </_static/files/document-generation/demos/multiple-worksheets-template.xlsx>`_

          .. image:: /_static/img/document-generation/multiple-worksheets-template.png
                :alt: Multiple worksheets template
        - `Download result document </_static/files/document-generation/demos/multiple-worksheets-result.xlsx>`_

          .. image:: /_static/img/document-generation/multiple-worksheets-result.png
                :alt: Multiple worksheets result

.. rubric:: Template data

.. code:: json

    [
        {
            "name": "Jessica Adams",
            "jobInfo": {
                "title": "Marketing manager",
                "department": "Marketing Department",
                "manager": "Derek Clark",
                "telephone": "(206) 789-1598",
                "dateOfHire": "2012-04-21T00:00:00"
            },
            "personalInfo": {
                "address": "132, My Street, Kingston, New York 12401",
                "cell": "(123) 555-5551",
                "dateOfBirth": "1983-08-22",
                "SIN": "046 454 286"
            },
            "inCaseOfEmergency": {
                "name": "Sarah Adams",
                "relationship": "Mom",
                "telephone": "(123) 987-6541",
                "cell": "(123) 444-4441"
            }
        },
        {
            "name": "Katsuko Kawakami",
            "jobInfo": {
                "title": "Analyst",
                "department": "Financial Department",
                "manager": "Xue Li",
                "telephone": "(206) 784-1258",
                "dateOfHire": "2016-03-06T00:00:00"
            },
            "personalInfo": {
                "address": "257, My Street, East Village, New York 12401",
                "cell": "(123) 555-5552",
                "dateOfBirth": "1979-09-19",
                "SIN": "073 454 287"
            },
            "inCaseOfEmergency": {
                "name": "Jane Smith",
                "relationship": "Friend",
                "telephone": "(123) 987-6542",
                "cell": "(123) 333-3332"
            }
        },
        {
            "name": "Brenda Coel",
            "jobInfo": {
                "title": "Marketing director",
                "department": "Marketing Department",
                "manager": "Derek Clark",
                "telephone": "(206) 854-9798",
                "dateOfHire": "2011-11-05T00:00:00"
            },
            "personalInfo": {
                "address": "87, My Street, Lower East Side, New York 12401",
                "cell": "(123) 555-5553",
                "dateOfBirth": "1975-12-01",
                "SIN": "051 454 288"
            },
            "inCaseOfEmergency": {
                "name": "John Smith",
                "relationship": "Husband",
                "telephone": "(123) 987-6543",
                "cell": "(123) 222-2223"
            }
        }
    ]

.. _links:

Links
-----

This demo shows how to add external links to your document. You can find the description of this case in the `links <external-links.html>`_  section of the documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document </_static/files/document-generation/demos/external-links-template.xlsx>`_

          .. image:: /_static/img/document-generation/external-links-template-xlsx.png
                :alt: Links template
        - `Download result document </_static/files/document-generation/demos/external-links-result.xlsx>`_

          .. image:: /_static/img/document-generation/external-links-result-xlsx.png
                :alt: Links result

.. rubric:: Template data

.. code:: json

    [
        {
            "name": "Coursera",
            "type": "Commercial",
            "headquarters": "USA",
            "linkName": "Go to the site",
            "linkURL": "https://plato.stanford.edu/"
        },
        {
            "name": "edX",
            "type": "Non-profit",
            "headquarters": "USA",
            "linkName": "Go to the site",
            "linkURL": "https://www.edx.org/"
        },
        {
            "name": "FutureLearn",
            "type": "Commercial",
            "headquarters": "UK",
            "linkName": "Go to the site",
            "linkURL": "https://www.futurelearn.com/"
        }
    ]

.. _clear-cells:

Conditionally clear cells
-------------------------

This demo shows how to to conditionally clear content in Excel cells or named ranges. You can find the description of this case in the `conditionally clear cells <conditionally-clear-cells.html>`_  section of the documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    * - Template
      - Result
    * - `Download template document </_static/files/document-generation/demos/conditionally-clear-cells-template.xlsx>`_

        .. image:: /_static/img/document-generation/conditionally-clear-cells-template.png
            :alt: Clear cells template
      - `Download result document </_static/files/document-generation/demos/conditionally-clear-cells-result.xlsx>`_

        .. image:: /_static/img/document-generation/conditionally-clear-cells-result.png
            :alt: Clear cells result

.. rubric:: Template data

.. code:: json

  {
    "companyName": "Plumsail",
    "site": "http://plumsail.com",
    "contacts": null,  
    "hideConfNotice": true
  }


