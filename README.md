vagrant-ansible-btsync
==============

Ansible playbook and Vagrantfile to perform quick setup of VM with btsync onboard.
Mostly usefull for BTSync API debugging.

How to use
==============

1. Edit `playbook-vagrant.yaml` and setup your `api_key` *(in case you want API interface been available)*
2. Run `vagrant up`

Few minutes later you will have btsync available on `http://192.168.33.15:8888`



