.. Plumsail Documents documentation master file, created by
   sphinx-quickstart on Tue Apr 12 16:52:35 2016.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Plumsail Documents Documentation
================================
      
.. toctree::
  :hidden:

  Table of contents <self>

.. container:: pl-left-column

  .. toctree::
    :caption: Getting started
    :name: toc-getting-started
    :maxdepth: 1
    :titlesonly:
    
    Create documents from template <getting-started/use-processes>
    getting-started/use-from-zapier    
    getting-started/use-from-flow
    Use Power Apps <flow/how-tos/documents/use-the-Plumsail-Documents-connection-in-Powerapps>
    getting-started/use-as-rest-api

  .. toctree::
    :caption: User guide
    :name: toc-user-guide
    :maxdepth: 1
    :titlesonly:
    
    Processes <user-guide/processes/index>
    user-guide/api-keys
    user-guide/reports
    user-guide/manage-email-notifications
    Power Automate actions reference <../flow/actions/document-processing.rst>
    Zapier actions reference
    REST API reference <https://api.plumsail.com/swagger/index.html?urls.primaryName=Documents>  

  .. toctree::
    :caption: Templates syntax
    :name: toc-document-generation
    :maxdepth: 1
    :titlesonly:
    
    document-generation/docx/index
    document-generation/pptx/index
    document-generation/xlsx/index
    Fillable PDF <document-generation/fillable-pdf/index>
    document-generation/html/index

  .. toctree::     
    :name: toc-document-generation-hidden
    :maxdepth: 1            
    :hidden:
    :titlesonly:
                      
    document-generation/common-docx-xlsx/formatters
    document-generation/common-docx-xlsx/value-properties        

  .. toctree::
    :caption: PDF processing and more 
    :name: toc-pdf-processing
    :maxdepth: 1
    :titlesonly:

    Convert DOCX, XLSX, PPTX, HTML to PDF <../how-tos/index-convert-to-pdf.rst>
    Convert DOC, XLS, PPT to DOCX, XLSX, PPTX <../../../flow/how-tos/documents/convert-doc-to-docx-xls-to-xlsx-ppt-to-pptx.rst>
    Extract data from fillable PDF forms <../../../flow/how-tos/documents/collect-data-pdf-form.rst>
    Protect PDF files <https://medium.com/plumsail/how-to-protect-pdf-disable-printing-modification-annotations-set-password-in-microsoft-flow-and-e255100bd04e>
    Add watermarks <../how-tos/index-watermarks.rst>
    Split PDF <../../../flow/how-tos/documents/split-pdf-files.rst>
    Merge PDF <../../../flow/how-tos/documents/merge-pdf-files.rst>
    Read CSV files <../how-tos/index-parse-csv.rst>
    Extract data using regular expressions <../../../flow/how-tos/documents/use-regex-match-to-extract-values.rst>
    Fill merge fields in DOCX document <../../../flow/how-tos/documents/fill-docx-merge-fields.rst>

.. container:: pl-right-column

  .. toctree::
    :caption: General 
    :name: generaltoc
    :maxdepth: 1
    :titlesonly:
    
    general/licensing-details
    general/architecture
    general/security-policy
    general/sla
    general/manage-email-notifications                     

  .. toctree::    
    :caption: Integration examples
    :name: toc-Integration-examples
    :maxdepth: 2
    :titlesonly:

    how-tos/index-form-integrations
    how-tos/index-esignature
    how-tos/index-cloud-storage-integrations
    Your custom service <../how-tos/custom-service-rest-api.rst>