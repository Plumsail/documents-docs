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
    getting-started/use-from-flow
    getting-started/use-as-rest-api
    getting-started/license-activation 

  .. toctree::
    :caption: User guide
    :name: toc-user-guide
    :maxdepth: 1
    :titlesonly:
    
    Processes <user-guide/processes/index>
    user-guide/api-keys
    user-guide/reports
    user-guide/manage-email-notifications  

  .. toctree::
    :caption: Document generation
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
      
  .. rst-class:: single-page-nav
  
    .. toctree::
      :caption: Power Automate actions    
      :name: toc-microsoft-flow-actions
      :maxdepth: 2      
      
      flow/actions/document-processing    

.. container:: pl-right-column

  .. toctree::
    :caption: General 
    :name: generaltoc
    :maxdepth: 1
    :titlesonly:
    
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
    :titlesonly:
    
    REST API Reference <https://api.plumsail.com/swagger/index.html?urls.primaryName=Documents>                      

  .. toctree::    
    :caption: How-tos
    :name: toc-microsoft-flow-examples
    :maxdepth: 2
    :titlesonly:

    how-tos/index-create-documents-from-template
    how-tos/index-form-integrations
    how-tos/index-e-signature
    how-tos/index-convert-documents
    how-tos/index-process-pdf
    how-tos/index-other