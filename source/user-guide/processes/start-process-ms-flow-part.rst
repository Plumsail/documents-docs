You can use `Plumsail Documents connector <https://emea.flow.microsoft.com/en-us/connectors/shared_plumsail/plumsail-documents/>`_ for Power Automate (Microsoft Flow) to start a process. Start by `creating an API key <../user-guide/api-keys.html>`_. You will need it in your flow.

Then add the `Start process <../flow/actions/document-processing.html#start-process>`_ action to your flow. You will be asked for *'Connection Name'* and for *'Access Key'*. You can type any name for the connection. For example, *'Plumsail Documents'*. Then paste API key that you created earlier to *'Access Key'*.

.. image:: ../../_static/img/getting-started/create-flow-connection.png
   :alt: Screen of Plumsail Documents

Optionally, once the action is executed you can get the result document as an output of the action and continue to work with it in your flow.

Here is an example of a simple flow that starts a process and then uploads it to OneDrive:

.. image:: ../../_static/img/user-guide/processes/start-process-flow.png
    :alt: Start process flow

.. rubric:: Review other examples of Power Automate (Microsoft Flow)s with processes:

.. toctree::      
  :name: toc-processes-flow-examples
  :maxdepth: 1
  
  ../../how-tos/index-form-integrations
  ../../how-tos/index-E-signature 