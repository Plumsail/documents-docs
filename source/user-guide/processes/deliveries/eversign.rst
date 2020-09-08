eversign delivery
=================

The `eversign <https://eversign.com/>`_ delivery sends the resulting document to eversign for signing.

To start with, you need to log in to your eversign account from the Plumsail account and authorize Plumsail Documents to access it.

.. image:: ../../../_static/img/user-guide/processes/connect-eversign.png
    :alt: connect to eversign

After that, you'll be able to customize the eversign delivery.

**Select the business** from the dropdown:

.. image:: ../../../_static/img/user-guide/processes/select-eversign-business.png
    :alt: select eversign business

**Fill in email subject and body**:

.. image:: ../../../_static/img/user-guide/processes/eversign-email.png
    :alt: fill in email subject and body

**Add recipients** - as many as you need. They could have :code:`Needs to sign` and :code:`Receives a copy` roles:

.. image:: ../../../_static/img/user-guide/processes/eversign-roles.png
    :alt: roles of recipients in eversign delivery

In the screenshot above, you may see lock buttons. One is green, which means it's activated. Another is off.

.. image:: ../../../_static/img/user-guide/processes/locks.png
    :alt: locks to set signer PINs

Clicking on the lock, you can **set a signer PIN**. Signer PINs provide you with extra signer authentication and security. 

.. image:: ../../../_static/img/user-guide/processes/signer-pin.png
    :alt: apply signer PINs

Advanced settings
-----------------

Expand **Advanced** to customize more settings.

.. image:: ../../../_static/img/user-guide/processes/advanced-eversign-settings.png
    :alt: advanced eversign settings

- Here you can switch on **Sequential signing**, then just drag and drop recipients to define an order in which they should sign the document:

.. image:: ../../../_static/img/user-guide/processes/drag-drop-recipients.gif
    :alt: drag and drop recipients to change the sequence of signing

- Enable **Require all signers to sign** to complete the document. If this option is on, all signers must sign the document in order to complete it. If at least one of them declines to sign, this document will be canceled.

- One more significant option here is to enable **Sandbox eversign mode**. With Sandbox on, you won't be charged, and signed documents won't be valid. They will have a tag :code:`[test-only-not-binding]`. Use this mode for testing purposes.

Use tokens inside email subject and body
----------------------------------------

.. include:: ../tokens-description-part.rst

.. note:: Review `the full list of available deliveries <../create-delivery.html#list-of-deliveries>`_.