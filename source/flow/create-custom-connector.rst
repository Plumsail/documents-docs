Create custom connector
=======================

Open Microsoft Flow account then navigate to *'Custom Connectors'*:

.. image:: ../_static/img/getting-started/1-flow-custom-connectors.png
   :alt: Microsoft Flow custom connectors menu

Click *'Create custom connector → Import an OpenAPI from URL'*:

.. image:: ../_static/img/getting-started/connector-from-url.png
   :alt: Connector from URL

There are two connectors available in Plumsail Actions:

- `Plumsail Documents <../flow/actions/document-processing.html>`_ - provides a set of actions for operations with Documents
- `Plumsail SharePoint <../flow/actions/sharepoint-processing.html>`_ - provides a set of actions for operations with SharePoint

If you want to use *'Plumsail Documents'*, fill in name *'Plumsail Documents'* and swagger definition URL:

  https://api.plumsail.com/swagger/DocumentsFlow/swagger.json

If you want to use *'Plumsail SharePoint'*, fill in name *'Plumsail SharePoint'* and swagger definition URL:

  https://api.plumsail.com/swagger/SharePointFlow/swagger.json

Once you clicked *'Continue'* you will see *'General'* step of connector configuration:

.. image:: ../_static/img/getting-started/general-connector-step.png
   :alt: General connector configuration

You may want to differentiate this connector from others. In this case, you can assign a custom icon and custom color for it. We suggest this icon:

.. image:: ../_static/img/getting-started/actions-connector-icon.png
   :alt: Connector icon
   :target: ../_static/img/getting-started/actions-connector-icon.png

And this color:

::

  #ce2d7d

Then click *'Continue'*. You should see authentication type screen:

.. image:: ../_static/img/getting-started/2-flow-accesskey-label.png
   :alt: Microsoft Flow access key

Fill in *'Label'* with the value *'Access Key'* and click *'Create connector'*:

.. image:: ../_static/img/getting-started/create-connector-link.png
   :alt: Create Connector link