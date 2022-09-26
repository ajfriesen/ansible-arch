![Arch Logo](logos/ansible-arch-laptop.png)

# Ansible Arch [Desk|Lap]top

This is a playbook for my StarLabs Starlite MK IV installing and configuring most packages I use on this device.

**Goal**: I want to keep multiple machines in sync in regards of packages and configuration.

- StarLabs StarLite MK IV

Comming soon (maybe|hopefully):
- Desktop (Currently on Ubuntu 22.04)
- Tuxedo Aura15 (work, currently on Ubuntu 22.04)

## Arch Setup

Started with Archiso:

- Current Release: 2022.08.05
- Included Kernel: 5.18.16


I used the official [archinstall](https://wiki.archlinux.org/title/Archinstall) scrip to initally setup my device.
Here my initial [config for the StarLabs Starlite MK IV](archinstall/starlite.json).


## Ansible run

`ansible-playbook starlite.yaml -K`

## AUR packages

I handle AUR packages without ansible for now.
Reason beeing, there seems to be no ansible module I would trust to do that now.
But I will use [yay](https://github.com/Jguer/yay)

### Install yay:

```shell
git clone https://aur.archlinux.org/yay-bin.git
cd yay-bin
makepkg -si
```

### Installing AUR packages

```shell
yay --aur --sync \
    zoom \
    slack-desktop \
    visual-studio-code-bin \
    kopia \
    kopia-ui-bin \
    syncthing-gtk-python3 \
    signal-desktop-beta-bin \
    google-chrome \
    youtube-music-bin \
    typora \
    insomnia-bin \
    slack-desktop \
```
## TODO

- [ ] kubectl
- [ ] kubectx
- [ ] terraform
- [ ] tfenv
- [ ] terragrunt
- [ ] pyenv
- [ ] pyenv virtualenv
- [ ] oh-my-zsh
- [ ] gnome applets
  -  [ ] caffeine
  -  [ ] AppIndicator and KStatusNotifierItem Support
-  [ ] snapper
-  [ ] virtmanager setup for local kvm vms
-  [ ] tailscale
-  [ ] openvpn
-  [ ] yubikey login
-  [ ] fwdupd firmware thingy
-  [ ] vim
-  [ ] kubectl and helm env
-  [ ] Deactivate promtail and possibly other services when metered connection is set

## Development

Some notes for development.

Lint yaml:

`yamllint .`

ansible syntax check:

`ansible-playbook --syntax-check playbook.yaml`

ansible lint, checks for "best" practises in ansible playbooks:

`ansible-lint playbook.yaml`

# Resources to check

- https://github.com/hurricanehrndz/ansible-yubikey

# Author

This project was created by [Andrej Friesen](https://ajfriesen.com).
Inspired by Jeff Geerling [Mac Development Ansible Playbook](https://github.com/geerlingguy/mac-dev-playbook).

# Logo

I have created/curated the logo myself with my awesome GIMP skill.

- [Laptop Logo by oNline Web Fonts](https://www.onlinewebfonts.com/icon/452486)
- [Arch Logo](https://archlinux.org/art/)
- [Ansible Logo from Wikipedia](https://de.wikipedia.org/wiki/Datei:Ansible_logo.svg)