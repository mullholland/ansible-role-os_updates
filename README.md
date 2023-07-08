# [os_updates](#os_updates)

Ansible role to install OS updates.

|GitHub|GitLab|Quality|Downloads|Version|
|------|------|-------|---------|-------|
|[![github](https://github.com/mullholland/ansible-role-os_updates/workflows/Ansible%20Molecule/badge.svg)](https://github.com/mullholland/ansible-role-os_updates/actions)|[![gitlab](https://gitlab.com/opensourceunicorn/ansible-role-os_updates/badges/master/pipeline.svg)](https://gitlab.com/opensourceunicorn/ansible-role-os_updates)|[![quality](https://img.shields.io/ansible/quality/56826)](https://galaxy.ansible.com/mullholland/os_updates)|[![downloads](https://img.shields.io/ansible/role/d/56826)](https://galaxy.ansible.com/mullholland/os_updates)|[![Version](https://img.shields.io/github/release/mullholland/ansible-role-os_updates.svg)](https://github.com/mullholland/ansible-role-os_updates/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/mullholland/ansible-role-os_updates/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true
  roles:
    - role: "mullholland.os_updates"
```


## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/mullholland/ansible-role-os_updates/blob/master/defaults/main.yml):

```yaml
---
# Possible Values
# ALWAYS = Always reboot after updates
# NEVER = Never reboot after updates
# NEEDED = Only reboot after Kernel changes
os_updates_reboot: "NEEDED"

# YUM
# define packages which should not upgraded
os_updates_yum_exclude: ""
os_updates_yum_clean_cache: true

# APT
# define packages which should not upgraded
os_updates_apt_exclude: []
os_updates_apt_autoremove: true

# reboot options
os_updates_reboot_delay: 30
os_updates_reboot_timeout: 300
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/mullholland/ansible-role-os_updates/blob/master/requirements.txt).


## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://mullholland.net) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/mullholland/ansible-role-os_updates/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/repository/docker/mullholland/docker-centos-systemd/general)|all|
|[Amazon](https://hub.docker.com/repository/docker/mullholland/docker-amazonlinux-systemd/general)|Candidate|
|[Fedora](https://hub.docker.com/repository/docker/mullholland/docker-fedora-systemd/general)|all|
|[Ubuntu](https://hub.docker.com/repository/docker/mullholland/docker-ubuntu-systemd/general)|all|
|[Debian](https://hub.docker.com/repository/docker/mullholland/docker-debian-systemd/general)|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-os_updates/issues)

## [License](#license)

[MIT](https://github.com/mullholland/ansible-role-os_updates/blob/master/LICENSE).

## [Author Information](#author-information)

[Mullholland](https://mullholland.net)

Please consider [sponsoring me](https://github.com/sponsors/mullholland).
