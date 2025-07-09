This is a simple project meant to showcase the automating capabilities of ansible. This project consists of a yaml file, commonly referred to as a playbook, which consists of
a ist of rules, commands and tasks that are run in a serial fashion. There is also an inventory file, which is just a fancy way of addressing a list of hosts. The inventory file
is often created with either a JSON or a ini extension, although the latter is more common. Ansible is an automation tool meant to make system administrators' jobs easier, 
especially for configuration tasks and provisioning, which bypasses the use of individual remote access by ssh. The playbook in question uses the ansible command
os_{{ansible.facts['distribution_version']}} in order to read the operating system version (or distribution) and place it in a group specifically named after
the operaitng system itself e.g.: if the operating system is ubuntu, it will be automatically added to the os_ubuntu group. the key os_{{ ansible.facts[distribution']}}
is meant to classify all hosts according to their operaitng system. Also, if you also the hosts' version, you'd want to use ['distribution_version'] instead. 
Ansible operates with a nested system of units, one containing the other, which can be summarised as follows:

Ansible -> playbooks -> plays -> tasks -> modules

Once both the playbook and the inventory file are in the same directory, you can run them with:
ansible-playbook -i inventory.ini distribution.yml

It goes without saying that you should have ansible installed on your system

main ansible reference:
https://docs.ansible.com/ansible/latest/index.html
