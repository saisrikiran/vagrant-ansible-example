# vagrant-ansible-example

For this example, we consider a fresh VM where we will install devstack.
Then, the a http-server is installed within the devstack VM. 


Ansible is installed in a virtualenv with pip. Folder is created for holding the example code.

$ mkdir ansible_tutorial
 
$ cd ansible_tutorial

$ virtualenv venv -p python3

$ source venv/bin/activate

$ pip install ansible

The Ansible playbook is run in the fresh VM which will install Devstack
Once devstack is up, a new VM instance is created using Nova boot command within the Ansible playbook.
Within the nova boot command, the Apache2 Http-server will be installed using Raw Bash commands.

To run the playbook, just type the following command:

$ ansible-playbook -i "${SERVER_IP}," playbook.yml


Customizations to the template and Ansible playbook can be done by editing the customize.yml.example file
To run successfully, copy the customize.yml.example to customize.yml



#Create a Vagrant file:
#$ touch Vagrantfile
##Use the attached Vagrantfile here. The Vagrantfile contains the Ansible playbook which will install Devstack and also a Http-server within Devstack VM. 
#
#Running the Ansible playbook will do the needful using the following command:
#$ vagrant up
#
