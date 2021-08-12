infra_client_dhcp_relayagent
=========

A simple role to setup a dhcp relay agent for a host with subnets not directly connected to the the dhcp server network.

Requirements
------------

* The dhcp relay agent configuration provided MUST be correct. The role DOES NOT validate if the listening network interface or the DHCP Server IP is correct.

Releases
------------

|Branch|Status|Description| Date
|---	|---	|---	|---
|main|Unstable|Development Branch|Now
|1.0.0|Release|Release 1.0.0|12-08-2021


Role Variables
--------------

**top level vars**
|Variable|Level|Type|Description
|---|---|---|---	
|dhcp_listen_interface|Default|string|The interface which listens for DHCP Requests
|dhcp_server_ip|Default|string|The DHCP Server to forward the request.
|dhcp_relayagent_package|Vars|string|The dhcp relay agent package in a valid NEVRA or NSVCA form. https://docs.fedoraproject.org/en-US/modularity/architecture/nsvca/  	



```
dhcp_relayagent_package: dhcp-relay-12:4.3.6-44.0.1.el8

dhcp_listen_interface: tap0
dhcp_server_ip: 10.0.2.100
```



Dependencies
------------
NA


Example Playbook
----------------


```
---
- hosts: dhcp_relay_agent
  become: yes
  roles:
    - role: infra_server_dhcp_dhcpd
      vars:
        dhcp_listen_interface: tap0
        dhcp_server_ip: 10.0.2.100
```

License
-------

Apache-2.0

Author Information
------------------

```
Petros Petrou
email: ppetrou@gmail.com
web: www.petrospetrou.co.uk
```
