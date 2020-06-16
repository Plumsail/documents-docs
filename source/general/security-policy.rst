Data protection and security
############################

Privacy Policy
--------------

General information about privacy protection can be found in the `Plumsail Documents Privacy Policy <privacy-policy.html>`_.

Application security
--------------------

Plumsail Documents is hosted in Microsoft Azure. The infrastructure for databases and application servers is managed and maintained by `Azure`_.

We are seriously concerned about your security, so, everything from engineering to deployment performed with our highest standards of security. Our source code repositories are regularly scanned for security issues and our network is protected by a firewall.

We have a QA department which reviews and test our code for any security vulnerabilities. Testing is occurred in a separate environment from production. We don't use any customer's data during testing.

Also, we are using IDS technologies to monitor our network for malicious activity or policy violations.

Data security
-------------

Plumsail Documents collects very few information about customers - only subscription email is required for license validation. After installing Plumsail Documents, the only data that we are gathering from you is application logs from the system.

Whenever your data is in transit between you and us, everything is encrypted and sent using HTTPS. Data at rest is encrypted using `AES 256`_ bit standards (one of the strongest block ciphers available) with keys managed by Azure Storage Service Encryption. Data in transit is encrypted with SSL/TLS protocols.

In Documents we use a multi-tenant data model, so each user has a unique tenant ID and only logged-in and verified users can have an access to the application.

Access to data of your subscription governed by access rights and can be configured to different permission levels.

All that data is stored in Microsoft Azure. Backups are taken every day. Application logs are stored for a week.


Business transactions
---------------------

We protect your billing information. All transactions are processed through secure encryption and sensitive data are transmitted, stored and processed on PCI DSS network.

Physical security
-----------------

Plumsail Documents hosts all data in Microsoft Azure which data centers have been tested for security, availability and business continuity. For more information, take a look at `this link`_.
`Disaster recovery program`_ ensures that our services will be available or are easily recoverable in the case of any catastrophe.


Compliance Certifications
-------------------------

Azure data center is certified for ISO 27001, SOC I, II AND III, HIPAA and FedRAMP compliance. Visit `Azure trust center`_. 

Get in touch with us
---------------------
If you have any questions about our security policy, please, feel free to drop a line at support@plumsail.com.


.. _Azure: https://www.microsoft.com/en-us/trustcenter/Security/AzureSecurity
.. _AES 256: https://en.wikipedia.org/wiki/Advanced_Encryption_Standard
.. _this link: https://www.microsoft.com/en-us/trustcenter/Security/AzureSecurity
.. _Disaster recovery program: https://azure.microsoft.com/en-us/documentation/articles/resiliency-disaster-recovery-high-availability-azure-applications/
.. _Azure trust center: https://azure.microsoft.com/en-us/support/trust-center/