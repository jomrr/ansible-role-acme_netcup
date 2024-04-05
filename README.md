# Ansible role acme_netcup

![GitHub](https://img.shields.io/github/license/jomrr/ansible-role-acme_netcup) ![GitHub last commit](https://img.shields.io/github/last-commit/jomrr/ansible-role-acme_netcup) ![GitHub issues](https://img.shields.io/github/issues-raw/jomrr/ansible-role-acme_netcup)

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
| RedHat | AlmaLinux | 8 | [jomrr/molecule-almalinux:8]( https://hub.docker.com/r/jomrr/molecule-almalinux ) |
| | | 9 | [jomrr/molecule-almalinux:9]( https://hub.docker.com/r/jomrr/molecule-almalinux ) |
| Alpine | Alpine | 3.18 | [jomrr/molecule-alpine:3.18]( https://hub.docker.com/r/jomrr/molecule-alpine ) |
| | | 3.19 | [jomrr/molecule-alpine:3.19]( https://hub.docker.com/r/jomrr/molecule-alpine ) |
| Debian | Debian | 11 | [jomrr/molecule-debian:11]( https://hub.docker.com/r/jomrr/molecule-debian ) |
| | | 12 | [jomrr/molecule-debian:12]( https://hub.docker.com/r/jomrr/molecule-debian ) |
| RedHat | Fedora | 39 | [jomrr/molecule-fedora:39]( https://hub.docker.com/r/jomrr/molecule-fedora ) |
| | | 40 | [jomrr/molecule-fedora:40]( https://hub.docker.com/r/jomrr/molecule-fedora ) |
| | | rawhide | [jomrr/molecule-fedora:rawhide]( https://hub.docker.com/r/jomrr/molecule-fedora ) |
| Debian | Ubuntu | 20.04 | [jomrr/molecule-ubuntu:20.04]( https://hub.docker.com/r/jomrr/molecule-ubuntu ) |
| | | 22.04 | [jomrr/molecule-ubuntu:22.04]( https://hub.docker.com/r/jomrr/molecule-ubuntu ) |
| | | 24.04 | [jomrr/molecule-ubuntu:24.04]( https://hub.docker.com/r/jomrr/molecule-ubuntu ) |

## Role Variables

No role default variables specified, see [defaults/main.yml](defaults/main.yml).

## Example Playbook

Example playbooks(s) that show how to use this role.

## Simple example playbook

A simple default example playbook for using jomrr.acme_netcup.
```yaml
---
# name: "jomrr.acme_netcup"
# file: "playbook_acme_netcup.yml"

- name: "PLAYBOOK | acme_netcup"
  hosts: all
  gather_facts: true
  roles:
    - role: "jomrr.acme_netcup"
```

## Author(s) and License

- :octocat:                 Author::    [jomrr](https://github.com/jomrr)
- :triangular_flag_on_post: Copyright:: 2024, Jonas Mauer
- :page_with_curl:          License::   [MIT](LICENSE)

## References

- [Community.Crypto](https://docs.ansible.com/ansible/latest/collections/community/crypto/index.html)

---
