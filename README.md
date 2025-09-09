# Automation of Domjudge Server

## Prerequisites
Caution: Everything was tested on Debian (ARM)

You have to download ansible...
```
sudo apt install ansible
```

... and need to establish an ssh connection between your Ansible Host Controller and the target server.
When you are finished access the ansible.cfg and enter you path to the ssh key you set up for ansible.
Furthermore access the inventory file and enter your connection credentials.

## Before installing

Create your own Database Admin Password via:
```
cd Automation-of-Domjudge
ansible-vault edit vault.yml
```
Password is: 123456 for your first login.

Please note that changing the password is important to secure your database!

Change the password via this command before installing Domjudge:
```
cd ~/Automation-of-Domjudge
ansible-vault rekey vault.yml
```

## To install
```
ansible-playbook domjudge.yml --ask-vault-pass --ask-become-pass
```
The BECOME password is your users password!

## Info
After the Installation of the domserver, a file with a password for the Webinterface will be provided. Make sure to safe the password. It is recommended to delete the file after you have saved the password!

## About DOMjudge

This repository contains an ansible automation script for the installation and configuration of DOMjudge.

DOMjudge is a Free and Open Source Software (FOSS) for runnung programming contests. It is licensed under the GNU General Public License (GPL) v2.0.

For more information and to support the original authors, please visit the official DOMjudge Website.

[Visit DOMjudge](https://www.domjudge.org/)
