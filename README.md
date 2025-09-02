# Automation of Domjudge

## Prerequisites
You have to download ansible

## To install:
```
ansible-playbook domjudge.yml --ask-vault-pass --ask-become-pass
```

## When installed:

Create your own Database Admin Password via:
```
cd Automation-of-Domjudge
ansible-vault edit vault.yml
```

## Info
At the end of the setup process you will receive a password to log into the Domserver
