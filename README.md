# Automation of Domjudge Server

## Prerequisites
Caution: Everything was tested on Debian (ARM)

You have to download ansible
```
sudo apt install ansible
```

## Before installing

Create your own Database Admin Password via:
```
cd Automation-of-Domjudge
ansible-vault edit vault.yml
```
Password is: 123456 for your first login.
Please note that changing the password is important to secure your database password!

Change the password via this command before installing Domjudge:
```
cd ~/Automation-of-Domjudge
ansible-vault rekey vault.yml
```

## To install:
```
ansible-playbook domjudge.yml --ask-vault-pass --ask-become-pass
```
The BECOME password is your users password!

## Info
At the end of the setup process you will receive a password to log into the Domserver. Note it down!
