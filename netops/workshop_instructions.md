## Overview
These instructions describe the process of building the development environment for the *Network Automation Integration* section of API 102: Programming with Meraki APIs. This workshop is at [DevNet Create](https://www.devnetcreate.io/2017/) May 2017

### Review the Meraki API documentation
The Meraki dashboard API documentation landing page is on [developers.meraki.com](http://developers.meraki.com/tagged/Dashboard). The detailed API documentation is available on the [Meraki dashboard](https://dashboard.meraki.com/api_docs), for the workshop, the sample use case is to add a [VLAN](https://dashboard.meraki.com/api_docs#add-a-vlan).

### Chrome Postman
Chrome Postman is an API developers tool which has gained wide adoption in the industry. As Putty is to SSH access to routers and switches, Postman is to device APIs. One feature is the ability to export, share, and import collections of API calls.

#### Install Postman
Download and install the free version at https://www.getpostman.com/.

#### Download the Meraki Postman collection
The Meraki developer portal hosts a postman collection which represents all the provisioning APIs available. Download them at https://developers.meraki.com/post/157014824756/dashboard-api-postman-collection and import the collection to your Postman instance.

### Install VirtualBox
Oracle VirtualBox is general-purpose software to virtualize x86 hardware to create development environments on your laptop. By installing VirtualBox on your laptop, we isolate your laptop OS from the development environment. Virtual Box, along with Vagrant, allows you to create an ephemeral virtual environment which can be instanciated and destroyed in a few minutes, with minimal systems administration experience.

Download and install VirtualBox at https://www.virtualbox.org/wiki/Downloads.

### Install Vagrant
Vagrant is a tool for building and managing virtual machine environments. Download and install the proper Vagrant package for your operating system and architecture. https://www.vagrantup.com/downloads.html.

### Create the Ansible virtual machine
In this step we create a directory, download the Vagrantfile, and instanciate and provision the virtual machine for the workshop exercises.

Assuming you are running a Mac or Windows, create a directory, e.g. `./devnetcreate`, enter the directory, and download the Vagrant file from the repository. 
```
https://raw.githubusercontent.com/joelwking/devnet-create-meraki-api/master/netops/Vagrantfile
```
Run `vagrant up` to instanciate the VM and provision it.

SSH to the VM by issueing the command `vagrant ssh`. Once logged in, set the password for the userid `ubuntu` by 
```
$ sudo passwd ubuntu
Enter new UNIX password: devnetcreate
Retype new UNIX password: devnetcreate
passwd: password updated successfully
```
### Ansible hacking
I wrote the ansible-hacking environment as a [mock](https://en.wikipedia.org/wiki/Mock_object) object to facilitate debugging. My goal was to facilitate remote execution and debugging from PyCharm Pro, without the need to install Ansible from source and execute the `ansible/hacking/test-module` to test my code.

#### Download ansible-hacking
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

### Install PyCharm Pro
PyCharm Pro offers a 30 day evaluation license. PyCharm Professional Edition includes support for Remote development capabilities, run/debug. While the Professional Edition is a licensed product, as my friend [Teren Bryson](@SomeClown) said, it takes Python programming to a whole new level.

Download and install the appropriate package for your OS at https://www.jetbrains.com/pycharm/download/

### Invoke and Configure PyCharm Pro
Pycharm is a powerful utility, but is also not the most intuitative to to configure

Start PyCharm Pro and create a new project using the directory you just cloned the Meraki Python code. We will also configure PyCharm to use the virtual machine created in previous steps as the target of our remote execution and debugging.

#### Create Project
It is helpful to have the SSH session to the virtual machine active, as well as the Meraki dashboard. Create a new project using the directory where we cloned the Meraki Python code.

![Example of creating new Project](https://github.com/joelwking/devnet-create-meraki-api/blob/master/netops/images/Create_new_project_1.png "Create New Project")

![Ignore the warning about the directory not empty](https://github.com/joelwking/devnet-create-meraki-api/blob/master/netops/images/Create_project_directory_not_empty.png "Directory not empty")

The project should contain the files from the Meraki repo. ![Project files](https://github.com/joelwking/devnet-create-meraki-api/blob/master/netops/image/Create_new_project_2.png "Project files")

#### Configure Remote Python Interpreter
We need to configure a remote Python Interpreter. We will add a server named `devnetcreate`, using the IP address of the VM, `192.168.56.200` and specify the username of `ubuntu`. Files will be deployed using sFTP

![Deployment Configuration](https://github.com/joelwking/devnet-create-meraki-api/blob/master/netops/images/Deployment_server_1.png "Deployment Server")

While configuring this screen, test the sFTP connection.

The deployment path is relative to the home directory of the deployment server. This mapping between your laptop project directory and the deployment path allows PyCharm to deploy, or upload, files to the ![Deployment Path](https://github.com/joelwking/devnet-create-meraki-api/blob/master/netops/images/Deployment_path.png "Deployment Path")

