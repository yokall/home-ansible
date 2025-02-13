# Home Ansible

This ansible is for managing my home server(s), currently there is only a single raspberry pi.

## Prerequisites

1. `apt update`
2. `apt install -y ansible ansible-lint`

## PiHole

The current aim of this project is to install [pi-hole](https://pi-hole.net/)

## Check Connection to Server

`ansible-playbook -i inventory/hosts.ini playbooks/test_connection.yml -e 'ansible_user=root'`

> **Note:** The ansible_user extra variable is only required if the remote user has not been created yet.

## Add non-root user

On a fresh Diet-Pi OS the only user is root, the below playbook installs another user.

Ran `ansible-playbook -i inventory/hosts.ini playbooks/add_user.yml -e 'ansible_user=root'`

> **Note:** The ansible_user extra variable is only required if the remote user has not been created yet.

## Install pi-hole

Install or update Pi-Hole

Ran `ansible-playbook -i inventory/hosts.ini playbooks/install_pihole.yml`

## Devices with Static IPs

For a list of devices with static IPs, see [Devices with Static IPs](devices.md).
