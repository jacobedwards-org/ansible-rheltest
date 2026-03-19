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
	    [shell_rc: <shell_rc>]
	    [password: <password>]

NOTE: If setting the password, it is highly recommended that you
      encrypt it with ansible-vault.

The `shell_rc` parameter is a map that defines environment variables,
functions, and settings in the profile and rc file of the shell.
Currently environment variables are processed normally by the shell
(in double quotes). If more of the system is covered in the future
(for example, default PATH), then this may change to be literal.
The map looks like this:

	env:
	  PS1: "\\h\\$ "
	functions:
	  ll: "ls -l"
	options:
	  vi: true

Requirements
------------

Ensure the following are installed:

- passlib
