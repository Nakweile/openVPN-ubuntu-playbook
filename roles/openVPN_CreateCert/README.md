OpenVPN Certificate Authority & Client Configuration Role
=========

This Ansible role automates the setup of a Certificate Authority (CA) and the generation of server and client certificates for an OpenVPN deployment using Easy-RSA.

Features
--------

- Initializes a Public Key Infrastructure (PKI) using Easy-RSA.

- Builds a CA, server certificates, and client certificates (no password).

- Generates dh.pem, crl.pem, and ta.key for enhanced security.

- Copies necessary certificate files to the OpenVPN server directory.

- Generates the server.conf from a template and starts the OpenVPN server.

- Prepares .ovpn configuration files for clients, fully bundled with certs/keys.

- Fetches the client .ovpn files to the Ansible controller for distribution.

Role Variables
--------------

|Variable|Description|Required|Example| 
|--|--|--|--|
|`openvpn_dir`|Base directory for OpenVPN setup|Yes|`/etc/openvpn`|
|`openvpn_easy_rsa_dir`|Path to Easy-RSA scripts|Yes|`/usr/share/easy-rsa`|
|openvpn_clients_list|List of client names to generate certificates|Yes|`['client1', 'client2']`|

*It is recommended to specify variables in the defaults folder*

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```
- 
  name: Download openVPN on ubuntu server
  hosts: vpn
  become: true

  roles:
    - openVPN_CreateCert

```

Templates
---------

Make sure the following templates exist in the role's templates/ directory:

- server.conf.j2 – server configuration template

- client.ovpn.j2 – client configuration template

Requirements
------------

OpenVPN installed on the target host

- Easy-RSA available on the system

- Ansible 2.9+

- Root privileges (become: true)

Output
------

Client configuration files in .ovpn format will be downloaded to:
```
<your playbook directory>/ovpn/<client_name>.ovpn
```
These files can be directly used by OpenVPN clients.

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).

Kornilov Kirill

kornilov.kd@mail.ru