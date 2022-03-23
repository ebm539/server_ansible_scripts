These are the Ansible scripts used to configure my server. They are a work-in-progress!

The Ansible scripts assume that the hosts have a dedicated `automatedscriptrunner` user created, with a `~automatedscriptrunner/.ssh/authorized_keys` file containing the public SSH key of the host/user that runs the Ansible scripts.
Additionally, the scripts assume that the `automatedscriptrunner` user can run all commands as root using `sudo` without requiring a password (i.e. in `/etc/sudoers`, the line `automatedscriptrunner ALL=(ALL) NOPASSWD: ALL` exists)

Other assumptions:
- The host (i.e. the machine the scripts are applied to) runs Debian bullseye on the amd64 architecture
- There is only one Ethernet interface, and it is `eth0`

## Roles to implement

- Firewall rules for all other services (firewalld?)
- chronyd
- Nginx
- [Nginx with quiche](https://github.com/cloudflare/quiche/tree/master/nginx)
- [Nginx with ngx_pagespeed](https://github.com/apache/incubator-pagespeed-ngx)
- Postfix, Dovecot, Rspamd, Redis, OpenDKIM, OpenDMARC
- MariaDB (may replace with Postgres)
- Grafana, Telegraf, InfluxDB
- [Mosquitto](https://github.com/eclipse/mosquitto)
- Unbound

I'm planning to use Docker when implementing the roles (with the exceptions firewalld and chronyd),
but I'm also planning not to be solely reliant on the Docker Hub (potential single point of failure and security concerns).
Perhaps I should look at something akin to FreeBSD jails.


## Potential roles to implement on my laptop

- GitLab, Jenkins (i.e. CI/CD)
