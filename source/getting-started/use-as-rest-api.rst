Use as REST API
===============

This tutorial shows how to use Plumsail Documents API.

1. :ref:`create-api-key`
2. :ref:`review-api-reference`
3. :ref:`use-own-language`
4. :ref:`two-ways-to-call-api`

.. _create-api-key:

Create an API key
-----------------

Just follow the steps described in `this topic <sign-up.html#generate-api-key>`_. You will pass this your API key as the :code:`Authorization` HTTP header in your requests to the API.

.. _review-api-reference:

Review reference for API that you want to call
----------------------------------------------

We recommend you to review the `API reference`_. The API is split into a few sections:

- `Convert <https://api.plumsail.com/swagger/index.html?urls.primaryName=Documents%20V2#/Convert>`_ - All operations for converting documents.
- `Generate <https://api.plumsail.com/swagger/index.html?urls.primaryName=Documents%20V2#/Generate>`_ - All operations for creating documents from templates.
- `PDF <https://api.plumsail.com/swagger/index.html?urls.primaryName=Documents%20V2#/Pdf>`_ - Utility operations on PDF files. For example, split, merge, and protect PDF files.
- `Processes <https://api.plumsail.com/swagger/index.html?urls.primaryName=Documents%20V2#/ProcessesAPI>`_ - Operations for starting `Processes <../user-guide/processes/index>`_.
- `Watermark <https://api.plumsail.com/swagger/index.html?urls.primaryName=Documents%20V2#/Watermark>`_ - All operations for adding watermarks to PDF files.

.. _use-own-language:

Use API from your programming language
---------------------------------------------

Our API is REST-based. Thus, you can use any programming language that can execute web requests. For example, you would use C#, PowerShell, node.js, Python, PHP.

There are a lot of ready to use helper REST API clients for those languages. Here are just a few of them:

- `RestSharp <http://restsharp.org/>`_ for C#
- `Invoke-RestMethod <https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-5.1>`_ cmdlets for PowerShell
- `request <https://www.npmjs.com/package/request>`_ - Simplified HTTP client for node.js
- `Requests: HTTP for Humans <http://docs.python-requests.org>`_ for Python
- `Guzzle <http://guzzle.readthedocs.io>`_ for PHP

.. _two-ways-to-call-api:

Learn two ways to call API
----------------------------

There are two ways to work with API:

1. :ref:`call-a-method-and-get-the-result`
2. :ref:`start-a-job-and-get-the-results-once-the-job-finished`

The first way is good for light operations. When execution of the method doesn't take a lot of time. You just call an API method and receive a response with results.

The second way is good if you want to perform a long-running operation. For example, convert a large file. You just start a conversion job and then download the result once the job is finished.

.. _call-a-method-and-get-the-result:

Call a method and get the result immediately
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This approach is good for processing a small amount of data and for testing purposes. If your request is can't be processed in 30 seconds our service will return an error. Thus, if you want to process a large amount of data it is better to use the second option with jobs.

All jobs are placed under :code:`/jobs/` path. You may notice it in the `API reference`_. The rest of the methods return results right in the response.

Below is the example of a curl request to create a document from the DOCX template without using jobs. The request returns the result immediately. 

::

  curl --location --request POST 'https://api.plumsail.com/api/v2/generate/from-docx' \
  --header 'Authorization: YOUR_API_KEY' \
  --form 'File=@/D:/Temp/template-file.docx' \
  --form 'Data={ "firstName": "Derek", "lastName": "Clark"}' \
  --form 'Locale=en-US'

There are a few parameters that you should specify:

- The :code:`Authorization` header. You need to pass your API key as a value for it. You need to replace :code:`YOUR_API_KEY` by the value of your API key.
- The :code:`File` form value. It is the path to your DOCX template file. If you have the file available online you can use the :code:`FileUrl` parameter instead of the :code:`File`. You can pass the URL of a file available for anonymous access.
- The :code:`Data` form value. It is a JSON object with values that will be applied to the document template.
- The :code:`Locale` form value. It is a locale that will be used to produce the result document. It can affect the formatting of dates, numbers, and currencies.

This is just an example. Other methods in the API may have different parameters but the :code:`Authorization` header is required everywhere.

Once the request is executed you will get an object with the :code:`link` property inside. It will contain the URL of the generated document. You can download it to see results.

.. code:: 

  {
    "link": "https://URL_OF_THE_RESULT_FILE"
  }

You can use other programming languages to send requests to the API.

.. toctree::   
  :name: toc-process-examples    
  :maxdepth: 2
    
  ./rest-api-examples/rest-api-examples-no-jobs.rst


.. _start-a-job-and-get-the-results-once-the-job-finished:

Start a job and get the result once the job is finished
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You may notice that some methods in `API reference`_ are located under :code:`/jobs/` path. For example, the method below starts the job of creating a DOCX document from template:

::

  /api/v2/generate/jobs/from-docx 

The curl for starting the job is almost the same as in the previous section of this article. The only difference, we added the :code:`jobs` part:

::

  curl --location --request POST 'https://api.plumsail.com/api/v2/generate/jobs/from-docx' \
  --header 'Authorization: YOUR_API_KEY' \
  --form 'File=@/D:/Temp/template-file.docx' \
  --form 'Data={ "firstName": "Derek", "lastName": "Clark"}' \
  --form 'Locale=en-US'

Once the job is created the method returns response message :code:`Accepted` with code :code:`202`. It means the job has been created and the generation of a document is in progress. There is the :code:`location` header present in the response. It contains a URL where the result of job execution will be available. This is the example response:

.. code:: 

  {
      "status": "202",
      "location": "https://api.plumsail.com/api/v2/generate/jobs/from-docx/0HM0M6S9HO2SN72E293925ab",
      "date": "Thu, 21 Sep 2017 16:11:07 GMT",      
      "x-jobid": "0HM0M6S9HO2SN72E293925ab",                
      "content-length": "0"        
  }

A URL with the result is usually the same as the URL of the original job plus ID of the job. Example:

::

    https://api.plumsail.com/api/v2/generate/jobs/from-docx/0HM0M6S9HO2SN72E293925ab

Where :code:`0HM0M6S9HO2SN72E293925ab` is an ID of the job.

All you need to do now is to execute the GET request for the URL from the :code:`location` header. If the result is not ready yet, it returns the :code:`Accepted` message and :code:`202` code with the same :code:`location` header again. If the result is ready it returns an object with the :code:`link` property inside. It will contain the URL of the generated document. You can download it to see results.

.. code:: 

  {
    "link": "https://URL_OF_THE_RESULT_FILE"
  }

.. _API reference: https://api.plumsail.com/swagger/index.html?urls.primaryName=Documents