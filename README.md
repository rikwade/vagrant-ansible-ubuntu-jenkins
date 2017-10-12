# Vagrant & Ansible Jenkins Server on Ubuntu Linux

## Description
This repository provides an automated way to create an Ubuntu Linux server running Jenkins (http://jenkins.io) for Continuous Integration / Continuous Deployment. You can use Vagrant (http://vagrantup.com) to automatically pull an Ubuntu image and continue to automatically update and install the necessary packages for Jenkins. Alternatively, if you already have an Ubuntu server, you can make minor edits and use the Ansible (http://ansible.com) Playbook (playbook.yml) with minor edits to automatically update and install the necessary packages. 

## Usage
To create and start the server using VirtualBox, simply type:
```
$ vagrant up
```
Vagrant will then use the `VagrantFile` to pull the named Ubuntu Linux image, start the VM, and then trigger Ansible as a provisioning tool to execute `playbook.yml`.

The `VagrantFile` is configured to expose the following ports:
* Guest port 22 (ssh) -exposed as-> host port 2200 
* Guest port 8080 (jenkins) -exposed as-> host port 8080

Once booted, you can point a Web broswser running on the host machine to `http://localhost:8080`, where you will see the Jenkins setup page. It will ask for an administration key.

To obtain the administration key, log in to the Ubuntu VM by typing the following from the same directory as the Vagrantfile:
```
$ vagrant ssh
```
You will then be logged in to the Ubuntu VM. To obtain the administration key for Jenkins, type the following:
```
$ sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
You will see a string which looks something like this: `5f83104af0faz400869dc730d9391bee`. Copy this string and enter it in to the Jenkins setup page. You will now be taken through the Jenkins setup process (see https://jenkins.io/doc/book/getting-started/).

## Dependencies:
* VirtualBox, to run the VM: http://virtualbox.org
* Vagrant, to automatically pull and create the VirtualBox VM: http://vagrantup.com
* Ansible, to automatically provision the VM with the required packages: http://ansible.com

### Author:
* Richard Wade (rik@rikwade.com)
* October 2017