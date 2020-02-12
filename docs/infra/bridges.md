Chat bridges
============

This page documents the bridge services maintained by the [FOSS@RIT Tech Team](https://github.com/orgs/FOSSRIT/teams/tech-team).
Chat bridges are used to "bridge" different chat rooms together (e.g. a Telegram group to an IRC channel).


## Matterbridge

[Matterbridge](https://github.com/42wim/matterbridge) is an open source chat bridge that supports various chat platforms.
Currently, FOSS@RIT uses it to connect the [RITlug Slack](https://rit-lug.slack.com) to IRC channels on Freenode (see [IRC (Freenode)](irc)).

### Maintenance

The FOSS@RIT Matterbridge instance is deployed on [RITlug](https://ritlug.com) infrastructure hosted in RIT's Institute Hall data center.
Configuration and deployment details are managed in [FOSSRIT/infrastructure](https://github.com/FOSSRIT/infrastructure) as an [Ansible Role](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html).
The upstream Ansible Role is maintained at [jwflory/ansible-role-matterbridge](https://github.com/jwflory/ansible-role-matterbridge).

### Upgrading

Upgrading Matterbridge requires changing two variables in the Ansible Role:

1. Version number (`matterbridge_config.version`)
2. Binary checksum (`matterbridge_config.binary_checksum`)

Both the version and binary checksum are found on Matterbridge's [releases page](https://github.com/42wim/matterbridge/releases).
You can find the binary checksum in the `checksums.txt` file, attached as an artifact to Matterbridge releases.
We use the hash for the `linux-64bit` compiled binary.

See the following pull requests for examples:

* [FOSSRIT/infrastructure#59](https://github.com/FOSSRIT/infrastructure/pull/59 "matterbridge: Update to v1.16.1")
* [FOSSRIT/infrastructure#66](https://github.com/FOSSRIT/infrastructure/pull/66 "matterbridge: Upgrade v1.16.2 -> v1.16.3")
* [FOSSRIT/infrastructure#76](https://github.com/FOSSRIT/infrastructure/pull/76 "matterbridge: Upgrade to v1.16.5")


## TeleIRC

[TeleIRC](https://github.com/RITlug/teleirc) is an open source chat bridge for connecting Telegram groups to IRC channels.
It is maintained by the [RIT Linux Users Group](https://ritlug.com).
Currently, FOSS@RIT uses it to connect various Telegram groups to IRC channels on Freenode (see [Telegram](telegram), [IRC (Freenode)](irc)).

### Maintenance

All FOSS@RIT TeleIRC instances are deployed on [RITlug](https://ritlug.com) infrastructure hosted in RIT's Institute Hall data center.
Configuration and deployment details are managed in [FOSSRIT/infrastructure](https://github.com/FOSSRIT/infrastructure) as an [Ansible Role](https://docs.ansible.co).
The upstream Ansible Role is maintained at [jwflory/ansible-role-teleirc](https://github.com/jwflory/ansible-role-teleirc).

### Upgrading

There are two types of upgrades: TeleIRC and the Ansible Role.

#### TeleIRC

Only one variable in the Ansible Role needs to be changed in most cases: `default_version`.
Change this variable to the targeted version and run the Ansible playbook to deploy the update.

See the following pull requests for examples:

* [FOSSRIT/infrastructure#55](https://github.com/FOSSRIT/infrastructure/pull/55 "teleirc: Version bump to v1.3.2")
* [FOSSRIT/infrastructure#63](https://github.com/FOSSRIT/infrastructure/pull/63 "teleirc: Upgrade v1.3.2 -> v1.3.3")

#### Ansible Role

Occasionally the upstream Ansible Role will change.
When this happens, the Ansible Role needs to be upgraded in the downstream repository, i.e. FOSSRIT/infrastructure.
The upgrade can be done from the root directory of the repo with the following commands:

```sh
ansible-galaxy role install --force jwflory.teleirc
git checkout HEAD roles/jwflory.teleirc/vars/{main,vault}.yml
```

An example of an upgrade is found in [FOSSRIT/infrastructure@75c0bbc](https://github.com/FOSSRIT/infrastructure/commit/75c0bbc94a74207088a09221199c1a0c94438539).
