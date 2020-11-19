Prepare and test a template
===========================

After you `created the process <./create-process.html>`_, its first step **Configure template** will appear showing the substep **Editor**. Here you can start composing the template online or upload a pre-made one. 

.. image:: ../../_static/img/user-guide/processes/configure-template.png
    :alt: configure step

The only exception is fillable PDF templates. You'll be offered to upload a pre-made template right away after the process creation. And after that, you'll proceed to the Configure template step.

.. contents::
    :local:
    :depth: 2

Templating syntax
~~~~~~~~~~~~~~~~~

To make your own templates easily, get acquainted with how the templating syntax works for supported formats. 

Plumsail Documents templating engine uses a minimum of syntax to make your work done. Please, consult the documentation for details:

- `DOCX template <../../document-generation/docx/index.html>`_
- `XLSX template <../../document-generation/xlsx/index.html>`_
- `PPTX template <../../document-generation/pptx/index.html>`_
- `Fillable PDF form <../../document-generation/fillable-pdf/index.html>`_
- `HTML template <../../document-generation/html/index.html>`_

Online editor
~~~~~~~~~~~~~

The online editor allows you to create document templates and modify them online right in the Plumsail process.

Get started
-----------

For Office document templates, the editor mode in the Configure template step starts with the template preview. To start working on the document template online, click on the **Edit online** button:

.. image:: ../../_static/img/user-guide/processes/edit-online-button.png
    :alt: Edit online button


If you're working on the HTML template, you're able to make changes right away, because there is no preview mode:

.. image:: ../../_static/img/user-guide/processes/edit-html-template.png
    :alt: Edit HTML html template

.. note:: No online editor is available for fillable PDF form templates. You'll have only its preview on this step. You can consult our detailed description of `how to create fillable PDFs <../../document-generation/fillable-pdf/index.html>`_. 

Complex Office document templates
---------------------------------

Online editor for Word, Excel, and PowerPoint templates is based on Google Docs. 
That's why you may encounter incompatibilities for certain Microsoft Office features. For example, Google Docs doesn't support watermarks.

We recommend you to work on complex document templates outside the process. Use Upload/Download buttons for it:

.. image:: ../../_static/img/user-guide/processes/upload-download-button.png
    :alt: Edit HTML html template                

Full-screen mode
----------------

The online editor provides a full-screen mode for more convenience in working with the template.  
Switch to a fullscreen and back by simply clicking on the button.

**Go to fullscreen**

.. image:: ../../_static/img/user-guide/processes/full-screen-button.png
    :alt:  Full screen button

**Exit fullscreen**

.. image:: ../../_static/img/user-guide/processes/exit-full-screen.png
    :alt:  Exit full screen button


Test the document template
--------------------------

You can instantly check how all your modifications to the template will affect the resulting file.
You can do it from the preview:

.. image:: ../../_static/img/user-guide/processes/test-from-preview.png
    :alt: Test template from preview

Or right from the online editor:

.. image:: ../../_static/img/user-guide/processes/test-button-template.png
    :alt: Test template button in Online editor

After you've clicked on the **Test template**, the dialog appears and you will see two options for testing the template. 

You can fill the testing form or submit JSON representing data for the document template. 

Read more about `testing templates <./test-template.html>`_. 

Save the template
-----------------

You can switch between preview and edit modes by clicking **Edit online** and **Exit editor**. But none of the changes will pass to the process until you press **Save&Next**. To confirm you're satisfied with the template result and ready to go to the next step, click on this button:

.. image:: ../../_static/img/user-guide/processes/save-button.png
    :alt: Save template button in Online editor

.. note:: Once you've finished with the template, you can proceed to `configure output file settings <./configure-settings.html>`_.