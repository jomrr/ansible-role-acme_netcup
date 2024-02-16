# ansible-role-acme_netcup

![GitHub](https://img.shields.io/github/license/jam82/ansible-role-acme_netcup) ![GitHub last commit](https://img.shields.io/github/last-commit/jam82/ansible-role-acme_netcup) ![GitHub issues](https://img.shields.io/github/issues-raw/jam82/ansible-role-acme_netcup)

**Ansible role to generate LetsEncrypt certificates with Ansible and the Netcup DNS API.**

This role is intended to implement a client-less management of letsencrypt
certificates. It retrieves the certificates on a configured controller
and pushes them to configured web servers via rsync over ssh.
Therefore no additional dependencies need to be installed and managed
on the configured target machines.

## Supported Platforms

| OS Family | Distribution  | Latest | Supported Version(s) | Comment |
|-----------|---------------|--------|----------------------|---------|
| Alpine    | Alpine        | :heavy_check_mark: | 3.18, 3.19 | |
| Archlinux | Archlinux     | :heavy_check_mark: | - | |
| Debian    | Debian        | :heavy_check_mark: | 11, 12 | |
|           | Ubuntu        | :heavy_check_mark: | 22.04 | |
| RedHat    | Almalinux     | :heavy_check_mark: | 8, 9 | |
|           | Fedora        | :heavy_check_mark: | 38, 39 | |
|           | Oraclelinux   | :heavy_check_mark: | 8 | |
| Suse      | OpenSuse Leap | :heavy_check_mark: | 15.5 | |
|           | Tumbleweed    | :heavy_check_mark: | - | |

## Requirements

Ansible 2.15 or higher.

## Variables

Variables and defaults for this role.

### defaults/main.yml

```yaml
---
# role: ansible-role-acme_netcup
# file: defaults/main.yml

# Account and domain configuration for netcup dns challenge
# default: []
acme_netcup_conf: []
#  - name: home
#    email: admin@example.com
#    netcup_cid: 081500
#    netcup_key: testkey
#    netcup_pwd: testpwd
#    domains:
#      - example.com

# Deactivate authentication objects (authz) after issuing a certificate
# default: true
acme_netcup_deactivate_authzs: true

# Debug flag
# default: false
acme_netcup_debug: false

# Target directory for accounts, keys, csrs and certificates.
# default: /etc/acme-staging
acme_netcup_dir: /etc/acme-staging

# The letsecrypt endpoint / directory to use, defaults to staging.
# staging: https://acme-staging-v02.api.letsencrypt.org/directory
# production: https://acme-v02.api.letsencrypt.org/directory
#
# default: "https://acme-staging-v02.api.letsencrypt.org/directory"
acme_netcup_endpoint: "https://acme-staging-v02.api.letsencrypt.org/directory"

# nolog option, true ~= do not log, false ~= log
# default: true
acme_netcup_nolog: true

# Remaining days a certificate must be valid, before it is renewed.
# cert_days < remaining_days
# default: 20
acme_netcup_remaining_days: 20
```

## Dependencies

```yaml
collections:
  - ansible.posix
  - community.crypto
  - community.general
  - containers.podman

roles: []
```

## Example Playbook

> Install the role to your roles path

```yaml
---
# role: ansible-role-acme_netcup
# file: site.yml

- hosts: all
  gather_facts: true
  roles:
    - role: acme_netcup
```

## License and Author

- Author:: [jam82](https://github.com/jam82/)
- Copyright:: 2024, [jam82](https://github.com/jam82/)

Licensed under [MIT License](https://opensource.org/licenses/MIT).
See [LICENSE](https://github.com/jam82/ansible-role-acme_netcup/blob/master/LICENSE) file in repository.

## References

- [Community.Crypto](https://docs.ansible.com/ansible/latest/collections/community/crypto/index.html)
