Ansible Playbooks for Red Hat/Rocky Linux Testing
=================================================

This project is a by-product of my study on RHEL specifics to prepare
for the RHCSA exam. The roles are self-contained and modular, so
they should be easy to be repurpose for other projects.

Bootstrapping
-------------

In the future I may include a bootstrap playbook, but for now to
bootstrap the server, create the ansible user, grant ansible sudo
privledges without a password, and authorize your ssh key:

	# useradd ansible
	# visudo # Insert "ansible	ALL=(ALL)	NOPASSWD: ALL"
	# su ansible
	$ cd
	$ mkdir .ssh
	$ chown 750 .ssh
	$ cat "$SSH_KEY" > .ssh/authorized_keys
	$ chown 640 .ssh/authorized_keys


Ansible Vault
-------------

The `vault_password_file` is a script that integrates with an
internal package manager, and must be updated to use your system
of choice (or just a password file).

The `vaultvar` is a helper script included in the `bin` directory
wrapping `ansible-vault` to set the variable name for encrypted
data.

Playbooks
---------

Playbooks are located in the `playbooks` directory. To configure
the system, run the `configure.yml` playbook.

Roles
-----

See each role's `README.md` for documentation on their purpose and
variables.
