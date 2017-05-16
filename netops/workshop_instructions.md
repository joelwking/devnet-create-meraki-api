## Overview
These instructions describe the process of building the development environment for the *Network Automation Integration* section of API 102: Programming with Meraki APIs. This workshop was presented at [DevNet Create](https://www.devnetcreate.io/2017/) May 2017

### Review the Meraki API documentation

### Chrome Postman

#### Install Postman

#### Download the Meraki Postman collection

### Install Virtual Box

### Install Vagrant

### Install PyCharm Pro
PyCharm Pro offers a 30 day evaluation license.

### Create the Ansible virtual machine

### Download ansible-hacking
Download the python and JSON files to the `~/ansible/playbooks/library` directory
```
cd ~/ansible/playbooks/library
curl -o ansible_hacking.py https://raw.githubusercontent.com/joelwking/ansible-hacking/master/ansible_hacking.py
curl -o ansible_hacking.json https://raw.githubusercontent.com/joelwking/ansible-hacking/master/ansible_hacking.json
```
#### Familiarize yourself with ansible-hacking
Take a look at the documentation, some do, some don't, but it helps. https://github.com/joelwking/ansible-hacking/blob/master/README.md

#### Logon the Meraki Dashboard
Logon and obtain your network name, API key......
#### Edit the JSON file
Edit the `ansible_hacking.json` and substitute the appropriate values for the keys specified

### Clone the sample Meraki Python code
https://github.com/joelwking/ansible-meraki

### Start PyCharm
Start PyCharm Pro and create a new project using the directory you just cloned the Meraki Python code.

### Configure PyCharm
