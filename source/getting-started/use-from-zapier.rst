Use Zapier
==========

`Zapier <https://zapier.com/apps/plumsail-documents/integrations>`_ allows you to connect the `Processes <https://plumsail.com/docs/documents/v1.x/user-guide/processes/index.html>`_ with thousands of other web applications. 

**Plumsail Processes** are a user-friendly interface where you can configure your documents flow and make it automated. You work with templates, create documents in different formats, convert them, protect if needed, or add watermarks to PDFs, deliver the results - all actions in one place. 

.. contents::
    :local:
    :depth: 2

Introduction to Zapier
~~~~~~~~~~~~~~~~~~~~~~

**Zaps** are automated connections between apps in Zapier. Every Zap has a **trigger** - an event that makes this Zap start. And after the trigger, an **action** or a series of actions follow to bring the desired result.

Some apps integrated with Zapier have both triggers and actions. Some have either triggers or actions.

Plumsail Documents include an action **Start Process**.

.. image:: ../../_static/img/user-guide/processes/start-process-zapier.png
    :alt: Start process in Zapier

Create zaps with Plumsail Documents
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can generate personalized documents based on data from thousands of apps in Zapier. Various events can trigger an automated connection of apps - a Zap. It can be web form entries, new rows in sheets, new events in calendars, new opportunities in CRM - the list is never-ending. 

We'll show how to handle Plumsail Documents action - Start Process - in Zapier.  

Let us say you have a Google Calendar for conferences. You need to generate personalized invitations. 

This is how our Zap looks:

.. image:: ../../_static/img/user-guide/processes/sample-zap.png
    :alt: sample zap

Set trigger
-----------

The first step is a trigger. In this particular case, it's a new event in the Google Calendar. 

When a new event is added to the Google Calendar, the process of generating tickets for this event will start.

Start Process in Plumsail Documents
-----------------------------------

After setting a trigger, add an action Start process. For that, search for Plumsail Documents, choose an action Start Process.

.. image:: ../../_static/img/user-guide/processes/zapier-start-process-action.png
    :alt: sample zap

Click Continue. If this is your first Zap, at this point, you'll need to Sign in to your `Plumsail Account <https://auth.plumsail.com/account/login>`_ from Zapier to establish a connection between the app and your account. If you already have a Plumsail account tied to the app, you can add another one at this step, and use it instead.

Customize Start Process
-----------------------

Choose the process you want to start by this Zap from the dropdown. 

.. image:: ../../_static/img/user-guide/processes/select-process-zapier.png
    :alt: select process

Then, you need to specify the data in JSON. This data will be applied to the template to personalize documents. 

.. important:: Properties from the JSON object should correspond to tokens used in your template. Learn more about templates `here <../user-guide/processes/create-template.html>`_.

Use the output from the trigger to specify values:

.. image:: ../../_static/img/user-guide/processes/JSON-data-Zapier.png
    :alt: JSON data in Zapier

Use the result file in Zapier
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

It's possible to use the output of the Start process action further in the zap. 

You'll be able to add the result file as an attachment:

.. image:: ../../_static/img/user-guide/processes/result-file-zapier.png
    :alt: use resul file in Zapier



