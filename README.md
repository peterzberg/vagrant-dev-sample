# Setup a DEV machine in minutes
The goal of this sample project is to proof that it is possible to set up a developer's machine within minutes. 

The use case: There will be a new guy working on your project. What is the fastest way to get him/her up and running. 

This includes:
- Setting up a VM
- Provision the VM with common developer tools
  - IDE (IntelliJ)
  - Editors (Sublimetext)
  - Git
  - Docker
  - NodeJS
- Check out all needed sources from git

# Vagrant and Ansible
For the creation and configuration of the reproducible and portable development environment, I decided to use [Vagrant](https://www.vagrantup.com). As the base image I created a vagrant box with Ubuntu 16.04 (without OpenOffice, Games, ...). To provision the base image I decided to use [Ansible](https://www.ansible.com), because it is already used at my company.

## Ignored at the moment, but not forgotten
- Provide preconfigured IDE with company specific settings
- Project files generated for the checked-out sources
- SSH keys for any given user using this VM
- ansible_local (that's why the roles are checked in)

# Getting up and running
Clone repository first, then

```
vagrant up
```

Attention: unfortunately the box is not configured as it should be :-( I should have disabled default system updates in ubuntu. [BUG](https://github.com/boxcutter/ubuntu/issues/73)

# Getting up and running until the bug is fix
```
vagrant up --no-provision
```
wait until no apt-process is running, then
```
vagrant up --provision
```

## Preconditions:
- Vagrant installed
- Virtualbox installed
