# Ansible Container Linux Bootstrapper

CoreOS Container Linux (formerly known as CoreOS Linux) ships with no Python
interpreter.So, people who work with this OS can't run Ansible playbooks neither
remotely or locally.

To Automate Container Linux machines or applying configurations on, this project
can do this easily without any pain and blood ! This set of Ansible playbooks
installs "pypy" as a lightweight Python interpreter on top of Container Linux.

## Install
To prepare Container Linux machines and bootstrap them follow bellow steps:

* Install Ansible 2.5.x or above on the local machine. There is no guaranty for
older versions of Ansible.

* Add public ssh keys into the machines. This step probably has been done during
Container Linux installation process. So it's not neccessary do anything.

* Open `inventory.cfg` and add destination machine(s) IP instead of `w.x.y.z` in
line `ansible_host=` as well as local user on Container Linux. in most of public
cloud providers like AWS, GCP or Azure, default user is `core`.

* And then run playbooks with this command:
```
ansible-playbook -i inventory playbook.yml
```

You can use this playbook independently or merge it into your own playbooks to
automate Container Linux machines easily.
