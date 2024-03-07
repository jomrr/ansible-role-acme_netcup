# Ansible role acme_netcup

![GitHub](https://img.shields.io/github/license/jam82/ansible-role-acme_netcup) ![GitHub last commit](https://img.shields.io/github/last-commit/jam82/ansible-role-acme_netcup) ![GitHub issues](https://img.shields.io/github/issues-raw/jam82/ansible-role-acme_netcup)

**Ansible role for setting up acme_netcup.**

## Description

This role is intended to implement a client-less management of letsencrypt certificates. It retrieves the certificates on a configured controller and pushes them to configured web servers via rsync over ssh. Therefore no additional dependencies need to be installed and managed on the configured target machines.


## Prerequisites

This role has no special prerequisites.

### System packages (Fedora)

- `python3` (Python 3.8 or later)

### Python (requirements.txt)

- ansible >= 2.15

## Dependencies (requirements.yml)

```yaml
collections:
  - ansible.posix
  - community.crypto
  - community.general
  - containers.podman

roles: []
```

## Supported Platforms

| OS Family | Distribution | Version | Container Image |
|-----------|--------------|---------|-----------------|
| RedHat | AlmaLinux | 8 | [jam82/molecule-almalinux:8]( https://hub.docker.com/r/jam82/molecule-almalinux ) |
| | | 9 | [jam82/molecule-almalinux:9]( https://hub.docker.com/r/jam82/molecule-almalinux ) |
| Alpine | Alpine | 3.18 | [jam82/molecule-alpine:3.18]( https://hub.docker.com/r/jam82/molecule-alpine ) |
| | | 3.19 | [jam82/molecule-alpine:3.19]( https://hub.docker.com/r/jam82/molecule-alpine ) |
| Debian | Debian | 11 | [jam82/molecule-debian:11]( https://hub.docker.com/r/jam82/molecule-debian ) |
| | | 12 | [jam82/molecule-debian:12]( https://hub.docker.com/r/jam82/molecule-debian ) |
| RedHat | Fedora | 39 | [jam82/molecule-fedora:39]( https://hub.docker.com/r/jam82/molecule-fedora ) |
| | | 40 | [jam82/molecule-fedora:40]( https://hub.docker.com/r/jam82/molecule-fedora ) |
| | | rawhide | [jam82/molecule-fedora:rawhide]( https://hub.docker.com/r/jam82/molecule-fedora ) |
| Debian | Ubuntu | 20.04 | [jam82/molecule-ubuntu:20.04]( https://hub.docker.com/r/jam82/molecule-ubuntu ) |
| | | 22.04 | [jam82/molecule-ubuntu:22.04]( https://hub.docker.com/r/jam82/molecule-ubuntu ) |
| | | 24.04 | [jam82/molecule-ubuntu:24.04]( https://hub.docker.com/r/jam82/molecule-ubuntu ) |

## Role Variables

No role default variables specified, see [defaults/main.yml](defaults/main.yml).

## Example Playbook

Example playbooks(s) that show how to use this role.

## Simple example playbook

A simple default example playbook for using jam82.acme_netcup.
```yaml
---
# name: "jam82.acme_netcup"
# file: "playbook_acme_netcup.yml"

- name: "PLAYBOOK | acme_netcup"
  hosts: all
  gather_facts: true
  roles:
    - role: "jam82.acme_netcup"
```

## License, Author(s) and Contributors

This role is published under the [MIT License](LICENSE)

and was initially created in 2024 by Jonas Mauer (@jam82).

## References

- [Community.Crypto](https://docs.ansible.com/ansible/latest/collections/community/crypto/index.html)

---
