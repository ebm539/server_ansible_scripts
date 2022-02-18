These are the Ansible scripts used to configure my server. They are a work-in-progress!

The Ansible scripts assume that the hosts have a dedicated `automatedscriptrunner` user created, with a `~automatedscriptrunner/.ssh/authorized_keys` file containing the public SSH key of the host/user that runs the Ansible scripts.
Additionally, the scripts assume that the `automatedscriptrunner` user can run all commands as root using `sudo` without requiring a password (i.e. in `/etc/sudoers`, the line `automatedscriptrunner ALL=(ALL) NOPASSWD: ALL` exists)

Other assumptions:
- The host (i.e. the machine the scripts are applied to) runs Debian bullseye on the amd64 architecture
- There is only one Ethernet interface, and it is `eth0`
