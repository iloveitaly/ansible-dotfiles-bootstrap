# Ansible Role: Dotfiles [![Ansible Role](https://img.shields.io/ansible/role/52749)](https://galaxy.ansible.com/radek_sprta/dotfiles) [![GitHub tag (latest SemVer)](https://img.shields.io/github/v/tag/radek-sprta/ansible-role-dotfiles)](https://gitlab.com/radek-sprta/ansible-role-dotfiles/-/tags) [![Ansible Role](https://img.shields.io/ansible/role/d/52749)](https://galaxy.ansible.com/radek_sprta/dotfiles) [![Ansible Role](https://img.shields.io/ansible/quality/52749)](https://galaxy.ansible.com/radek_sprta/dotfiles) [![Pipeline status](https://gitlab.com/radek-sprta/ansible-role-dotfiles/badges/master/pipeline.svg)](https://gitlab.com/radek-sprta/ansible-role-dotfiles/commits/master)

Install a set of dotfiles from a given Git repository. By default, it will install my (Radek Sprta's) [dotfiles](https://github.com/radek-sprta/dotfiles), but you can use any set of dotfiles you'd like, as long as they follow a conventional format.

## Requirements

Requires `git` on the managed machine (you can easily install it with `geerlingguy.git` if required).

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```
dotfiles_recursive: true
```

Clone recursively with submodules.

```
dotfiles_repo: "https://gitlab.com/radek-sprta/dotfiles.git"
dotfiles_repo_version: master
```

The git repository and branch/tag/commit hash to use for retrieving dotfiles. Dotfiles should generally be laid out within the root directory of the repository.

```
dotfiles_repo_accept_hostkey: false
```

Add the hostkey for the repo url if not already added. If ssh\_opts contains "-o StrictHostKeyChecking=no", this parameter is ignored.

```
dotfiles_repo_local_destination: "~/dotfiles"
```

The local path where the `dotfiles_repo` will be cloned.

```
dotfiles_force_clone: false
```

When true, it will force clone the repository, overwriting any local changes.

```
dotfiles_home: "~"
```

Whether the files in the repository start with dot or not.

## Example Playbook

```
- hosts: localhost
  roles:
    - { role: radek_sprta.dotfiles }
```

## License

MIT

## Author Information

Radek Sprta <mail@radeksprta.eu>. Based on dotfiles role by [Jeff Geerling](https://www.jeffgeerling.com/).
