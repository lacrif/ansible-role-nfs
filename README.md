# Ansible Role NFS Server

[![GitHub CI](https://github.com/lacrif/ansible-role-nfs/actions/workflows/ci.yml/badge.svg)](https://github.com/lacrif/ansible-role-nfs/actions/workflows/ci.yml)
[![GitHub forks](https://img.shields.io/github/forks/lacrif/ansible-role-nfs?link=https%3A%2F%2Fgithub.com%2Flacrif%2Fansible-role-nfs)](https://github.com/lacrif/ansible-role-nfs)
[![GitHub Repo stars](https://img.shields.io/github/stars/lacrif/ansible-role-nfs?link=https%3A%2F%2Fgithub.com%2Flacrif%2Fansible-role-nfs)](https://github.com/lacrif/ansible-role-nfs)

Installs NFS utilities on RedHat/CentOS or Debian/Ubuntu.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
nfs_package_name: []
```

A list of packages which will be installed. (Simple example: nfs_package_name: ['nfs-utils >= 0.9']).
Not set this variable if you want le last version of the packages.

```yaml
nfs_exports: []
```

A list of exports which will be placed in the /etc/exports file. See Ubuntu's simple Network File System (NFS) guide for more info and examples. (Simple example: nfs_exports: [ "/home/public    *(rw,sync,no_root_squash)" ]).

```yaml
nfs_rpcbind_state: 'started'
nfs_rpcbind_enabled: true
```

(RedHat/CentOS/Fedora only) The state of the `rpcbind` service, and whether it should be enabled at system boot.

## Dependencies

None.

## Example Playbook

```yaml
- hosts: 'all'
    roles:
    - role: 'lacrif.nfs'
```

## Author Information

Lacrif
