# setup-arch
My ArchLinux Set Up

The following is the automated installation/set-up for my ArchLinux (currently Manjaro) computer after updating or resetting it.
It does install all the apps i use daily, like JetBrains, Docker, Postaman and so on.
It does also set the configuration for my zsh and dotfile plugins (git configuration, zsh aliases, fonts ...etc) and soon it will also set my new Vim configuration.
Everything is based on Homebrew package manager.

## Requirements
* Curl
* Git
* Ansible

## Commands

Run the following command to install dependencies and run the ansible playbook.
```
$ ./setup.sh -i
```

Ansible command
```
$ ansible-playbook -i inventory localhost.yml -K
```

## Ansible tag usage
### Tags list
* pacman    Install applications by pacman (Official arch)
* aur       Install applications by AUR (Official community)
* k8s       Install kubectx and kubeseal
* dotfile   My dotfile
* zsh       Configuration zsh

### Ansible commands
```
$ ansible-playbook -i inventory localhost.yml -K --tags "pacman,aur"
$ ansible-playbook -i inventory localhost.yml -K --tags zsh
```
