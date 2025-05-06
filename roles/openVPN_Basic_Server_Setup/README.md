OpenVPN Basic Server Setup Role
=========

The openVPN_Basic_Server_Setup Ansible role configures basic network settings required for an OpenVPN server. Specifically, it enables IP forwarding and adds a NAT masquerade rule to iptables.

Role Variables
--------------

- Enables IP forwarding (net.ipv4.ip_forward).

- Adds a NAT masquerade rule for the VPN subnet 10.8.0.0/24.

- Supports saving iptables rules via a handler.

Example Playbook
----------------

Example of how to use role:

1. When specifying variables in a variable file::
````
  - hosts: vpn_servers
    become: true
    roles:
    - openVPN_Basic_Server_Setup
````

Requirements
------------

- Ansible 2.9+

- Recommended to run as root (or with become: true)

- Required collections:

  - ansible.builtin (included by default)

Notes
-----

- Make sure iptables is installed and used as the active firewall.

- The default subnet (10.8.0.0/24) and interface are assumed; you can modify the role if needed.

License
-------

BSD

Author Information
------------------

Kornilov Kirill

kornilov.kd@mail.ru