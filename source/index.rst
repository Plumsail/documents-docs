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
    
    getting-started/sign-up
    getting-started/use-from-flow
    getting-started/use-as-rest-api
    getting-started/license-activation  

  .. toctree::
    :caption: User guide
    :name: toc-user-guide
    :maxdepth: 1
    
    user-guide/api-keys
    user-guide/reports
    user-guide/manage-email-notifications

  .. toctree::
    :caption: Document generation
    :name: toc-document-generation
    :maxdepth: 1
    
    document-generation/docx/index
    document-generation/xlsx/index
    document-generation/html/index

  .. toctree::     
    :name: toc-document-generation-hidden
    :maxdepth: 1            
    :hidden:        
                      
    document-generation/common-docx-xlsx/formatters
    document-generation/common-docx-xlsx/value-properties        
      
  .. rst-class:: single-page-nav
  
    .. toctree::
      :caption: Microsoft Flow actions    
      :name: toc-microsoft-flow-actions
      :maxdepth: 2
      
      flow/actions/document-processing    

.. container:: pl-right-column

  .. toctree::
    :caption: General 
    :name: generaltoc
    :maxdepth: 1
    
    general/version-history
    general/licensing-details
    general/upgrade-renew
    general/architecture
    general/security-policy
    general/sla
    general/manage-email-notifications   

  .. toctree::
    :caption: REST API
    :name: toc-test-api
    :maxdepth: 2
    
    REST API Reference <https://api.plumsail.com/swagger/index.html?urls.primaryName=Documents>                      

  .. toctree::    
    :caption: Microsoft Flow examples
    :name: toc-microsoft-flow-examples
    :maxdepth: 2

    flow/how-tos/documents/index-create-documents-from-template
    flow/how-tos/documents/index-convert-documents
    flow/how-tos/documents/index-process-pdf
    flow/how-tos/documents/index-integrations
    flow/how-tos/documents/index-E-signature
    flow/how-tos/documents/index-other