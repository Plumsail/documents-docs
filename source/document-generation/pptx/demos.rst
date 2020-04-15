Demos for PPTX templates
========================

.. contents:: List of demos
   :local:
   :depth: 1

Company Report
-------------
This demo demonstrates how to create a presentation for an simple report.
Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/pptx-report-template.pptx>`_
         
          .. image:: ../../_static/img/document-generation/pptx-report-template.png
                :alt: invoice template
        - `Download result document <../../_static/files/document-generation/demos/pptx-report-result.pptx>`_
         
          .. image:: ../../_static/img/document-generation/pptx-report-result.png
                :alt: invoice result                    

.. rubric:: Template data

.. code:: json

    {
	    "title": "Plumsail monthly report",
	    "subtitle": "made by David Navarro",
	    "date": "Today",
	    "state": "On track",
	    "action": [
		    {
			    "description": "Hire more experts"
		    },
		    {      
			    "description": "Remove obstacles"
		    },
		    {
			    "description": "Marketing"
		    },
		    {
			    "description": "..."
		    },
		    {
			    "description": "Profit!!!"
		    }
	    ],
	    "sales": [
		    {
			    "country": "Romania",
			    "lead": "Count Drakula",
			    "churn": 50,
		    	"new": 220
		    },
		    {
			    "country": "USA",
			    "lead": "John Doe",
			    "churn": 450,
			    "new": 1500
		    },
		    {
			    "country": "Australia",
			    "lead": "Jacky Coala",
			    "churn": 0,
			    "new": 3060
		    },
		    {
			    "country": "Japan",
			    "lead": "Naruto",
			    "churn": 260,
			    "new": 820
		    }
	    ],
	    "history": [
		    {
			    "period": "2018/Q1",
			    "total": 5030
		    },
		    {
			    "period": "2018/Q2",
			    "total": 5050
		    },
		    {
			    "period": "2018/Q3",
			    "total": 6120
		    },
		    {
			    "period": "2018/Q4",
			    "total": 6650
		    },
		    {
			    "period": "2019/Q1",
			    "total": 7660
		    },
		    {
			    "period": "2019/Q2",
			    "total": 7540
		    },
		    {
			    "period": "2019/Q3",
			    "total": 8220
		    }
	    ]
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
    *   - `Download template document <../../_static/files/document-generation/demos/pptx-table-template.pptx>`_

          .. image:: ../../_static/img/document-generation/pptx-table-template.png
                :alt: Table template
        - `Download result document <../../_static/files/document-generation/demos/pptx-table-result.pptx>`_

          .. image:: ../../_static/img/document-generation/pptx-table-result.png
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
    *   - `Download template document <../../_static/files/document-generation/demos/pptx-table-from-array-template.pptx>`_

          .. image:: ../../_static/img/document-generation/table-from-array-template.png
                :alt: Table from array template
        - `Download result document <../../_static/files/document-generation/demos/pptx-table-from-array-result.pptx>`_

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


.. _links-and-endnotes:

Links
------

This demo shows how to add external links to your presentation. You can find the description of this 
case in the `links <external-links.html>`_ section of the documentation.

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
.. note::  If you are use multiple bullet lists or tables better to copy data array for each using ("employees1" for a table, "employees2" for bullet list, etc)

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
      companyName": "Plumsail",
      "site": "http://plumsail.com",
      "contacts": null,
      "employees1": [
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
      ],
      "employees2": [
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
