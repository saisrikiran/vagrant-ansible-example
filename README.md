# vagrant-ansible-example

For this example, we run a Vagrantfile which will install devstack.
Then, the a http-server is installed within the devstack VM. 

Step1:

Ansible is installed in a virtualenv with pip. Folder is created for holding the example code.

$ mkdir ansible_tutorial

$ cd ansible_tutorial

$ virtualenv venv -p python3.6

$ source venv/bin/activate

$ pip install ansible flask

Create a Vagrant file:

$ touch Vagrantfile
