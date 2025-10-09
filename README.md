# Automation of Domjudge Server

## Prerequisites
Caution: Everything was tested on Debian (ARM)

You have to download ansible...
```
sudo apt install ansible
```

... and need to establish an ssh connection between your Ansible Host Controller and the target server.

## SSH Setup
### Step 1 (on your Host Machine)
Generate a ssh key
``` 
ssh-keygen -t ed25519 -C "ansible"
```
Choose a path to your ssh key
``` Example
/host/<username>/.ssh/ansible
```
-> Don't enter a passphrase, except if you want to type it in when you start the playbook.

Copy the ssh key to the Domjudge Server
```
ssh-copy-id -i ~/Path/to/your/public/key <IP Address Domjudge Server>
```

### Step 2 (the machine which should be the Domjudge Server)
To ensure that the key was correctly copied from your host to your future Domjudge Server type into the terminal of the Domjudge Server
```
cat .ssh/authorized_keys
```
-> You should be able to see a key with your key name at the end

When you are finished access the ansible.cfg and enter you path to the ssh key you set up for ansible.
Furthermore access the inventory file and enter your connection credentials.

## Before installing
Clone the Repository
```
git clone https://github.com/iszshara/Automation-of-Domjudge.git
```
Create your own Database Admin Password via:
```
cd Automation-of-Domjudge
ansible-vault edit vault.yml
```
Password is: 123456 for your first login.

Please note that changing the password is important to secure your database!

Change the password via this command before running the Ansible Playbook and thus installing Domjudge:
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
