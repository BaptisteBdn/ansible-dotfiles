# ansible-dotfiles
Automatically install and use my dotfiles !

## Roles
This ansible playbook is split into two roles, one to install the configuration files (aka dotfiles) along with fonts and icon themes.
The other one is optional and availabe only to archlinux users, it will install the packages that I use and configure your shell with plugins and themes.

## Requirements

`git` and `ansible-playbook` is needed.

Archlinux is only required for the second role, however it can be easily adapted for other distro.
If you are using the second role, you will also need to add collections to ansible in order to install packages.

```
ansible-galaxy collection install community.general
ansible-galaxy collection install kewlfft.aur
```

Keep in mind that while I specify Archlinux, I used EndeavourOS for simplicity which install basics i3 dependencies so you may be missing some packages (like i3 for example).

## How to use

Clone the repository :

```
git clone https://github.com/BaptisteBdn/ansible-dotfiles
```

Launch the playbook, some tasks require root usage, so `--ask-become-pass` will prompt for your sudo password.
```
ansible-playbook --inventory hosts --connection=local main.yml --ask-become-pass
```

If you don't want to use the `packages` role, you can modify `ansible/main.yml` and delete the role.
