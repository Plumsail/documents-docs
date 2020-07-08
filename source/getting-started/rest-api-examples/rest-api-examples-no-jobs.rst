Examples API request using different programming languages
==========================================================

Below are examples of request to Plumsail Documents API using different languages. The API call generates a document from DOCX template.

.. note:: You need to replace the value of :code:`YOUR_API_KEY` by your API key. Also, the code assumes that the DOCX template is stored locally in this location: :code:`D:/Temp/template-file.docx`. You should adjust it as well.

The responce of this request will contain an URL of the result file. You can use it to download the result file.

.. contents:: Languages
    :local:

C# - Rest RestSharp
-------------------

.. code:: csharp

    var client = new RestClient("https://api.plumsail.com/api/v2/generate/from-docx");    
    var request = new RestRequest(Method.POST);
    request.AddHeader("Authorization", "YOUR_API_KEY");
    request.AddFile("File", "/D:/Temp/template-file.docx");
    request.AddParameter("Data", "{ \"firstName\": \"Derek\", \"lastName\": \"Clark\"}");
    request.AddParameter("Locale", "en-US");
    IRestResponse response = client.Execute(request);
    Console.WriteLine(response.Content);

Node.js - Axios
---------------

.. code:: js

    var axios = require('axios');
    var FormData = require('form-data');
    var fs = require('fs');
    var data = new FormData();
    data.append('File', fs.createReadStream('/D:/Temp/template-file.docx'));
    data.append('Data', '{ "firstName": "Derek", "lastName": "Clark"}');
    data.append('Locale', 'en-US');

    var config = {
      method: 'post',
      url: 'https://api.plumsail.com/api/v2/generate/from-docx',
      headers: { 
        'Authorization': 'YOUR_API_KEY', 
        ...data.getHeaders()
      },
      data : data
    };

    axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });

JavaScript - Fetch
------------------

.. code:: js

    var myHeaders = new Headers();
    myHeaders.append("Authorization", "YOUR_API_KEY");

    var formdata = new FormData();
    formdata.append("File", fileInput.files[0], "/D:/Temp/template-file.docx");
    formdata.append("Data", "{ \"firstName\": \"Derek\", \"lastName\": \"Clark\"}");
    formdata.append("Locale", "en-US");

    var requestOptions = {
      method: 'POST',
      headers: myHeaders,
      body: formdata,
      redirect: 'follow'
    };

    fetch("https://api.plumsail.com/api/v2/generate/from-docx", requestOptions)
      .then(response => response.text())
      .then(result => console.log(result))
      .catch(error => console.log('error', error));

C - libcurl
-----------

.. code:: c

    CURL *curl;
    CURLcode res;
    curl = curl_easy_init();
    if(curl) {
      curl_easy_setopt(curl, CURLOPT_CUSTOMREQUEST, "POST");
      curl_easy_setopt(curl, CURLOPT_URL, "https://api.plumsail.com/api/v2/generate/from-docx");
      curl_easy_setopt(curl, CURLOPT_FOLLOWLOCATION, 1L);
      curl_easy_setopt(curl, CURLOPT_DEFAULT_PROTOCOL, "https");
      struct curl_slist *headers = NULL;
      headers = curl_slist_append(headers, "Authorization: YOUR_API_KEY");
      curl_easy_setopt(curl, CURLOPT_HTTPHEADER, headers);
      curl_mime *mime;
      curl_mimepart *part;
      mime = curl_mime_init(curl);
      part = curl_mime_addpart(mime);
      curl_mime_name(part, "File");
      curl_mime_filedata(part, "/D:/Temp/template-file.docx");
      part = curl_mime_addpart(mime);
      curl_mime_name(part, "Data");
      curl_mime_data(part, "{ \"firstName\": \"Derek\", \"lastName\": \"Clark\"}", CURL_ZERO_TERMINATED);
      part = curl_mime_addpart(mime);
      curl_mime_name(part, "Locale");
      curl_mime_data(part, "en-US", CURL_ZERO_TERMINATED);
      curl_easy_setopt(curl, CURLOPT_MIMEPOST, mime);
      res = curl_easy_perform(curl);
      curl_mime_free(mime);
    }
    curl_easy_cleanup(curl);

