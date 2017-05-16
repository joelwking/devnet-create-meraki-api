## Overview
These instructions describe the process of building the development environment for the *Network Automation Integration* section of API 102: Programming with Meraki APIs. This workshop is at [DevNet Create](https://www.devnetcreate.io/2017/) May 2017

### Review the Meraki API documentation
The Meraki dashboard API documentation landing page is on [developers.meraki.com](http://developers.meraki.com/tagged/Dashboard). The detailed API documentation is available on the [Meraki dashboard](https://dashboard.meraki.com/api_docs), for the workshop, the sample use case is to add a [VLAN](https://dashboard.meraki.com/api_docs#add-a-vlan).

### Chrome Postman
Chrome Postman is an API developers tool which has gained wide adoption in the industry. As Putty is to SSH access to routers and switches, Postman is to device APIs. One feature is the ability to export, share, and import collections of API calls.

#### Install Postman
Download and install the free version at https://www.getpostman.com/.

#### Download the Meraki Postman collection
The Meraki developer portal hosts a postman collection which represents all the provisioning APIs available. Download them at developers.meraki.com/post/157014824756/dashboard-api-postman-collection and import the collection to your Postman instance.


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
