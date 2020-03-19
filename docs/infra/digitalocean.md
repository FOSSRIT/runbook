DigitalOcean
============

This page documents the DigitalOcean team and infrastructure used for FOSS@MAGIC.


## Team

There is a _FOSS @ RIT MAGIC_ team registered in DigitalOcean's admin interface.
The DigitalOcean team is a shared group of accounts with direct access to the DigitalOcean Droplets:

![Screenshot of default DigitalOcean project from admin interface, shared among members of the FOSS @ RIT MAGIC team](/_static/infra/digitalocean-project.png)

### Access

Currently, three people have access to the shared _FOSS @ RIT MAGIC_ DigitalOcean team:

* Brenda Schlageter
* Justin W. Flory
* Stephen Jacobs

![Screenshot of FOSS @ RIT MAGIC team members from DigitalOcean admin interface](/_static/infra/digitalocean-team-members.png)

### Billing

FOSS@MAGIC covers the expenses for the Droplets on a monthly basis.
This is set up with automatic billing to the RIT MAGIC Center via an RIT-managed credit card.


## Droplets

Droplets are the billable "unit" in DigitalOcean.
They represent a specific service or server.

### Services

Currently, only one service is hosted as a DigitalOcean Droplet:

* [Discourse](discourse)

The Discourse Droplet is configured with automatic snapshot backups, taken once a week:

![Screenshot of Discourse Droplet backup configuration and history of recent backups in DigitalOcean admin interface](/_static/infra/digitalocean-droplet-backups.png)