Python - Requests
--------------------

.. code:: pyx

    import requests

    url = "https://api.plumsail.com/api/v2/generate/from-docx"

    payload = {'Data': '{ "firstName": "Derek", "lastName": "Clark"}',
    'Locale': 'en-US'}
    files = [
      ('File', open('/D:/Temp/template-file.docx','rb'))
    ]
    headers = {
      'Authorization': 'YOUR_API_KEY'
    }

    response = requests.request("POST", url, headers=headers, data = payload, files = files)

    print(response.text.encode('utf8'))

Go - Native
-----------

.. code:: go

    package main

    import (
      "fmt"
      "bytes"
      "mime/multipart"
      "os"
      "path/filepath"
      "io"
      "net/http"
      "io/ioutil"
    )

    func main() {

      url := "https://api.plumsail.com/api/v2/generate/from-docx"
      method := "POST"

      payload := &bytes.Buffer{}
      writer := multipart.NewWriter(payload)
      file, errFile1 := os.Open("/D:/Temp/template-file.docx")
      defer file.Close()
      part1,
            errFile1 := writer.CreateFormFile("File",filepath.Base("/D:/Temp/template-file.docx"))
      _, errFile1 = io.Copy(part1, file)
      if errFile1 !=nil {
              
        fmt.Println(errFile1)
      }
      _ = writer.WriteField("Data", "{ \"firstName\": \"Derek\", \"lastName\": \"Clark\"}")
      _ = writer.WriteField("Locale", "en-US")
      err := writer.Close()
      if err != nil {
        fmt.Println(err)
      }


      client := &http.Client {
      }
      req, err := http.NewRequest(method, url, payload)

      if err != nil {
        fmt.Println(err)
      }
      req.Header.Add("Authorization", "YOUR_API_KEY")

      req.Header.Set("Content-Type", writer.FormDataContentType())
      res, err := client.Do(req)
      defer res.Body.Close()
      body, err := ioutil.ReadAll(res.Body)

      fmt.Println(string(body))
    }

PowerShell - RestMethod
-----------------------

.. code:: powershell

    $headers = New-Object "System.Collections.Generic.Dictionary[[String],[String]]"
    $headers.Add("Authorization", "YOUR_API_KEY")

    $multipartContent = [System.Net.Http.MultipartFormDataContent]::new()
    $multipartFile = '/D:/Temp/template-file.docx'
    $FileStream = [System.IO.FileStream]::new($multipartFile, [System.IO.FileMode]::Open)
    $fileHeader = [System.Net.Http.Headers.ContentDispositionHeaderValue]::new("form-data")
    $fileHeader.Name = "File"
    $fileHeader.FileName = "/D:/Temp/template-file.docx"
    $fileContent = [System.Net.Http.StreamContent]::new($FileStream)
    $fileContent.Headers.ContentDisposition = $fileHeader
    $multipartContent.Add($fileContent)

    $stringHeader = [System.Net.Http.Headers.ContentDispositionHeaderValue]::new("form-data")
    $stringHeader.Name = "Data"
    $StringContent = [System.Net.Http.StringContent]::new("{ `"firstName`": `"Derek`", `"lastName`": `"Clark`"}")
    $StringContent.Headers.ContentDisposition = $stringHeader
    $multipartContent.Add($stringContent)

    $stringHeader = [System.Net.Http.Headers.ContentDispositionHeaderValue]::new("form-data")
    $stringHeader.Name = "Locale"
    $StringContent = [System.Net.Http.StringContent]::new("en-US")
    $StringContent.Headers.ContentDisposition = $stringHeader
    $multipartContent.Add($stringContent)

    $body = $multipartContent

    $response = Invoke-RestMethod 'https://api.plumsail.com/api/v2/generate/from-docx' -Method 'POST' -Headers $headers -Body $body
    $response | ConvertTo-Json