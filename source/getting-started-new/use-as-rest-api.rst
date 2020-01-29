Use as REST API
===============

This tutorial shows how to use Plumsail Documents API. There are just a few steps to get started:

1. :ref:`create-api-key`
2. :ref:`review-api-reference`
3. :ref:`use-own-language`
4. :ref:`two-ways-to-call-api`

.. _create-api-key:

Create an API key
-----------------

Just follow the steps described in `this topic <sign-up.html#generate-api-key>`_.

.. _review-api-reference:

Review reference for API that you want to call
----------------------------------------------

You can find API reference on `this page <https://api.plumsail.com/swagger/index.html?urls.primaryName=Documents>`_.

.. _use-own-language:

Use API from your programming language
---------------------------------------------

Our API is REST based. Thus, you can use any programming language that is able to execute web requests. For example, you would use C#, PowerShell, node.js, Python, PHP.

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

The first way is good for light operations. When execution of method doesn't take a lot of time. You just call an API method and receive a response with results.

The second way is good if you want to perform a long-running operation. For example, convert a large file. You just start a conversion job and then download the result once the job is finished.

You can find descriptions of all available methods in `API reference`_

.. _call-a-method-and-get-the-result:

Call a method and get the result immediately
````````````````````````````````````````````

This approach is good for processing of a small amount of data and for testing purposes. If your request is can't be processed in 30 seconds our service will return an error. Thus, if you want to process a large amount of data it is better to use the second option with jobs.

Some of the methods in the API are not mirrored in jobs. Those methods are designed to work with quick operations. They just don't need any jobs.

All jobs are placed under *'/jobs/'* path. You may notice it in `API reference`_. The rest of methods return results right in the response.

This is an example of a raw request to convert DOCX to PDF:

::

    POST https://api.plumsail.com/api/v1/Documents/Docx2Pdf

    Authorization: API_KEY
    Content-Type: application/json
    Accept:  application/json

    {
        "fileContent": "BASE64_FILE_CONTENT"
    }

And this is cURL representation for it:

::

    curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' --header \ 
      'Authorization: b4994846db1a4773123717f7f0a3cf90' -d '{ \    
      "fileContent": "BASE64_FILE_CONTENT" \ 
    }' ' https://api.plumsail.com/api/v1/Documents/Docx2Pdf'

You have to pass *'Authorization'* header with an API access key and specify send the rest of parameters in the body of the request. You can find the description of parameters in API reference.

You will receive results of conversion in the response for your request. It will return *'OK'* status with the code *'200'*. It means conversion succeed. This is the example response:

::

    {
        "fileContent": "BASE64_FILE_CONTENT"
    }

.. _start-a-job-and-get-the-results-once-the-job-finished:

Start a job and get the result once the job is finished
````````````````````````````````````````````````````````

You may notice that some methods in `API reference`_ are located under *'/jobs/'* path. For example, the method below starts DOCX to PDF conversion job:

::

    /api/v1/Documents/jobs/Docx2Pdf

This is an example of a raw request to start the job:

::

    POST https://api.plumsail.com/api/v1/Documents/jobs/Docx2Pdf

    Authorization: API_KEY
    Content-Type: application/json
    Accept:  application/json

    {
        "fileContent": "BASE64_FILE_CONTENT"
    }

And this is cURL representation for it:

::

    curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' --header \ 
      'Authorization: b4994846db1a4773123717f7f0a3cf90' -d '{ \    
      "fileContent": "BASE64_FILE_CONTENT" \ 
    }' ' https://api.plumsail.com/api/v1/Documents/jobs/Docx2Pdf'

You have to pass *'Authorization'* header with an API access key and specify send the rest of parameters in the body of the request. You can find the description of parameters in API reference.

Once the job is created the method returns response message *'Accepted'* with the code *'202'*. It means the job has been created and conversion operation is in progress. There is *'Location'* header present in the response. It contains URL where the result of job execution will be available. This is the example response:

::

    {
        "status": "202",
        "location": "http://api.plumsail.com/api/v1/Documents/jobs/Docx2Pdf/0HL80VGO2DC6N",
        "date": "Thu, 21 Sep 2017 16:11:07 GMT",
        "server": "cloudflare-nginx",
        "access-control-allow-origin": "*",
        "cf-ray": "3a1e4c69c8a28da7-DME",
        "content-length": "0"        
    }

A URL with the result is usually the same as URL of the original job plus identificator of the job. Example:

::

    http://api.plumsail.com/api/v1/Documents/jobs/Docx2Pdf/0HL80VGO2DC6N

Where *'0HL80VGO2DC6N'* is an ID of the job.

All you need to do now is to execute GET request for the URL from the *'Location'* header. If the result is not ready yet, it returns *'Accepted'* message and *'202'* code again with the same "'Location'" header.

.. _API reference: https://api.plumsail.com/swagger/index.html?urls.primaryName=Documents