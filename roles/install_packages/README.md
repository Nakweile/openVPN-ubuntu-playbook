Install packages
=========

For Ubuntu OS.
This role updates the package cache, upgrades already installed packages, and installs the packages specified in the /Install_packages/vars/main.yml variable.

Role Variables
--------------

To install the required list of packages, add them to the vars/main.yml file or explicitly specify them in your playbook. 
The default variable for the role is Python3.

Example Playbook
----------------

Example of how to use your role:

1. When specifying variables in a variable file::
````
	- hosts: servers
	  roles:
		- Install_packages
````
2. When specifying variables in the playbook:
````
	- hosts: servers
	  roles:
		- role: Install_packages
		  vars:
			packages_list_for_install:
			  - bat
			  - nginx
````

License
-------

BSD

Author Information
------------------

Kornilov Kirill

kornilov.kd@mail.ru