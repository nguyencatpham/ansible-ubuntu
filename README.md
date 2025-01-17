# Ansible Ubuntu setup

Ansible roles to setup Ubuntu desktop and Ubuntu server (14.04 and 16.04). This playbook is focused on quickly deploying a "ready to use" dev machine.

## Requirements

- Git
- Ansible 2+ (automatically installed from [Ansible offical PPA](https://launchpad.net/~ansible/+archive/ubuntu/ansible) with the provided install.sh script)

## Installation

First, you need to install Git and Ansible :

```
sudo apt-get install git
git clone https://github.com/nguyencatpham/ansible-ubuntu.git
cd ansible-ubuntu
./install.sh
```

Then you need to customize the playbook `ansible-desktop.yml` (or create a new one) to suit your needs. Every roles are disabled by default.

Run `ansible-playbook ansible-desktop.yml --ask-become-pass` and enter your sudo password to run the playbook

## Roles included

| Role                      | Description                                                                                                                                                                         |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                           | **General**                                                                                                                                                                         |
| common                    | Install a lot of usefull packages (curl, htop, less, zip ... see [corresponding task file](https://github.com/Benoth/ansible-ubuntu/blob/master/roles/common/tasks/main.yml))       |
| locales                   | Configure system locales and timezone                                                                                                                                               |
| ripgrep                   | Install [ripgrep](https://github.com/jimhester/ripgrep) (grep++)                                                                                                                    |
| sift                      | Install [Sift](https://sift-tool.org/) tool, a fast and powerful alternative to grep                                                                                                |
| zsh                       | Install [ZSH](http://www.zsh.org/) and create a [zshrc file](https://github.com/Benoth/ansible-ubuntu/blob/master/roles/zsh/files/zshrc) for the current user / root                |
|                           | **Desktop tools**                                                                                                                                                                   |
| albert                    | Install [Albert](https://github.com/ManuelSchneid3r/albert) omnilauncher from [Alin Andrei WebUpd8 PPA](https://launchpad.net/~nilarimogard/+archive/ubuntu/webupd8)                |
| altyo                     | Install [AltYo](https://github.com/linvinus/AltYo) Gtk3 drop-down terminal emulator from [Denis Konstantinov AltYo PPA](https://launchpad.net/~linvinus/+archive/ubuntu/altyo)      |
| chromium                  | Install [Chromium](https://www.chromium.org/). May also install plugins and set policies                                                                                            |
| copyq                     | Install [CopyQ](https://hluk.github.io/CopyQ/) clipboard manager                                                                                                                    |
| dbeaver                   | Install [DBeaver](http://dbeaver.jkiss.org/) from online deb file                                                                                                                   |
| desktop                   | Install a lot of usefull packages (meld, tilda, vlc, xclip)                                                                                                                         |
| desktop-autostart         | Update autostart handling (unhide all apps, create, remove...)                                                                                                                      |
| desktop-cleanup           | Remove Unity sh... integrations and install Nautilus plugins                                                                                                                        |
| desktop-preferences-unity | This one is very personal. Imports all my Unity preferences                                                                                                                         |
| filezilla                 | Install [Filezilla](https://filezilla-project.org/) (no particular settings, basic installation)                                                                                    |
| firefox                   | Install [Firefox](https://www.mozilla.org/firefox/) (no particular settings, basic installation)                                                                                    |
| flatabulous               | Install [Flatabulous Theme](https://github.com/anmoljagetia/Flatabulous) from source and apply some gsettings                                                                       |
| gimp                      | Install [Gimp](https://www.gimp.org/) and some minor settings                                                                                                                       |
| grub-customizer           | Install Grub Customizer using [Daniel Richter PPA](https://launchpad.net/~danielrichter2007/+archive/ubuntu/grub-customizer)                                                        |
| indicator-sysmonitor      | Install [indicator-sysmonitor](https://github.com/fossfreedom/indicator-sysmonitor) from [FOSSFreedom PPA](https://launchpad.net/~fossfreedom/+archive/ubuntu/indicator-sysmonitor) |
| ksuperkey                 | Install [ksuperkey](https://github.com/hanschen/ksuperkey) using [Eugene Mikhantiev PPA](https://launchpad.net/~mehanik/+archive/ubuntu/ksuperkey)                                  |
| libreoffice               | Install [LibreOffice](https://www.libreoffice.org/) using [LibreOffice 5.1 PPA](https://launchpad.net/~libreoffice/+archive/ubuntu/libreoffice-5-1)                                 |
| maim                      | Install [maim (make image)](https://github.com/naelstrof/maim) (screenshots tool) from [WebUpd8 Alin Andrei PPA](https://launchpad.net/~nilarimogard/+archive/ubuntu/webupd8)       |
| nemo                      | Install [Nemo](https://github.com/linuxmint/nemo) from [WebUpd8 PPA](https://launchpad.net/~webupd8team/+archive/ubuntu/nemo)                                                       |
| notepadqq                 | Install [Notepadqq](http://notepadqq.altervista.org/wp/) from [Notepadqq Team PPA](https://launchpad.net/~notepadqq-team/+archive/ubuntu/notepadqq)                                 |
| notify-osd                | Install ehanced Notidy-OSD from [Leolik PPA](https://launchpad.net/~leolik/+archive/ubuntu/leolik)                                                                                  |
| rofi                      | Compile [rofi](https://davedavenport.github.io/rofi/) from source                                                                                                                   |
| remarkable                | Install [Remarkable](https://remarkableapp.github.io/linux.html) from online deb file                                                                                               |
| remmina                   | Install [Remmina](http://www.remmina.org/)                                                                                                                                          |
| shutter                   | Install [Shutter](http://shutter-project.org/) screenshot tool                                                                                                                      |
| skype                     | Install [Skype](https://www.skype.com/)                                                                                                                                             |
| slop                      | Install [slop (select operation)](https://github.com/naelstrof/slop) (selection tool) from [WebUpd8 Alin Andrei PPA](https://launchpad.net/~nilarimogard/+archive/ubuntu/webupd8)   |
| teamviewer                | Install [TeamViewer](https://www.teamviewer.com/) from online deb file                                                                                                              |
| ultra-flat-icons          | Install [Ultra flat icons](http://www.noobslab.com/2015/01/make-linux-more-elegant-with-ultra-flat.html) from [Noobslab PPA](https://launchpad.net/~noobslab/+archive/ubuntu/icons) |
| xmind                     | Install [XMind](http://www.xmind.net/) from online deb file                                                                                                                         |
|                           | **Services & server tools**                                                                                                                                                         |
| docker                    | Install [Docker](https://www.docker.com/) and Docker compose from Docker deb repository                                                                                             |
| nodejs                    | Install [NodeJS](https://nodejs.org/en/) from Node deb repository                                                                                                                   |
| python                    | Install [Python](https://www.python.org/)                                                                                                                                           |
| ssh                       | Install [OpenSSH Server](http://www.openssh.com/)                                                                                                                                   |
| nvm                       | Install [NVM](https://github.com/nvm-sh/nvm)                                                                                                                                        |
| slack                     | Install [SLACK](https://slack.com/downloads/)                                                                                                                                       |
| vscode                    | Install [VSCODE](https://code.visualstudio.com/download)                                                                                                                            |
| Postman                   | Install [POSTMAN](https://www.postman.com/)                                                                                                                                         |
| Go                        | Install [Go](https://go.dev/doc/install)                                                                                                                                            |
| awscli                    | Install [AWS CLI](https://aws.amazon.com/cli/)                                                                                                                                      |
| eksctl                    | Install [EKSCTL](https://eksctl.io/)                                                                                                                                                |
| Lens                      | Install [LENS](https://app.k8slens.dev/)                                                                                                                                            |
| Chrome                    | Install [Chrome](https://github.com/darkwizard242/ansible-role-googlechrome)                                                                                                        |
| kubectl                   | Install [Kubectl](https://kubernetes.io/docs/tasks/tools/)                                                                                                                          |
|                           | **Missing**                                                                                                                                                                         |
| Ubuntu Configuration      | Install [My Ubuntu Configuration](https://www.docker.com/)                                                                                                                          |
| Code for life             | Setting Code for life [CFL](https://www.docker.com/)                                                                                                                                |
| Telegram                  | Install [Telegram](https://www.docker.com/)                                                                                                                                         |
| Go tieng viet             | Setting unikey [CFL](https://www.docker.com/)                                                                                                                                       |
| yarn                      | Install [Yarn](https://www.docker.com/)                                                                                                                                             |
