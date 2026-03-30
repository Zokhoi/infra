# Infra

This ansible playbook is used to set up and configure my local servers for self hosted services, and machines for daily usage.

A few of the tasks directly calls for `apt` or `apk`, therefore this playbook repo mostly only applies to Debian or Alpine based distros.
Other distros may gain support when I decide to adapt them.

Host mappings:
* main -> main homelab server
* pirouter -> a mobile router on Raspberry Pi 4
* dev -> a dev server which can be wiped at any moment, a Radxa Rock 3C
* phone -> a linux phone running postmarketOS, OnePlus 6T

Runtimes include:
* NodeJS
  * nvm
* Python
  * pyenv
* Docker
  * portainer

Services include:
* postgres
* cloudflared
* certbot
* dnsmasq
* hostapd

Applications include:
* [Homepage](https://github.com/gethomepage/homepage)
* [Nextcloud](https://github.com/nextcloud/server)
* [Code-server](https://github.com/coder/code-server)
* [Icalingua++](https://github.com/Icalingua-plus-plus/Icalingua-plus-plus)
* [Mustemmer](https://github.com/Zokhoi/Mustemmer)
* [Gitea](https://github.com/go-gitea/gitea) or [Forgejo](https://codeberg.org/forgejo/forgejo)
* [Uptime Kuma](https://github.com/louislam/uptime-kuma)
* [Grafana](https://github.com/grafana/grafana)

## Deployment
Activate the python venv, then run
```sh
ansible-playbook --ask-pass --ask-become-pass --ask-vault-pass run-<system>.yml
```
or shortened version
```sh
ansible-playbook -kKJ run-<system>.yml
```

