# [os_updates](#os_updates)

|GitHub|GitLab|
|------|------|
|[![github](https://github.com/mullholland/ansible-role-os_updates/workflows/Ansible%20Molecule/badge.svg)](https://github.com/mullholland/ansible-role-os_updates/actions)|[![gitlab](https://gitlab.com/mullholland/ansible-role-os_updates/badges/main/pipeline.svg)](https://gitlab.com/mullholland/ansible-role-os_updates)|

Ansible role to install OS updates.

## [Role Variables](#role-variables)

These variables are set in `defaults/main.yml`:
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
os_updates_apt_upgrade: "safe"
# define packages which should not upgraded
os_updates_apt_exclude: []
os_updates_apt_autoremove: true

# reboot options
os_updates_reboot_delay: 30
os_updates_reboot_timeout: 300
```


## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true
  roles:
    - role: "mullholland.os_updates"
```





## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

-   [debian9](https://hub.docker.com/r/mullholland/docker-molecule-debian9)
-   [debian10](https://hub.docker.com/r/mullholland/docker-molecule-debian10)
-   [debian11](https://hub.docker.com/r/mullholland/docker-molecule-debian11)
-   [ubuntu1804](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu1804)
-   [ubuntu2004](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu2004)
-   [ubuntu2204](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu2204)
-   [centos7](https://hub.docker.com/r/mullholland/docker-molecule-centos7)
-   [centos-stream8](https://hub.docker.com/r/mullholland/docker-molecule-centos-stream8)
-   [centos-stream9](https://hub.docker.com/r/mullholland/docker-molecule-centos-stream9)
-   [ubi8](https://hub.docker.com/r/mullholland/docker-molecule-ubi8)
-   [fedora35](https://hub.docker.com/r/mullholland/docker-molecule-fedora35)
-   [fedora36](https://hub.docker.com/r/mullholland/docker-molecule-fedora36)
-   [amazonlinux](https://hub.docker.com/r/mullholland/docker-molecule-amazonlinux)

The minimum version of Ansible required is 2.10, tests have been done to:

-   The previous versions.
-   The current version.





If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-os_updates/issues)

## [License](#license)

MIT


## [Author Information](#author-information)

[Mullholland](https://github.com/mullholland)

## [Special Thanks](#special-thanks)

Template inspired by [Robert de Bock](https://github.com/robertdebock)
