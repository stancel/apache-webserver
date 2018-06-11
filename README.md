apache-webserver
=========

A basic role to setup Apache Webserver on a Debian / Ubuntu based Linux OS.

Requirements
------------

You need the following items in order to use this role.
	
	* Domain that you want to use
	* SSL Cert File
	* Certificate Authority Cert File
	* Private Key Used to Create CSR (Certificate Signing Request)


Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

The Fully Qualified Domain Name you'll be using for the server you are creating. 

`server_fqdn: "yourdomainhere.com"`

The Apache Server Alias directive

`server_alias: "*.yourdomainhere.com"`

Path to your SSL Cert file

`ssl_certificate_file: "{{ lookup('file', '~/.ssh/my_ssl_cert.crt') }}"`

Path to your private key

`ssl_certificate_key_file: "{{ lookup('file', '~/.ssh/my_privatekey.key') }}" `

Path to the Certificate Authority Cert file

`ssl_ca_certificate_file: "{{ lookup('file', '~/.ssh/ca_cert.crt') }}"`


Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

	- hosts: your_server
	  vars_files:
	    - vars/main.yml
	  roles:
	    - { role: stancel.apache-webserver }


or 


	- hosts: your_server
	  vars:
		server_fqdn: "yourdomainhere.com"
		server_alias: "*.yourdomainhere.com"
		ssl_certificate_file: "{{ lookup('file', '~/.ssh/my_ssl_cert.crt') }}"
		ssl_certificate_key_file: "{{ lookup('file', '~/.ssh/my_privatekey.key') }}" 
		ssl_ca_certificate_file: "{{ lookup('file', '~/.ssh/ca_cert.crt') }}"


License
-------

BSD

Author Information
------------------

Brad Stancel
