Ansible user role
=================

This role adds and configures users with their password, shell, ssh
key, etc.

Variables
---------

Use the `users` array to define users and their parameters:

	users:
	  - name: <username>
	    [groups: <groups>]
	    [shell: <shell>]
	    [key: <ssh public key>]
	    [home: <home>]
	    [password: <password>]

NOTE: If setting the password, it is highly recommended that you
      encrypt it with ansible-vault.

Requirements
------------

Ensure the following are installed:

- passlib
