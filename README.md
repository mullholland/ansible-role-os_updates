# [os_updates](#os_updates)

|GitHub|GitLab|
|------|------|
|[![github](https://github.com/mullholland/ansible-role-os_updates/workflows/Ansible%20Molecule/badge.svg)](https://github.com/mullholland/ansible-role-os_updates/actions)|[![gitlab](https://gitlab.com/mullholland/ansible-role-os_updates/badges/master/pipeline.svg)](https://gitlab.com/mullholland/ansible-role-os_updates)|[![quality](https://img.shields.io/ansible/quality/unset)](https://galaxy.ansible.com/mullholland/os_updates)|

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

# Check ports after reboot
os_updates_reboot_host_address: '{{ (ansible_ssh_host|default(ansible_host))|default(inventory_hostname) }}'
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
    - role: "{{ lookup('env', 'MOLECULE_PROJECT_DIRECTORY') | basename }}"
```

The machine needs to be prepared in CI this is done using `molecule/default/prepare.yml`:
```yaml
---
- name: Prepare
  hosts: all
  become: true
  gather_facts: true

  tasks:
    - name: SmokeTests
      debug:
        msg:
          - "ansible_version => {{ansible_version}}"
          - "ansible_distribution => {{ ansible_distribution }}"
          - "ansible_distribution_major_version => {{ ansible_distribution_major_version }}"
          - "ansible_os_family  => {{ ansible_os_family}}"
          - "ansible_system  => {{ ansible_system }}"
```





## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

-   [debian9](https://hub.docker.com/r/mullholland/docker-molecule-debian9)
-   [debian10](https://hub.docker.com/r/mullholland/docker-molecule-debian10)
-   [debian11](https://hub.docker.com/r/mullholland/docker-molecule-debian11)
-   [ubuntu1804](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu1804)
-   [ubuntu2004](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu2004)
-   [centos7](https://hub.docker.com/r/mullholland/docker-molecule-centos7)
-   [centos8](https://hub.docker.com/r/mullholland/docker-molecule-centos8)
-   [centos8-stream](https://hub.docker.com/r/mullholland/docker-molecule-centos8-stream)
-   [ubi8](https://hub.docker.com/r/mullholland/docker-molecule-ubi8)
-   [fedora33](https://hub.docker.com/r/mullholland/docker-molecule-fedora33)
-   [fedora34](https://hub.docker.com/r/mullholland/docker-molecule-fedora34)
-   [fedora35](https://hub.docker.com/r/mullholland/docker-molecule-fedora35)
-   [rockylinux8](https://hub.docker.com/r/mullholland/docker-molecule-rockylinux8)
-   [almalinux8](https://hub.docker.com/r/mullholland/docker-molecule-almalinux8)
-   [amazonlinux](https://hub.docker.com/r/mullholland/docker-molecule-amazonlinux)

The minimum version of Ansible required is 2.10, tests have been done to:

-   The previous version.
-   The current version.
-   The development version.





If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-os_updates/issues)

## [License](#license)

MIT


## [Author Information](#author-information)

[Mullholland](https://github.com/mullholland)

## [Special Thanks](#special-thanks)

Template inspired by [Robert de Bock](https://github.com/robertdebock)
