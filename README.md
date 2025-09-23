
# Rôle Ansible Serveur NFS

[![GitHub CI](https://github.com/lacrif/ansible-role-nfs/actions/workflows/ci.yml/badge.svg)](https://github.com/lacrif/ansible-role-nfs/actions/workflows/ci.yml)
[![GitHub forks](https://img.shields.io/github/forks/lacrif/ansible-role-nfs?link=https%3A%2F%2Fgithub.com%2Flacrif%2Fansible-role-nfs)](https://github.com/lacrif/ansible-role-nfs)
[![GitHub Repo stars](https://img.shields.io/github/stars/lacrif/ansible-role-nfs?link=https%3A%2F%2Fgithub.com%2Flacrif%2Fansible-role-nfs)](https://github.com/lacrif/ansible-role-nfs)

Installation de NFS sur RedHat/CentOS ou Debian/Ubuntu.

## Prérequis

Aucun

## Variables du rôle

Les variables disponibles sont listées ci-dessous, avec leurs valeurs par défaut (voir `defaults/main.yml`) :

```yaml
nfs_package_name: []
```

Liste des paquets qui seront installés. (Exemple simple : nfs_package_name: ['nfs-utils >= 0.9']).
Ne pas définir cette variable si vous souhaitez la dernière version des paquets.

```yaml
nfs_exports: []
```

Liste des exports qui seront placés dans le fichier /etc/exports. Voir le guide NFS d'Ubuntu pour plus d'informations et d'exemples. (Exemple simple : nfs_exports: [ "/home/public    *(rw,sync,no_root_squash)" ]).

```yaml
nfs_rpcbind_state: 'started'
nfs_rpcbind_enabled: true
```

(RedHat/CentOS/Fedora uniquement) L'état du service `rpcbind` et s'il doit être activé au démarrage du système.

## Dépendances

Aucune.

## Exemple de Playbook

```yaml
- hosts: 'all'
  roles:
    - role: 'lacrif.nfs'
```

## Molecule

Lancer les tests

```bash
export MOLECULE_DISTRO_NAME=rockylinux && export MOLECULE_DISTRO_VERSION=9 && molecule test
export MOLECULE_DISTRO_NAME=ubuntu && export MOLECULE_DISTRO_VERSION=noble && molecule test
export MOLECULE_DISTRO_NAME=debian && export MOLECULE_DISTRO_VERSION=bookworm && molecule test
```

## Informations sur l'auteur

Lacrif
