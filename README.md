# Ansible Role: Bootstrap Dotfiles [![Ansible Role](https://img.shields.io/ansible/role/52749)](https://galaxy.ansible.com/iloveitaly/dotfiles_bootstrap) [![Ansible Role](https://img.shields.io/ansible/role/d/52749)](https://galaxy.ansible.com/iloveitaly/dotfiles_bootstrap) [![Ansible Role](https://img.shields.io/ansible/quality/52749)](https://galaxy.ansible.com/iloveitaly/dotfiles_bootstrap)

Install a set of dotfiles from a given Git repository and run a installation or bootstrap script (like GitHub codespaces). By default, it will install my [dotfiles](https://github.com/iloveitaly/dotfiles), but you can use any set of dotfiles you'd like, as long as they follow a conventional format.

## Requirements

Requires `git` on the managed machine (you can easily install it with `geerlingguy.git` if required).

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```
dotfiles_recursive: true
```

Clone recursively with submodules.

```
dotfiles_repo: "https://gitlab.com/iloveitaly/dotfiles.git"
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
    - { role: iloveitaly.dotfiles_bootstrap }
```

## License

MIT

## Author Information

* Originally based on dotfiles role by [Jeff Geerling](https://www.jeffgeerling.com/).
* Leveraged improvements by Radek Sprta <mail@radeksprta.eu>
