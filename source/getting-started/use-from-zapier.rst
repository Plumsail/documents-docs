Use Zapier
==========

`Zapier <https://zapier.com/apps/plumsail-documents/integrations>`_ allows you to connect the `Processes <https://plumsail.com/docs/documents/v1.x/user-guide/processes/index.html>`_ with thousands of other web applications. 

**Plumsail Processes** are a user-friendly interface where you can configure your documents flow and make it automated. You work with templates, create documents in different formats, convert them, protect if needed, or add watermarks to PDFs, deliver the results - all actions in one place. 

Introduction to Zapier
~~~~~~~~~~~~~~~~~~~~~~

**Zaps** are automated connections between apps in Zapier. Every zap has a **trigger** - an event that makes this zap start. And after the trigger, an **action** or a series of actions follow to bring the desired result.

Some apps integrated with Zapier have both triggers and actions. Some have either triggers or actions.

Plumsail Documents include an action **Start Process**.

.. image:: ../../_static/img/user-guide/processes/start-process-zapier.png
    :alt: Start process in Zapier

Let's have a look at how to create a zap with Plumsail Documents to start a process of generating personalized documents from your favorite apps. 

Connect Plumsail Documents to other apps in Zapier
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can generate personalized documents from thousands of apps. You need to set a trigger. It may be various events like web form entries, new rows in sheets, new events in calendars, new opportunities in CRM - the list is never-ending. 

We'll show a simple case of generating event tickets from a newly created event in a Google Calendar. 

Let us say you have a Google Calendar for conferences. You need to generate personalized invitations. 

This is how our zap looks:

.. image:: ../../_static/img/user-guide/processes/sample-zap.png
    :alt: sample zap

A new event in the Google Calendar starts the process of generating tickets for this event. 

After setting a trigger, add an action Start process. For that, search for Plumsail Documents, choose an action Start Process.

.. image:: ../../_static/img/user-guide/processes/zapier-start-process-action.png
    :alt: sample zap

Click Continue. If this is your first Zap, at this point, you'll need to Sign in to your `Plumsail Account <https://auth.plumsail.com/account/login>`_ from Zapier to establish a connection between the app and your account. If you already have a Plumsail account tied to the app, you can add another one at this step, and use it instead.

The next step is **Customize Start Process**. 

At first, choose the process you want to start by this Zap from the dropdown. 

.. image:: ../../_static/img/user-guide/processes/select-process-zapier.png
    :alt: select process

Then, you need to specify the data in JSON. This data will be applied to the template to personalize the documents. 

.. important:: Properties from the JSON object should correspond to tokens used in your template. 

We use the output from our trigger to specify values:

.. image:: ../../_static/img/user-guide/processes/JSON-data-Zapier.png
    :alt: JSON data in Zapier

Use the result file in Zapier
-----------------------------

It's possible to use the output of the Start process action further in the zap. 

You'll be able to add the result file as an attachment:

.. image:: ../../_static/img/user-guide/processes/result-file-zapier.png
    :alt: use resul file in Zapier



