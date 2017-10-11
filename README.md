# Vagrant & Ansible Jenkins Server on Ubuntu Linux

## Description
This repository provides an automated way to create an Ubuntu Linux server running Jenkins (http://jenkins.io) for Continuous Integration / Continuous Deployment. You can use Vagrant (http://vagrantup.com) to automatically pull an Ubuntu image and continue to automatically update and install the necessary packages for Jenkins. Alternatively, if you already have an Ubuntu server, you can make minor edits and use the Ansible (http://ansible.com) Playbook (playbook.yml) with minor edits to automatically update and install the necessary packages.

## Dependencies:
* VirtualBox, to run the VM: http://virtualbox.org
* Vagrant, to automatically pull and create the VirtualBox VM: http://vagrantup.com
* Ansible, to automatically provision the VM with the required packages: http://ansible.com

### Author:
* Richard Wade (rik@rikwade.com)
* October 2017