Ansible
=======

This page documents the Ansible configuration management repository at [FOSSRIT/infrastructure](https://github.com/FOSSRIT/infrastructure).
Any changes to services or applications managed on FOSS@MAGIC infrastructure are managed in this git repo.


## Contact information

* **Owner**: FOSS@MAGIC Tech Team
* **Contact**: `#rit-foss-admin` / `#rit-foss-admin:matrix.org` / [telegram.me/fossrit_infra](https://t.me/fossrit_infra)
* **Persons**: [Justin W. Flory](https://github.com/jwflory), [Tim Zabel](https://github.com/tjzabel)
* **Location**: Toronto, Canada (`TOR1`)
* **Purpose**: Configuration management for FOSS@MAGIC infrastructure.


## Background

The FOSS@MAGIC Tech Team uses Ansible for system change management.
Previously, no configuration management tool was used for our infrastructure.
Some git commits go back to 2013 for a few scripts used back in the day, but the migration to Ansible started in September 2018.


## Overview

Ansible playbooks are run locally by a system administrator.
A system administrator can run Ansible playbooks once a user and SSH key is set up for them on the host.
New SSH keys and users are defined in the `sshd` role (see [Roles](#roles)).

Playbooks are idempotent (or should be).
Meaning you should be able to re-run the same playbook over and over and it should get to a state where 0 items are changing.


## git repo

There is one repository associated with Ansible, [FOSSRIT/infrastructure](https://github.com/FOSSRIT/infrastructure).
This is a public repository.
Private data is stored via encryption with [Ansible Vault](https://docs.ansible.com/ansible/latest/user_guide/vault.html).
The encryption passphrase is shared on a need-to-know basis with infrastructure maintainers.

It is recommended to configure `git` to use `pull --rebase` by default.
Do this with the following command in your local clone of the infrastructure git repo:

```sh
git config --bool pull.rebase true
```

This prevents unneeded merges which can occur if someone else pushes changes to the repository while you are working on your own local changes.


## Directory setup

### Inventory

The `inventory/` directory tells Ansible what hosts are available and any groups they belong to.
All files in this directory are concatenated together, so you can split out groups/hosts into separate files for readability.
They are in `ini` file format.

Additionally, under the inventory directory are `host_vars/` and `group_vars/` subdirectories.
These are files named for the host or group and containing variables to set for that host or group.
You should strive to set inventory variables in the highest level possible, and precedence is in:

* Global
* Group
* Host order.

### Vars

This directory contains global variables as well as OS specific variables.
Note that in order to use OS-specific variables, you must have `gather_facts` as `True` or Ansible will not be able to determine the OS.

### Roles

Roles are a collection of tasks/files/templates that can be used on any host or group of hosts that all share that role.
In other words, roles should be used except in cases where configuration only applies to a single host.
Roles can be reused between hosts and groups and are more portable/flexible than tasks or specific plays.

### Scripts

The `scripts/` directory includes miscellaneous utilty scripts for sysadmins.

### Playbooks

There is a `playbooks/` directory where YAML playbooks are stored.
The top level contains utility playbooks for sysadmins.
These playbooks perform one-off functions or gather information.
Under this directory are `hosts/` and `groups/` playbooks.
These playbooks are for specific hosts and groups of hosts, from provision to fully configured.
You should only use a host playbook in cases where there will never be more than one of that thing.


## Additional resources

* [Upstream docs](https://docs.ansible.com/)
* Examples:
    * [github.comansible/ansible-examples](https://github.com/ansible/ansible-examples)
    * [gist.github.com/marktheunissen/2979474](https://gist.github.com/marktheunissen/2979474)
* [Jinja docs](https://jinja.palletsprojects.com/)
