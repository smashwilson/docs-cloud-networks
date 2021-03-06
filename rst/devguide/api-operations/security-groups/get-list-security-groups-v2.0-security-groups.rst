
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _get-list-security-groups-v2.0-security-groups:

List security groups
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v2.0/security-groups

Retrieves a list of all security groups to which the specified tenant has access.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |Success                  |Request succeeded.       |
+--------------------------+-------------------------+-------------------------+
|401                       |Unauthorized             |The user is unauthorized |
|                          |                         |to make this request.    |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""








This operation does not accept a request body.




Response
""""""""""""""""





This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|security_groups           |Object                   |An array of security     |
|                          |                         |groups.                  |
+--------------------------+-------------------------+-------------------------+
|id                        |Uuid                     |The UUID for the         |
|                          |                         |security group.          |
+--------------------------+-------------------------+-------------------------+
|name                      |String                   |The security group name. |
+--------------------------+-------------------------+-------------------------+
|description               |String                   |The security group       |
|                          |                         |description.             |
+--------------------------+-------------------------+-------------------------+
|tenant_id                 |Uuid                     |The tenant ID of the     |
|                          |                         |owner of the security    |
|                          |                         |groups.                  |
+--------------------------+-------------------------+-------------------------+
|security_group_rules      |String                   |An array of rules in a   |
|                          |                         |security group.          |
+--------------------------+-------------------------+-------------------------+
|id                        |Uuid                     |The ID for the security  |
|                          |                         |group rule.              |
+--------------------------+-------------------------+-------------------------+
|direction                 |String                   |The direction (          |
|                          |                         |``ingress`` ). For a     |
|                          |                         |Cloud Servers instance,  |
|                          |                         |an ``ingress`` security  |
|                          |                         |group rule is applied to |
|                          |                         |incoming traffic for     |
|                          |                         |that instance.           |
+--------------------------+-------------------------+-------------------------+
|ethertype                 |String                   |The network ether type,  |
|                          |                         |either ``IPv4`` or       |
|                          |                         |``IPv6``.                |
+--------------------------+-------------------------+-------------------------+
|security_group_id         |Uuid                     |The security group ID    |
|                          |                         |for the security group   |
|                          |                         |with which the rule is   |
|                          |                         |associated.              |
+--------------------------+-------------------------+-------------------------+
|tenant_id                 |Uuid                     |The tenant ID of the     |
|                          |                         |security group rule      |
|                          |                         |owner.                   |
+--------------------------+-------------------------+-------------------------+
|port_range_min            |Int                      |The minimum port number  |
|                          |                         |in the range that is     |
|                          |                         |matched by the security  |
|                          |                         |group rule. If the       |
|                          |                         |protocol is ``TCP`` or   |
|                          |                         |``UDP``, this value must |
|                          |                         |be less than or equal to |
|                          |                         |the value of the         |
|                          |                         |``port_range_max``       |
|                          |                         |parameter. If the        |
|                          |                         |protocol is ``ICMP``,    |
|                          |                         |this value may be an     |
|                          |                         |``ICMP`` type. If the    |
|                          |                         |protocol attribute is    |
|                          |                         |"null", this value must  |
|                          |                         |be "null".               |
+--------------------------+-------------------------+-------------------------+
|port_range_max            |Int                      |The maximum port number  |
|                          |                         |in the range that is     |
|                          |                         |matched by the security  |
|                          |                         |group rule. The          |
|                          |                         |``port_range_min``       |
|                          |                         |parameter constrains     |
|                          |                         |this ``port_range_max``  |
|                          |                         |parameter. If the        |
|                          |                         |protocol is ``ICMP``,    |
|                          |                         |this value may be an     |
|                          |                         |``ICMP`` code. If the    |
|                          |                         |protocol attribute is    |
|                          |                         |"null", this value must  |
|                          |                         |be "null".               |
+--------------------------+-------------------------+-------------------------+
|protocol                  |String                   |The protocol that is     |
|                          |                         |matched by the security  |
|                          |                         |group rule. Valid values |
|                          |                         |are ``null``, ``tcp``,   |
|                          |                         |``udp``, and ``icmp``.   |
+--------------------------+-------------------------+-------------------------+
|remote_group_id           |String                   |The remote group ID.     |
|                          |                         |This attribute must be   |
|                          |                         |set to null since self-  |
|                          |                         |referential Security     |
|                          |                         |Groups are not supported.|
+--------------------------+-------------------------+-------------------------+
|remote_ip_prefix          |String                   |The remote IP prefix.    |
|                          |                         |This attribute matches   |
|                          |                         |the specified IP prefix  |
|                          |                         |as the source IP address |
|                          |                         |of the IP packet.        |
+--------------------------+-------------------------+-------------------------+







**Example List security groups: JSON response**


.. code::

   {
       "security_groups": [
           {
               "description": "default",
               "id": "85cc3048-abc3-43cc-89b3-377341426ac5",
               "name": "default",
               "security_group_rules": [
                   {
                       "direction": "ingress",
                       "ethertype": "IPv6",
                       "id": "c0b09f00-1d49-4e64-a0a7-8a186d928138",
                       "port_range_max": 22,
                       "port_range_min": 22,
                       "protocol": "TCP",
                       "remote_group_id": null,
                       "remote_ip_prefix": null,
                       "security_group_id": "85cc3048-abc3-43cc-89b3-377341426ac5",
                       "tenant_id": "5831008"
                   },
                   {
                       "direction": "ingress",
                       "ethertype": "IPv4",
                       "id": "f7d45c89-008e-4bab-88ad-d6811724c51c",
                       "port_range_max": 22,
                       "port_range_min": 22,
                       "protocol": "TCP",
                       "remote_group_id": null,
                       "remote_ip_prefix": null,
                       "security_group_id": "85cc3048-abc3-43cc-89b3-377341426ac5",
                       "tenant_id": "5831008"
                   }
               ],
               "tenant_id": "5831008"
           }
       ]
   }




