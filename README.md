# Home Ansible

This ansible is for managing my home server(s), currently there is only a single raspberry pi.

## Prerequisites

1. `apt update`
2. `apt install -y ansible ansible-lint`

## PiHole

The current aim of this project is to install [pi-hole](https://pi-hole.net/)

## Check Connection to Server

`ansible-playbook -i inventory/hosts.ini --user=root playbooks/test_connection.yml`

> **Note:** The user flag is only required if the remote user has not been created yet.

## Add non-root user

On a fresh Diet-Pi OS the only user is root.  The below playbook installs another user.
The first time this is ran it must be as root as that is the only user that exists

Ran `ansible-playbook -i inventory/hosts.ini playbooks/add_user.yml -e 'ansible_user=root'`
