Zapier
======

You can use `Zapier integration <https://zapier.com/apps/plumsail-documents/integrations>`_ to start the process of generating documents from template.

`Zapier <https://zapier.com/>`_ allows you to connect the document generation process with other web applications. It's quite easy to handle automated connections in Zapier - zaps - to get your paperwork done automatically. 

.. contents::
    :local:
    :depth: 2

Use ready zap templates
-----------------------

There are various ready-to-use zap templates you can go to right from the step *Start process*. Just hit *Use this Zap*. You'll be redirected to your Zapier account to personalize this particular zap. Learn how to `customize Start Process in Plumsail Documents action <#customize-start-process>`_.

.. image:: ../../_static/img/user-guide/processes/start-zapier.png
    :alt: Start process from Zapier

Or you can create your own zap to start the process. 

Create zap to start process in Zapier
-------------------------------------

We'll take a look at a simple zap to show how to use Start process action in Zapier. 

Let us say you have a Google Calendar for conferences. You need to generate personalized invitations. 

This is how our Zap looks:

.. image:: ../../_static/img/user-guide/processes/sample-zap.png
    :alt: sample zap

Set trigger
~~~~~~~~~~~

The first step is a trigger. In this particular case, it's a new event in the Google Calendar. 

When a new event is added to the Google Calendar, the process of generating tickets for this event will start.

Start Process in Plumsail Documents
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

After setting a trigger, add an action Start process. For that, search for Plumsail Documents, choose an action Start Process.

.. image:: ../../_static/img/user-guide/processes/zapier-start-process-action.png
    :alt: sample zap

Click Continue. If this is your first Zap, at this point, you'll need to Sign in to your `Plumsail Account <https://auth.plumsail.com/account/login>`_ from Zapier to establish a connection between the app and your account. If you already have a Plumsail account tied to the app, you can add another one at this step, and use it instead.

Customize Start Process
~~~~~~~~~~~~~~~~~~~~~~~

Choose the process you want to start by this Zap from the dropdown. 

.. image:: ../../_static/img/user-guide/processes/select-process-zapier.png
    :alt: select process

Then, you need to specify the data in JSON. This data will be applied to the template to personalize documents. 

.. important:: Properties from the JSON object should correspond to tokens used in your template. Learn more about templates `here <../user-guide/processes/create-template.html>`_.

Use the output from the trigger to specify values:

.. image:: ../../_static/img/user-guide/processes/JSON-data-Zapier.png
    :alt: JSON data in Zapier

Use the result file in Zapier
-----------------------------

It's possible to use the output of the Start process action further in the zap. 

You'll be able to add the result file as an attachment:

.. image:: ../../_static/img/user-guide/processes/result-file-zapier.png
    :alt: use resul file in Zapier

