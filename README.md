ansible-playbooks
=================

This repository includes some ansible playbooks and roles I use to bootstrap and maintain the services I run in my local network using a bunch of raspberry pi's. The goal is to make the installation process easy and repeatable, but it's not (yet) fully automated: some configurations need to be done manually before running, such as installing and configuring the OS, setting up partitions, networking, installing python, etc...

I run Alpine Linux, some parts use `apk` and `lbu`.

Sensitive variables are encripted using ansible vault, I made a simple client for [`pass`](https://www.passwordstore.org), the password manager I use.

Services
--------

* AdGuardHome: add blocker and dns server
* Caddy: used as reverse proxy and dynamic DNS client
* Prometheus Server to collect metrics
* Grafana for dashboards and alerting
* Speedtest to measure internet speeds

Run
---

```
ansible-playbook --vault-id $VAULT_ID@vault-pass-client.sh -i hosts.yml main.yml
```
