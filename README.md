# OpenVPN Ubuntu Setup Playbook
---

OpenVPN Setup Playbook
----------------------
This playbook automates the installation and basic configuration of an OpenVPN server on Ubuntu.

Features
--------
- Installs required packages

- Enables IP forwarding and sets up NAT

- Initializes a certificate authority and generates server/client certificates

Usage
-----
Run the playbook with:
```
ansible-playbook -vD -K -i inventory playbook.yaml
```

Roles Used
----------

- install_packages – installs OpenVPN and required dependencies

- openVPN_Basic_Server_Setup – configures system networking for VPN

- openVPN_CreateCert – generates CA, server, and client certificates

Requirements
------------
- Ubuntu-based target hosts

- Root access (become: true)

- Defined vpn group in your inventory

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).

Kornilov Kirill

kornilov.kd@mail.ru