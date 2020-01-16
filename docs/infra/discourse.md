Discourse ([fossrit.community](https://fossrit.community/))
===========================================================

This page documents the Discourse service used for our community forums at [fossrit.community](https://fossrit.community/).
Discourse is where anyone may share topics for discussion with the wider FOSS@RIT community.


## Contact information

* **Owner**: FOSS@MAGIC Tech Team
* **Contact**: `#rit-foss-admin` / `#rit-foss-admin:matrix.org` / [telegram.me/fossrit_infra](https://t.me/fossrit_infra)
* **Persons**: [Justin W. Flory](https://github.com/jwflory)
* **Location**: Toronto, Canada (`TOR1`)
* **Servers**: `fossrit.community`
* **Purpose**: Discussion forums for FOSS@RIT community.


## Hosts

The current deployment is made up of a single DigitalOcean droplet, `fossrit.community`.
This host runs:

* Docker
* [Discourse Docker image](https://github.com/discourse/discourse_docker)

This host relies on:

* SendGrid API key (for outgoing mail, eventually incoming)


## Deploying

Our Discourse site was deployed exactly as described in upstream's documentation:

* [Install guide](https://github.com/discourse/discourse/blob/0c4ac2a7bc726176b1d76b98f789a35e5d1bddfc/docs/INSTALL-cloud.md)
* [Email setup guide](https://github.com/discourse/discourse/blob/0c4ac2a7bc726176b1d76b98f789a35e5d1bddfc/docs/INSTALL-email.md)


## Configuration

We do not use config files to maintain Discourse.
The config settings are dynamic and stored inside the image container.
If a rollback is needed, see [Backups](#backups).


## Upgrading

[_Excerpt from meta.discourse.org._](https://meta.discourse.org/t/how-do-i-manually-update-discourse-and-docker-image-to-latest/23325)

> If you self-host Discourse, you occasionally need to run a manual update via the command line to get the latest security releases newest libraries.
> These updates are not picked up in admin/upgrade, which is why you’ll occasionally need to do this additional step.
>
> * Discourse itself should be updated about twice a month, by clicking the “Update to Latest Version” button in your admin dashboard (`admin/upgrade`).
>   We do beta releases roughly once every week.
> * Every two months we recommend SSH’ing into your web server and doing

```sh
cd /var/discourse
git pull
./launcher rebuild app
```

> * As for Ubuntu updates, make sure you have automatic security updates enabled for your Ubuntu!
>   The command is:

```sh
dpkg-reconfigure -plow unattended-upgrades
```

> However, that just covers critical security updates. Every so often you should get all the OS updates like so:

```sh
apt-get update
apt-get dist-upgrade
```

> To summarize:
>
> * update Discourse twice a month via web updater
> * update the container every two months
> * update the OS every six months
>
> You could double these numbers and still be fairly safe, e.g. update Discourse once a month, container every 4 months, OS once every 12 months, and so on.
>
> But you really, really want automatic security updates enabled in Ubuntu, as listed above – all our Digital Ocean “one-time installs” already have automatic security updates set up.


## Backups

Two types of backups are made of the Discourse site:

### Site-level backups

The Discourse site takes a weekly backup of site content, usually between 00:00–01:00 on Thursdays.
These backups are available from the admin panel:

> [fossrit.community/admin/backups](https://fossrit.community/admin/backups)

These backups can be used for rollbacks, triggered by admin users.


### Droplet-level snapshots

Snapshots are currently enabled via DigitalOcean ($2/month).
They are scheduled to start weekly Friday 3 PM to Saturday 2 PM (EST).
Snapshots can be accessed via the DigitalOcean droplet settings.
