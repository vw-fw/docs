==================================
Access / User Management
==================================

.. image:: images/user_manager.png
   :width: 100%

The user manager of Veritawall allows for controlling access to the different
part (pages) of the configurator as well as controlling access to particular
services on a per user bases.

Authentication
--------------
Veritawall offers integration with external servers for services that require user
authentication. These services include:

* IPsec
* OpenVPN
* Captive Portal
* Proxy

Integrated into Veritawall are the **Local User Database** and **Voucher Server**.
The Voucher Server is intended to be used with the Captive portal.

External service currently supported are:

* LDAP (OpenLDAP, MS Active Directory, Novell eDirectory)
* Radius

Authorization
-------------
Besides authenticating, user authorization to access parts of the configuration
can also be setup with an external server, but in order to grant the appropriate
privileges to the users they need to be imported in Veritawall's local user manager.
This way one can validate a user against its externally stored password and have
a fine grained control over the configuration pages that user may access.


Users, Groups & Privileges
--------------------------
When using the local user manager, either stand alone or on combination with an
external authentication server one can define groups to combine a set of privileges
for a specific user group. A user should be an individual, a group needs to be
specific in such a way that anyone of that group can be granted the same access
rights, called privileges.

Authentication services
----------------------------------

Authentication services can be configured using the settings in :menuselection:`System --> Access --> Servers`.
This includes both local accounts and remote authentication.

By default, Veritawall GUI login will use local accounts. This can be changed, however,
by going to :menuselection:`System --> Settings --> Administration`, scrolling down to the "Authentication" group,
and changing the 'Server' option.

Local account configuration
---------------------------

Settings for handling login via local accounts can be set by going to :menuselection:`System --> Access --> Servers`,
then clicking the 'Edit' icon (a pencil) for 'Local Database'. Here, you can improve security of
local user accounts by setting password length and complexity constraints.

An overview of available settings:

=====================================  ============================================================================================
 **Policy**                            Enable password policy constraints.
 **Duration**                          [Policy] Password duration, optionally define how often the user should change his or her password.
 **Length**                            [Policy] Minimum password length to require.
 **Complexity**                        [Policy] Enforce password complexity checks.
=====================================  ============================================================================================



Configuration
-------------


.. toctree::
   :maxdepth: 2
   :titlesonly:

   how-tos/user-local
   how-tos/user-ldap
   how-tos/user-radius
   two_factor


.. Note::

    When using external authentication services (such as ldap), the firewall needs a route to the configured target machine
    in order to function properly. Specifically when the server is only reachable over a classic IPsec tunnel (non VTI),
    a static route might be needed to guide the packets into the right tunnel matching the policy. (for example
    when a policy for LAN exists, add a gateway pointing to our own address and a static routing pusing traffic to the
    other end).

    A quick test if the routes are properly setup can always be performed using ping from the :code:`default` source address.
