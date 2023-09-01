==================
Trust
==================

In Veritawall, certificates are used for ensuring trust between peers. To make using them easier, Veritawall allows creating
certificates from the front-end. In addition to that, it also allows creating certificates for other purposes,
avoiding the need to use the ``openssl`` command line tool. Certificates in Veritawall can be managed from
:menuselection:`System --> Trust --> Certificates`.

Examples of Veritawall components that use certificates:

* OpenVPN
* IPsec
* Captive Portal
* Web Proxy

-----------------
Certificate types
-----------------

The following types of certificate can be generated in Veritawall:

* Client
* Server
* Combined Client/Server
* Certificate Authority

In addition to this, Veritawall can generate a Certificate Signing Request (CSR). This can be used if you want to create a
certficate signed by an external CA.

.. warning::

    Make sure that you select the correct certificate type, as many clients will refuse connection (or at least show
    errors) if an incorrect certificate type is used. For example, you can use either a server certificate or a
    combined client/server certificate to secure the connection to the web interface, but not a CA or client certificate.


-------------------------
Usage examples
-------------------------
In :doc:`/manual/how-tos/self-signed-chain` you will find examples of how to setup certificate chains yourself.
